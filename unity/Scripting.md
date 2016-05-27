---
title: Scripting
layout: unity
weight : 2
---

Script control of the sky is via the trueSKY object. While the Sequence asset represents the initial state, you can change any value in-game from script.

To obtain a reference to the trueSKY object in the scene (there should only be one):

		simul.trueSKY trueSky=simul.trueSKY.GetTrueSky();

This is something you can do on initialization.

**int GetNumSkyKeyframes()**: Returns the number of sky keyframes in the current sequence.

**int GetNumCloudKeyframes()**: Return the number of (3D) cloud keyframes.

**int GetNumCloud2DKeyframes()**: Returns the number of 2D cloud keyframes.

We use uint's as unique identifiers (uid's) to represent keyframes. Note: these are unique and persistent for the session, but not across saves or restarts, so don't store these.
		
**uint GetInterpolatedCloudKeyframe(int layer)**: Get the special uid that refers to the interpolated cloud keyframe, i.e. the *current* values. The layer specifies 0=3D clouds, 1=2D clouds.

**uint GetInterpolatedSkyKeyframe()**: Get the special uid that refers to the interpolated sky keyframe, i.e. the *current* values.

**uint GetSkyKeyframeByIndex(int index)**: Get a uid for the specified sky keyframe, between zero and (1-GetNumSkyKeyframes()).

**uint GetCloudKeyframeByIndex(int index)**: Get a uid for the specified 3D cloud keyframe, between zero and (1-GetNumCloudKeyframes()).

**uint GetCloud2DKeyframeByIndex(int index)**: Get a uid for the specified 3D cloud keyframe, between zero and (1-GetNumCloud2DKeyframes()).

**uint InsertSkyKeyframe(float t)**: Insert a sky keyframe at the specified time (0=midnight on the first day, 0.5=midday, etc).

**uint InsertCloudKeyframe(float t)**: Insert a cloud keyframe at the specified time.

**uint Insert2DCloudKeyframe(float t)**: Insert a 2D cloud keyframe.

We can get keyframe properties if we know the uid.

**object GetKeyframeValue(uint uid,string name)**: Returns property *name* of keyframe *uid*. The result will be a *float*, or an *int*.

We can modify and delete keyframes at any point, but this only works on keyframes in the sequence, not on the interpolated keyframes - as these represent the current, calculated state.

**void DeleteKeyframe(uint uid)**: Delete the keyframe (sky or clouds).

**void SetKeyframeValue(uint uid,string name,object value)**: Set the property of keyframe *uid* named by *name* to the *value* given, which should be a *float* or an *int* (*double*s are accepted for *float* values, but *float* values can't be passed to *int* properties and vice versa).

For example,in the script KeyframeTesting.cs in the Simul directory, is a function that sets all the cloud keyframes to have a "cloudiness" of 0.8 when the game is run:

	
	int numk=trueSky.GetNumCloudKeyframes();
	for(int i=0;i<numk;i++)
	{
		uint uid=trueSky.GetCloudKeyframeByIndex(i);
		trueSky.SetKeyframeValue(uid,"cloudiness",0.8);
	}

For details of the properties you can change, see the Clouds and Sky Reference pages.
 
**Vector3 TrueSkyToUnityPosition(Vector3 ts_pos)**
**Vector3 TrueSkyToUnityDirection(Vector3 ts_dir)**
**Vector3 UnityToTrueSkyPosition(Vector3 upos)** 
**Vector3 UnityToTrueSkyDirection(Vector3 u_dir)**

As Unity and trueSKY treat coordinates differently -- for example, which axis is considered "up" -- these functions are provided to convert between them when needed.


Next: <a href="/unity/Clouds">Clouds</a>