---
title: Rendering the Environment
layout: reference
weight: 3
---
=========================<br>Previous: <a href="gettingstarted">Getting Started</a>
<hr size="1">

All Simul's default renderers use a right-handed co-ordinate system with x pointing East, y North, and z up. All units of distance are metres or kilometres. If not specified as km, distance is in metres. Angular units are radians, unless specified as degrees. Temperature is in kelvins, unless specified as degrees Celsius.

Weather Rendering is handled by  [simul::clouds::BaseWeatherRenderer](/ref/simul/clouds/baseweatherrenderer)
.

The Weather Renderer owns and manages renderers for sky, clouds, atmospherics and other effects.
So the Weather Renderer is the main interface between your program and trueSKY.

The following table describes the elements of a sky as implemented in the renderer:

| Features                                      |
| -------------------------     |
| Cosmic Background                     |
| Stars                                         |
| Planets                                       |
| Volumetric Clouds                     |
| 2D Clouds                                     |
| Mixed resolution rendering|
| Atmospherics                          |
| Godrays                                       |
| Precipitation                         |
| Rain streaks                          |

Cosmic Background
-----------------
The cosmic background texture is drawn first, at an orientation that corresponds to the plane of the Milky Way galaxy - see [simul::sky::SkyKeyframer::SetBackgroundBrightness](/ref/simul/sky/skykeyframer/setbackgroundbrightness)
.

It uses a plate-carree projection, aligned with the galactic horizon. Given the vector "view", which is the direction in galactic co-ordinates, the calculation is:

float az       =atan2(view.y,-view.x);
vec2 texcoord  =vec2((ang/(pi*2.0)),0.5-asin(view.z)/pi);

i.e. the x coordinate is proportional to the azimuth, and the y coordinate is proportional to the elevation

![](/Images/MilkyWay.png)
""

You may see some stretching at the top and bottom of the image due to degeneracy of the projection, so it is preferable to have the texture fade to black at the top and bottom edges.

Stars
-----
Stars are drawn as point sprites, and spun around the axis of the Earth's rotation, in the same direction as the sun. Stars are usually drawn to the highest-resolution buffer (i.e. the frame buffer or final buffer). See
[simul::sky::SkyKeyframer::SetStarBrightness](/ref/simul/sky/skykeyframer/setstarbrightness)
and [simul::sky::SkyKeyframer::SetMaxStarMagnitude](/ref/simul/sky/skykeyframer/setmaxstarmagnitude)
.

The Sun
-------
The sun is drawn after the stars.

Planets
-------
Planets (e.g. the Moon) are drawn by BaseSkyRenderer.
A planet texture map needs to be supplied, and the shader takes a sun direction as a parameter -
this is used to light the planet (e.g. phases of the moon). Like stars, planets are usually drawn to the
highest-resolution buffer, in order to make sure they have sharp outlines.


Sky/Atmospherics
----------------
The sky and atmospherics are drawn to a volumetric texture for which the x and y axes are screen coordinates, and the z axis is distance. The final compositing step puts the sky, atmospherics and clouds to the current
rendertarget.

Clouds
------
Clouds are usually drawn to a pair of lower-resolution buffers.
The [simul::clouds::BaseCloudRenderer](/ref/simul/clouds/basecloudrenderer)
keeps the cloud volume textures up to date, and draws the clouds volumetrically.

Performance
-----------
Rendering performance is chiefly dependent on the number of pixels drawn, and the number of raycasting steps (or Cloud Slices).
Calculation performance - mainly cloud lighting - depends strongly on the grid size - the larger the grid, the more time will be taken to light a cloud keyframe.

It is usual to downsample the cloud part of the sky rendering, controlled by
[simul::clouds::CloudRenderingOptions::MaximumCubemapResolution](/ref/simul/clouds/cloudrenderingoptions/maximumcubemapresolution)

in the [simul::clouds::CloudRenderingOptions](/ref/simul/clouds/cloudrenderingoptions)
.


Rain and Snow
-------------

![](/Images/rain.jpg)
""

The [simul::clouds::CloudKeyframe::precipitation](/ref/simul/clouds/cloudkeyframe/precipitation)
is used to control the amount of rain or snowfall
at a given time, whilst the [simul::clouds::CloudKeyframer](/ref/simul/clouds/cloudkeyframer)
property is used to set the thickness of cloud required for rain to fall (setting this to 0 will allow even the smallest of clouds to produce rain). To switch between snow and rain use [simul::clouds::CloudKeyframe](/ref/simul/clouds/cloudkeyframe)
(where 0 is rain, 1 is snow). 

Each cloud keyframe has a [simul::clouds::PrecipitationRegion](/ref/simul/clouds/precipitationregion)
, which defines the local area of precipitation,
if it is not global for the keyframe. The amount of particles used for precipitation can be altered with the [simul::clouds::BasePrecipitationRenderer](/ref/simul/clouds/baseprecipitationrenderer)
property.

![](/Images/Lightning-RainStreaks.jpg)
""

Classes derived from simul::clouds::BasePrecipitationRenderer are used to draw the rain or snow particles, while the [simul::clouds::PrecipitationRegion](/ref/simul/clouds/precipitationregion)
is drawn by the cloud renderer. This class has a property "UseSimulationTime" which determines whether rain and snow speed is based on the simulated time-of-day, or real time in seconds.

Shaders
-------
Shaders are provided as source in the shader subdirectories of the platform directories (see <a href="classes/shaders">Shaders</a>).

<hr>
Next: <a href="pri">The Plugin Rendering Interface</a>
