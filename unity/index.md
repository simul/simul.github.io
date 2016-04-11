---
title: Unity
layout: unity
---

trueSKY alpha for Unity
================

Getting started
--------------

Because the current version works only with DirectX 11, you will need to switch your project to DirectX 11 mode to see the rendered output. Do this using Edit:Project Settings:Player. In the Inspector, under "Settings for PC, Mac and Linux Standalone", in "Other Settings", chose "Use Direct3D 11*".

To activating trueSKY alpha, got to the GameObject menu, and select "*initialize trueSKY in scene*". This launches a dialogue - usually the default options will be fine. At the last step, this dialog will create:

* A Sequence asset containing sky and cloud data.
* A trueSKY object in the scene.
* A TrueSkyCamera component for the main camera.
* A TransparencyCamera component for the main camera.
* A SimulSun component for the Directional Light in the scene.

If there is no Directional Light, one will be created.

After initialization, select your main Camera, and find the TrueSkyCamera component. This component has a checkbox for "Flipped View". If you are using Forward rendering (under "Rendering Path" in the Camera component), and have extra post-processing components attached and enabled, you may need to set the "Flipped View" box. This is because Unity reverses the y-component of its framebuffers when performing post-processing.

trueSKY performs best with a near clipping plane around 1m, and a far plane between 100,000 and 500,000 metres. This is because the appearance of the atmospheric effects is dependent on the numerical precision of the depth buffer.

User Interface
--------------
The wizard to add trueSKY to a scene is found in the GameObject menu.
Under the Window menu are toggles for the trueSKY debug overlays.
General trueSKY properties are found by selecting the trueSKY object in the scene.
Sequence properties are found by editing Sequence assets. 

Transparencies
-----------------------
trueSKY rendering now occurs between the solid and transparent rendering in Unity. Therefore  the **TransparencyCamera** component is no longer required.

The trueSKY object
---------------
This is your connection to trueSKY within a scene. Its controls are:

**Render in Edit Mode**: Draw the trueSKY environment in the Game view from the Editor.

**Cloud Steps**: Number of raytracing steps to use - more=higher definition, fewer=faster.

**Downscale**: Resolution to render the clouds to - higher numbers = lower resolution.

**Gamma**: If you are not using Linear Color Space, this controls gamma-correction of the trueSKY environment.

**Sequence Asset**: The asset containing sky sequence data. Double-click this to edit the sky sequence.

**Time**: Time in days, so 0.5 would be midday on the first day, etc.

**Speed**: Determines how quickly Time changes when in-game.

**Diagnostics**: A set of overlays for debugging. Of particular interest is "Show Celestial Display", which tracks the motion of the Sun and Moon in the sky.

**Simulation Time Rain:** Set true or false - if true, rain falls at simulation speeds - faster if time is progressing more quickly. If false, rain falls relative to real time.

**Performance** If true, this enables CPU and GPU profiling for trueSKY. The results will be updated every few frames, and shown in the text area beneath the "Performance" checkbox. The sliders "CPU level" and "GPU level" let you set the depth of the profiling tree for CPU and GPU respectively.

The Sky Sequence
---------------

To control the sky properties from within the Editor, you can edit the sequence asset. This will usually be in the same directory as your scene, with a Simul "S" icon, and named [scene name]_sq. Click on this asset to launch the Sky Sequencer. Then:

Select the Properties tab or the Map. Click a keyframe to edit its properties. Double-click a line to edit all the keyframes in that line. Click on the title text to the left to edit the properties of the whole layer (sky or clouds).

Read more about editing Sky and Cloud properties on [The Sky Sequencer Page](http://docs.simul.co/reference/man_8_sequencer.html).

Scripting
---------
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

For details of the properties you can change, see the Reference pages below.

**Vector3 TrueSkyToUnityPosition(Vector3 ts_pos)**
**Vector3 TrueSkyToUnityDirection(Vector3 ts_dir)**
**Vector3 UnityToTrueSkyPosition(Vector3 upos)**
**Vector3 UnityToTrueSkyDirection(Vector3 u_dir)**
As Unity and trueSKY treat coordinates differently -- for example, which axis is considered "up" -- these functions are provided to convert between them when needed.

Reference
---------
[Sky and Atmospherics](Sky.html)

[Clouds](Clouds.html)

Techniques
----------
[Fixing Time of Day](FixingDaytime.html)