---
title: crossplatform
layout: reference
weight: 0
---
namespace crossplatform
===

| Include: | Clouds/BaseGpuCloudGenerator.h |

The namespace and library for cross-platform base classes, which abstract rendering functionality.
  


Classes and Structures
---

| struct [AmortizationStruct](crossplatform/AmortizationStruct) |  |
| class [BaseFramebuffer](crossplatform/BaseFramebuffer) |  |
| class [BaseOpticsRenderer](crossplatform/BaseOpticsRenderer) |  |
| class [BaseRenderer](crossplatform/BaseRenderer) |  |
| class [Camera](crossplatform/Camera) |  |
| struct [CommandLineParams](crossplatform/CommandLineParams) |  |
| struct [ContextState](crossplatform/ContextState) |  |
| struct [DeviceContext](crossplatform/DeviceContext) |  |
| struct [DisjointQueryStruct](crossplatform/DisjointQueryStruct) |  |
| class [DisplaySurfaceManager](crossplatform/DisplaySurfaceManager) |  |
| class [Effect](crossplatform/Effect) |  |
| struct [EffectDefineOptions](crossplatform/EffectDefineOptions) |  |
| class [EffectTechniqueGroup](crossplatform/EffectTechniqueGroup) |  |
| struct [Frustum](crossplatform/Frustum) |  |
| class [GpuProfiler](crossplatform/GpuProfiler) |  |
| class [GpuProfilingInterface](crossplatform/GpuProfilingInterface) |  |
| class [GraphicsDeviceInterface](crossplatform/GraphicsDeviceInterface) |  |
| class [Layout](crossplatform/Layout) |  |
| struct [LayoutDesc](crossplatform/LayoutDesc) |  |
| class [LensFlare](crossplatform/LensFlare) |  |
| struct [MixedResolutionStruct](crossplatform/MixedResolutionStruct) |  |
| struct [MouseCameraInput](crossplatform/MouseCameraInput) |  |
| struct [MouseCameraState](crossplatform/MouseCameraState) |  |
| class [PlatformRendererInterface](crossplatform/PlatformRendererInterface) |  |
| class [PlatformStructuredBuffer](crossplatform/PlatformStructuredBuffer) |  |
| struct [PosColourVertex](crossplatform/PosColourVertex) |  |
| class [Quaterniond](crossplatform/Quaterniond) |  |
| struct [Query](crossplatform/Query) |  |
| class [RenderDelegater](crossplatform/RenderDelegater) |  |
| class [RenderPlatform](crossplatform/RenderPlatform) |  |
| struct [RenderStateDesc](crossplatform/RenderStateDesc) |  |
| struct [RenderTargetFormatDesc](crossplatform/RenderTargetFormatDesc) |  |
| struct [ShaderResource](crossplatform/ShaderResource) |  |
| class [SphericalHarmonics](crossplatform/SphericalHarmonics) |  |
| struct [TargetsAndViewport](crossplatform/TargetsAndViewport) |  |
| class [Texture](crossplatform/Texture) |  |
| class [TextureView](crossplatform/TextureView) |  |
| class [View](crossplatform/View) |  |
| class [ViewManager](crossplatform/ViewManager) |  |
| struct [Viewport](crossplatform/Viewport) |  |
| struct [ViewStruct](crossplatform/ViewStruct) |  |

Functions
---

| void | [DrawGrid](#DrawGrid)(simul::crossplatform::DeviceContext deviceContext, vec3 centrePos, float square_size, float brightness, int numLines) |
| void | [GetCameraPosVector](#GetCameraPosVector)(float v, float dcam_pos, float view_dir, float up) |
| float  const * | [GetCameraPosVector](#GetCameraPosVector)(float v) |
| void | [GetCommandLineParams](#GetCommandLineParams)(simul::crossplatform::CommandLineParams commandLineParams, int argCount, char szArgList) |
| void | [GetCommandLineParams](#GetCommandLineParams)(simul::crossplatform::CommandLineParams commandLineParams, int argCount, wchar_t szArgList) |
| simul::crossplatform::GpuProfilingInterface * | [GetGpuProfilingInterface](#GetGpuProfilingInterface)(simul::crossplatform::DeviceContext context) |
| void | [MakeCentredViewProjMatrix](#MakeCentredViewProjMatrix)(float vp, float view, float proj) |
| void | [MakeInvViewProjMatrix](#MakeInvViewProjMatrix)(float ivp, float v, float p) |
| void | [MakeInvWorldViewProjMatrix](#MakeInvWorldViewProjMatrix)(float ivp, float world, float v, float p) |
| void | [MakeViewProjMatrix](#MakeViewProjMatrix)(float vp, float view, float proj) |
| void | [MakeWorldViewProjMatrix](#MakeWorldViewProjMatrix)(float wvp, float world, float view, float proj) |
| void | [SetGpuProfilingInterface](#SetGpuProfilingInterface)(simul::crossplatform::DeviceContext context, simul::crossplatform::GpuProfilingInterface p) |
| vec4 | [ViewportToTexCoordsXYWH](#ViewportToTexCoordsXYWH)(simul::crossplatform::Viewport vi, simul::crossplatform::Texture t) |
| vec4 | [ViewportToTexCoordsXYWH](#ViewportToTexCoordsXYWH)(int4 vi, simul::crossplatform::Texture t) |

The namespace and library for cross-platform base classes, which abstract rendering functionality.
  


Functions
---

### <a name="DrawGrid"/>void DrawGrid(simul::crossplatform::DeviceContext deviceContext, vec3 centrePos, float square_size, float brightness, int numLines)
Draw a horizontal grid in 3D.


### <a name="GetCameraPosVector"/>void GetCameraPosVector(float v, float dcam_pos, float view_dir, float up)
Get the camera position, direction, and up-vector, from a view matrix v.

### <a name="GetCameraPosVector"/>float  const * GetCameraPosVector(float v)
Get the camera position from a view matrix.

### <a name="GetCommandLineParams"/>void GetCommandLineParams(simul::crossplatform::CommandLineParams commandLineParams, int argCount, char szArgList)
Convert the inputs to an executable into a CommandLineParams struct.

### <a name="GetCommandLineParams"/>void GetCommandLineParams(simul::crossplatform::CommandLineParams commandLineParams, int argCount, wchar_t szArgList)
Convert the inputs to an executable into a CommandLineParams struct.

### <a name="GetGpuProfilingInterface"/>simul::crossplatform::GpuProfilingInterface * GetGpuProfilingInterface(simul::crossplatform::DeviceContext context)
Returns a pointer to the current GPU profiler.

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

### <a name="SetGpuProfilingInterface"/>void SetGpuProfilingInterface(simul::crossplatform::DeviceContext context, simul::crossplatform::GpuProfilingInterface p)
Set the GPU profilerFuture use of SIMUL_GPU_PROFILE_START or SIMUL_COMBINED_PROFILE_START will use that profiler.

### <a name="ViewportToTexCoordsXYWH"/>vec4 ViewportToTexCoordsXYWH(simul::crossplatform::Viewport vi, simul::crossplatform::Texture t)
Given a viewport struct and a texture, get the texture coordinates that viewport represents within the texture.

### <a name="ViewportToTexCoordsXYWH"/>vec4 ViewportToTexCoordsXYWH(int4 vi, simul::crossplatform::Texture t)
Given a viewport struct and a texture, get the texture coordinates that viewport represents within the texture.

Enums
---

**DepthTextureStyle**  How to interpret the depth texture.

**NearFarPass**  Values that represent what pass to render, be it the near pass, the far, or both: far to render target 0, near to render target 1.

**PixelFormat**  A cross-platform equivalent to the OpenGL and DirectX pixel formats

**PixelOutputFormat**  Pixel formats for pixel shader output - only relevant for some API's.

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
