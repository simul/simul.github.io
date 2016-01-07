---
title: Blueprint
layout: unreal
---

trueSKY Lighting
--------------

The simplest way to drive Unreal Engine lighting from trueSKY is to use the trueSKY macros. These are in the file trueSkyMacros.uasset, which is to be found in [UE4]/Engine/Plugins/TrueSkyPlugin/Content.

To set the direction and colour of a Directional Light, find the trueSKYSun or trueSKYMoon macro, and connect a reference to the DirectionalLight to the input. Make sure that the "Exec" input is hit once per frame by an event tick. 


<a href="http://docs.simul.co/unrealengine/images/trueSKYSun.png"><img src="http://docs.simul.co/unrealengine/images/trueSKYSun.png" alt="Blueprint"/></a>

Alternatively, use the TrueSkyLighting macro - this also allows time of day to be set.


<a href="http://docs.simul.co/unrealengine/images/trueSkyLighting.png"><img src="http://docs.simul.co/unrealengine/images/trueSkyLighting.png" alt="Blueprint"/></a>

Time of Day
------------

To change the time of day, use the SetTime function of the trueSKY sequence actor (time is in days, from midnight on the first day (0.0):


<a href="http://docs.simul.co/unrealengine/images/SetTime.png"><img src="http://docs.simul.co/unrealengine/images/SetTime.png" alt="Blueprint" /></a>

Transparency
------------

To correctly affect transparent objects, trueSKY will write loss, inscatter and cloud transparency textures once per frame. Connect the textures from the (automatically created) trueSky folder, to the texture properties in the trueSKY Sequence Actor to enable this.

<a href="http://docs.simul.co/unrealengine/images/TrueSkyRenderTargets.png"><img src="http://docs.simul.co/unrealengine/images/TrueSkyRenderTargets.png" alt="Blueprint" /></a>

In a material that uses transparency, insert the trueSKYTransparencyModifier function between the inputs and the final output node:

<a href="http://docs.simul.co/unrealengine/images/Transparency.png"><img src="http://docs.simul.co/unrealengine/images/Transparency.png" alt="Blueprint" /></a>

Queries
-------
To test how much cloud (from 0 to 1) is at a specified point, use the function CloudPointTest.

<a href="CloudPointTest.png"><img src="http://docs.simul.co/unrealengine/images/CloudPointTest.png" alt="Blueprint" /></a>

To test if there is cloud between two points, use CloudLineTest:

<a href="CloudLineTest.png"><img src="http://docs.simul.co/unrealengine/images/CloudLineTest.png" alt="Blueprint" /></a>

Lighting
--------
Point lights can be used to illuminate the clouds. Because of the relative scale of clouds to the UE scene, the intensity of the light must be very large in order to have a visible effect.

<a href="SetPointLight.png"><img src="http://docs.simul.co/unrealengine/images/SetPointLight.png" alt="Blueprint" /></a>

If you do not have a PointLight actor, you can use SetPointLightSource to apply individually the position, colour and intensity of a light to the clouds.

Setting keyframe properties from Blueprint
--------------------------------------------------------------------------------------------------

To set a keyframe's value from Blueprint, use the SetKeyframeFloat, or SetKeyframeInt functions. You must pass the keyframe's integer uid, the name of the property as a string, and the value.

Similarly, GetKefyrameFloat and GetKeyframeInt are used to obtain current values.

You can get the next uid in the future that can be modified without recalculation using GetNextModifiableCloudKeyframe - that's needed if the cloud keyframer's Update property is set to "Instant". If it's "Gradual", any keyframe can be modified at any time.

* GetCloudKeyframeByIndex: To get an identifier for the cloud keyframe at the specified index, returns 0 if out of range.

* GetNextCloudKeyframeAfterTime: Get an identifier for the next cloud keyframe at or after the specified time.

* GetPreviousCloudKeyframeBeforeTime: Get an identifier for the last cloud keyframe before the specified time.
	
* GetSkyKeyframeByIndex Get an identifier for the cloud keyframe at the specified index. Returns zero if there is none at that index (e.g. you have gone past the end of the list).

* GetNextSkyKeyframeAfterTime: Get an identifier for the next cloud keyframe at or after the specified time.

* GetPreviousSkyKeyframeBeforeTime: Get an identifier for the last sky keyframe before the specified time.


Setting sun and moon position from Blueprint
---------------------

<img src="http://docs.simul.co/unrealengine/images/SetFromSunAndMoon.png" alt="Blueprint" />

In a reversal of the default setup, SetSunDirection and SetMoonDirection can be used to drive the trueSKY sun and moon directly from an Unreal Engine direction light (or some other object). In order to user this feature, it is recommended to set the Mode properties of the Sky keyframer to "Fixed Intervals (real time)", and "Gradual" update. This is so that any changes to the sun and moon direction will affect the trueSKY atmospherics regardless of whether game time is changing, and so that slight or slow changes in sun direction will not cause a per-frame recalculation of the atmospheric tables.

<img src="http://docs.simul.co/unrealengine/images/SkyModeForSetSunDirection.png" alt="Blueprint" />

Measuring performance
---------------------
trueSKY has a built-in profiler for GPU and CPU performance. Use "Get Profiling Text" to obtain the values, with the inputs "cpu_level" and "gpu_level" to determine how far down the call tree to display.

The outputs are in milliseconds.

<img src="http://docs.simul.co/unrealengine/images/GetProfilingText.png" alt="Blueprint" />

Next: <a href="/unrealengine/Clouds">Clouds</a>