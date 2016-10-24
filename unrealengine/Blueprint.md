---
title: Blueprint
layout: unreal
weight : 3
---

trueSKY in Blueprint
========

The trueSKY Blueprint macros provide a wide array of functionality while your game is playing or simulating. These macros will not take effect unless you are in one of these modes. To permanently change the properties of a light, start simulating, and right-click your Directional Light, then select "Keep Simulation Changes".


The TrueSky Sequence Actor
--------------

The values of the Sequence Actor itself can be changed via Blueprint. To Get and/or set these values, make a reference to the TrueSkySequenceActor and drag the output pin onto an empty space and either search for a value directly or navigate to Class-> TrueSkySequenceActor.

Lighting
--------------

The simplest way to drive Unreal Engine lighting from trueSKY is to use the trueSKY macros. These are in the file trueSkyMacros.uasset, which is to be found in [UE4]/Engine/Plugins/TrueSkyPlugin/Content.

To set the direction and colour of a Directional Light, find the trueSKYSun or trueSKYMoon macro, and connect a reference to the DirectionalLight to the input. Make sure that the "Exec" input is hit once per frame by an event tick. 


<a href="http://docs.simul.co/unrealengine/images/UpdateSunlight.png"><img src="http://docs.simul.co/unrealengine/images/UpdateSunlight.png" alt="Blueprint"/></a>

Alternatively, use the TrueSkyLighting macro -- this also allows time of day to be set.

<a href="http://docs.simul.co/unrealengine/images/trueSkyLighting.png"><img src="http://docs.simul.co/unrealengine/images/trueSkyLighting.png" alt="Blueprint"/></a>

Additionally, point lights can be used to illuminate the clouds. Because of the relative scale of clouds to the UE4 scene, the intensity of the light must be very large in order to have a visible effect.
 
<a href="http://docs.simul.co/unrealengine/images/SetPointLight.png"><img src="http://docs.simul.co/unrealengine/images/SetPointLight.png" alt="Blueprint" /></a>

If you do not have a PointLight actor, you can use SetPointLightSource to individually apply the position, colour and intensity of a light to the clouds.

For ambient lighting, add a TrueSkyLight actor to your scene. This replaces the default UE SkyLight, and automatically updates ambient lighting.

Cloud Shadows
-------------
The shadows of clouds can be applied to your directional light object using the M_LightFunction in the Content/TrueSky directory of your project. If you modify this function, make a copy of it with a different name, otherwise it will be overwritten when the plugin next starts (this applies to all the content in the TrueSky folder).

<a href="http://docs.simul.co/unrealengine/images/LightFunction.png"><img src="http://docs.simul.co/unrealengine/images/LightFunction.png" alt="Blueprint" /></a>

Time of Day
------------

To change the time of day, use the SetTime function of the trueSKY sequence actor (time is in days, from midnight on the first day (0.0). For framerate-independent progression, it is advisable to make use of Delta Time. For information on how to do this, please [view the tutorial here](http://docs.simul.co/unrealengine/Tutorial.html).
 
<a href="http://docs.simul.co/unrealengine/images/SettingTime.png"><img src="http://docs.simul.co/unrealengine/images/SettingTime.png" alt="Blueprint"/></a>

Physical Units (trueSKY 4.1 onward)
--------------

trueSKY is a physically-based renderer, which means that the light and colour values generated correspond to true physical properties. The pixel colours rendered to a view are spectral radiance values. However, to keep the numbers from getting too high or low, a global adjustment is applied. This is because numerical accuracy would be lost, particularly for very dark night-time scenes, if we kept the same scale at all times. The Sky property "Brightness Power" controls this adjustment - if equal to one, there is no adjustment. Values smaller than one reduce the range of outputs - brightening dark skies and dimming very bright skies. To obtain the current value of the multiplier, use the Blueprint function "GetReferenceSpectralRadiance". Then you can use the calculation:

	spectral radiance (watts/square metre/steradian/nm) = pixel value * reference spectral radiance

You can use this value to calibrate the other lights in your scene. Say you have a point light representing an electric bulb. The brightness of this light would in reality be constant. But because trueSKY adjusts the physical value of a pixel as time passes, you must compensate for this by scaling the intensity of the bulb by the inverse of the reference radiance.

<a href="http://docs.simul.co/unrealengine/images/ReferenceSpectralRadiance.png"><img src="http://docs.simul.co/unrealengine/images/ReferenceSpectralRadiance.png" alt="Blueprint"/></a>

So the light appears to get brighter as day turns to night. You can get the same effect using Unreal's Eye Adaptation (Auto Exposure). But because this is a post-process effect, it cannot cope with very dark scenes - you may see banding in the sky colours due to the low numerical accuracy of very small numbers.

<a href="http://docs.simul.co/unrealengine/images/DayLightRadiance.png"><img src="http://docs.simul.co/unrealengine/images/DayLightRadiance.png" alt="Blueprint"/></a>
<a href="http://docs.simul.co/unrealengine/images/SunsetLightRadiance.png"><img src="http://docs.simul.co/unrealengine/images/SunsetLightRadiance.png" alt="Blueprint"/></a>
<a href="http://docs.simul.co/unrealengine/images/NightLightRadiance.png"><img src="http://docs.simul.co/unrealengine/images/NightLightRadiance.png" alt="Blueprint"/></a>


The Sky and Clouds 
------------

Both the sky and clouds can be accessed and edited in Blueprint.  

Read more about [editing the sky here](http://docs.simul.co/unrealengine/Sky.html) and [editing the clouds here](http://docs.simul.co/unrealengine/Clouds.html).


Transparency
------------

To correctly affect transparent objects, trueSKY will write loss, inscatter and cloud transparency textures once per frame. Connect the textures from the (automatically created) trueSky folder, to the texture properties in the trueSKY Sequence Actor to enable this. **Note**: If you are using the True Sky Light in place of the default UE4 Skylight, do not set the Skylight Cubemap RT.

<a href="http://docs.simul.co/unrealengine/images/TrueSkyRenderTargets.png"><img src="http://docs.simul.co/unrealengine/images/TrueSkyRenderTargets.png" alt="Blueprint" /></a>

In a material that uses transparency, insert the trueSKYTransparencyModifier function between the inputs and the final output node:

<a href="http://docs.simul.co/unrealengine/images/Transparency.png"><img src="http://docs.simul.co/unrealengine/images/Transparency.png" alt="Blueprint" /></a>


Queries
-------
To test how much cloud (from 0 to 1) is at a specified point, use the function CloudPointTest. **Note**: The Query Id can be set to any integer value, but should differ from any Query Ids used in seperate queries (or else they will be overwritten).

<a href="http://docs.simul.co/unrealengine/images/CloudPointTest.png"><img src="http://docs.simul.co/unrealengine/images/CloudPointTest.png" alt="Blueprint" /></a>

To test if there is cloud between two points, use CloudLineTest:

<a href="http://docs.simul.co/unrealengine/images/CloudLineTest.png"><img src="http://docs.simul.co/unrealengine/images/CloudLineTest.png" alt="Blueprint" /></a>
 

Layer Properties
--------------------------------------------------------------------------------------------------

To set a layer property Blueprint, use the functions below. The following will need to be prefixed onto the property's name string: "sky:", "clouds:" or "2dclouds:", depending on the layer in use. E.g., to set the 2D cloud layer's noise period to 3.5, the SetFloat function would be called with "2dclouds:noisePeriod" as the Name parameter, and 3.5 as the Value parameter.

* **GetInt (String Name):** Gets the specified integer property for the prefixed layer.
* **SetInt (String Name, int Value):** Sets the specified integer property for the prefixed layer to the given value.
* **GetFloat (String Name):** Gets the specified float property for the prefixed layer.
* **SetFloat (String Name, float Value):**  Sets the specified float property for the prefixed layer to the given value.

For information about the layer properties you can change and the name strings needed to do so, see the [Cloud](http://docs.simul.co/unrealengine/Clouds.html) and [Sky](http://docs.simul.co/unrealengine/Sky.html) pages.


Keyframe Properties
--------------------------------------------------------------------------------------------------

To set a keyframe's value from Blueprint, use the SetKeyframeFloat, or SetKeyframeInt functions. You must pass the keyframe's integer uid, the name of the property as a string, and the value. Similarly, GetKeyframeFloat and GetKeyframeInt are used to obtain current values. 

There are multiple functions provided to get the uid required to modify a keyframe. However, if the cloud keyframer's Update property is set to "Instant", you will need to use GetNextModifiableCloudKeyframe*(int Layer)* function to get the next uid that can be modified without recalculation. If the Update property is instead set to "Gradual", any keyframe can be modified at any time, and the functions below can be used to return the uids required for setting and getting keyframe values. Note: For clouds, the correct layer parameters are 1 for 3D and 2 for 2D.

* **GetCloudKeyframeByIndex (int Layer, int Index):** To get an identifier for the cloud keyframe at the specified layer and index, returns 0 if out of range. 
* **GetNextCloudKeyframeAfterTime (int Layer, float T):** Get an identifier for the next cloud keyframe at or after the specified time T. 
* **GetPreviousCloudKeyframeBeforeTime (int Layer, float T):** Get an identifier for the last cloud keyframe before the specified time T. 
* **GetSkyKeyframeByIndex (int Index):** Get an identifier for the cloud keyframe at the specified index. Returns 0 if there is none at that index (e.g. you have gone past the end of the list). 
* **GetNextSkyKeyframeAfterTime (float T):** Get an identifier for the next cloud keyframe at or after the specified time T. 
* **GetPreviousSkyKeyframeBeforeTime (float T):** Get an identifier for the last sky keyframe before the specified time T.


Sun and Moon Properties
---------------------

<a href="http://docs.simul.co/unrealengine/images/SetFromSunAndMoon.png"><img src="http://docs.simul.co/unrealengine/images/SetFromSunAndMoon.png" alt="Blueprint" />

In a reversal of the default setup, SetSunRotation and SetMoonRotation can be used to drive the trueSKY sun and moon directly from a direct light source (or some other object). In order to user this feature, it is recommended to set the Mode properties of the Sky keyframer to "Fixed Intervals (real time)", and "Gradual" update. This is so that any changes to the sun and moon direction will affect the trueSKY atmospherics regardless of whether game time is changing, and so that slight or slow changes in sun direction will not cause a per-frame recalculation of the atmospheric tables.

<a href="http://docs.simul.co/unrealengine/images/SkyModeForSetSunDirection.png"><img src="http://docs.simul.co/unrealengine/images/SkyModeForSetSunDirection.png" alt="Blueprint" />

In addition to these Set functions for the sun/moon rotation, there are also Get functions for sun/moon rotation, colour and intensitiy. Additionally, you can Get/Set the texture of the moon in Blueprint.

<a href="http://docs.simul.co/unrealengine/images/GetSetMoonTexture.png"><img src="http://docs.simul.co/unrealengine/images/GetSetMoonTexture.png" alt="Blueprint" /></a>


Precipitation and Lightning
---------------------

There are Blueprint functions provided to test a scene for lightning and for rain. For lightning, the "Get Lightning" function will provide the start position, end position, colour and magnitude of any lightning present. A magnitude of 0 means there is no lightning present. Additionally, the "Get Rain At Position" function will take a given position and return a float between 0.0 and 1.0 indicating the strength of the rain (or snow) at this position.

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



Further Information
--------------
 
* [The Sequencer](http://docs.simul.co/reference/man_8_sequencer.html)   
* [The Clouds in trueSKY for UE4](http://docs.simul.co/unrealengine/Clouds.html)
* [The Sky in trueSKY for UE4](http://docs.simul.co/unrealengine/Sky.html)
* [Watch a video tutorial](https://www.youtube.com/watch?v=hE6qFzJgED4) 




Next: <a href="/unrealengine/Deploy">Deploy</a>