---
title: crossplatform
layout: reference
weight: 0
---
namespace crossplatform
===

| Include: | Platform/CrossPlatform/DemoOverlay.h |



Classes and Structures
---

| struct [AmortizationStruct](crossplatform/amortizationstruct) |  |
| class [BaseRenderer](crossplatform/baserenderer) |  |
| struct [CommandLineParams](crossplatform/commandlineparams) |  |
| struct [ContextState](crossplatform/contextstate) |  |
| struct [DisjointQueryStruct](crossplatform/disjointquerystruct) |  |
| class [DisplaySurfaceManager](crossplatform/displaysurfacemanager) |  |
| class [EffectTechniqueGroup](crossplatform/effecttechniquegroup) |  |
| struct [Frustum](crossplatform/frustum) |  |
| class [GpuProfiler](crossplatform/gpuprofiler) |  |
| class [GpuProfilingInterface](crossplatform/gpuprofilinginterface) |  |
| class [GraphicsDeviceInterface](crossplatform/graphicsdeviceinterface) |  |
| class [Layout](crossplatform/layout) |  |
| struct [LayoutDesc](crossplatform/layoutdesc) |  |
| class [LensFlare](crossplatform/lensflare) |  |
| class [Material](crossplatform/material) |  |
| struct [MixedResolutionStruct](crossplatform/mixedresolutionstruct) |  |
| struct [MouseCameraInput](crossplatform/mousecamerainput) |  |
| struct [MouseCameraState](crossplatform/mousecamerastate) |  |
| class [PlatformRendererInterface](crossplatform/platformrendererinterface) |  |
| struct [PosColourVertex](crossplatform/poscolourvertex) |  |
| class [Quaterniond](crossplatform/quaterniond) |  |
| struct [RasterizerDesc](crossplatform/rasterizerdesc) |  |
| class [RenderDelegater](crossplatform/renderdelegater) |  |
| struct [RenderTargetFormatDesc](crossplatform/rendertargetformatdesc) |  |
| struct [ShaderResource](crossplatform/shaderresource) |  |
| class [SphericalHarmonics](crossplatform/sphericalharmonics) |  |
| struct [TargetsAndViewport](crossplatform/targetsandviewport) |  |
| struct [TextureCreate](crossplatform/texturecreate) |  |
| class [TextureView](crossplatform/textureview) |  |
| class [View](crossplatform/view) |  |
| class [ViewManager](crossplatform/viewmanager) |  |
| struct [Viewport](crossplatform/viewport) |  |

Functions
---

| void | [DrawGrid](#DrawGrid)(simul::crossplatform::DeviceContext deviceContext, vec3 centrePos, float square_size, float brightness, int numLines) |
| void | [GetCameraPosVector](#GetCameraPosVector)(float v, float dcam_pos, float view_dir, float up) |
| float  const * | [GetCameraPosVector](#GetCameraPosVector)(float v) |
| void | [MakeCentredViewProjMatrix](#MakeCentredViewProjMatrix)(float vp, float view, float proj) |
| void | [MakeInvViewProjMatrix](#MakeInvViewProjMatrix)(float ivp, float v, float p) |
| void | [MakeInvWorldViewProjMatrix](#MakeInvWorldViewProjMatrix)(float ivp, float world, float v, float p) |
| void | [MakeViewProjMatrix](#MakeViewProjMatrix)(float vp, float view, float proj) |
| void | [MakeWorldViewProjMatrix](#MakeWorldViewProjMatrix)(float wvp, float world, float view, float proj) |
| vec4 | [ViewportToTexCoordsXYWH](#ViewportToTexCoordsXYWH)(simul::crossplatform::Viewport vi, simul::crossplatform::Texture t) |
| vec4 | [ViewportToTexCoordsXYWH](#ViewportToTexCoordsXYWH)(int4 vi, simul::crossplatform::Texture t) |


Functions
---

### <a name="DrawGrid"/>void DrawGrid(simul::crossplatform::DeviceContext deviceContext, vec3 centrePos, float square_size, float brightness, int numLines)
Draw a horizontal grid in 3D.

[in,out] deviceContext   Context for the device.
[in]     centrePos       Origin of the grid in 3D.
[in]     square_size     Spacing between lines - in whatever units the renderer is working in.
[in]     brightness      Brightness of the lines.
[in]     numLines        Number of gridlines to draw.

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

### <a name="ViewportToTexCoordsXYWH"/>vec4 ViewportToTexCoordsXYWH(simul::crossplatform::Viewport vi, simul::crossplatform::Texture t)
Given a viewport struct and a texture, get the texture coordinates that viewport represents within the texture.

### <a name="ViewportToTexCoordsXYWH"/>vec4 ViewportToTexCoordsXYWH(int4 vi, simul::crossplatform::Texture t)
Given a viewport struct and a texture, get the texture coordinates that viewport represents within the texture.

Enums
---

**CullFaceMode**  < Enable the scissor rectangle for a viewport.

**DepthTextureStyle**  How to interpret the depth texture.

**FrontFace**  < Cull front and back faces.

**NearFarPass**  Values that represent what pass to render, be it the near pass, the far, or both: far to render target 0, near to render target 1.

**PixelFormat**  A cross-platform equivalent to the OpenGL and DirectX pixel formats

**PixelOutputFormat**  Pixel formats for pixel shader output - only relevant for some API's.

**PolygonMode**  < Counter-clockwise is front-facing.

**PolygonOffsetMode**  < Render polygons as solid/filled.

**RenderPlatformType**  Should correspond to UnityGfxRenderer

**ResourceTransition**  Type of resource transition, some platforms used this (dx12)

**ShaderBuildMode**  Tells the renderer what to do with shader source to get binaries. values can be combined, e.g. ALWAYS_BUILD|TRY_AGAIN_ON_FAIL

**ShaderResourceType**  This refers to the type of a shader resource, which should be compatible with the type of any resource assigned to it.

**ShaderType**  
OpenGL                                  |       Direct3D
-------------------------------------------
Vertex Shader                   |       Vertex Shader
Tessellation Control    |       Hull Shader
Tessellation Evaluation |       Domain Shader
Geometry Shader                 |       Geometry Shader
Fragment Shader                 |       Pixel Shader
Compute Shader                  |       Compute Shader


**Topology**  A cross-platform equivalent to the OpenGL and DirectX vertex topology formats
