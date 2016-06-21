---
title: Scripting
layout: unity
weight : 2
---

Overview
--------

Alongside the Sequencer tool, trueSKY can be driven and configured via Unity scripting. The settings and properties in trueSKY for Unity are split into three varieties: Keyframe properties (temporal values for clouds and sky), Layer properites (values for clouds and sky that persist throughout a sequence) and the properties of the trueSKY object itself (configuration settings).


The trueSKY Object
--------

To modify trueSKY object via scripting, a reference to the active object in the scene must first be obtained (there should only be one). This can be done upon initialiation; the code to do so is as follows:

	simul.trueSKY trueSky=simul.trueSKY.GetTrueSky();

All editor properties of the trueSKY object are publicly accessible, so once a reference to the trueSKY object has been obtained, they can also be accessed and modified via scripting. For example, to disable depth blending:

	private trueSKY tS;  
 
	void Start () 
	{
		tS = trueSKY.GetTrueSky (); 
		tS.DepthBlending = false;
	}


Sky and Clouds Layers
--------

Layer properties are those accessible in the sequencer by clicking on "Sky", "3D Clouds" or "2D clouds" on the left of the timeline. These affect the entire sequence and the values will remain until the user changes them manually. This differs in nature from keyframe properties, which are active only between specified times and will be automatically modified via interpolation (for example if two adjacent keyframes have cloudiness set to 0.4 and 0.6 respectively, trueSKY will interpolate these values for times in between, increasing gradually from 0.4 to 0.6). The functions needed to Get and Set layer properties are as follows:


**Sky**:

* **GetSkyFloat (string name)**: Gets the sky layer float specified by the name string.
* **GetSkyInt (string name)**: Gets the sky layer int specified by the name string.
* **SetSkyFloat  (string name, float value)**: Sets the sky layer float specified by the name string to the given float value.
* **SetSkyInt  (string name, int value)**: Sets the sky layer int specified by the name string to the given float value.

**3D Clouds**:

* **GetCloudFloat (string name)**: Gets the 3D cloud layer float specified by the name string.
* **GetCloudInt (string name)**: Gets the 3D cloud layer int specified by the name string.
* **SetCloudFloat  (string name, float value)**: Sets the 3D cloud layer float specified by the name string to the given float value.
* **SetCloudInt  (string name, int value)**: Sets the 3D cloud layer int specified by the name string to the given float value.

**2D Clouds**:

* **Get2DCloudFloat (string name)**: Gets the 2D cloud layer float specified by the name string.
* **Get2DCloudInt (string name)**: Gets the 2D cloud layer int specified by the name string.
* **Set2DCloudFloat  (string name, float value)**: Sets the 2D cloud layer float specified by the name string to the given float value.
* **Set2DCloudInt  (string name, int value)**: Sets the 2D cloud layer int specified by the name string to the given float value.



**Example**: To increment the 3D cloud layer rain speed by 5:

	private trueSKY tS;  
 
		void Start () 
		{
			tS = trueSKY.GetTrueSky (); 
			tS.SetCloudFloat("rainFallSpeedMS", tS.GetCloudFloat("rainFallSpeedMS") + 5.0f);  
		}


For information about the layer properties you can change and the name strings needed to do so, see the [Cloud](http://docs.simul.co/unity/Clouds.html) and [Sky](http://docs.simul.co/unity/Sky.html) pages.


Sky and Cloud Keyframes
--------

Keyframes in trueSKY can be accessed, counted, modified, created and deleted via scripting. To delete a keyframe or change its properties, the Unique Identifier (Uid) will need to be known. These can be retrieved either by index (the keyframes in the sequencer, which are zero-indexed) or by retrieving the current/interpolated keyframe (not viewable in the sequencer, as they are interpolated). Uids are unique and persistent for the session, but not across saves or restarts, so they should not be stored. **Note**: For any functions with a layer parameter, the layer indexes are as follows: **0** for the sky, **1** for 3D Clouds and **2** for 2D Clouds.

**Sky**:

* **GetSkyKeyframeByIndex (int index)**: Get the sky keyframe with specified index.
* **GetInterpolatedSkyKeyframe ()**: Retrieve the interpolated (current) sky keyframe.
* **InsertSkyKeyframe (float t)**: Insert a sky keyframe at specified time t.
* **GetNumSkyKeyframes ()**: Returns the total number of sky keyframes.

**3D Clouds**:

* **GetCloudKeyframeByIndex (int index)**: Get the 3D cloud keyframe with specified index.
* **GetInterpolatedCloudKeyframe (int layer = 1)**: Retrieve the interpolated (current) 3D cloud keyframe.
* **InsertCloudKeyframe (float t)**: Insert a 3D cloud keyframe at specified time t.
* **GetNumCloudKeyframes ()**: Returns the total number of 3D cloud keyframes.

**2D Clouds**:

* **GetCloud2DKeyframeByIndex (int index)**: Get the 2D cloud keyframe with specified index.
* **GetInterpolatedCloudKeyframe (int layer = 2)**: Retrieve the interpolated (current) 2D cloud keyframe.
* **Insert2DCloudKeyframe (float t)**: Insert a 2D cloud keyframe at specified time t.
* **GetNumCloud2DKeyframes ()**: Returns the total number of 2D cloud keyframes.


Once you know the Uid of a keyframe, you can then get the values of its properties, set said values or delete the keyframe. Whether you're accessing/modifying sky, 3D cloud or 2D cloud keyframes, these tasks are accomplished via the following functions: 

* **GetKeyframeValue (uint uid, string name)**: Gets the float or int value of the property specified by the name string, for the keyframe specified by the Uid.
* **SetKeyframeValue (uint uid, string name, object value)**: Sets the property specified by the name string, for the keyframe specified by the Uid, to the given value. The value should be an int or float (, though doubles are acceptable in place of floats.
* **DeleteKeyframe (uint uid)**: Deletes the keyframe specified by the Uid. This only works on sequencer-viewable keyframes, not interpolated ones.

**Example**: In the script KeyframeTesting.cs in the Simul directory, is a function that sets all the cloud keyframes to have a "cloudiness" of 0.8 when the game is run:

	int numk = trueSky.GetNumCloudKeyframes();
	for(int i = 0; i < numk; i++)
	{
		uint uid = trueSky.GetCloudKeyframeByIndex(i);
		trueSky.SetKeyframeValue(uid, "cloudiness", 0.8);
	}

For information about the keyframe properties you can change and the name strings needed to do so, see the [Cloud](http://docs.simul.co/unity/Clouds.html) and [Sky](http://docs.simul.co/unity/Sky.html) pages.



Other Functions
---------------
 
**Queries**

TrueSKY for Unity also provides some built in functions to carry out queries at given positions. It is possible to carry out cloud queries at a given position, and cloud line queries across two positions. These will return a VolumeQueryResult and a LineQueryResult respectively. Additionally there are more simplified functions for when you want just one value, for example, the amount of rain at a given position. Where applicable, id parameters should be given any unique integer (calling another query with the same id will overwrite the former). The functions are as follows:


* **GetCloudQuery (int id, Vector3 pos)**: Given an id and a position, returns a VolumeQueryResult struct.
* **CloudLineQuery (int id, Vector3 startpos, Vector3 endpos)**: Given an id, a start position and an end position, returns a LineQueryResult struct.
* **GetCloudAtPosition (Vector3 pos)**: Returns the amount of cloud at the given position, as a float value between 0.0 and 1.0.
* **GetCloudShadowAtPosition (Vector3 pos)**: Returns the amount of cloud shadow at the given position, as a float value between 0.0 and 1.0.
* **GetPrecipitationAtPosition (Vector3 pos)**: Returns the amount of rain/snow at the given position, as a float value between 0.0 and 1.0.


The contents of the structs are as follows:

**VolumeQueryResult**:
	
* vec3 pos_m: The position used for the query (this may be modified from the original position, and projected elsewhere to avoid testing areas we know to not have cloud).
* int valid: Whether the query is valid (1) or not (0). Returns 0 for the first 3 frames.
* float density: The cloud density (between 0.0 and 1.0).
* float direct_light: The amount of direct light (between 0.0 and 4.0).
* float indirect_light: The amount of indirect light (between 0.0 and 4.0).
* float ambient_light: The amount of ambient light (between 0.0 and 4.0).
* float precipitation: The amount of rain/snow (between 0.0 and 1.0).

**LineQueryResult**:

* vec3 pos1_m: The start position used for the query (this may be modified from the original position, and projected elsewhere to avoid testing areas we know to not have cloud).
* vec3 pos2_m: The end position used for the query (this may be modified from the original position, and projected elsewhere to avoid testing areas we know to not have cloud).
* int valid: Whether the query is valid (1) or not (0). Returns 0 for the first 3 frames.
* float density: The cloud density (between 0.0 and 1.0).
* float visibility: The visibility distance, in km (between 0.1 and 10000.0).
* float optical_thickness_metres: The amount of cloud filling the distance between the start and end positions. If completely cloudy  = distance in metres, if none = 0.
* float first_contact_metres: The distance to the nearest cloud, in metres.


**Storms**

The centre of a storm can be set via the SetStormCentre (float x, float y) function. This is equivalent to setting the storm centre via the map window in the sequencer (hence only two axes).


**Unity <-> trueSKY Coordinate Conversions**

As Unity and trueSKY treat coordinates differently (which axis is considered "up"), these functions are provided to convert between them when needed: 

* **Vector3 TrueSkyToUnityPosition(Vector3 ts_pos)**: Takes a trueSKY position and returns the converted Unity position.
* **Vector3 TrueSkyToUnityDirection(Vector3 ts_dir)**: Takes a trueSKY direction and returns the converted Unity direction.
* **Vector3 UnityToTrueSkyPosition(Vector3 upos)**: Takes a Unity position and returns the converted trueSKY position.
* **Vector3 UnityToTrueSkyDirection(Vector3 u_dir)**: Takes a Unity direction and returns the converted trueSKY direction.


Further Information
--------------
 
* [The Sequencer](http://docs.simul.co/reference/man_8_sequencer.html)   
* [The Clouds in trueSKY for Unity](http://docs.simul.co/unity/Clouds.html)
* [The Sky in trueSKY for Unity](http://docs.simul.co/unity/Sky.html)
* [Watch a video tutorial](https://www.youtube.com/watch?v=Eljf5CjZ4vc)




Next: <a href="/unity/Clouds">Clouds</a>