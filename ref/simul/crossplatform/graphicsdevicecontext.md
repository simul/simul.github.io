---
title: GraphicsDeviceContext
layout: reference
weight: 0
---
struct GraphicsDeviceContext
===

| Include: | Platform/CrossPlatform/DemoOverlay.h |


[simul::crossplatform::DeviceContext](devicecontext.html)

Functions
---

| simul::crossplatform::GraphicsDeviceContext * | [AsGraphicsDeviceContext](#AsGraphicsDeviceContext)() |
| void | [setDefaultRenderTargets](#setDefaultRenderTargets)(simul::crossplatform::ApiRenderTarget, simul::crossplatform::ApiDepthRenderTarget, uint32_t viewportLeft, uint32_t viewportTop, uint32_t viewportRight, uint32_t viewportBottom, simul::crossplatform::Texture texture_targets, int num_targets, simul::crossplatform::Texture depth_target) |


Base Classes
---
[simul::crossplatform::DeviceContext](devicecontext.html)

Functions
---
<a name="AsGraphicsDeviceContext"></a>
### simul::crossplatform::GraphicsDeviceContext * AsGraphicsDeviceContext()
The base class for Device contexts. The actual context pointer is only applicable in DirectX - in OpenGL, it will be null.
The DeviceContext also carries a pointer to the platform-specific RenderPlatform.
DeviceContext is context in the DirectX11 sense, encompassing a platform-specific deviceContext pointer
<a name="setDefaultRenderTargets"></a>
### void setDefaultRenderTargets(simul::crossplatform::ApiRenderTarget, simul::crossplatform::ApiDepthRenderTarget, uint32_t viewportLeft, uint32_t viewportTop, uint32_t viewportRight, uint32_t viewportBottom, simul::crossplatform::Texture texture_targets, int num_targets, simul::crossplatform::Texture depth_target)
Set the RT's to restore to, once all Simul Framebuffers are deactivated. This must be called at least once,
as
