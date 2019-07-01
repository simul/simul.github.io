---
title: DeviceContext
layout: reference
weight: 0
---
struct DeviceContext
===

| Include: | Platform/CrossPlatform/DemoOverlay.h |



Functions
---

| void | [setDefaultRenderTargets](#setDefaultRenderTargets)(simul::crossplatform::ApiRenderTarget, simul::crossplatform::ApiDepthRenderTarget, uint32_t viewportLeft, uint32_t viewportTop, uint32_t viewportRight, uint32_t viewportBottom, simul::crossplatform::Texture texture_targets, int num_targets, simul::crossplatform::Texture depth_target) |
| simul::crossplatform::GpuProfilingInterface * | [GetGpuProfilingInterface](#GetGpuProfilingInterface)(simul::crossplatform::DeviceContext context) |
| void | [SetGpuProfilingInterface](#SetGpuProfilingInterface)(simul::crossplatform::DeviceContext context, simul::crossplatform::GpuProfilingInterface p) |


Functions
---

### <a name="setDefaultRenderTargets"/>void setDefaultRenderTargets(simul::crossplatform::ApiRenderTarget, simul::crossplatform::ApiDepthRenderTarget, uint32_t viewportLeft, uint32_t viewportTop, uint32_t viewportRight, uint32_t viewportBottom, simul::crossplatform::Texture texture_targets, int num_targets, simul::crossplatform::Texture depth_target)
Set the RT's to restore to, once all Simul Framebuffers are deactivated. This must be called at least once,
as

### <a name="GetGpuProfilingInterface"/>simul::crossplatform::GpuProfilingInterface * GetGpuProfilingInterface(simul::crossplatform::DeviceContext context)
Returns a pointer to the current GPU profiler.

### <a name="SetGpuProfilingInterface"/>void SetGpuProfilingInterface(simul::crossplatform::DeviceContext context, simul::crossplatform::GpuProfilingInterface p)
Set the GPU profilerFuture use of SIMUL_GPU_PROFILE_START or SIMUL_COMBINED_PROFILE_START will use that profiler.

Fields
---

**platform_context**  The base class for Device contexts. The actual context pointer is only applicable in DirectX - in OpenGL, it will be null.
The DeviceContext also carries a pointer to the platform-specific RenderPlatform.
DeviceContext is context in the DirectX11 sense, encompassing a platform-specific deviceContext pointer
