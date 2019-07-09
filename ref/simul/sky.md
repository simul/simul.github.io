---
title: sky
layout: reference
weight: 0
---
namespace sky
===

| Include: | Sky/Sun.h |



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
| class [SiderealSky](sky/siderealsky) |  |
| class [SiderealSkyInterface](sky/siderealskyinterface) |  |
| struct [SkyKeyframe](sky/skykeyframe) |  |
| class [SkyKeyframer](sky/skykeyframer) | A class that maintains sky properties and interpolates them based on keyframe values.<br> |
| class [SkyTexturesCallback](sky/skytexturescallback) |  |
| class [Stars](sky/stars) |  |
| struct [SubdivInterpolation](sky/subdivinterpolation) |  |
| class [Texture3D4](sky/texture3d4) |  |

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
