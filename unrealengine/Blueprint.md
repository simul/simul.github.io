---
title: Blueprint
layout: unreal
weight : 3
---

trueSKY in Blueprint
========

The trueSKY Blueprint macros provide a wide array of functionality while your game is playing or simulating, so these macros will not take effect unless you are in one of these modes. To permanently change the properties of a light, start simulating, and right-click your Directional Light, then select "Keep Simulation Changes".


Lighting
--------------

The simplest way to drive Unreal Engine lighting from trueSKY is to use the trueSKY macros. These are in the file trueSkyMacros.uasset, which is to be found in [UE4]/Engine/Plugins/TrueSkyPlugin/Content.

To set the direction and colour of a Directional Light, find the trueSKYSun or trueSKYMoon macro, and connect a reference to the DirectionalLight to the input. Make sure that the "Exec" input is hit once per frame by an event tick. 


<a href="http://docs.simul.co/unrealengine/images/trueSKYSun.png"><img src="http://docs.simul.co/unrealengine/images/trueSKYSun.png" alt="Blueprint"/></a>

Alternatively, use the TrueSkyLighting macro -- this also allows time of day to be set.

<a href="http://docs.simul.co/unrealengine/images/trueSkyLighting.png"><img src="http://docs.simul.co/unrealengine/images/trueSkyLighting.png" alt="Blueprint"/></a>

Additionally, point lights can be used to illuminate the clouds. Because of the relative scale of clouds to the UE4 scene, the intensity of the light must be very large in order to have a visible effect.
 
<a href="http://docs.simul.co/unrealengine/images/SetPointLight.png"><img src="http://docs.simul.co/unrealengine/images/SetPointLight.png" alt="Blueprint" /></a>

If you do not have a PointLight actor, you can use SetPointLightSource to apply individually the position, colour and intensity of a light to the clouds.


Time of Day
------------

To change the time of day, use the SetTime function of the trueSKY sequence actor (time is in days, from midnight on the first day (0.0). For framerate-independent progression, it is advisable to make use of Delta Time. For information on how to do this, please [view the tutorial here](http://docs.simul.co/unrealengine/Tutorial.html).
 
<a href="http://docs.simul.co/unrealengine/images/SettingTime.png"><img src="http://docs.simul.co/unrealengine/images/SettingTime.png" alt="Blueprint"/></a>


The Sky and Clouds 
------------

Both the sky and clouds can be accessed and edited in Blueprint.  

Read more about [editing the sky here](http://docs.simul.co/unrealengine/Sky.html) and about [editing the clouds here](http://docs.simul.co/unrealengine/Clouds.html).


Transparency
------------

To correctly affect transparent objects, trueSKY will write loss, inscatter and cloud transparency textures once per frame. Connect the textures from the (automatically created) trueSky folder, to the texture properties in the trueSKY Sequence Actor to enable this. Note: If you are using the True Sky Light in place of the default UE4 Skylight, do not set the Skylight Cubemap RT.

<a href="http://docs.simul.co/unrealengine/images/TrueSkyRenderTargets.png"><img src="http://docs.simul.co/unrealengine/images/TrueSkyRenderTargets.png" alt="Blueprint" /></a>

In a material that uses transparency, insert the trueSKYTransparencyModifier function between the inputs and the final output node:

<a href="http://docs.simul.co/unrealengine/images/Transparency.png"><img src="http://docs.simul.co/unrealengine/images/Transparency.png" alt="Blueprint" /></a>


Queries
-------
To test how much cloud (from 0 to 1) is at a specified point, use the function CloudPointTest. NOTE: The Query Id can be set to any integer value, but should differ from any Query Ids used in different queries.

<a href="http://docs.simul.co/unrealengine/images/CloudPointTest.png"><img src="http://docs.simul.co/unrealengine/images/CloudPointTest.png" alt="Blueprint" /></a>

To test if there is cloud between two points, use CloudLineTest:

<a href="http://docs.simul.co/unrealengine/images/CloudLineTest.png"><img src="http://docs.simul.co/unrealengine/images/CloudLineTest.png" alt="Blueprint" /></a>
 

Keyframe Properties
--------------------------------------------------------------------------------------------------

To set a keyframe's value from Blueprint, use the SetKeyframeFloat, or SetKeyframeInt functions. You must pass the keyframe's integer uid, the name of the property as a string, and the value.

Similarly, GetKeyframeFloat and GetKeyframeInt are used to obtain current values.

You can get the next uid in the future that can be modified without recalculation using GetNextModifiableCloudKeyframe -- that's needed if the cloud keyframer's Update property is set to "Instant". If it's "Gradual", any keyframe can be modified at any time.

* GetCloudKeyframeByIndex: To get an identifier for the cloud keyframe at the specified index, returns 0 if out of range.

* GetNextCloudKeyframeAfterTime: Get an identifier for the next cloud keyframe at or after the specified time.

* GetPreviousCloudKeyframeBeforeTime: Get an identifier for the last cloud keyframe before the specified time.
	
* GetSkyKeyframeByIndex Get an identifier for the cloud keyframe at the specified index. Returns 0 if there is none at that index (e.g. you have gone past the end of the list).

* GetNextSkyKeyframeAfterTime: Get an identifier for the next cloud keyframe at or after the specified time.

* GetPreviousSkyKeyframeBeforeTime: Get an identifier for the last sky keyframe before the specified time.


Sun and Moon Properties
---------------------

<a href="http://docs.simul.co/unrealengine/images/SetFromSunAndMoon.png"><img src="http://docs.simul.co/unrealengine/images/SetFromSunAndMoon.png" alt="Blueprint" />

In a reversal of the default setup, SetSunRotation and SetMoonRotation can be used to drive the trueSKY sun and moon directly from an Unreal Engine direction light (or some other object). In order to user this feature, it is recommended to set the Mode properties of the Sky keyframer to "Fixed Intervals (real time)", and "Gradual" update. This is so that any changes to the sun and moon direction will affect the trueSKY atmospherics regardless of whether game time is changing, and so that slight or slow changes in sun direction will not cause a per-frame recalculation of the atmospheric tables.

<a href="http://docs.simul.co/unrealengine/images/SkyModeForSetSunDirection.png"><img src="http://docs.simul.co/unrealengine/images/SkyModeForSetSunDirection.png" alt="Blueprint" />

In addition to these Set functions for the sun/moon rotation, there are also Get functions for sun/moon rotation, colour and intensitiy. Additionally, you can Get/Set the texture of the moon in Blueprint.

<a href="http://docs.simul.co/unrealengine/images/GetSetMoonTexture.png"><img src="http://docs.simul.co/unrealengine/images/GetSetMoonTexture.png" alt="Blueprint" /></a>


Precipitation and Lightning
---------------------

There are Blueprint functions provided to test a scene for lightning and for rain. For lightning, the Get Lightning function will provide the start position, end position, colour and magnitude of any lightning present. A magnitude of 0 means there is no lightning present. Additionally, the Get Rain At Position function will take a given position and return a float between 0.0 and 1.0 indicating the strength of the rain (or snow) at this position.

<a href="http://docs.simul.co/unrealengine/images/LightningRainTest.png"><img src="http://docs.simul.co/unrealengine/images/LightningRainTest.png" alt="Blueprint" /></a>


Managing Sequences
---------------------

Though you can only set the active sequence in the editor, it is possible to change the sequence in use mid-game using Blueprint. To do this, create a reference to your TrueSkySequenceActor in Blueprint, then drag the output pin onto the canvas. In the Action List, search for and select "Set Active Sequence". Repeat for as many sequences as you wish and connect them to relevant events. 

<a href="http://docs.simul.co/unrealengine/images/SetActiveSequence.png"><img src="http://docs.simul.co/unrealengine/images/SetActiveSequence.png" alt="Blueprint" />

You can also get the active sequence in Blueprint. Similarly, just drag the output pin of your TrueSkySequence actor onto the canvas and search for and select "Get Active Sequence". This will return the Sequence Asset in use. 

<a href="http://docs.simul.co/unrealengine/images/GetActiveSequence.png"><img src="http://docs.simul.co/unrealengine/images/GetActiveSequence.png" alt="Blueprint" />


Measuring Performance
---------------------
trueSKY has a built-in profiler for GPU and CPU performance. Use "Get Profiling Text" to obtain the values, with the inputs "cpu_level" and "gpu_level" to determine how far down the call tree to display.

The outputs are in milliseconds.

<a href="http://docs.simul.co/unrealengine/images/GetProfilingText.png"><img src="http://docs.simul.co/unrealengine/images/GetProfilingText.png" alt="Blueprint" />

Next: <a href="/unrealengine/Clouds">Clouds</a>