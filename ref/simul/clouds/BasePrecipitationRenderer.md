---
title: BasePrecipitationRenderer
layout: reference
weight: 0
---
class BasePrecipitationRenderer
===

| Include: | Clouds/BasePrecipitationRenderer.h |

The class that renders rain and snow.


Functions
---

| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [New](#New)() |
| void | [PreRenderUpdate](#PreRenderUpdate)(simul::crossplatform::DeviceContext deviceContext, float dt_seconds) |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [Render](#Render)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depth_tex, simul::crossplatform::Texture cubemapTexture, float max_fade_distance_metres, vec4 viewportTextureRegionXYWH, vec3 sunlight, vec3 moonlight, simul::clouds::RainMethod rainMethod, double time) |
| void | [RenderOverlay](#RenderOverlay)(simul::crossplatform::DeviceContext deviceContext, int x0, int y0, int dx, int dy) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform renderPlatform) |
| void | [SetRandomTexture3D](#SetRandomTexture3D)(simul::crossplatform::Texture texture) |
| void | [SetWind](#SetWind)(float speed, float heading_degrees) |

The class that renders rain and snow.
  


Functions
---

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Free any API-dependent objects allocated.
Free any API-dependent objects allocated.

### <a name="New"/>void New()
Clear the data()
Clear the data()

### <a name="PreRenderUpdate"/>void PreRenderUpdate(simul::crossplatform::DeviceContext deviceContext, float dt_seconds)
Call this once per frame to update the rain.
Call this once per frame to update the rain.

### <a name="RecompileShaders"/>void RecompileShaders()
Recompile any API-dependent shaders - used internally and useful for debugging.
Recompile any API-dependent shaders - used internally and useful for debugging.

### <a name="Render"/>void Render(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depth_tex, simul::crossplatform::Texture cubemapTexture, float max_fade_distance_metres, vec4 viewportTextureRegionXYWH, vec3 sunlight, vec3 moonlight, simul::clouds::RainMethod rainMethod, double time)
Call this to draw precipitation.
Call this to draw precipitation.

### <a name="RenderOverlay"/>void RenderOverlay(simul::crossplatform::DeviceContext deviceContext, int x0, int y0, int dx, int dy)
Show the textures onscreen for debugging.
Show the textures onscreen for debugging.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform renderPlatform)
Create the API-dependent objects.
Create the API-dependent objects.

### <a name="SetRandomTexture3D"/>void SetRandomTexture3D(simul::crossplatform::Texture texture)
Provide a random 3D texture. This is set externally so the texture can be shared.
Provide a random 3D texture. This is set externally so the texture can be shared.

### <a name="SetWind"/>void SetWind(float speed, float heading_degrees)
Set the wind velocity.
Set the wind velocity.
