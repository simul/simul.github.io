---
title: Troubleshooting
layout: unreal
weight : 8
---

Troubleshooting: Unreal
================


Frequently Asked Questions and Common Problems
---------------

**Installation and Compilation**

* **When packaging the game, I get errors and/or the screen is black.**
<br>If you are using the binary installer, then you will need to follow some additional steps to be able to package your game with trueSKY. You can read about this [here](https://docs.simul.co/unrealengine/Deploy.html). 


**Performance**

* **trueSKY is taking too many milliseconds to render a frame. How can I reduce this value?**
<br>With default settings, the cost of trueSKY should be between 2 and 4 ms per frame. If this is not being achieved or in the use case, speed is a higher priority than visual performance, then this can be improved by altering the Amortization, Atmospherics Amortization and/or Downscale Factor settings in the details panel of the trueSKYSequenceActor. To aid the measurement of performance, trueSKY also provides profiling information (Windows -> Overlays -> Profiling or use the GetProfilingText function in blueprint).

* **How do I make the clouds appear less pixelated?**
<br>Try increasing the Maximum Resolution setting, in the details panel of the trueSKYSequenceActor.

* **the trueSKY binary plugin is not working correctly.**
<br>Try deleting the plugin folder Engine/Plugins/TrueSkyPlugin and the plugin binaries Engine/Binaries/ThirdParty/Simul. Then re-install the latest version of the plugin.

* **How do I make the clouds move independently of time-of-day?**
<br>Call the Blueprint function **SetBool** with the name "clouds:overrideWind" and the value *true*.

**Behaviour**

* **On PS4 there is an apparent "trail" in the sky as the camera moves**
<br>The Unreal Engine screen clear is faulty in some versions: the Hardware Clear option does not work. To fix this, go to Project Settings -> Rendering -> Optimization and change "Clear Scene" to "Clear at Far Plane".

**The Sequencer and Sequences**

* **The sequencer won't initialize, I get an error that the application failed to start because it could not find the Qt platform plugin "windows".**
<br>The Houdini Engine plugin uses an incompatible version of the Qt widget system, please deactivate this plugin to enable trueSKY.

* **I can't edit the values in the sequencer.**
<br>Ensure your license key has been entered at the top of the sequencer, and that it is valid.

* **When I change sequences in blueprint, how do I make the transition smooth and imperceptible?**
<br>Make sure that the Sequence Actor's Update option is set to "Real Time". To set how long it takes to transition between sequences, adjust the "Interval(s)" parameter to the desired amount of seconds.

<br>In trueSKY 4.1, you should make sure that the 3D Clouds, 2D Clouds, and Sky properties are the same for all sequences.
Then, with cloud keyframes, make sure that any property that has horizontal extension is the same: Cloud Volume Width, Noise Scale, Worley Scale.

<br>So for example if your 2D cloud keyframes have width 1000.0 in one sequence, they should have 1000.0 in all sequences. It doesn't have to be exact, and some variation will be ok. But if there's more than about 10% change over a few seconds of transition time, you'll notice it resizing, and that will look wrong.


**Weather Effects and Celestial Objects**

* **Rain drops are large and blocky.**
<br>Try lowering the rain drop size in the 3D cloud layer.

* **The rain moves too quickly when I move the camera.**
<br>This can happen when the camera is moving quite quickly. If you do not want to lower the speed of the camera's movement, then try lowering the trueSKYSequenceActor's metres per unit setting.

* **The sun/moon is too big/small.**
<br>Try altering the sun and/or moon diameter setting in the sky layer.


**Lighting**

* **It's too dark at night.**
<br>Try lowering the brightness power setting in the sky layer.

* **Objects are light too brightly, especially at night.**
<br>Try disabling Global Illumination, or set Indirect Lighting Intensity to a small vale (e.g. 0.001) on the PostProcessVolume.

* **The sun is flickering.**
<br>This may be caused by how UE4's postprocessors deal with large brightnesses, along with the small pixel size of the sun. To get around this, we've introduced MaxSunRadiance as a property of the Sequence Actor. When sun radiance goes past this value, the size of the drawn sun is increased, and the radiance decreased, so that the overall energy is kept constant, but the output brightness reduced. Additionally, if you haven't already, try deleting the default Atmospheric Fog and Sky Sphere actors.

* **The sun isn't moving.**
<br>Ensure that you are driving the sun via blueprint. Please see [here](https://docs.simul.co/unrealengine/Blueprint.html) for information on how to do this.

* **The sun is too bright.**
<br>Post process volumes can cause issues with trueSKY. Try lowering the intensity of the volume's bloom setting.



Deprecated Functions, Files and Arguments
---------------------

The following should no longer be used in trueSKY for UE4, either due to deprecation or partial implementation:

trueSKYSequenceActor's Downscale Factor setting is deprecated: use Maximum Resolution instead.

Any function calls to modify cloud keyframes(GetKeyframeValue and SetKeyframeValue) should not use the following name string arguments:

* "lightning"
* "simulation"

Any function calls to modify cloud keyframers/layers (GetCloudInt, GetCloudFloat, SetCloudInt and SetCloudFloat) should not use the following name string arguments:

* "vorticityConfinement"
* "viscosity"
* "godraysSteps"
* "meetHorizon"


Further Information
-----------------

If you're still having trouble with trueSKY, please view the trueSKY thread on the Unreal forum to see if other users have encountered the issue and/or contact us directly. You can post the problem on the forum or email us directly.

* [trueSKY for UE4 forum thread](https://forums.unrealengine.com/showthread.php?33944-RELEASED-trueSKY-Alpha-for-UE4-Complete-Sky-and-Weather-System/)
* [Email us at: contact@simul.co](mailto:contact@simul.co)


Next: <a href="/unrealengine/index">Home</a>