---
title: Scripting
layout: unity
weight : 2
---

The trueSKY Object
--------

Script control of the sky is via the trueSKY object. While the Sequence asset represents the initial state, you can change any value in-game from script.

To obtain a reference to the trueSKY object in the scene (there should only be one):

	simul.trueSKY trueSky=simul.trueSKY.GetTrueSky();

This is something you can do on initialization.


Sky and Clouds Layers
--------

Layer properties are those accessible in the sequencer by clicking on "Sky", "3D Clouds" or "2D clouds" on the left of the timeline. These affect the entire sequence and the values will remain until the user changes them manually. This differs in nature from keyframe properties, which are active only between specified times and will be automatically modified via interpolation (for example if two adjacent keyframes have cloudiness set to 0.4 and 0.6 respectively, trueSKY will interpolate these values for times in between, increasing gradually from 0.4 to 0.6). 

The functions needed to Get and Set layer properties are as follows:

* **GetSkyFloat (string name)**:
* **GetSkyInt (string name)**:
* **GetCloudFloat (string name)**:
* **GetCloudInt (string name)**:
* **SetSkyFloat  (string name, float value)**:
* **SetSkyInt  (string name, int value)**:
* **SetCloudFloat  (string name, float value)**:
* **SetCloudInt  (string name, int value)**:


Sky and Cloud Keyframes
--------

Keyframes in trueSKY can be accessed, counter, modified, created and deleted via scripting. To change or delete a keyframe, the Unique Identifier (Uid) will need to be known. These can be retrieved either by index (the keyframes in the sequencer, which are zero-indexed) or by retrieving the current/interpolated keyframe (not viewable in the sequencer, as they are interpolated). Uids are unique and persistent for the session, but not across saves or restarts, so they should not be stored. **Note**: For any functions with a layer parameter, the layer indexes are as follows: **0** for the sky, **1** for 3D Clouds and **2** for 2D Clouds.

**Sky**:
* **GetSkyKeyframeByIndex (int index)**: Get the sky keyframe with specified index.
* **GetInterpolatedSkyKeyframe ()**: Retrieve the interpolated (current) sky keyframe.
* **InsertSkyKeyframe ()**: Insert a sky keyframe at specified time t.
* **GetNumSkyKeyframes ()**: Returns the total number of sky keyframes.

**3D Clouds**:
* **GetCloudKeyframeByIndex (int index)**: Get the 3D cloud keyframe with specified index.
* **GetInterpolatedCloudKeyframe (int layer /*1*/)**: Retrieve the interpolated (current) 3D cloud keyframe.
* **InsertCloudKeyframe ()**: Insert a 3D cloud keyframe at specified time t.
* **GetNumCloudKeyframes ()**: Returns the total number of 3D cloud keyframes.

**2D Clouds**:
* **GetCloud2DKeyframeByIndex (int index)**: Get the 2D cloud keyframe with specified index.
* **GetInterpolatedCloudKeyframe (int layer /*2*/)**: Retrieve the interpolated (current) 2D cloud keyframe.
* **Insert2DCloudKeyframe (float t)**: Insert a 2D cloud keyframe at specified time t.
* **GetNumCloud2DKeyframes ()**: Returns the total number of 2D cloud keyframes.


Once you know the Uid of a keyframe, you can then get the values of its properties, set said values or delete the keyframe. Whether you're accessing/modifying sky, 3D cloud or 2D cloud keyframes, these tasks are accomplished  via the following functions: 

* **GetKeyframeValue (uint uid, string name)**: Gets the float or int value of the property specified by the name string, for the keyframe specified by the Uid.
* **SetKeyframeValue (uint uid, string name, object value)**: Sets the property specified by the name string, for the keyframe specified by the Uid, to the given value. The value should be an int or float (, though doubles are acceptable in place of floats.
* **DeleteKeyframe (uint uid)**: Deletes the keyframe specified by the Uid. This only works on sequencer-viewable keyframes, not interpolated ones.


**Example**: In the script KeyframeTesting.cs in the Simul directory, is a function that sets all the cloud keyframes to have a "cloudiness" of 0.8 when the game is run:

	int numk=trueSky.GetNumCloudKeyframes();
	for(int i=0;i<numk;i++)
	{
		uint uid=trueSky.GetCloudKeyframeByIndex(i);
		trueSky.SetKeyframeValue(uid,"cloudiness",0.8);
	}

For details of the properties you can change, see the [Cloud](http://docs.simul.co/unity/Clouds.html) and [Sky](http://docs.simul.co/unity/Sky.html) pages.



Other Functions
---------------
 
As Unity and trueSKY treat coordinates differently (which axis is considered "up"), these functions are provided to convert between them when needed: 

**Vector3 TrueSkyToUnityPosition(Vector3 ts_pos)**
**Vector3 TrueSkyToUnityDirection(Vector3 ts_dir)**
**Vector3 UnityToTrueSkyPosition(Vector3 upos)** 
**Vector3 UnityToTrueSkyDirection(Vector3 u_dir)**



Next: <a href="/unity/Clouds">Clouds</a>