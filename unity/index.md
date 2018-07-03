---
title: Unity
layout: unity
weight : 1255
---

trueSKY alpha for Unity
================

Getting started
--------------

* Register your username at [https://simul.co/register](https://simul.co/register)
* You'll find your licence at [simul.co/account](https://simul.co/account).
* After evaluating, to get a full indie licence, head to [simul.co/account/](http://simul.co/account/). For all other licences, write to [contact@simul.co](mailto:contact@simul.co).


Installation and Initialisation
--------------

You can download the packaged trueSKY assets from [http://simul.co/download/](http://simul.co/download/). Simply import these into a your project to use.

Because the current version works only with DirectX 11, you will need to ensure your project is in DirectX 11 mode to see the rendered output. Unity should automatically select DirectX 11, but if not, you can force this by going to Edit -> Project Settings -> Player. In the Inspector, under "Settings for PC, Mac and Linux Standalone", in "Other Settings", untick "“Auto Graphics API for Windows” and drag "Direct3D 11" to the top of the list. Additionally, if you are using the PopcornFX plugin, you will need to set native rendering to "Before Image Effect" for it to work alongside trueSKY.

There is a demo scene in the folder Assets/Simul/demo.

To activate trueSKY, go to the GameObject menu, and select "*initialize trueSKY in scene*". This launches the trueSKY Setup Wizard — usually the default options will be fine. This will create:

* A Sequence asset containing sky and cloud data.
* A trueSKY object in the scene.
* A TrueSkyCamera component for the main camera. 
* A trueSKY Cubemap Probe component for the main camera.
* A SimulSun component for the Directional Light in the scene.

If there is no Directional Light, one will be created. Similarly, if there are no cameras, one can be created; if there are multiple cameras an option to assign the script to all cameras will be provided.

After initialisation, select your main Camera, and find the TrueSkyCamera component. This component has a checkbox for "Flipped View". If you are using Forward rendering (under "Rendering Path" in the Camera component), and have extra post-processing components attached and enabled, you may need to set the "Flipped View" box. This is because Unity reverses the y-component of its framebuffers when performing post-processing.

trueSKY performs best with a near clipping plane around 1m, and a far plane between 100,000 and 500,000 metres. This is because the appearance of the atmospheric effects is dependent on the numerical precision of the depth buffer.

User Interface
--------------
As mentioned above, the wizard to add trueSKY to a scene is found in the GameObject menu, under "Initialize trueSKY in scene". Just below this, you can click "Remove trueSKY from scene", to do just that. A selection of overlays and visual toggles are also provided to aid testing and debugging. These can be found under Window -> trueSKY, along with an option to recompile the trueSKY shaders.
General trueSKY properties are found by selecting the trueSKY object in the scene.
Sequence properties are found by editing Sequence assets. 

Activate licence
--------------
In order for trueSKY to work in Unity, you will need to enter your username and licence key. If you do not have a licence key, you can either sign up for a free trial or purchase a licence at www.simul.co.

To enter your licence key into Unity, follow the instructions below:

1. Load your project in Unity.
2. In the 'Hierarchy' window, select 'truesky'.
3. The inspector window will show an field for 'sequence asset'. Double click on the asset.
4. Click 'show sequencer'.
5. A new window will appear. You will see 2 fields at the top of this window where you can enter your username and licence key.

If the username and licence key are valid, trueSKY will be active on in Unity. If you are unable to validate a valid licence key, try clearing the field before trying again.


Transparencies
-----------------------
trueSKY rendering now occurs between the solid and transparent rendering in Unity. Therefore  the **TransparencyCamera** component is no longer required.

The trueSKY object
---------------
This is your connection to trueSKY within a scene. Its controls are:

**Render in Edit Mode**: Draw the trueSKY environment in the Game view from the Editor.

**Metres Per Unit**: Number of trueSKY metres per Unity unit.

**Cloud Shadowing**: The strength of the cloud shadowing effect (darkens objects beneath clouds).

**Shadow Sharpness**: How much to sharpen cloud shadows.

**Threshold Distance**: Heuristic threshold for depth downscaling (optimal values between 0.1 and 2.0).

**Cloud Steps**: Number of raytracing steps to use; more = higher definition, fewer = faster.

**Downscale Factor**: Resolution at which to render the clouds; higher numbers = lower resolution.

**Amortization**: Amortization of scattering volume generation for clouds.

**Atmospherics Amortization**: Amortization to use for generating atmospherics tables.

**Depth Blending**: If true, uses depth-blending for clouds. If false, clouds are drawn behind or in front of scenery, depending on altitude.

**Sequence Asset**: The asset containing sky sequence data. Double-click this to edit the sky sequence.

**Time**: Time in days, so 0.5 would be midday on the first day, etc.

**Speed**: Determines how quickly Time changes when in-game.

**Sim Time Rain:** If true, rain falls at simulation speeds (and even faster if time is progressing more quickly). If false, rain falls relative to real time.

**Cosmic Background**: Image for use as the cosmic background.

**Moon Texture**: Texture to be applied to the moon.

**Find Constellation**: Find a star constellation at given coordinates.

**GPU Level**: Sets depth of profiling tree for GPU.

**CPU Level**: Sets depth of profiling tree for CPU.

**Profiling**: If true, enables CPU and GPU profiling for trueSKY. The results will be updated every few frames, and shown in the text area beneath the "Profiling" checkbox. 


The Sky Sequence
---------------

To control the sky properties from within the Editor, you can edit the sequence asset. This will usually be in the same directory as your scene, with a Simul "S" icon, and named [scene name]_sq. Click on this asset to launch the Sky Sequencer. Then:

Select the Properties tab or the Map. Click a keyframe to edit its properties. Double-click a line to edit all the keyframes in that line. Click on the title text to the left to edit the properties of the whole layer (sky or clouds).

Read more about editing Sky and Cloud properties on [The Sky Sequencer Page](https://docs.simul.co/reference/man_8_sequencer.html).


Fixing Time-of-Day
------------------

Sometimes, you might not want a day-night cycle or changing time-of-day, but still want the clouds to move and weather to change over time. To do this, you can uncouple keyframe time (the position of a keyframe on the timeline) from daytime.

Edit the Sequence asset by clicking on it in the Project window. Select the Sky (click on the word "Sky" at lower left) and uncheck "*Link Keyframe time and daytime*".

<a href="https://docs.simul.co/unity/images/FixingDaytime1.png"><img src="https://docs.simul.co/unity/images/FixingDaytime1.png" alt="index"/></a>

Now, select all the Sky keyframes (box-select or double-click). Under "Sun and Moon", change the "daytime" of the keyframes to be the same value (e.g. 06:45 below). Now time and time-of-day are uncoupled.
 
<a href="https://docs.simul.co/unity/images/FixingDaytime2.png"><img src="https://docs.simul.co/unity/images/FixingDaytime2.png" alt="index"/></a> 


Further Information
---------

* [trueSKY Tutorial: Unity](https://docs.simul.co/unity/Tutorial.html)
* [The Sequencer](https://docs.simul.co/reference/man_8_sequencer.html)
* [Scripting in trueSKY for Unity](https://docs.simul.co/unity/Scripting.html)
* [The trueSKY Renderer](https://docs.simul.co/reference/man_4_rendering.html)


Next: <a href="/unity/Tutorial">Tutorial</a>