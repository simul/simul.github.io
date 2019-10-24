---
title: Standalone Sequencer
layout: reference
weight: 500
---




Standalone Sequencer Window
====================

The Sky Sequencer is a tool for artists, technical artists, level designers, 
and mission planners. It also helps programmers to understand the workings of trueSKY's sky, 
clouds and time-of-day systems. Use the sequencer to design and test settings, and to create time-sequences of weather states that can be loaded into your final program.

The standalone Sequencer can be downloaded from [here](https://simul.co/downloads/) under the Sky Sequencer Tab.

To launch the Sequencer, launch the Sky Sequencer Executable that was installed in your designated directory. 

The features in the standalone sequencer are very similar to those within the plugin or SDK versions, however there are a few distinct differences. Only the features that are unique to the standalone version are detailed below. For a basic understanding of how to use the sky sequencer, head to [the Sky Sequencer](sequencer) page.


Properties that need sections
------------------------------

Navigation 

Exporting a sequence

Multi Api View

Performance (has begun below)



Properties Window
-----------------

The Properties Window can be activated from the Window>>Properties menu option. Whatever
is selected in the timeline can be edited in the properties window. Its contents depend
on the current selection.

When nothing is selected (click on a blank part of the timeline), the general properties
are shown, including camera and view properties.

Performance Window
------------------

The Performance Window can be activated from the Window>>Performance menu option. When
active, this window shows a text display of GPU and CPU profiling data for trueSKY. The GPU
data is taken from the DirectX11 view.

The values are shown in a hierarchical tree - the time for each element includes the times
of its children. The numbers given are times in milliseconds. The colour of the text for
each item indicates what percentage of its parent time it occupies. The more red the text,
the larger its contribution.

You'll see a slight pause in the Sequencer about once per second as the performance window
updates - this doesn't affect the measurements.

![](/images/PerformanceWindow.jpg)



Presets
![](/images/Presets.png)


The Sky and Clouds (both 2D and 3D) have various presets available, to quickly set a keyframe to a specific arrangement of values, designed to simulate the desired outcome. Be this a specific type of cloud or just a clear sky. The available presets are, for the Sky: Clear Sky and Fog, for 2D Clouds: Cirrus, Cirrocumulus and Altocumulus and for 3D Clouds: Cumulonimbus, Cumulus, Stratus, Stratocumulus and Altocumulus.

