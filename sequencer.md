---
title: The Sky Sequencer
layout: reference
weight: 60
---
The Sky Sequencer
===

=================<br>Previous: \ref classes::mixed

The Sky Sequencer is a tool for artists, technical artists, level designers, 
    and mission planners. It also helps programmers to understand the workings of True Sky's sky, 
    clouds and time-of-day systems.
    
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
\image html "SkyKeyframeSelect.png"

To select a whole row of keyframes, double-click on the space in-between them.
\image html "SkyKeyframesSelect.png"

To select a layer (the sky, a layer of clouds, etc.), click on its name in the column on the left of the timeline.
\image html "SkyLayerSelect.png"

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

<h2>Presets
</h2> 
\image html "Presets.png"

The Sky and Clouds (both 2D and 3D) have various presets available, to quickly set a keyframe to a specific arrangement of values, designed to simulate the desired outcome. Be this a specific type of cloud or just a clear sky. The available presets are, for the Sky: Clear Sky and Fog, for 2D Clouds: Cirrus, Cirrocumulus and Altocumulus and for 3D Clouds: Cumulonimbus, Cumulus, Stratus, Stratocumulus and Altocumulus.


<h2>Clouds
</h2> 
In the sequencer, clouds can be edited in two ways. Clicking (or shift-clicking) individual keyframes will allow the properties for one or more keyframes at any point in time to be altered. Alternatively, clicking the 2D Clouds or 3D Clouds column will allow the properties for the respective cloud layer to be altered. Cloud layer properties will impact the entire sequence indefinitely, allowing you to enable/disable cloud rendering, alter the speed of rainfall, change the render mode and more. Whereas keyframe properties are temporal, allowing you to alter cloudiness, rain strength, wind speed and so on, for the point in time at which the keyframe is active. Note: If just a single keyframe is present in the sequencer, then those settings will be applied continously. 

<h3>Cloud Layer Properties</h3>
<p>Note that for 2D clouds, there is no Precipitation section. The cloud layer properties accessible in the sequencer are:</p>
<table  style="width: 718px; background-color: #E3EEFB; margin-left: 56px;">
<tr>
<th>Feature</th><th><b>Description</b> </th></tr>
<tr>
<td><b>Mode</b></td><td> </td></tr>
<tr>
<td>Loop</td><td>Whether or not to loop the keyframes. </td></tr>
<tr>
<td>Keyframe Subdivision</td><td>How keyframes are transitionsed between (real time is simplest). </td></tr>
<tr>
<td>Update</td><td>Whether to apply updates instantly or gradually. If gradually, any keyframe can be modified at any time. If instant, only the next keyframe can be modified. </td></tr>
<tr>
<td>Number</td><td>If using fixed intervals, this is the total number of seconds/minutes/days/months. </td></tr>
<tr>
<td>Interval</td><td>Interval between keyframes in minutes/days/months (if game time). </td></tr>
<tr>
<td>Interval (s)</td><td>Interval between keyframes in seconds (if real time). </td></tr>
<tr>
<td><b>Main</b></td><td> </td></tr>
<tr>
<td>Enabled</td><td>Whether or not GPU cloud generator should calculate clouds. </td></tr>
<tr>
<td>Wrap Horizontally</td><td>Whether to wrap clouds horizontally. </td></tr>
<tr>
<td>Overide Wind</td><td>Whether to set wind speed and direction directly, or use the keyframe values. </td></tr>
<tr>
<td>Render Mode</td><td>A hint for the renderer on how to raytrace these clouds. </td></tr>
<tr>
<td><b>Precipitation </b></td><td> </td></tr>
<tr>
<td>Max Particles</td><td>The maximum number of rain particles to render. </td></tr>
<tr>
<td>Threshold</td><td>What local thickness of cloud is needed for rain to fall, in km. </td></tr>
<tr> 
<td>Radius</td><td>Size of the particle zone, in metres. </td></tr>
<tr>
<td>Rain Speed</td><td>Speed of falling precipitation, in m/s. </td></tr>
<tr>
<td>Raindrop Size</td><td>Size of a single raindrop, in mm. </td></tr>
<tr>
<td><b>Rendering</b></td><td> </td></tr>
<tr>
<td>Default Slices</td><td>Number of slices in the main view. </td></tr>
<tr>
<td>Shadow</td><td>Amount of shadow between 0 and 1. </td></tr>
<tr>
<td>Shadow Range</td><td>Range of the cloud shadow texture, in km. </td></tr>
<tr>
<td>Shadow Texture Size</td><td>Size of the cloud shadow texture.  </td></tr>
<tr>
<td>Max cloud dist</td><td>Distance of the furthest cloud layer. </td></tr> 
<tr>
<td><b>Grid</b></td><td> </td></tr>
<tr>
<td>Grid Width</td><td>Width of the grid, in powers of 2 (determines cloud detail). </td></tr>
<tr>
<td>Grid Height</td><td>Height of the grid, in powers of 2 (determines cloud detail).</td></tr> 
<tr> 
<td><b>Generation Noise</b></td><td> </td></tr>
<tr>
<td>Noise Period</td><td>Period in days of the fractal noise function. </td></tr>
<tr>
<td>Noise Phase</td><td>Offset for Noise Period.</td></tr>
<tr>
<td>Noise Resolution</td><td>Resolution of the 3D Perlin noise used to generate clouds. </td></tr>
<tr>
<td><b>Edge Noise</b></td><td> </td></tr>
<tr>
<td>Frequency</td><td>Frequency (power of 2) of the edge noise effect. </td></tr>
<tr>
<td>Resolution</td><td>Resolution of the 3D Perlin noise used to generate clouds. </td></tr>
<tr>
<td>Persistence</td><td>Fractal persistence to use when generating the noise texture. </td></tr>
</table> 
See the public attributes of \link simul::clouds::CloudKeyframer CloudKeyframer\endlink for a full description of all the cloud layer properties.

<h3>Cloud Keyframe Properties</h3>
Note that for 2D clouds, there is no Weather Effects section. The cloud keyframe properties accessible in the sequencer are:
<table  style="width: 718px; background-color: #E3EEFB; margin-left: 56px;">
<tr>
<th>Feature</th><th><b>Description</b> </th></tr>
<tr>
<td><b>Main</b></td><td> </td></tr>
<tr>
<td>Cloudiness</td><td>How much cloud in the layer at this time. </td></tr>
<tr>
<td>Cloudbase</td><td>Base altitude, in km. </td></tr>
<tr>
<td>Layer Height </td><td>How tall the cloud layer is, in km. </td></tr>
<tr>
<td>Volume Width</td><td>The width of the cloud layer, in km. Typically between 10 and 100. </td></tr>
<tr>
<td>Wind Speed</td><td>Wind speed, in m/s. </td></tr>
<tr>
<td>Wind Heading</td><td>Wind motion of the clouds, in degrees. Defines the horizontal direction the clouds move in. </td></tr>
<tr>
<td><b>Shape</b></td><td> </td></tr>
<tr>
<td>Base Layer</td><td>Proportion of the volume vertically that forms the base of the clouds. </td></tr>
<tr>
<td>Transition</td><td>Proportion that transitions from the cloudbase to the upper layer. </td></tr>
<tr>
<td>Upper Density</td><td>Density of the upper layer as a proportion of the base density. </td></tr>
<tr>
<td>Octaves</td><td>How many fractal octaves to use. </td></tr>
<tr>
<td>Persistence</td><td>Fractal persistence. </td></tr>
<tr>
<td>Worley Noise</td><td>How much Worley (cell) noise to apply in cloud generation. </td></tr>
<tr>
<td>Worley Scale</td><td>Scale of the Worley noise. Will be locked to an integer if clouds are wrapping.  </td></tr>
<tr>
<td>Diffusivity</td><td>How much the edges of clouds should be diffused. </td></tr>
<tr>
<td><b>Lighting</b></td><td> </td></tr>
<tr>
<td>Direct Light</td><td>The amount of direct light to be used. </td></tr>
<tr>
<td>Asymmetry</td><td>The anisotropic distribution of direct lighting, or eccentricity.  </td></tr>
<tr>
<td>Indirect Light</td><td>The amount of indirect or secondary light to be used.  </td></tr>
<tr>
<td>Ambient Light</td><td>The amount of ambient light to be used. </td></tr>
<tr>
<td>Extinction</td><td>The amount of light scattered per metre. Larger values produce darker clouds.  </td></tr>
<tr>
<td>Godrays</td><td>Strength of the godrays effect, between 0 and 1. </td></tr>
<tr>
<td><b>Edge Noise</b></td><td> </td></tr>
<tr>
<td>Scale</td><td>The wavelength of the edge noise. </td></tr>
<tr>
<td>Amplitude</td><td>The strength of the edge noise. </td></tr>
<tr>
<td>Worley Scale</td><td>The wavelength of the fractal worley edge noise. </td></tr>
<tr>
<td>Worley Amplitude</td><td>The strength of the fractal worley edge noise.  </td></tr>
<tr>
<td>Sharpness</td><td>The sharpness to be applied when rendering the boundary.  </td></tr>
<tr>
<td>Base Factor</td><td>What proportion of noise is applied at the cloudbase, between 0 and 1.  </td></tr>
<tr>
<td>Churn</td><td>The strength of the cloud edge churning effect. Larger values produce more turbulent clouds.  </td></tr>
<tr>
<td><b>Weather Effects</b></td><td> </td></tr>
<tr>
<td>Regional</td><td>If checked then rain/snow will be limited to the specified region.  </td></tr>
<tr>
<td>Lock to cloud</td><td>Locks the precipitation region to the cloud wind motion.  </td></tr>
<tr>
<td>Radius (km)</td><td>The precipitation region, in km.  </td></tr>
<tr>
<td>Strength</td><td>How much rain or snow.  </td></tr>
<tr>
<td>Rain Streaks</td><td>The visual strength of the rain-streak effect.  </td></tr>
<tr>
<td>Rain - Snow</td><td>Set this to 0 for rain, or 1 for snow.  </td></tr>
<tr>
<td>Wind effect</td><td>Strength of the effect of wind on precipitation direction.  </td></tr>
<tr>
<td>Waver</td><td>How much precipitation layers waver as they fall. </td></tr>
</table>

See the public attributes of \link simul::clouds::CloudKeyframe CloudKeyframe\endlink for a full description of all the cloud keyframe properties.

<h2>The Sky</h2>
In the sequencer, just as with clouds, the sky can be edited in two ways. Clicking (or shift-clicking) individual keyframes will allow the properties for one or more keyframes at any point in time to be altered. Alternatively, clicking the Sky column will allow the properties for the sky layer to be altered. These properties will impact the entire sequence indefinitely, allowing you to adjust the amount of ozone, alter the diameter of the sun/moon, set the start date of the scene and more. Whereas keyframe properties are temporal, allowing you to adjust settings like visibility, haze, eccentricity and so on, for the point in time at which the keyframe is active. Note: If just a single keyframe is present in the sequencer, then those settings will be applied continously. 

<h3>Brightness Power</h3>
The sky at sunrise can be less than one quarter as bright as at noon. Moonlight is hundreds of times dimmer 
than sunlight. Starlight is much dimmer still. The human eye adjusts to a very wide range of light conditions, but for rendering we usually apply a brightness, 
or exposure level, to make dark scenes visible and bright scenes clear.<br />
The Brightness Power value for a sky sequence adjusts the light levels to compensate for this large variation by introducing a power function.
If the Power is 1.0, there is no adjustment. If it is 0.5, it will be a square-root dependence, e.g. a light 4 times dimmer than daylight would
appear only half as dim, and so on.

<h3>Automatic Sun and Moon Positions</h3>
<p>If these options are enabled, the sun and/or moon can be automatically placed in the sky based on the time, day, month and year. Otherwise, each sky keyframe will have manual position settings.</p> 
<h3>Colour Sky</h3>
<p>A colour sky has colours for sky and fade determined by a choice from a colour dialog. The default behaviour (non-colour sky) is to generate the colours from physical properties).
</p>
<h3>Sky Layer Properties</h3> 
<p>Sky layer properties are more general, and will affect all sky keyframes. The sky layer properties accessible in the sequencer are:</p>
<table  style="width: 718px; background-color: #E3EEFB; margin-left: 56px;">
<tr>
<th>Feature</th><th><b>Description</b> </th></tr>
<tr> 
<td><b>Atmospheric Scattering Tables</b></td><td> </td></tr>
<tr>
<td>Brightness Power</td><td> Set the brightness power (see above). </td></tr>
<tr>
<td>Altitudes</td><td>The number of altitudes to calculate / in atmospheric table textures. </td></tr>
<tr>
<td>Max Altitude</td><td>Maximum altitude (km) that will be used for fade and sky colour calculations. </td></tr>
<tr>
<td>Elevations</td><td>Number of elevations / height of table. </td></tr>
<tr>
<td>Distances</td><td>Number of distances / width of table. </td></tr>
<tr>
<td>Distance Range</td><td>The maximum distance for the fade. </td></tr>
<tr>
<td>Overcast Effect</td><td>How strongly the cloud layer blocks light when generating inscatter tables.</td></tr>
<tr>
<td>Reyleigh Coefficients</td><td>Rayleigh scattering coeeficients at standard sea level density, xyz = RGB. </td></tr>
<tr>
<td>Light Wavelengths</td><td>Red, green and blue wavelengths in nanometres. </td></tr>
<tr>
<td><b>The Atmosphere</b></td><td> </td></tr>
<tr>
<td>Ozone</td><td>The amount of ozone. </td></tr>
<tr>
<td>Emissivity</td><td>The blackbody emissivity of the atmosphere, between 0 and 1. </td></tr>
<tr>
<td><b>Sun</b></td><td> </td></tr>
<tr>
<td>Diameter</td><td>Diameter of the sun. </td></tr>
<tr>
<td>Start Date</td><td>Used to calculate start positions of sun and moon (if automatic position set). </td></tr>
<tr>
<td>Latitude & Longitude</td><td>The position of the sun. </td></tr>
<tr>
<td>Timezone +-</td><td>Where 0 is GMT. </td></tr>
<tr>
<td>Link Keyframe time and daytime</td><td>Will make daytime value = keyframe value. Otherwise these values are independent. </td></tr>
<tr>
<td><b>Moon</b></td><td> </td></tr>
<tr>
<td>Albedo</td><td>Albedo value of the moon (will affect colour). </td></tr>
<tr>
<td>Diameter</td><td>Diameter of the moon, in degrees. </td></tr>
<tr>
<td>Texture</td><td>Texture to be drawn on moon object. </td></tr>
<tr>
<td>Colour</td><td>The base colour of the moon (will be affected by albedo). </td></tr>
<tr>
<td><b>Stars</b></td><td> </td></tr>
<tr>
<td>Max Magnitude</td><td>Maximum magnitude of star to be visible. Between 0 (brightest) and 9 (dimmest). </td></tr>
<tr>
<td>Brightness</td><td>Brightness multiplier value. </td></tr>
<tr>
<td>Background</td><td>Multiplier for the brightness of cosmic background texture. </td></tr>
<tr>
<td>Find Constellation</td><td>Find a star constellation at given coordinates. </td></tr>
</table>
See the public attributes of \link simul::sky::SkyKeyframer SkyKeyframer\endlink for a full description of all the sky layer properties.

<h3>Sky Keyframe Properties</h3>
Sky keyframe properties allow you to change particular elements of one or more keyframes at a time. The sky keyframe properties accessible in the sequencer are:
<table  style="width: 718px; background-color: #E3EEFB; margin-left: 56px;">
<tr>
<th>Feature</th><th><b>Description</b> </th></tr>
<tr>
<td><b>Colours</b></td><td></td></tr>
<tr>
<td>Altitudes</td><td>Number of altitudes for use in custom atmospheric table texture. </td></tr>
<tr>
<td>Elevations</td><td>Number of elevations for use in custom atmospheric table texture. </td></tr>
<tr>
<td>Distances</td><td>Number of distances for use in custom atmospheric table texture. </td></tr>
<tr>
<td><b>Temperature</b></td><td></td></tr>
<tr>
<td>Sea Level deg. C </td><td>For infrared rendering. </td></tr>
<tr>
<td><b>Haze/Fog/Mist/Dust</b></td><td></td></tr>
<tr>
<td>Visibility </td><td>Visibility distance, in km. Fog = <1km, Mist = 1-2km, Haze = >2km. This will alter Haze/fog. </td></tr>
<tr>
<td>Haze/fog </td><td>Amount of haze, mist or fog. This will alter Visibility. </td></tr>
<tr>
<td>Haze base </td><td>Base altitude above which haze starts to decrease in density, in km. </td></tr>
<tr>
<td>Haze scale </td><td>Vertical scale over which haze reduces with altitude, in km. </td></tr>
<tr>
<td>Eccentricity </td><td>The anisotropy of Mie scattering. </td></tr>
<tr>
<td>Mie Coefficients </td><td>The Mie scattering coefficients, xyz = RGB. </td></tr>
<tr>
<td><b>Sun and Moon</b></td><td></td></tr>
<tr>
<td>Haze</td><td>How much haze or fog is present at this time. </td></tr>
<tr>
<td>Sun azimuth</td><td>Controls the horizontal angle of the sun (if sun position not automatic). </td></tr>
<tr>
<td>Sun elevation</td><td>Controls how high the sun is in the sky (if sun position not automatic). </td></tr>
<tr>
<td>Moon azimuth</td><td>Controls the horizontal angle of the moon (if moon position not automatic). </td></tr>
<tr>
<td>Moon elevation</td><td>Controls how high the moon is in the sky (if moon position not automatic). </td></tr>
</table>
See the public attributes of \link simul::sky::SkyKeyframe SkyKeyframe\endlink for a full description of all the sky keyframe properties.

<hr>
Next: \ref licensing
