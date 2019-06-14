---
title: sky
layout: reference
weight: 0
---
namespace sky
===

| Include: | Sky/Help.h |


![](/Images/SkyInheritance.png)


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

  


Classes and Structures
---

| class [BaseAtmosphericsRenderer](sky/baseatmosphericsrenderer) |  |
| struct [BaseKeyframe](sky/basekeyframe) |  |
| class [BaseKeyframer](sky/basekeyframer) |  |
| class [BaseSkyInterface](sky/baseskyinterface) |  |
| struct [ChunkInputOutput](sky/chunkinputoutput) |  |
| struct [EarthShadow](sky/earthshadow) |  |
| struct [HazeStruct](sky/hazestruct) |  |
| struct [Input](sky/input) |  |
| struct [KeyframeInterpolation](sky/keyframeinterpolation) |  |
| struct [KeyframeInUseState](sky/keyframeinusestate) |  |
| class [OpticalLengthInterface](sky/opticallengthinterface) |  |
| struct [Output](sky/output) |  |
| class [OvercastCallback](sky/overcastcallback) |  |
| class [SiderealSky](sky/siderealsky) |  |
| class [SiderealSkyInterface](sky/siderealskyinterface) |  |
| class [Sky](sky/sky) |  |
| struct [SkyKeyframe](sky/skykeyframe) |  |
| class [SkyKeyframer](sky/skykeyframer) | A class that maintains sky properties and interpolates them based on keyframe values.<br> |
| class [SkyTexturesCallback](sky/skytexturescallback) |  |
| class [Stars](sky/stars) |  |
| struct [SubdivInterpolation](sky/subdivinterpolation) |  |
| class [Texture3D4](sky/texture3d4) |  |

Functions
---

| simul::sky::float4 | [CalcMieCoefficients](#CalcMieCoefficients)(simul::sky::float4 ColourWavelengthsNm, float haze) |


![](/Images/SkyInheritance.png)


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

Variables
---

Enums
---

**SubdivMethod**  How to subdivide the keyframes for GPU generation.
