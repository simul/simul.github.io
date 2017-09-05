---
title: Skylight
layout: reference
weight: 0
---
class Skylight
===

| Include: | Clouds/Skylight.h |

A class to capture light from the sky in real time for diffuse and specular lighting.


Functions
---

| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [Render](#Render)(simul::crossplatform::DeviceContext parentDeviceContext, simul::clouds::BaseWeatherRenderer baseWeatherRenderer, int cube_id, simul::crossplatform::BaseFramebuffer fb, int faceIndex, mat4 engineToSimulMatrix4x4, float blend, float exposure, float gamma) |
| void | [RenderEnvmap](#RenderEnvmap)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::BaseFramebuffer fb_target, int cubemapIndex) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform r) |
| void | [ShowDebug](#ShowDebug)(simul::crossplatform::DeviceContext deviceContext, int X, int Y, int w) |
| void | [Update](#Update)(simul::crossplatform::DeviceContext deviceContext, simul::clouds::BaseWeatherRenderer weatherRenderer, float exposure, float gamma) |

A class to capture light from the sky in real time for diffuse and specular lighting.
  


Functions
---

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Free the GPU objects.
Free the GPU objects.

### <a name="RecompileShaders"/>void RecompileShaders()
Recompile the shaders for this class.
Recompile the shaders for this class.

### <a name="Render"/>void Render(simul::crossplatform::DeviceContext parentDeviceContext, simul::clouds::BaseWeatherRenderer baseWeatherRenderer, int cube_id, simul::crossplatform::BaseFramebuffer fb, int faceIndex, mat4 engineToSimulMatrix4x4, float blend, float exposure, float gamma)
Fill in the texture.
Fill in the texture.

### <a name="RenderEnvmap"/>void RenderEnvmap(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::BaseFramebuffer fb_target, int cubemapIndex)
Draw a diffuse environment map to the specified framebuffer.
Draw a diffuse environment map to the specified framebuffer.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform r)
Initialize GPU objects.
Initialize GPU objects.

### <a name="ShowDebug"/>void ShowDebug(simul::crossplatform::DeviceContext deviceContext, int X, int Y, int w)
Show debug displays onscreen.
Show debug displays onscreen.

### <a name="Update"/>void Update(simul::crossplatform::DeviceContext deviceContext, simul::clouds::BaseWeatherRenderer weatherRenderer, float exposure, float gamma)
Update the skylight per-frame.
Update the skylight per-frame.
