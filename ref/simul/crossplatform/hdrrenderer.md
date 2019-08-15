---
title: HdrRenderer
layout: reference
weight: 0
---
class HdrRenderer
===

| Include: | Clouds/TrueSkyRenderer.h |



Functions
---

| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [Render](#Render)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture texture, float Exposure, float Gamma, float offsetX) |
| void | [RenderDebug](#RenderDebug)(simul::crossplatform::DeviceContext deviceContext, int x0, int y0, int w, int h) |
| void | [RenderGlowTexture](#RenderGlowTexture)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture texture) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform r) |


Functions
---
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the HDR renderer.
<a name="Render"></a>
### void Render(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture texture, float Exposure, float Gamma, float offsetX)
Render: write the given texture to screen using the HDR rendering shaders
<a name="RenderDebug"></a>
### void RenderDebug(simul::crossplatform::DeviceContext deviceContext, int x0, int y0, int w, int h)
Draw the debug textures
<a name="RenderGlowTexture"></a>
### void RenderGlowTexture(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture texture)
Create the glow texture that will be overlaid due to strong lights.
<a name="RestoreDeviceObjects"></a>
### void RestoreDeviceObjects(simul::crossplatform::RenderPlatform r)
Platform-dependent function called when initializing the HDR renderer.

Fields
---

**hdr_effect**  The HDR tonemapping hlsl effect used to render the hdr buffer to an ldr screen.
