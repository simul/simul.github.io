---
title: Troubleshooting
layout: unity
weight : 7
---

Troubleshooting: Unity
================


Frequently Asked Questions and Common Problems
---------------

**Performance**

* How do I make the clouds appear less pixelated? 
* Try lowering the downscale factor setting, on the trueSKY object.*


**The Sequencer and Sequences**

* I can't edit the values in the sequencer.
* Ensure your license key has been entered at the top of the sequencer, and that it is valid.*

* When I change sequences in script, how do I make the transition smooth and imperceptible? 
* Make sure that all layers in all sequences have Keyframe subdivision set to "Fixed intervals (real time)" and Update to "Gradual". To set how long it takes to transition between sequences, adjust the "Interval(s)" parameter to the desired amount of seconds. *


**Camera**

* The camera view is upside down.
* Try checking/unchecking the "Flipped View" option in the TrueSkyCamera component*. 


**Weather Effects and Celestial Objects**

* Rain drops are large and blocky.
* Try lowering the rain drop size in the 3D cloud layer.*

* The rain moves too quickly when I move the camera
* This happens when the camera is moving quite quickly. If you do not want to lower the speed of the camera's movement, then try lowering the metres per unit setting of the trueSKY object.

* The sun/moon is too big/small.
* Try altering the sun and/or moon diameter setting in the sky layer.*


**Lighting**

* It's too dark at night
* Try lowering the brightness power setting in the sky layer.*



Compatibility with other Plugins
---------------------

**CETO**

Any transparent shaders in use will need to be modified, otherwise the water may render above the clouds. In the OceanTopSide_Transparent shader, find the "Queue" tag and change it from "Transparent-1" to "Transparent-500". Find the same tag in the "OceanUnderSide_Transparent" shader and change this from "Transparent-2" to "Transparent-501".   

This will make it so that trueSKY won't be visible when underwater, so if underwater views are needed, it is advisable to write a script that changes these queue values back to their defaults when the camera is underwater. 


**Popcorn FX**

If you are using the PopcornFX plugin, you will need to set native rendering to "Before Image Effect" for it to work alongside trueSKY.



Deprecated Functions, Files and Arguments
---------------------

The following should no longer be used in trueSKY for Unity, either due to deprecation or partial implementation:

* TransparencyCamera.cs

Any function calls to modifiy cloud keyframes(GetKeyframeValue and SetKeyframeValue) should not use the following name string arguments:

* "lightning"
* "simulation"

Any function calls to modify cloud keyframers/layers (GetCloudInt, GetCloudFloat, SetCloudInt and SetCloudFloat) should not use the following name string arguments:

* "vorticityConfinement"
* "viscosity"
* "godraysSteps"
* "meetHorizon"


Further Information
-----------------

If you're still having trouble with trueSKY, please view the Unity forum thread to see if other users have encountered the issue and/or contact us directly. You can post the problem on the forum or email us directly.

* [trueSKY for Unity forum thread](http://forum.unity3d.com/threads/released-truesky-alpha-for-unity-pro-volumetric-skies-clouds-and-time-of-day.262439/)
* [Email us at: contact@simul.co](mailto:contact@simul.co)


Next: <a href="/unity/index">Home</a>