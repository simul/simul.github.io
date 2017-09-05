---
title: crossplatform
layout: reference
weight: 0
---
namespace crossplatform
===

| Include: | Sky/BaseAtmosphericsRenderer.h |

The namespace and library for cross-platform base classes, which abstract rendering functionality.


Classes and Structures
---

| struct [AmortizationStruct](crossplatform/AmortizationStruct) | A small structure for per-frame amortization of buffers. |
| class [BaseFramebuffer](crossplatform/BaseFramebuffer) | A base class for API-dependent framebuffer classes. |
| class [BaseOpticsRenderer](crossplatform/BaseOpticsRenderer) | A base class for rendering optical effects such as lens flare. |
| class [BaseRenderer](crossplatform/BaseRenderer) | The base class for renderers. Placeholder for now. |
| class [Camera](crossplatform/Camera) | A camera class. The orientation has the z-axis facing backwards, the x-axis right and the y-axis up. |
| struct [CommandLineParams](crossplatform/CommandLineParams) | A simple structure to store the command-line parameters for an executable. |
| struct [ContextState](crossplatform/ContextState) | A structure to describe the state that is associated with a given deviceContext.<br>When rendering is to be performed, we can ensure that the state is applied. |
| struct [DeviceContext](crossplatform/DeviceContext) | The base class for Device contexts. The actual context pointer is only applicable in DirectX - in OpenGL, it will be null.<br>The DeviceContext also carries a pointer to the platform-specific RenderPlatform.<br>DeviceContext is context in the DirectX11 sense, encompassing a platform-specific deviceContext pointer |
| struct [DisjointQueryStruct](crossplatform/DisjointQueryStruct) | A disjoint query structure, like those in DirectX 11.<br>Its main use is actually to get the clock frequency that will<br>be used for timestamp queries, but the Disjoint value is<br>used on some platforms to indicate whether the timestamp values are invalid. |
| class [Effect](crossplatform/Effect) | The cross-platform base class for shader effects. |
| struct [EffectDefineOptions](crossplatform/EffectDefineOptions) | A crossplatform structure for a \#define and its possible values.<br>This allows all of the macro combinations to be built to binary. |
| class [EffectTechniqueGroup](crossplatform/EffectTechniqueGroup) | Crossplatform equivalent of D3DXEffectGroup - a named group of techniques. |
| struct [Frustum](crossplatform/Frustum) | A useful class to represent a view frustum. |
| class [GpuProfiler](crossplatform/GpuProfiler) | The Simul GPU profiler. Usage is as follows:<br> |
| class [GpuProfilingInterface](crossplatform/GpuProfilingInterface) | A virtual interface base class for GPU performance measurement. |
| class [GraphicsDeviceInterface](crossplatform/GraphicsDeviceInterface) | An interface class for managing GPU-accelerated graphics windows.<br>The derived class |
| class [Layout](crossplatform/Layout) | A cross-platform class representing vertex input layouts. Create with RenderPlatform::CreateLayout. |
| struct [LayoutDesc](crossplatform/LayoutDesc) | A cross-platform equivalent to D3D11_INPUT_ELEMENT_DESC, used<br>to create layouts. MEMBERS: const char *semanticName,int semanticIndex, PixelFormat     format, int inputSlot,  int alignedByteOffset,  bool perInstance,int instanceDataStepRate |
| class [LensFlare](crossplatform/LensFlare) | A helpful class to calculate lens flares. |
| struct [MixedResolutionStruct](crossplatform/MixedResolutionStruct) | A structure to translate between buffers of different resolutions. |
| struct [MouseCameraInput](crossplatform/MouseCameraInput) | A struct to provide input to a mouse-controlled camera.<br>Store persistently, as it needs to use the difference between current<br>and previous mouse positions. |
| struct [MouseCameraState](crossplatform/MouseCameraState) | A struct to represent the state of a mouse-controlled camera. |
| class [PlatformRendererInterface](crossplatform/PlatformRendererInterface) | This represents an interface that faces the raw API.<br>The implementing class should keep a list of integer view id's |
| class [PlatformStructuredBuffer](crossplatform/PlatformStructuredBuffer) | A base class for structured buffers, used by StructuredBuffer internally. |
| struct [PosColourVertex](crossplatform/PosColourVertex) | A vertex format for debugging. |
| class [Quaterniond](crossplatform/Quaterniond) | Quaterniond class to represent rotations. |
| struct [Query](crossplatform/Query) | Crossplatform GPU query class. |
| class [RenderPlatform](crossplatform/RenderPlatform) | RenderPlatform is an interface that allows Simul's rendering functions to be developed<br>        in a cross-platform manner. By abstracting the common functionality of the different graphics API's<br>        into an interface, we can write render code that need not know which API is being used. It is possible<br>        to create platform-specific objects like /link CreateTexture textures/endlink, /link CreateEffect effects/endlink<br>        and /link CreateBuffer buffers/endlink<br> |
| struct [RenderStateDesc](crossplatform/RenderStateDesc) | An initialization structure for a RenderState. Create a RenderStateDesc and pass it to RenderPlatform::CreateRenderState,<br>then store the returned pointer. Delete the pointer when done. |
| class [Texture](crossplatform/Texture) | A Texture base class. |
| struct [TextureAssignment](crossplatform/TextureAssignment) | A base class for API-specific rendering. |
| class [TextureView](crossplatform/TextureView) | Base class for a view of a texture (i.e. for shaders to use). TextureView instances should not be created, except inside derived classes of crossplatform::Texture. |
| class [View](crossplatform/View) | A class that encapsulates the generated mixed-resolution depth textures, and (optionally) a framebuffer with colour and depth.<br>One instance of View will be created and maintained for each live 3D view. |
| class [ViewManager](crossplatform/ViewManager) | A class to store a set of View objects, one per view id. |
| struct [Viewport](crossplatform/Viewport) | A crossplatform viewport structure. |
| struct [ViewStruct](crossplatform/ViewStruct) | A simple struct encapsulating a view and a projection matrix. |

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

The namespace and library for cross-platform base classes, which abstract rendering functionality.
  


Functions
---

### <a name="DrawGrid"/>void DrawGrid(simul::crossplatform::DeviceContext deviceContext, vec3 centrePos, float square_size, float brightness, int numLines)
Draw a horizontal grid in 3D.

\param [in,out] deviceContext   Context for the device.
\param [in]     centrePos       Origin of the grid in 3D.
\param [in]     square_size     Spacing between lines - in whatever units the renderer is working in.
\param [in]     brightness      Brightness of the lines.
\param [in]     numLines        Number of gridlines to draw.

### <a name="GetCameraPosVector"/>void GetCameraPosVector(float v, float dcam_pos, float view_dir, float up)
Get the camera position, direction, and up-vector, from a view matrix v.
Get the camera position, direction, and up-vector, from a view matrix v.

### <a name="GetCameraPosVector"/>float  const * GetCameraPosVector(float v)
Get the camera position from a view matrix.
Get the camera position from a view matrix.

### <a name="GetCommandLineParams"/>void GetCommandLineParams(simul::crossplatform::CommandLineParams commandLineParams, int argCount, char szArgList)
Convert the inputs to an executable into a CommandLineParams struct.
Convert the inputs to an executable into a CommandLineParams struct.

### <a name="GetCommandLineParams"/>void GetCommandLineParams(simul::crossplatform::CommandLineParams commandLineParams, int argCount, wchar_t szArgList)
Convert the inputs to an executable into a CommandLineParams struct.
Convert the inputs to an executable into a CommandLineParams struct.

### <a name="GetGpuProfilingInterface"/>simul::crossplatform::GpuProfilingInterface * GetGpuProfilingInterface(simul::crossplatform::DeviceContext context)
Returns a pointer to the current GPU profiler.
Returns a pointer to the current GPU profiler.

### <a name="MakeCentredViewProjMatrix"/>void MakeCentredViewProjMatrix(float vp, float view, float proj)
Make a viewProj matrix, but ignore the view position.
Make a viewProj matrix, but ignore the view position.

### <a name="MakeInvViewProjMatrix"/>void MakeInvViewProjMatrix(float ivp, float v, float p)
Make an inverse viewProj matrix, which converts clip position to worldspace direction.
Make an inverse viewProj matrix, which converts clip position to worldspace direction.

### <a name="MakeInvWorldViewProjMatrix"/>void MakeInvWorldViewProjMatrix(float ivp, float world, float v, float p)
Make an inverse worldViewProj matrix, which converts clip position to worldspace direction.
Make an inverse worldViewProj matrix, which converts clip position to worldspace direction.

### <a name="MakeViewProjMatrix"/>void MakeViewProjMatrix(float vp, float view, float proj)
Make a viewProj matrix, which converts worldspace into clip position.
Make a viewProj matrix, which converts worldspace into clip position.

### <a name="MakeWorldViewProjMatrix"/>void MakeWorldViewProjMatrix(float wvp, float world, float view, float proj)
Make a worldViewProj matrix.
Make a worldViewProj matrix.

### <a name="SetGpuProfilingInterface"/>void SetGpuProfilingInterface(simul::crossplatform::DeviceContext context, simul::crossplatform::GpuProfilingInterface p)
Set the GPU profilerFuture use of SIMUL_GPU_PROFILE_START or SIMUL_COMBINED_PROFILE_START will use that profiler.
Set the GPU profilerFuture use of SIMUL_GPU_PROFILE_START or SIMUL_COMBINED_PROFILE_START will use that profiler.

### <a name="ViewportToTexCoordsXYWH"/>vec4 ViewportToTexCoordsXYWH(simul::crossplatform::Viewport vi, simul::crossplatform::Texture t)
Given a viewport struct and a texture, get the texture coordinates that viewport represents within the texture.
Given a viewport struct and a texture, get the texture coordinates that viewport represents within the texture.

Enums
---

**DepthTextureStyle** How to interpret the depth texture. How to interpret the depth texture.

**NearFarPass** Values that represent what pass to render, be it the near pass, the far, or both: far to render target 0, near to render target 1. Values that represent what pass to render, be it the near pass, the far, or both: far to render target 0, near to render target 1.

**PixelFormat** A cross-platform equivalent to the OpenGL and DirectX pixel formats A cross-platform equivalent to the OpenGL and DirectX pixel formats

**PixelOutputFormat** Pixel formats for pixel shader output - only relevant for some API's. Pixel formats for pixel shader output - only relevant for some API's.

**ShaderBuildMode** Tells the renderer what to do with shader source to get binaries. values can be combined, e.g. ALWAYS_BUILD|TRY_AGAIN_ON_FAIL Tells the renderer what to do with shader source to get binaries. values can be combined, e.g. ALWAYS_BUILD|TRY_AGAIN_ON_FAIL

**ShaderResourceType** This refers to the type of a shader resource, which should be compatible with the type of any resource assigned to it. This refers to the type of a shader resource, which should be compatible with the type of any resource assigned to it.

**ShaderType** OpenGL                                  |       Direct3D
                -------------------------------------------
                Vertex Shader                   |       Vertex Shader
                Tessellation Control    |       Hull Shader
                Tessellation Evaluation |       Domain Shader
                Geometry Shader                 |       Geometry Shader
                Fragment Shader                 |       Pixel Shader
                Compute Shader                  |       Compute Shader
 
		OpenGL					|	Direct3D
		-------------------------------------------
		Vertex Shader			|	Vertex Shader
		Tessellation Control	|	Hull Shader
		Tessellation Evaluation	|	Domain Shader
		Geometry Shader			|	Geometry Shader
		Fragment Shader			|	Pixel Shader
		Compute Shader			|	Compute Shader


**Topology** A cross-platform equivalent to the OpenGL and DirectX vertex topology formats A cross-platform equivalent to the OpenGL and DirectX vertex topology formats
