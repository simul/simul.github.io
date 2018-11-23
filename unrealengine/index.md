---
title: Unreal
layout: unreal
weight : 1250
---

trueSKY for Unreal Engine 4
================

Before you begin
----------------
Please first ensure that trueSKY supports the platforms and API's that you need.

| x64 (D3D11) | x64 (D3D12) |  x64 (Vulkan) | x64 (OpenGL) |PS4 | Xbox One (D3D11) | x64 (D3D12) | Switch       |      OSX     |
|:-----------:|:-----------:|:-------------:|:------------:|---:|:----------------:|:-----------:|:------------:|:------------:|
|      ✓      |      ✓     |       x       |       x      | ✓  |    ✓            |    ✓        |    ✓         |       x      |


Getting started
--------------

* Register your username at [https://simul.co/register](https://simul.co/register)
* You'll find your licence at [simul.co/account](https://simul.co/account).
* After evaluating, to get an indie licence, you can buy or subscribe at [simul.co/account](https://simul.co/account). For all other licences, write to [contact@simul.co](mailto:contact@simul.co).

# Installing the Plugin
For binary installations of Unreal Engine, binary trueSKY plugin installers are available from [https://simul.co/download](https://simul.co/truesky/download). For other versions, or if you have a version of Unreal Engine built from source, you will need to build the plugin. [**For GitHub/Engine Source Integration, check this page**](https://docs.simul.co/unrealengine/source.html).

**Important**
The stock binary version of Unreal does not deploy trueSKY files when packaging a project. You will see a black sky unless you deploy these files. See [Deployment](/unrealengine/Deploy) for instructions.

# Running the Plugin
* Run UE4, either standalone or with the debugger.
TrueSkyPlugin loads `TrueSkyUI_MD.dll` and `TrueSkyPluginRender_MT.dll` from `[UE4]\Engine\Binaries\ThirdParty\Simul\Win64`.

When you run the UE4 editor, the trueSKY plugin should be enabled by default. If not, open up the Plugin Configurator for Unreal Engine (from the menu bar: **Edit->Plugins**). In the plugin configuration window and type "trueSKY" into the search box to find the plugin; check the "Enabled" box to enable it.

[![alt text](https://simul.co/wp-content/uploads/2014/07/UE4_ShowPlugins-96x300.png "Opening the Plugin Configurator for Unreal Engine (from the main menu bar: Edit->Plugins).")](http://simul.co/wp-content/uploads/2014/07/UE4_ShowPlugins.png)

[![alt text](https://docs.simul.co/unrealengine/images/EnableTrueSKY.png "Enabling the trueSKY Plugin in Unreal Engine 4's editor.")](https://docs.simul.co/unrealengine/images/EnableTrueSKY.png)

If you had to change the "Enabled" setting from disabled to enabled (or vice versa), you'll need to restart the editor for the change to take effect, as with all editor plugin changes.

# Adding trueSKY to Your Level

## Precautions
* Most UE4 maps contain a Sky Sphere and Atmospheric Fog:
	* **Delete the Sky Sphere object** -- The Sky Sphere will actively obscure aspects of the trueSKY rendering system, as it's basically a giant ball of geometry with a texture applied; you'll want to delete this object.
	* **Delete any Atmospheric Fog object** -- Having Atmospheric Fog will not *break* anything, per se, but given that trueSKY provides a more detailed and physically-accurate atmospheric rendering solution, it can serve as a complete replacement.

## Adding the trueSKY Sequence Actor
The trueSKY Sequence Actor is the primary way to access and interact with the trueSKY renderer and its rendered sky sequence within Unreal Engine 4. You can add this actor from the standard "Place" sidebar in the editor, choosing "All Classes", typing "trueSKY", and choosing the "True Sky Sequence Actor" to drag into your scene, or you can use this handy little shortcut:
* From the menu bar, use: "Window->Add Sequence to Scene"
	* This adds the default True Sky Sequence Actor to the current level at the map's origin (though its location doesn't matter -- its rotation, however, does).

 <a href="http://simul.co/wp-content/uploads/2014/07/UE4_AddSequence.png"><img src="http://simul.co/wp-content/uploads/2014/07/UE4_AddSequence-81x300.png"/></a> 

Once you have the True Sky Sequence Actor in your scene, choose it from "World Outliner" window. Then, to customize it, open up the "Details" window/sidebar; set the reference to an existing **TrueSky Sequence Asset** in the "Active Sequence" dropdown. By default, there are two sample sequences you can instantly check and see the results for yourself:

* `TrueSkySequenceCumulus` -- A prototypical cumulus cloud pattern (with a 3D and 2D cloud keyframe for example purposes).
[![alt text](https://docs.simul.co/unrealengine/images/ue4_samplesequence_cumulus.png "Screen shot of the sample cumulus sky sequence in Unreal Engine 4.")](https://docs.simul.co/unrealengine/images/ue4_samplesequence_cumulus.png)

* `TrueSkySequenceStratus` -- A prototypical stratus cloud system; i.e. there's a rain/snow comin' (with a 3D and 2D cloud keyframe for example purposes).
[![alt text](https://docs.simul.co/unrealengine/images/ue4_samplesequence_stratus.png "Screen shot of the sample cumulus sky sequence in Unreal Engine 4.")](https://docs.simul.co/unrealengine/images/ue4_samplesequence_stratus.png)

### Creating New Sky Sequences
To create a new TrueSkySequence asset, go to the "Content Browser" window. Press "New Asset" button (or do a right mouse click inside the window) to open an asset selection window. Choose "Miscellaneous / trueSKY Sequence Asset". A new asset will be created. Now you can rename/save/delete it.

<a href="http://simul.co/wp-content/uploads/2014/07/UE4_CreateAsset.png"><img src="http://simul.co/wp-content/uploads/2014/07/UE4_CreateAsset-233x300.png"/></a> 

In the World Outliner, select your trueSKY sequence actor, and in the Details panel, set its Active Sequence to be the newly created asset: 
 
<a href="http://simul.co/wp-content/uploads/2014/07/Clipboard-Image-8.png"><img src="http://simul.co/wp-content/uploads/2014/07/Clipboard-Image-8-150x150.png"/></a> 

To edit the TrueSkySequence asset just double-click on it:

<a class=" id=" title="" href="http://simul.co/wp-content/uploads/2014/07/Editor.png"><img src="http://simul.co/wp-content/uploads/2014/07/Editor-150x150.png" /></a>

This will open up the True Sky Sequence Editor:

### Creating and Configuring a Sky Sequence
* Enter your licence key in the Sequencer Window. This enables the window's editing functions. The Sequencer will contact the Simul licence server, and if successful the Sequencer will print an "OK" message.

* You can see changes to the properties (e.g. "preview") only if the edited asset is also assigned to the level's TrueSkySequenceActor. The trueSky plugin renderer uses only the asset which is referenced from that actor. If you are editing some other asset (which is not assigned to the TrueSky actor of the current level) then you won't see any visualization of it.

* You can edit any number of TrueSkySequence assets at once. However, only that which is also assigned to the active TrueSkySequenceActor is visible in the editor rendering window.

* To add clouds, double-click the trueSKY Sequence Asset and right-click on the timeline to add cloud keyframes.

* For real-time ambient lighting and reflections, replace the default SkyLight Actor with the TrueSkyLight (found in Modes -> All Classes). Simply drag it into the scene to use. 

### Multiple Sequence Actors and Transitions
TrueSKY supports three different modes of update. In Game-Time mode, it takes a specified amount of time in game hours. The weather won't change if game time does not. Fixed Intervals mode is similar, only there's a specific number of interpolated intervals between any two keyframes. You can use this mode to create more detailed transitions around sunrise/sunset for example.

If you're using real-time transition, you can adjust the Interval in seconds to determine how quickly the change takes place.

<a href="https://docs.simul.co/unrealengine/images/Interpolation.png"><img src="https://docs.simul.co/unrealengine/images/Interpolation.png" alt="Interpolation"/></a>

In all cases, the number of Subdivisions controls how finely the interpolation is performed. It's the number of intermediate steps between keyframes (for Fixed Intervales), or in the Game Time or Real Time period specified.

Performance
---------
Use the Blueprint function GetProfilingText to get GPU and CPU timing numbers for trueSKY as a tree.
trueSKY performance is highly dependent on your choice of settings. Once you have good settings for a given target hardware setup, performance will be consistent - i.e. there won't be spikes or hitches. For PC, you may want to make some of these settings controllable for the end user. For console hardware, it is usually best to choose the settings based on your target GPU time for skies, then lock them down.

#### Sequence Actor Settings

* **Max Resolution**: This is the cubemap resolution that we render clouds into. A lower value will be faster to render. Too low, and clouds may appear blocky. A good value tends to be:
	* **512** -- Likely the optimal resolution for *most* use-cases; it tends to be the best mix of memory consumption/performance and rendering sharpness/clarity for general use.
	* **256** -- This is a decent resolution that is faster and uses less memory than 512, but is not quite as sharp and clear. 
* **Amortization**: This is a measure of how cloud rendering is spread across multiple frames. A value of 1 means all pixels are rendered every frame.


Further Information
---------

* [trueSKY Tutorial: Unreal Engine 4](https://docs.simul.co/unrealengine/tutorial.html)
* [trueSKY from GitHub (and UE4 Source Integration)](https://docs.simul.co/unrealengine/source.html)
* [trueSKY in Blueprint](https://docs.simul.co/unrealengine/blueprint.html)
* [The Sky Sequencer](https://docs.simul.co/sequencer.html)
* [The trueSKY Renderer](https://docs.simul.co/rendering.html)


Next: <a href="/unrealengine/Tutorial">Tutorial</a>