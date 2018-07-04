---
title: DeviceContext
layout: reference
weight: 0
---
struct DeviceContext
===

| Include: | Clouds/BaseLightningRenderer.h |

The base class for Device contexts. The actual context pointer is only applicable in DirectX - in OpenGL, it will be null.
The DeviceContext also carries a pointer to the platform-specific RenderPlatform.
DeviceContext is context in the DirectX11 sense, encompassing a platform-specific deviceContext pointer
  


Functions
---

| void | [setDefaultRenderTargets](#setDefaultRenderTargets)(simul::crossplatform::ApiRenderTarget, simul::crossplatform::ApiDepthRenderTarget, uint32_t viewportLeft, uint32_t viewportTop, uint32_t viewportRight, uint32_t viewportBottom) |

The base class for Device contexts. The actual context pointer is only applicable in DirectX - in OpenGL, it will be null.
The DeviceContext also carries a pointer to the platform-specific RenderPlatform.
DeviceContext is context in the DirectX11 sense, encompassing a platform-specific deviceContext pointer
  


Functions
---

### <a name="setDefaultRenderTargets"/>void setDefaultRenderTargets(simul::crossplatform::ApiRenderTarget, simul::crossplatform::ApiDepthRenderTarget, uint32_t viewportLeft, uint32_t viewportTop, uint32_t viewportRight, uint32_t viewportBottom)
Set the RT's to restore to, once all Simul Framebuffers are deactivated. This must be called at least once,
as
