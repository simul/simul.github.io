---
title: Blueprints
layout: reference
weight: 10
---





The TrueSky Sequence Actor
--------------------------

{:.unity-specific}
Unity does not support Blueprints, but you can edit trueSKY via [scripting](/unity/scripting).

The trueSKY Blueprints provide a wide array of functionality while your game is playing or simulating. We have aimed to make sure our blueprints are as accessible as possible, while still being able to alter all of our different variables.

If you have never used blueprints before, [Unreal](https://docs.unrealengine.com/en-US/Engine/Blueprints/index.html) have a large number of tutorials on understanding and using blueprints.

You can edit any of the variables present in the keyframes, layers or even values attached to the trueSKY Actor. To access these nodes, we have split our variables based on their location and their data type. For example, if you want to edit a float value on a cloud keyframe, you would use the Set CloudKeyframe Float node. There is also a correlating GetCloudKeyframeFloat for retrieving data

![](/Images/Unreal/CloudKeyframeFloat.png)



From the image above, Property is the value that you want to change, which is selected using the dropdown. For the keyframe nodes, a Keyframe Unique Identifier (UID) is needed to access the correct keyframe. You can get this by manually going to your keyframe and looking for the UID at the top of the details panel, or there are multiple blueprint nodes available to help you select the correct keyframe. See more of these [here](#accessingKeyframesThroughBlueprints).

There are also nodes for sky keyframes, sky and cloud layers, and the variables within trueSkSequenceActor. To access these, use the FloatProperty and RenderingFloat Nodes, with either get or set.

Macros
------------
Macros are a combination of blueprint nodes we have put together for you to make certain tasks easier. You use a macro like you would a blueprint node, you can also double click to see exactly what it is doing.

![](/Images/unreal/timeofdaymacro.png)


<sup>Our time of day macro, with the nodes it is encapsulating on the right.</sup>


Our current Macros are:
Update Atmosphere Light
Update Atmosphere Light COmponent
Update Sequence
Update Time of Day

The values of the Sequence Actor itself can be changed via Blueprint. To Get and/or set these values, make a reference to the TrueSkySequenceActor and drag the output pin onto an empty space and either search for a value directly or navigate to Class-> TrueSkySequenceActor.


Queries
------------

To test how much cloud (from 0 to 1) is at a specified point, use the function CloudPointTest. **Note**: The Query Id can be set to any integer value, but should differ from any Query Ids used in separate queries (or else they will be overwritten).

![](/Images/unreal/CloudPointTest.png)

<sup>Sample usage of the Cloud Point Test functionality</sup>

To test if there is cloud between two points, use CloudLineTest:

![](/Images/unreal/CloudLineTest.png)

<sup>Sample usage of the Cloud Line Test functionality</sup> 

Driving trueSKY's Simulation through In-Scene Sun and Moon Data 
---------------------------
![](/Images/unreal/SetFromSunAndMoon.png )
Driving trueSKY through in-game actors/components, instead of the standard trueSKY-driving in-game actors/components.")

In a reversal of the default setup, SetSunRotation and SetMoonRotation can be used to drive the trueSKY sun and moon directly from a direct light source (or some other object). In order to user this feature, it is recommended to set the Interpolation Mode property of the trueSky Sequence Actor to "RealTime". This is so that any changes to the sun and moon direction will affect the trueSKY atmospherics regardless of whether game time is changing, and so that slight or slow changes in sun direction will not cause a per-frame recalculation of the atmospheric tables.

In addition to these Set functions for the sun/moon rotation, there are also Get functions for sun/moon rotation, colour and intensitiy. Additionally, you can Get/Set the texture of the moon in Blueprint.

![](/Images/unreal/GetSetMoonTexture.png)

<sup> Example of how to change the moon texture at runtime in blueprint </sup>

Managing Sequences
------------------------

Though you can only set the active sequence in the editor, it is possible to change the sequence in use mid-game using Blueprint. To do this, create a reference to your TrueSkySequenceActor in Blueprint, then drag the output pin onto the canvas. In the Action List, search for and select "Set Active Sequence". Repeat for as many sequences as you wish and connect them to relevant events. 

![](/Images/unreal/SetActiveSequence.png)

<sup>Example of how to change the active trueSKY sequence at runtime in blueprint </sup>

You can also get the active sequence in Blueprint. Similarly, just drag the output pin of your TrueSkySequence actor onto the canvas and search for and select "Get Active Sequence". This will return the Sequence Asset in use. 

![](/Images/unreal/GetActiveSequence.png)


<sup>Example of how to query the active trueSKY sequence at runtime in blueprint</sup>


Keeping Changes from Simulation
-------------------------

If you like the variables that are present while simulating the game, you can keep these changes. To do this, you must first start simulating the world. Next, in the World Outliner, right click the the object that you want to keep the changes of. Then select "Keep Simulated Changes", and your changes will be saved.

![](/Images/unreal/simulatedchanges.png)




Measuring Performance
------------------

trueSKY has a built-in profiler for GPU and CPU performance. Use "Get Profiling Text" to obtain the values, with the inputs "cpu_level" and "gpu_level" to determine how far down the call tree to display.

The outputs are in milliseconds.

![](/Images/unreal/GetProfilingText.png)

<sup> How to retrieve profiling text </sup>

Tests
--------

There are Blueprint functions provided to test a scene for lightning and for rain. For lightning, the "Get Lightning" function will provide the start position, end position, colour and magnitude of any lightning present. A magnitude of 0 means there is no lightning present. Additionally, the "Get Rain At Position" function will take a given position and return a float between 0.0 and 1.0, indicating the strength of the rain (or snow) at this position.

![](/Images/unreal/LightningRainTest.png )
Example of testing the weather conditions in blueprint.")


Editing in Blueprint: Keyframes
--------------------------

To get a keyframe's properties, you will first need its Unique ID (Uid) to identify it. Uids can be retrieved using a variety of provided Blueprint functions.

There is a Cloud version of all these functions, just replace sky with cloud in the function name. For Cloud Keyframes, you must specify the layer. Layers values start at 0

* **GetSkyKeyframebyIndex:** Returns a sky keyframe's Uid, given an index (this is zero-indexed; the first sky keyframe in a sequence is 0, the second is 1 and so on).

* **GetPreviousSkyKeyframeBeforeTime:** Given a time, returns the Uid of the last sky keyframe before said time.

* **GetNextSkyKeyframeAfterTime:** Given a time, returns the Uid of the next sky keyframe after said time.

* **GetNextModifiableSkyKeyframe:** Returns the Uid of the next sky keyframe that can be modified without requiring any recalculation (this will be the next sky keyframe + 1).

* **GetInterpolatedSkyKeyframe:** Returns the current interpolated sky keyframe's Uid (Note: this cannot be used to set any values; it is read-only).

Once you have a keyframe's Uid, you can Get and Set its properties. Select a Property from the Dropdown, input a keyframe UID and can you get or set the value. You can also use *CloudKeyframe* instead of SkyKeyframe to get Cloud variables.

* **GetSkyKeyFrameFloat:** Given a keyframe Uid and a name string, returns the float value matching the name.

* **GetSkyKeyframeInt:** Given a keyframe Uid and a name string, returns the integer value matching the name.

* **SetSkyKeyframeFloat:** Given a keyframe Uid, a name string and a float value, will set the matching property for the Name to the specified float value.

* **SetSkyKeyframeInt:** Given a keyframe Uid, a name string and an integer value, will set the matching property for the Name to the specified integer value.

![](/Images/unreal/BPGetSet.png)



