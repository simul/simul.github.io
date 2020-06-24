---
title: sky
layout: reference
weight: 0
---
namespace sky
===

| Include: | Sky/Aurora.h |



Classes and Structures
---

| class [BaseAtmosphericsRenderer](sky/baseatmosphericsrenderer.html) |  |
| struct [BaseKeyframe](sky/basekeyframe.html) |  |
| class [BaseKeyframer](sky/basekeyframer.html) |  |
| class [BaseSkyInterface](sky/baseskyinterface.html) |  |
| class [BaseSkyRenderer](sky/baseskyrenderer.html) |  |
| struct [ChunkInputOutput](sky/chunkinputoutput.html) |  |
| struct [EarthShadow](sky/earthshadow.html) |  |
| struct [Input](sky/input.html) |  |
| struct [KeyframeInterpolation](sky/keyframeinterpolation.html) |  |
| struct [KeyframeInUseState](sky/keyframeinusestate.html) |  |
| class [OpticalLengthInterface](sky/opticallengthinterface.html) |  |
| struct [Orbit](sky/orbit.html) |  |
| struct [Output](sky/output.html) |  |
| class [SiderealSky](sky/siderealsky.html) |  |
| struct [SkyKeyframe](sky/skykeyframe.html) |  |
| class [SkyTexturesCallback](sky/skytexturescallback.html) |  |
| class [Stars](sky/stars.html) |  |
| struct [SubdivInterpolation](sky/subdivinterpolation.html) |  |
| class [Texture3D4](sky/texture3d4.html) |  |

Functions
---

| simul::sky::float4 | [CalcMieCoefficients](#CalcMieCoefficients)(simul::sky::float4 ColourWavelengthsNm, float haze) |
| simul::sky::uid | [GenerateUid](#GenerateUid)() |


Functions
---
<a name="CalcMieCoefficients"></a>
### simul::sky::float4 CalcMieCoefficients(simul::sky::float4 ColourWavelengthsNm, float haze)
Calculates the mie coefficients (r,g,b) due to aerosol haze.
<a name="GenerateUid"></a>
### simul::sky::uid GenerateUid()
Get an unused uid.

Variables
---

Typedefs
---

**id**  An id that is unique for the type of thing it identifies, but not globally unique.

Enums
---

**SubdivMethod**  How to subdivide the keyframes for GPU generation.
