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
| void | [RenderGlowTexture](#RenderGlowTexture)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture texture) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform r) |


Functions
---

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Call this when the device has been lost.
Call this when the device has been lost.

### <a name="Render"/>void Render(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture texture, float Exposure, float Gamma, float offsetX)
Render: write the given texture to screen using the HDR rendering shaders
Render: write the given texture to screen using the HDR rendering shaders

### <a name="RenderGlowTexture"/>void RenderGlowTexture(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture texture)
Create the glow texture that will be overlaid due to strong lights.
Create the glow texture that will be overlaid due to strong lights.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform r)
Call when we've got a fresh device - on startup or when the device has been restored.
Call when we've got a fresh device - on startup or when the device has been restored.

Fields
---

**hdr_effect** The HDR tonemapping hlsl effect used to render the hdr buffer to an ldr screen. The HDR tonemapping hlsl effect used to render the hdr buffer to an ldr screen.
