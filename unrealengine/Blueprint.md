---
title: Blueprint
layout: page
---

trueSKY Lighting
--------------

The simplest way to drive Unreal Engine lighting from trueSKY is to use the trueSKY macros - [UE4]/Engine/Plugins/TrueSkyPlugin/Blueprint/trueSkyMacros.uasset. Copy this file into your project's assets directory to make the macros available.

To set the direction and colour of a Directional Light, find the trueSKYLightColourAndRotation macro, and connect references for the trueSkySequenceActor and the DirectionalLight to the inputs. Make sure that the "Exec" input is hit once per frame by an event tick. 

<img src="http://docs.simul.co/unrealengine/images/MacroLightColourRotation.png" alt="Blueprint"/>

Alternatively, use the GetSunRotation and Get Sun Colour functions directly. Place a reference to the trueSKY actor, and the directional light, on the master Level Blueprint. Connect the Get Sun Rotation output from trueSKY to the Directional Light's Rotator input; and connect the Sun Colour output from trueSKY to the SetLightColor input of the light.

<img src="http://docs.simul.co/unrealengine/images/SetLightColourDirection.png" alt="Blueprint"/>

Time of Day
------------

To change the time of day, use the SetTime function of the trueSKY sequence actor (time is in days, from midnight on the first day (0.0):

<a href="SetTime.png"><img src="http://docs.simul.co/unrealengine/images/SetTime.png" alt="Blueprint" /></a>

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

Next: <a href="/unrealengine/Clouds">Clouds</a>