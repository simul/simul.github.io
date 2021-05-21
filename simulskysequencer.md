---
title: Simul Sky Sequencer
layout: reference
weight: 45
---



Simul Sky Sequencer
--------------------

Simul Sky sequencer is used to generate .sq files for use within projects that have integrated the SDK. It features all settings and variables found within the Unreal / Unity sequencers.


Launching the Sky Sequencer
---------------------------

The Sky sequencer can be downloaded from the [downloads section of the site.](https://simul.co/downloads/#skysequencer)

Once downloaded, follow through the install wizard, and install into your desired location. The application will prompt you to launch upon completion of installation.

The location to open is C:/Simul/build/bin/Release/SkySequencer_MD.exe 


Presets
--------

There are a selection of presets available with the Sky sequencer. To load these navigate to File -> Load 
The presets will be found within C:/Simul/Applications/SkySequencer/Presets

This will load a pre-made sequence with keyframe settings. 

* Current presets available are:
* Cirrocumulus
* Cirrus
* Clear sky
* Cumulus
* Fog
* StratoCumulus
* Stratus


Navigation
------------

By default opening the SkySequencer will look like this:

Re-arranging the Skysequencer to fit your work style is simple and easy to do. Here is a quick video covering initial rearrangement to a more standard layout, as well as a basic controls overview.


<div class="video-wrapper">
<div class="video-container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/Hq7Z20VUhHI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
</div>


If following the above video, you will now be able to navigate easily through each tab as you desire, their functionality is outlined below.

Properties navigation is covered in the latter half of the video and I will describe in more detail here. There are 3 distinct sections you can work in, the keyframe properties, accessed by clicking on either a cloud or sky keyframe within the Keyframer. Layer properties, accessed by clicking on a cloud or sky layer in the keyframer. And finally the global properties, which can be accessed by clicking on any empty space within the keyframer (including the Time tab).


You will begin to see a lot of similarities to that of the Sequencers supplied with our Engine Plugins. All of the information for these plugins is directly transferable to the SkySequencer, however certain settings may be in slightly different locations (most notably any setting on the trueSKY actor/object will most likely be within the Skysequencers global settings).

[This page should help you understand trueSKY's time, keyframes and layers information if you are new to trueSKY.](/tutorials/sequencer/keyframes.html)


Windows Functionality
---------------------


All windows are movable and dock-able anywhere in the skysequencer, and can be closed if not in use. These can be reopened simply by navigating to the Window drop down on the top bar, and selecting the window you wish to reopen.


**Keyframer:** This is where we add keyframes to the time-line, as well as access the sky and cloud layers. Has time controls, such as the time multiplier and the time scrubber.

**Properties:** This covers the settings and properties of the selected keyframe or layer. When no layer is selected it will show general scene settings as well as API options and global settings.

**Performance:** Shows a variety of performance metrics and breakdowns - this information can compliment information gained from the use of on-screen displays

**Screenshot:** Allows setting of resolution of screenshot, then saves an image of your scene.

**Clouds:** Gives an overview of the noise textures used to generate the clouds as well as some MIP information and a brief overview of some of the cloudconstants settings.

**Cloud Window:** Allows control of the Latitude and Longitude of the scene, as well as shows the location of keyframes - position of the scene on the globe, and a summary view of the current clouds in the scene from a top down view.

**Viewport:** Shows the current view of the scene. The Scroll wheel will increase or decrease the FOV of the camera, holding right click and moving the mouse looks around, Alt + Right click and movement alters the camera angle. WASD for movement around the scenes (camera speed can be altered within the global properties)





Saving and Loading Files
------------------------------

Saving a .sq file for use within your SDK scene is simple and easy, navigate to File -> Save as then save the .sq into the desired location.

If your project requires .seq files rather than .sq then rather than using save as, use File -> Export as Binary, which will then save out as .seq.

Loading a .sq files is a simple as navigating to file -> load and locating the desired .sq file. Presets can be accessed to this as mentioned above in this page.

Loading a .seq file is similar, just opt for "load binary sequence".


Note - When saving a .sq only layer and keyframe data is saved to the file, this means that any global settings will need to be manually set within your code to be able to fully match the results being shown in the Skysequencer viewport.

Information on SDK implementation can be found [here](/sdk.html)


Common Questions
------------------------------

My clouds appear incredibly bright:

There are a few different solutions to this. Adjusting the Exposure setting within the global settings, or adjusting the lighting settings of the directional light and indirect lighting to the clouds.


My clouds appear low resolution:

Within the global settings you can adjust the overall cloud resolution. In most use-cases 512 or 1024 should suffice.
Alternatively adjusting the edge noise wavelength and size may increase fidelity of the clouds, which can also be found in the global settings. Notably this setting with not carry across when saving a .sq file and will need to be set manually within the engine as mentioned in the "saving and loading" section.
