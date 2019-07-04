---
title: crossplatform
layout: reference
weight: 0
---
namespace crossplatform
===

| Include: | Platform/CrossPlatform/Topology.h |



Classes and Structures
---

| struct [AmortizationStruct](crossplatform/amortizationstruct) |  |
| class [BaseRenderer](crossplatform/baserenderer) |  |
| struct [CommandLineParams](crossplatform/commandlineparams) |  |
| struct [ContextState](crossplatform/contextstate) |  |
| struct [Frustum](crossplatform/frustum) |  |
| class [GpuProfiler](crossplatform/gpuprofiler) |  |
| class [GpuProfilingInterface](crossplatform/gpuprofilinginterface) |  |
| class [GraphicsDeviceInterface](crossplatform/graphicsdeviceinterface) |  |
| class [Layout](crossplatform/layout) |  |
| struct [LayoutDesc](crossplatform/layoutdesc) |  |
| class [LensFlare](crossplatform/lensflare) |  |
| struct [MixedResolutionStruct](crossplatform/mixedresolutionstruct) |  |
| struct [MouseCameraInput](crossplatform/mousecamerainput) |  |
| struct [MouseCameraState](crossplatform/mousecamerastate) |  |
| class [PlatformRendererInterface](crossplatform/platformrendererinterface) |  |
| class [Quaterniond](crossplatform/quaterniond) |  |
| class [RenderDelegater](crossplatform/renderdelegater) |  |
| struct [TargetsAndViewport](crossplatform/targetsandviewport) |  |
| struct [TextureCreate](crossplatform/texturecreate) |  |
| class [TextureView](crossplatform/textureview) |  |
| struct [Viewport](crossplatform/viewport) |  |
| struct [ViewStruct](crossplatform/viewstruct) |  |

Functions
---

| void | [GetCameraPosVector](#GetCameraPosVector)(float v, float dcam_pos, float view_dir, float up) |
| float  const * | [GetCameraPosVector](#GetCameraPosVector)(float v) |
| void | [MakeCentredViewProjMatrix](#MakeCentredViewProjMatrix)(float vp, float view, float proj) |
| void | [MakeInvViewProjMatrix](#MakeInvViewProjMatrix)(float ivp, float v, float p) |
| void | [MakeInvWorldViewProjMatrix](#MakeInvWorldViewProjMatrix)(float ivp, float world, float v, float p) |
| void | [MakeViewProjMatrix](#MakeViewProjMatrix)(float vp, float view, float proj) |
| void | [MakeWorldViewProjMatrix](#MakeWorldViewProjMatrix)(float wvp, float world, float view, float proj) |


Functions
---

### <a name="GetCameraPosVector"/>void GetCameraPosVector(float v, float dcam_pos, float view_dir, float up)
Get the camera position, direction, and up-vector, from a view matrix v.

### <a name="GetCameraPosVector"/>float  const * GetCameraPosVector(float v)
Get the camera position from a view matrix.

### <a name="MakeCentredViewProjMatrix"/>void MakeCentredViewProjMatrix(float vp, float view, float proj)
Make a viewProj matrix, but ignore the view position.

### <a name="MakeInvViewProjMatrix"/>void MakeInvViewProjMatrix(float ivp, float v, float p)
Make an inverse viewProj matrix, which converts clip position to worldspace direction.

### <a name="MakeInvWorldViewProjMatrix"/>void MakeInvWorldViewProjMatrix(float ivp, float world, float v, float p)
Make an inverse worldViewProj matrix, which converts clip position to worldspace direction.

### <a name="MakeViewProjMatrix"/>void MakeViewProjMatrix(float vp, float view, float proj)
Make a viewProj matrix, which converts worldspace into clip position.

### <a name="MakeWorldViewProjMatrix"/>void MakeWorldViewProjMatrix(float wvp, float world, float view, float proj)
Make a worldViewProj matrix.

Enums
---

**DepthTextureStyle**  How to interpret the depth texture.

**NearFarPass**  Values that represent what pass to render, be it the near pass, the far, or both: far to render target 0, near to render target 1.

**PixelFormat**  A cross-platform equivalent to the OpenGL and DirectX pixel formats

**PixelOutputFormat**  Pixel formats for pixel shader output - only relevant for some API's.

**ShaderResourceType**  This refers to the type of a shader resource, which should be compatible with the type of any resource assigned to it.

**Topology**  A cross-platform equivalent to the OpenGL and DirectX vertex topology formats
