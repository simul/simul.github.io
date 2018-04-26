---
title: sky
layout: reference
weight: 0
---
namespace sky
===

| Include: | Clouds/BaseGpuCloudGenerator.h |



  


Classes and Structures
---

| class [AtmosphericScatteringInterface](sky/AtmosphericScatteringInterface) |  |
| class [BaseAtmosphericsRenderer](sky/BaseAtmosphericsRenderer) |  |
| struct [BaseKeyframe](sky/BaseKeyframe) |  |
| class [BaseKeyframer](sky/BaseKeyframer) |  |
| class [BaseSkyInterface](sky/BaseSkyInterface) |  |
| class [BaseSkyRenderer](sky/BaseSkyRenderer) |  |
| struct [ChunkInputOutput](sky/ChunkInputOutput) |  |
| struct [EarthShadow](sky/EarthShadow) |  |
| struct [HazeStruct](sky/HazeStruct) |  |
| struct [Input](sky/Input) |  |
| struct [KeyframeInterpolation](sky/KeyframeInterpolation) |  |
| struct [KeyframeInUseState](sky/KeyframeInUseState) |  |
| class [OpticalLengthInterface](sky/OpticalLengthInterface) |  |
| struct [Output](sky/Output) |  |
| class [OvercastCallback](sky/OvercastCallback) |  |
| class [SiderealSky](sky/SiderealSky) |  |
| class [SiderealSkyInterface](sky/SiderealSkyInterface) |  |
| class [Sky](sky/Sky) |  |
| struct [SkyKeyframe](sky/SkyKeyframe) |  |
| class [SkyKeyframer](sky/SkyKeyframer) | A class that maintains sky properties and interpolates them based on keyframe values.<br> |
| class [SkyTexturesCallback](sky/SkyTexturesCallback) |  |
| class [Stars](sky/Stars) |  |
| struct [SubdivInterpolation](sky/SubdivInterpolation) |  |
| class [Texture3D4](sky/Texture3D4) |  |
| struct [Variant32](sky/Variant32) |  |

Functions
---

| simul::sky::float4 | [CalcMieCoefficients](#CalcMieCoefficients)(simul::sky::float4 ColourWavelengthsNm, float haze) |



  


Functions
---

### <a name="CalcMieCoefficients"/>simul::sky::float4 CalcMieCoefficients(simul::sky::float4 ColourWavelengthsNm, float haze)
Calculates the mie coefficients (r,g,b) due to aerosol haze.

Variables
---

Enums
---

**SubdivMethod**  How to subdivide the keyframes for GPU generation.
