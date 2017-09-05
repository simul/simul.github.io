---
title: sky
layout: reference
weight: 0
---
namespace sky
===

| Include: | Sky/BaseAtmosphericsRenderer.h |





Classes and Structures
---

| class [AtmosphericScatteringInterface](sky/AtmosphericScatteringInterface) | An abstract interface class for skies. |
| class [BaseAtmosphericsRenderer](sky/BaseAtmosphericsRenderer) | The graphics API-independent base class for atmospherics renderers, which draw distance fades, aerial perspective, fog and so on. |
| struct [BaseKeyframe](sky/BaseKeyframe) | The base keyframe structure, containing  |
| class [BaseKeyframer](sky/BaseKeyframer) | The base class for keyframers. A keyframer stores a list of keyframes, each representing the state at<br>a particular time. |
| class [BaseSkyInterface](sky/BaseSkyInterface) | An abstract interface class for skies. |
| class [BaseSkyRenderer](sky/BaseSkyRenderer) | The Sky Renderer performs the following tasks:<br>- Rendering stars: using RenderPointStars(void *context,float exposure)<br>- Rendering planets (e.g. the Moon): using RenderPlanets(void *context,float exposure)<br>- Rendering the sun, using RenderSun(void *context,float exposure)<br> |
| struct [ChunkInputOutput](sky/ChunkInputOutput) |  streaming is out of date. |
| struct [EarthShadow](sky/EarthShadow) | Properties of the Earth's shadow on the atmosphere and other objects. |
| struct [HazeStruct](sky/HazeStruct) | A data structure to contain haze properties in the atmosphere at any given moment. |
| struct [Input](sky/Input) | A virtual base class to load objects from binary. |
| struct [KeyframeInterpolation](sky/KeyframeInterpolation) | A structure to represent a position in the subdivisions. |
| struct [KeyframeInUseState](sky/KeyframeInUseState) | There are three keyframes in use.<br>Two are complete, one is in construction.<br>The keyframe values are interpolated from the true, control keyframes. |
| class [OpticalLengthInterface](sky/OpticalLengthInterface) | An abstract interface class for skies that can calculate optical lengths. |
| struct [Output](sky/Output) | A virtual base class to save objects to binary |
| class [OvercastCallback](sky/OvercastCallback) | A virtual callback class for skies to get overcast information from cloud classes. |
| class [SiderealSky](sky/SiderealSky) | A class that calculates the positions of sun, moon and stars. |
| class [SiderealSkyInterface](sky/SiderealSkyInterface) | An abstract interface class for a sky that is calculated using sidereal data. |
| class [Sky](sky/Sky) | Sky tracks the time of day, time of year, and viewing location in order to<br>calculate the relative position of the sun in the sky and hence the lighting.<br>If you set the year, it can even calculate the position of the moon.<br>TimeStep() advances the time of day, or you can use SetTime(), or SetHourOfTheDay().<br> |
| struct [SkyKeyframe](sky/SkyKeyframe) | The properties of any sky keyframe can be changed at any time. However, only HazeEccentricity<br>can be changed for an in-use keyframe without triggering a recalculation of the colour tables. |
| class [SkyKeyframer](sky/SkyKeyframer) | A class that maintains sky properties and interpolates them based on keyframe values.<br> |
| class [SkyTexturesCallback](sky/SkyTexturesCallback) | A callback virtual base class that fade tables use. A fade table is any class derived from FadeTableInterface, and it<br>uses these callback functions to tell your platform-specific renderer how to create and modify the sky and fade textures.<br>Usually you would derive your sky-rendering class from SkyTexturesCallback, and implement these functions. See, for example,<br>the DirectX implementation of SimulSkyRenderer. |
| class [Stars](sky/Stars) | A class that stores star positions by declination, ascension and magnitude. |
| struct [SubdivInterpolation](sky/SubdivInterpolation) | A structure to represent a position in the subdivisions. |
| class [Texture3D4](sky/Texture3D4) | A CPU 3D texture. |
| struct [Variant32](sky/Variant32) | Very simple 32-bit variant class for passing parameters. |

Functions
---

| simul::sky::float4 | [CalcMieCoefficients](#CalcMieCoefficients)(simul::sky::float4 ColourWavelengthsNm, float haze) |

The simul::sky namespace corresponds to the Simul/Sky library.

Static library: Simul/lib/(PLATFORM)/(COMPILER)/(ConfigurationName)/SimulSky_(RUNTIME).lib

Dynamic library: Simul/exe/(PLATFORM)/(COMPILER)/(ConfigurationName)/SimulSky_(RUNTIME).dll

Sky depends on the Base and Math libraries.

Simul Sky calculates the colour gradations of the sky, including the
position of the sun, the colour of sunlight and variations in brightness with azimuth, elevation, altitude,
and weather conditions..

Simul Sky integrates with the Simul Clouds library, which provides realistic volume-
rendering of various types of cloud.

To use Simul Sky directly, create an instance of simul::sky::BaseSkyRenderer.

  


Functions
---

### <a name="CalcMieCoefficients"/>simul::sky::float4 CalcMieCoefficients(simul::sky::float4 ColourWavelengthsNm, float haze)
Calculates the mie coefficients (r,g,b) due to aerosol haze.
Calculates the mie coefficients (r,g,b) due to aerosol haze.

Variables
---

Enums
---

**SubdivMethod** How to subdivide the keyframes for GPU generation. How to subdivide the keyframes for GPU generation.
