---
title: Blueprint
layout: home
---

trueSKY Lighting
--------------

The simplest way to drive Unreal Engine lighting from trueSKY is to use the trueSKY macros - [UE4]/Engine/Plugins/TrueSkyPlugin/Blueprint/trueSkyMacros.uasset. Copy this file into your project's assets directory to make the macros available.

To set the direction and colour of a Directional Light, find the trueSKYLightColourAndRotation macro, and connect references for the trueSkySequenceActor and the DirectionalLight to the inputs. Make sure that the "Exec" input is hit once per frame by an event tick. 

<img src="images/MacroLightColourRotation.png" alt="Blueprint"/>

Alternatively, use the GetSunRotation and Get Sun Colour functions directly. Place a reference to the trueSKY actor, and the directional light, on the master Level Blueprint. Connect the Get Sun Rotation output from trueSKY to the Directional Light's Rotator input; and connect the Sun Colour output from trueSKY to the SetLightColor input of the light.

<img src="https://simul.co/wp-content/uploads/documentation/html/SetLightColourDirection.png" alt="Blueprint"/>

Time of Day
------------

To change the time of day, use the SetTime function of the trueSKY sequence actor (time is in days, from midnight on the first day (0.0):

<a href="SetTime.png"><img src="https://simul.co/wp-content/uploads/documentation/html/SetTime.png" alt="Blueprint" /></a>


Setting keyframe properties from Blueprint
--------------------------------------------------------------------------------------------------

To set a keyframe's value from Blueprint, use the SetKeyframeFloat, or SetKeyframeInt functions. You must pass the keyframe's integer uid, the name of the property as a string, and the value.

Similarly, GetKefyrameFloat and GetKeyframeInt are used to obtain current values.

You can get the next uid in the future that can be modified without recalculation using GetNextModifiableCloudKeyframe. 
