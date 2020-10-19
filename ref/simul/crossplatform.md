---
title: crossplatform
layout: reference
weight: 0
---
namespace crossplatform
===

| Include: | Sky/BaseAtmosphericsRenderer.h |



Classes and Structures
---

| class [BaseRenderer](crossplatform/baserenderer.html) |  |
| struct [CommandLineParams](crossplatform/commandlineparams.html) |  |
| struct [ContextState](crossplatform/contextstate.html) |  |
| struct [DisjointQueryStruct](crossplatform/disjointquerystruct.html) |  |
| class [DisplaySurfaceManager](crossplatform/displaysurfacemanager.html) |  |
| struct [EffectDefineOptions](crossplatform/effectdefineoptions.html) |  |
| class [EffectTechniqueGroup](crossplatform/effecttechniquegroup.html) |  |
| struct [Frustum](crossplatform/frustum.html) |  |
| class [GpuProfiler](crossplatform/gpuprofiler.html) |  |
| class [GpuProfilingInterface](crossplatform/gpuprofilinginterface.html) |  |
| class [GraphicsDeviceInterface](crossplatform/graphicsdeviceinterface.html) |  |
| struct [LayoutDesc](crossplatform/layoutdesc.html) |  |
| class [LensFlare](crossplatform/lensflare.html) |  |
| struct [MixedResolutionStruct](crossplatform/mixedresolutionstruct.html) |  |
| struct [MouseCameraInput](crossplatform/mousecamerainput.html) |  |
| struct [MouseCameraState](crossplatform/mousecamerastate.html) |  |
| class [PlatformRendererInterface](crossplatform/platformrendererinterface.html) |  |
| struct [RasterizerDesc](crossplatform/rasterizerdesc.html) |  |
| class [RenderDelegater](crossplatform/renderdelegater.html) |  |
| struct [RenderStateDesc](crossplatform/renderstatedesc.html) |  |
| struct [RenderTargetFormatDesc](crossplatform/rendertargetformatdesc.html) |  |
| struct [ShaderResource](crossplatform/shaderresource.html) |  |
| class [SphericalHarmonics](crossplatform/sphericalharmonics.html) |  |
| class [TextRenderer](crossplatform/textrenderer.html) |  |
| struct [TextureCreate](crossplatform/texturecreate.html) |  |
| class [TextureView](crossplatform/textureview.html) |  |
| class [View](crossplatform/view.html) |  |
| class [ViewManager](crossplatform/viewmanager.html) |  |

Functions
---

| void | [DrawGrid](#DrawGrid)(simul::crossplatform::GraphicsDeviceContext deviceContext, vec3 centrePos, float square_size, float brightness, int numLines) |
| void | [GetCameraPosVector](#GetCameraPosVector)(float v, float dcam_pos, float view_dir, float up) |
| float  const * | [GetCameraPosVector](#GetCameraPosVector)(float v) |
| void | [MakeCentredViewProjMatrix](#MakeCentredViewProjMatrix)(float vp, float view, float proj) |
| void | [MakeInvViewProjMatrix](#MakeInvViewProjMatrix)(float ivp, float v, float p) |
| void | [MakeInvWorldViewProjMatrix](#MakeInvWorldViewProjMatrix)(float ivp, float world, float v, float p) |
| void | [MakeViewProjMatrix](#MakeViewProjMatrix)(float vp, float view, float proj) |
| void | [MakeWorldViewProjMatrix](#MakeWorldViewProjMatrix)(float wvp, float world, float view, float proj) |
| void | [Multiply](#Multiply)(vec3d ret, simul::crossplatform::Quaterniond q, vec3d v) |
| vec4 | [ViewportToTexCoordsXYWH](#ViewportToTexCoordsXYWH)(simul::crossplatform::Viewport vi, simul::crossplatform::Texture t) |
| vec4 | [ViewportToTexCoordsXYWH](#ViewportToTexCoordsXYWH)(int4 vi, simul::crossplatform::Texture t) |


Functions
---
<a name="DrawGrid"></a>
### void DrawGrid(simul::crossplatform::GraphicsDeviceContext deviceContext, vec3 centrePos, float square_size, float brightness, int numLines)
Draw a horizontal grid in 3D.

[in,out] deviceContext   Context for the device.
[in]     centrePos       Origin of the grid in 3D.
[in]     square_size     Spacing between lines - in whatever units the renderer is working in.
[in]     brightness      Brightness of the lines.
[in]     numLines        Number of gridlines to draw.
<a name="GetCameraPosVector"></a>
### void GetCameraPosVector(float v, float dcam_pos, float view_dir, float up)
Get the camera position, direction, and up-vector, from a view matrix v.
<a name="GetCameraPosVector"></a>
### float  const * GetCameraPosVector(float v)
Get the camera position from a view matrix.
<a name="MakeCentredViewProjMatrix"></a>
### void MakeCentredViewProjMatrix(float vp, float view, float proj)
Make a viewProj matrix, but ignore the view position.
<a name="MakeInvViewProjMatrix"></a>
### void MakeInvViewProjMatrix(float ivp, float v, float p)
Make an inverse viewProj matrix, which converts clip position to worldspace direction.
<a name="MakeInvWorldViewProjMatrix"></a>
### void MakeInvWorldViewProjMatrix(float ivp, float world, float v, float p)
Make an inverse worldViewProj matrix, which converts clip position to worldspace direction.
<a name="MakeViewProjMatrix"></a>
### void MakeViewProjMatrix(float vp, float view, float proj)
Make a viewProj matrix, which converts worldspace into clip position.
<a name="MakeWorldViewProjMatrix"></a>
### void MakeWorldViewProjMatrix(float wvp, float world, float view, float proj)
Make a worldViewProj matrix.
<a name="Multiply"></a>
### void Multiply(vec3d ret, simul::crossplatform::Quaterniond q, vec3d v)
Multiply, or rotate, vec3d v by q, return the value in vec3d ret. v and ret must have size 3.
<a name="ViewportToTexCoordsXYWH"></a>
### vec4 ViewportToTexCoordsXYWH(simul::crossplatform::Viewport vi, simul::crossplatform::Texture t)
Given a viewport struct and a texture, get the texture coordinates that viewport represents within the texture.
<a name="ViewportToTexCoordsXYWH"></a>
### vec4 ViewportToTexCoordsXYWH(int4 vi, simul::crossplatform::Texture t)
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
