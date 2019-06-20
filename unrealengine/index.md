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
|      ✓      |      ✓      |   ✓ UE 4.22   |       x      | ✓  |       ✓          |     ✓       |    ✓         |       x      |


Getting started
--------------

* Register your username at [simul.co/register](https://simul.co/register)
* You'll find your licence at [simul.co/account](https://simul.co/account).
* After evaluating, to get an indie licence, you can buy or subscribe at [simul.co/account](https://simul.co/account). For all other licences, write to [contact@simul.co](mailto:contact@simul.co).

# Installing the plugin
This page shows you how to install the binary version of trueSKY onto your existing binary UE installation. For other versions, or if you have a version of Unreal Engine built from source, you will need to build the plugin. [For GitHub/Engine Source Integration, check this page](https://docs.simul.co/unrealengine/source.html).

* Step 1: Login or register for an account with [simul.co](https://simul.co/account).

* Step 2: Download trueSKY binary installer from [simul.co/downloads](https://simul.co/downloads).

* Step 3: Run the installer, ensuring that the correct directory is selected on your local machine. After the installation process is complete, the plugin should be installed into your UE directory.

### Running the binary plugin

* Step 1: Launch 'Epic Games Launcher' and start 'Unreal Engine'.

* Step 2: Click on the 'Edit' dropdown menu at the top of the window and click 'plugins'.

* Step 3: A new 'Plugins' window will appear. Use the search box to find 'trueSKY' and then click enable.

* Step 4: You will be prompted to restart 'Unreal Editor'. Click 'restart now'.

Now trueSKY is installed.

### Adding trueSKY to Your Level

* Step 1: Launch your scene in 'Unreal Engine'.

* Step 2: Click the menu option 'window' in the top menu bar and click 'initialise trueSKY'.

* Step 3: A popup window will appear. Click initialise. 

The installer will automatically perform the following actions to enable trueSKY in your scene. 

- Delete Atmospheric Fog actors
- Delete BP_Sky_Sphere
- Add trueSKY Sequence Actor
- Add trueSKYLight

You should now see the sky appear in your scene.

* Step 4: Activate your trueSKY licence within UE4 using the following steps. Failure to do this will result in trueSKY not working.

### Activate your trueSKY licence

To ensure trueSKY works, you will need your user name & licence key. These can be found in your account dashboard at simul.co/account. 

* Step 1: Login to your account at simul.co and click my account. 

* Step 2: Your username is at the top left, on the second line, underneath your name. Please note this down.

* Step 3: Your licence key is in your account dashboard. Please note this down also.

* Step 4: Launch your game/scene in UE4.

* Step 5: Select the 'TrueSkySequenceActor' in the 'World Outliner' window.

* Step 6: In the 'details' window, use the search to find 'true sky'.

* Step 7: In the results, find the 'Active Sequence' property and double click the icon. A new window will appear.

* Step 8: In the new widow, enter your username and licence key under 'registration'. If the details are correct, you will see the text 'OK' displayed under the licence key fields.

trueSKY should now be fully working in your scene.

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