Rendering the Environment	{#rendering}
=========================

Weather Rendering is handled by  \link simul::clouds::BaseWeatherRenderer BaseWeatherRenderer\endlink, or (if necessary) a derived class of this.

All Simul's default renderers use a right-handed co-ordinate system with x pointing East, y North, and z up.

The Weather Renderer owns and manages renderers for sky, clouds, atmospherics and other effects.
So the Weather Renderer is the main interface between your program and trueSKY.

The following table describes the elements of a sky as implemented in the supplied renderers:

| Feature					|
| -------------------------	|
| Cosmic Background			|
| Stars						|
| Planets					|
| Vlumetric Clouds			|
| 2D Clouds					|
| Mixed resolution rendering|
| Atmospherics				|
| Godrays					|
| Precipitation				|
| Rain streaks				|

Cosmic Background
-----------------
The cosmic background texture is drawn first, at an orientation that corresponds to the plane of the Milky Way galaxy - see \link simul::sky::SkyKeyframer::SetBackgroundBrightness BackgroundBrightness\endlink.

Stars
-----
Stars are drawn as points, and spun around the axis of the Earth's rotation, in the same direction as the sun. Stars are usually drawn to the highest-resolution buffer (i.e. the frame buffer or final buffer). See
\link simul::sky::SkyKeyframer::SetStarBrightness StarBrightness\endlink and \link simul::sky::SkyKeyframer::SetMaxStarMagnitude MaxStarMagnitude\endlink.

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
The \link simul::clouds::BaseCloudRenderer BaseCloudRenderer\endlink keeps the cloud volume textures up to date, and draws the clouds volumetrically.

Performance
-----------
Rendering performance is chiefly dependent on the number of pixels drawn, and the number of raycasting steps (or Cloud Slices).
Calculation performance - mainly cloud lighting - depends strongly on the grid size - the larger the grid, the more time will be taken to light a cloud keyframe.

To adjust the number of drawn layers, the simul::clouds::CloudKeyframer class offers the maximum
distance (in kilometres) with
\link simul::clouds::CloudKeyframer::SetMaxCloudDistanceKm SetMaxCloudDistanceKm\endlink
and BaseCloudRenderer has the maximum number of layers (\link simul::clouds::BaseCloudRenderer::SetMaxSlices SetMaxSlices\endlink) functions.

It is usual to downsample the cloud part of the sky rendering to 1/2 or 1/4 resolution. This is controlled by
\link simul::clouds::BaseWeatherRenderer::SetDownscale SetDownscale\endlink
in the \link simul::clouds::BaseWeatherRenderer weather renderer\endlink.

	
Rain and Snow
-------------

\image html "rain.jpg" ""

The \link simul::clouds::CloudKeyframe::precipitation precipitation\endlink is used to control the amount of rain or snowfall
at a given time, while \link simul::clouds::CloudKeyframe::rain_to_snow rain_to_snow\endlink determines the type.

Each cloud keyframe has a \link simul::clouds::PrecipitationRegion PrecipitationRegion\endlink, which defines the local area of precipitation,
if it is not global for the keyframe.
	
\image html "Lightning-RainStreaks.jpg" ""

Classes derived from simul::clouds::BasePrecipitationRenderer are used to draw the rain or snow particles, while distant rain streaks are drawn by the cloud renderer.

Shaders
-------
Shaders are provided as source in the shader subdirectories of the platform directories.
-	\subpage shaders

<hr>
Next: \ref mixed_resolution
