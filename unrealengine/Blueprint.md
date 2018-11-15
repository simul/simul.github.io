---
title: Blueprint
layout: unreal
weight : 3
---

trueSKY in Blueprint
====================

The trueSKY Blueprint macros provide a wide array of functionality while your game is playing or simulating. These macros will not take effect unless you are in one of these modes. To permanently change the properties of a light, start simulating, and right-click your Directional Light, then select "Keep Simulation Changes".


The TrueSky Sequence Actor
--------------------------

The values of the Sequence Actor itself can be changed via Blueprint. To Get and/or set these values, make a reference to the TrueSkySequenceActor and drag the output pin onto an empty space and either search for a value directly or navigate to Class-> TrueSkySequenceActor.

Time of Day & Lighting
----------------------

### Time of Day
Ultimately, the entirety of your environment depends on what you choose for your time of day and how (and if) you advance that time throughout gameplay. For the trueSKY sequence simulation, time is measured as a value in the range of [0,1]  (ie, an entire day from midnight to midnight the following day). If you just leave the time at 0.0, it's going to be dark. Because it's night time. So, now is the, ahem, *time* to ensure you're setting the time. You can do this directly on the TrueSkySequenceActor instance in your scene or, even better, you can drive that time value through C/C++ or Blueprint to allow for the full day-night cycle to rock your digital world.

You won't want to just take the `FrameDelta` and use it to modify the time of day. Days would go by in, *literally*, seconds. So, you'll want to modify that value by some scalar (what that is just depends on how long an in-game day should last in your context). Or maybe you don't want to alter the time of day at all, in which case you can just ignore the time of data value outside of setting its initial value.

For additional information on the time of day's role in the trueSKY simulation, you can [view a more hands-on tutorial here](https://docs.simul.co/unrealengine/Tutorial.html).

NOTE: It's also important to ensure that, even if you just set the time value initially, that you update your directional light using the following method:

### Cloud Shadows
Connect the CloudShadow asset in the TrueSky folder to "Cloud Shadow RT" on your trueSKY Sequence Actor, and connect the M_LightFunction asset to "Light Function Material" on your Directional Light. Now the clouds will cast shadows correctly.

### Point Lights
Additionally, point lights can be used to illuminate the clouds. Because of the relative scale of clouds to the UE4 scene, the intensity of the light must be very large in order to have a visible effect.
 
![alt text](https://docs.simul.co/unrealengine/images/SetPointLight.png "Blueprint nodes for setting a point light reference.")

If you do not have a PointLight actor, you can use SetPointLightSource to individually apply the position, colour and intensity of a light to the clouds.

### TrueSkyLight Actor
For ambient lighting, add a TrueSkyLight actor to your scene. The TrueSkyLight is very similar in functionality to the standard UE4 sky light, so it brings those same other features that the UE4 skylight provides (ie, distance field ambient occlusion and such).

As such, the TrueSkyLight replaces the standard ASkyLight/USkyLightComponent and automatically updates ambient lighting based on the settings that you have set (such as spreading changes in the sky light over `x` number of frames).

### Cloud Shadows
The shadows of clouds can be applied to your directional light object using the M_LightFunction in the Content/TrueSky directory of your project. If you modify this function, make a copy of it with a different name, otherwise it will be overwritten when the plugin next starts (this applies to all the content in the TrueSky folder).

![alt text](https://docs.simul.co/unrealengine/images/LightFunction.png "Setting up the lighting function in your Directional Light settings.")

### Physical Units (trueSKY 4.1 onward)
trueSKY is a physically-based renderer, which means that the light and colour values generated correspond to true physical properties. The pixel colours rendered to a view are spectral radiance values. However, to keep the numbers from getting too high or low, a global adjustment is applied. This is because numerical accuracy would be lost, particularly for very dark night-time scenes, if we kept the same scale at all times. The Sky property "Brightness Power" controls this adjustment - if equal to one, there is no adjustment. Values smaller than one reduce the range of outputs - brightening dark skies and dimming very bright skies. To obtain the current value of the multiplier, use the Blueprint function "GetReferenceSpectralRadiance". Then you can use the calculation:

	spectral radiance (watts/square metre/steradian/nm) = pixel value * reference spectral radiance

You can use this value to calibrate the other lights in your scene. Say you have a point light representing an electric bulb. The brightness of this light would in reality be constant. But because trueSKY adjusts the physical value of a pixel as time passes, you must compensate for this by scaling the intensity of the bulb by the inverse of the reference radiance.

![alt text](https://docs.simul.co/unrealengine/images/ReferenceSpectralRadiance.png "Using the spectral radiance value to modulate the intensity of lights in the scene.")

So the light appears to get brighter as day turns to night. You can get the same effect using Unreal's Eye Adaptation (Auto Exposure). But because this is a post-process effect, it cannot cope with very dark scenes - you may see banding in the sky colours due to the low numerical accuracy of very small numbers.

![alt text](https://docs.simul.co/unrealengine/images/DayLightRadiance.png "Spectral radiance example: Midday.")
![alt text](https://docs.simul.co/unrealengine/images/SunsetLightRadiance.png "Spectral radiance example: Sunset.")
![alt text](https://docs.simul.co/unrealengine/images/NightLightRadiance.png "Spectral radiance example: Night.")


### The Sky and Clouds 
Both the sky and clouds can be accessed and edited in Blueprint.  

Read more about [editing the sky here](https://docs.simul.co/unrealengine/Sky.html) and [editing the clouds here](https://docs.simul.co/unrealengine/Clouds.html).


### Transparency
To correctly affect transparent objects, trueSKY will write loss, inscatter and cloud transparency textures once per frame. Connect the textures from the (automatically created) trueSky folder, to the texture properties in the trueSKY Sequence Actor to enable this.

![alt text](https://docs.simul.co/unrealengine/images/TrueSkyRenderTargets.png "Setting up the appropriate render target references in the TrueSkySequenceActor settings.")

In a material that uses transparency, insert the trueSKYTransparencyModifier function between the inputs and the final output node:

![alt text](https://docs.simul.co/unrealengine/images/Transparency.png "Using the trueSKYTransparencyModifier material function to modulate the material output values.")

### Queries
To test how much cloud (from 0 to 1) is at a specified point, use the function CloudPointTest. **Note**: The Query Id can be set to any integer value, but should differ from any Query Ids used in seperate queries (or else they will be overwritten).

![alt text](https://docs.simul.co/unrealengine/images/CloudPointTest.png "Sample usage of the Cloud Point Test functionality.")

To test if there is cloud between two points, use CloudLineTest:

![alt text](https://docs.simul.co/unrealengine/images/CloudLineTest.png "Sample usage of the Cloud Line Test functionality.")
 
### Layer Properties
To set a layer property Blueprint, use the functions below. The following will need to be prefixed onto the property's name string: "sky:", "clouds:" or "2dclouds:", depending on the layer in use. E.g., to set the 2D cloud layer's noise period to 3.5, the SetFloat function would be called with "2dclouds:noisePeriod" as the Name parameter, and 3.5 as the Value parameter.

* `GetInt (String Name):` Gets the specified integer property for the prefixed layer.
* `SetInt (String Name, int Value):` Sets the specified integer property for the prefixed layer to the given value.
* `GetFloat (String Name):` Gets the specified float property for the prefixed layer.
* `SetFloat (String Name, float Value):`  Sets the specified float property for the prefixed layer to the given value.

For information about the layer properties you can change and the name strings needed to do so, see the [Cloud](https://docs.simul.co/unrealengine/Clouds.html) and [Sky](https://docs.simul.co/unrealengine/Sky.html) pages.


### Keyframe Properties
To set a keyframe's value from Blueprint, use the SetKeyframeFloat, or SetKeyframeInt functions. You must pass the keyframe's integer uid, the name of the property as a string, and the value. Similarly, GetKeyframeFloat and GetKeyframeInt are used to obtain current values. 

There are multiple functions provided to get the uid required to modify a keyframe. However, if the cloud keyframer's Update property is set to "Instant", you will need to use `GetNextModifiableCloudKeyframe(int Layer)` function to get the next uid that can be modified without recalculation. If the Update property is instead set to "Gradual", any keyframe can be modified at any time, and the functions below can be used to return the uids required for setting and getting keyframe values. Note: For clouds, the correct layer parameters are 1 for 3D and 2 for 2D.

* `GetCloudKeyframeByIndex (int Layer, int Index):` To get an identifier for the cloud keyframe at the specified layer and index, returns 0 if out of range. 
* `GetNextCloudKeyframeAfterTime (int Layer, float T):` Get an identifier for the next cloud keyframe at or after the specified time T. 
* `GetPreviousCloudKeyframeBeforeTime (int Layer, float T):` Get an identifier for the last cloud keyframe before the specified time T. 
* `GetSkyKeyframeByIndex (int Index):` Get an identifier for the cloud keyframe at the specified index. Returns 0 if there is none at that index (e.g. you have gone past the end of the list). 
* `GetNextSkyKeyframeAfterTime (float T):` Get an identifier for the next cloud keyframe at or after the specified time T. 
* `GetPreviousSkyKeyframeBeforeTime (float T):` Get an identifier for the last sky keyframe before the specified time T.


### Driving trueSKY's Simulation through In-Scene Sun and Moon Data 
![alt text](https://docs.simul.co/unrealengine/images/SetFromSunAndMoon.png "Driving trueSKY through in-game actors/components, instead of the standard trueSKY-driving in-game actors/components.")

In a reversal of the default setup, SetSunRotation and SetMoonRotation can be used to drive the trueSKY sun and moon directly from a direct light source (or some other object). In order to user this feature, it is recommended to set the Interpolation Mode property of the trueSky Sequence Actor to "RealTime". This is so that any changes to the sun and moon direction will affect the trueSKY atmospherics regardless of whether game time is changing, and so that slight or slow changes in sun direction will not cause a per-frame recalculation of the atmospheric tables.

In addition to these Set functions for the sun/moon rotation, there are also Get functions for sun/moon rotation, colour and intensitiy. Additionally, you can Get/Set the texture of the moon in Blueprint.

![alt text](https://docs.simul.co/unrealengine/images/GetSetMoonTexture.png "Change the moon texture at runtime in blueprint.")


### Precipitation and Lightning
There are Blueprint functions provided to test a scene for lightning and for rain. For lightning, the "Get Lightning" function will provide the start position, end position, colour and magnitude of any lightning present. A magnitude of 0 means there is no lightning present. Additionally, the "Get Rain At Position" function will take a given position and return a float between 0.0 and 1.0 indicating the strength of the rain (or snow) at this position.

![alt text](https://docs.simul.co/unrealengine/images/LightningRainTest.png "Example of testing the weather conditions in blueprint.")


### Managing Sequences
Though you can only set the active sequence in the editor, it is possible to change the sequence in use mid-game using Blueprint. To do this, create a reference to your TrueSkySequenceActor in Blueprint, then drag the output pin onto the canvas. In the Action List, search for and select "Set Active Sequence". Repeat for as many sequences as you wish and connect them to relevant events. 

![alt text](https://docs.simul.co/unrealengine/images/SetActiveSequence.png "Example of how to change the active trueSKY sequence at runtime in blueprint.")

You can also get the active sequence in Blueprint. Similarly, just drag the output pin of your TrueSkySequence actor onto the canvas and search for and select "Get Active Sequence". This will return the Sequence Asset in use. 

![alt text](https://docs.simul.co/unrealengine/images/GetActiveSequence.png "Example of how to query the active trueSKY sequence at runtime in blueprint.")


### Measuring Performance
trueSKY has a built-in profiler for GPU and CPU performance. Use "Get Profiling Text" to obtain the values, with the inputs "cpu_level" and "gpu_level" to determine how far down the call tree to display.

The outputs are in milliseconds.

![alt text](https://docs.simul.co/unrealengine/images/GetProfilingText.png "How to retrieve profiling text.")


### Further Information
* [The Sequencer](https://docs.simul.co/sequencer.html)   
* [The Clouds in trueSKY for UE4](https://docs.simul.co/unrealengine/Clouds.html)
* [The Sky in trueSKY for UE4](https://docs.simul.co/unrealengine/Sky.html)
* [Watch a video tutorial](https://www.youtube.com/watch?v=hE6qFzJgED4) 


Next: <a href="/unrealengine/Deploy">Deploy</a>