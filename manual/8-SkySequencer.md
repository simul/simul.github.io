The Sky Sequencer	{#sequencer}
=================

The Sky Sequencer is a tool for artists, technical artists, level designers, 
    and mission planners. It also helps programmers to understand the workings of True Sky's sky, 
    clouds and time-of-day systems.</p>
    
To launch the Sequencer, go to Start Menu/All Programs/Simul/Sky Sequencer/Sky Sequencer.

The Sequencer Window
====================

The Timeline
-------------
\image html "Timeline.png"

To change the current time, drag the red vertical line (the time marker) by its 
handle. To change the visible time-window, drag the timeline at the bottom. To 
adjust the range of visible time, use the mousewheel to zoom in and out.

To select keyframes, either click on a single keyframe, shift-click to select 
multiple keyframes, or box-select them. When one or more keyframes are selected, 
their properties can be changed in the property box. Changing any property 
affects all selected keyframes of the appropriate type (e.g. all cloud 
keyframes, or all sky keyframes.)

To select a whole row of keyframes, double-click on the space in-between them.

To select a layer (the sky, a layer of clouds, etc.), click on its name on the left
of the timeline.

To add a keyframe, right-click on the timeline and select the "Add sky 
keyframe..." or "Add cloud keyframe..." option.

Sky keyframes determine the colours of the sky from horizon to zenith, any haze 
effect, and light colour.

Cloud keyframes determine the properties of the cloud layer at a given time. As 
the light direction changes with time of day, it is necessary to have enough 
cloud keyframes to reflect the lighting throughout the day.
	
Map Window
----------
This window shows the cloud keyframes in a plan view. Wind heading and speed affects the
position of each keyframe - or they can be positioned individually. The camera is shown
as a red line indicating its direction of view. Rain regions are shown as filled grey circles
(blue when highlighted).

Properties Window
-----------------

The Properties Window can be activated from the Window>>Properties menu option. Whatever
is selected in the timeline can be edited in the properties window. Its contents depend
on the current selection.

When nothing is selected (click on a blank part of the timeline), the general properties
are shown, including camera and view properties.

Performance Window
------------------
<table>
<tr>
<td>
The Performance Window can be activated from the Window>>Performance menu option. When
active, this window shows a text display of GPU and CPU profiling data for trueSKY. The GPU
data is taken from the DirectX11 view.

The values are shown in a hierarchical tree - the time for each element includes the times
of its children. The numbers given are times in milliseconds. The colour of the text for
each item indicates what percentage of its parent time it occupies. The more red the text,
the larger its contribution.

You'll see a slight pause in the Sequencer about once per second as the performance window
updates - this doesn't affect the measurements.
</td>
<td>

\image html "PerformanceWindow.jpg"</td>
</td>
</table>

Features
========

<h2>Cloud features
</h2>
<h3>Grid</h3>
<p>The Grid height and width determine the amount of detail in a cloud volume.</p>
<h3>Cloud volume width</h3>
<p>The cloud volume may be typically 10-100km wide. It can repeat (wrap), so that it 
    covers the whole sky. Alternatively, a non-wrapping cloud volume can represent a 
    specific area of cloud in a clear sky.</p>
<h3>Keyframe features</h3>
The main properties for controlling the weather are:

<table style="width: 718px; background-color: #E3EEFB; margin-left: 56px;">
<tr><th>Feature</th><th><b>Description</b></th></tr>
<tr><td>cloudiness</td><td>How much cloud in the layer at this time.</td></tr>
<tr><td>cloudbase (km)</td><td>Base altitude.</td></tr>
<tr><td>cloud height (km)</td><td>How tall the cloud layer is.</td></tr>
</table>

See the public attributes of \link simul::clouds::CloudKeyframe CloudKeyframe\endlink for a full description of all the cloud keyframe properties.

<h2>Sky features</h2>

<h3>Brightness Power</h3>
The sky at sunrise can be less than one quarter as bright as at noon. Moonlight is hundreds of times dimmer 
than sunlight. Starlight is much dimmer still. The human eye adjusts to a very wide range of light conditions, but for rendering we usually apply a brightness, 
or exposure level, to make dark scenes visible and bright scenes clear.<br />
The Brightness Power value for a sky sequence adjusts the light levels to compensate for this large variation by introducing a power function.
If the Power is 1.0, there is no adjustment. If it is 0.5, it will be a square-root dependence, e.g. a light 4 times dimmer than daylight would
appear only half as dim, and so on.

<h3>Automatic Sun Position</h3>
<p>The sun is automatically placed in the sky based on time-of-day if this is enabled. Otherwise, each sky keyframe has sun 
    position settings.</p>
<h3>Automatic Moon Position</h3>
<p>If enabled, the moon is automatically placed in the sky based on time, day, 
    month, and year. Otherwise, each sky keyframe has moon position settings.</p>
<h3>Colour Sky</h3>
<p>A colour sky has colours for sky and fade determined by a choice from a colour dialog. The default behaviour (non-colour sky) is to generate the colours from physical properties).
</p>
<h3>Keyframe features</h3>
See the class definition for \ref simul::sky::SkyKeyframe.
The main sky keyframe properties are:

<table style="width: 718px; background-color: #E3EEFB; margin-left: 56px;">
<tr><th>Feature</th><th><b>Description</b></th></tr>
<tr><td>Haze</td><td>How much haze, or fog is present at this 
            time.</td></tr>
<tr><td>Sun azimuth</td><td>If sun position is not automatic, 
            this controls the horizontal angle of the sun.</td></tr>
<tr><td>Sun elevation</td><td>If sun position is not 
            automatic, this controls how high the sun is in the sky.</td></tr>
<tr><td>Moon azimuth</td><td>If moon position is not 
            automatic, this controls its horizontal angle.</td></tr>
<tr><td>Moon elevation</td><td>If not automatic, this controls 
            the moon's elevation</td></tr>
</table>
See the public attributes of \link simul::sky::SkyKeyframe SkyKeyframe\endlink for a full description of all the sky keyframe properties.

<hr>
Next: \ref changelist