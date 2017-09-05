---
title: TrueSkyRenderer
layout: reference
weight: 0
---
class TrueSkyRenderer
===

| Include: | Clouds/TrueSkyRenderer.h |




  

[simul::crossplatform::BaseRenderer](../crossplatform/BaseRenderer)

Functions
---

| bool | [CopySkylight](#CopySkylight)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture targetTexture, float targetShValues, int shOrder, mat4 engineToSimulMatrix4x4, int updateFrequency, float blend) |
| void | [EnsureSkylight](#EnsureSkylight)(int cubemap_view_id, int size, int mips, simul::crossplatform::PixelFormat format, mat4 cubeToSimulMatrix, int shOrder, int updateFrequency, float blend) |
| void | [SetAmortization](#SetAmortization)(int view_id, int a) |
| void | [RenderMixedResolutionSky](#RenderMixedResolutionSky)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture, simul::crossplatform::Viewport depthViewport, float exposure, float gamma, float brightnessToUnity) |
| void | [RenderTransparentTest](#RenderTransparentTest)(simul::crossplatform::DeviceContext deviceContext) |




  


Base Classes
---
[simul::crossplatform::BaseRenderer](../crossplatform/BaseRenderer)

Functions
---

### <a name="CopySkylight"/>bool CopySkylight(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture targetTexture, float targetShValues, int shOrder, mat4 engineToSimulMatrix4x4, int updateFrequency, float blend)
Update the specified texture as a cubemap, and its spherical harmonics.
Copy the specified skylight into the target texture. This texture MUST be the same size, format and mip count as
was specified for this cubemap id when GetSkylight was called.
This function has latency depending on the platform.
Update the specified texture as a cubemap, and its spherical harmonics.
Copy the specified skylight into the target texture. This texture MUST be the same size, format and mip count as
was specified for this cubemap id when GetSkylight was called.
This function has latency depending on the platform.

### <a name="EnsureSkylight"/>void EnsureSkylight(int cubemap_view_id, int size, int mips, simul::crossplatform::PixelFormat format, mat4 cubeToSimulMatrix, int shOrder, int updateFrequency, float blend)
Create or update a skylight. You can pass a unique view id to this.
Create or update a skylight. You can pass a unique view id to this.

### <a name="SetAmortization"/>void SetAmortization(int view_id, int a)
How often to update each cloud texel; 1:always, 2:every 4 frames, n:every n^2 frames.
How often to update each cloud texel; 1:always, 2:every 4 frames, n:every n^2 frames.

### <a name="RenderMixedResolutionSky"/>void RenderMixedResolutionSky(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture, simul::crossplatform::Viewport depthViewport, float exposure, float gamma, float brightnessToUnity)
Render the sky.
Render the sky.

### <a name="RenderTransparentTest"/>void RenderTransparentTest(simul::crossplatform::DeviceContext deviceContext)
//////////////////
//////////////////

Fields
---

**ReferenceSpectralRadiance** Spectral radiance at r,g,b for output colour value 1.0. Multiply by output colour to get the real spectral radiance. Spectral radiance at r,g,b for output colour value 1.0. Multiply by output colour to get the real spectral radiance.
