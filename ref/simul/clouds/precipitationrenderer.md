---
title: PrecipitationRenderer
layout: reference
weight: 0
---
class PrecipitationRenderer
===

| Include: | Clouds/PrecipitationRenderer.h |

The class that renders rain and snow.
  


Functions
---

|  | [PrecipitationRenderer](#PrecipitationRenderer)() |
|  | [~PrecipitationRenderer](#~PrecipitationRenderer)() |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [New](#New)() |
| void | [PreRenderUpdate](#PreRenderUpdate)(simul::crossplatform::DeviceContext deviceContext, float dt_seconds) |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [Render](#Render)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depth_tex, simul::crossplatform::Texture cubemapTexture, float max_fade_distance_metres, vec4 viewportTextureRegionXYWH, vec3 sunlight, vec3 moonlight, simul::clouds::RainMethod rainMethod, float time, bool write_blend_alpha) |
| void | [RenderOverlay](#RenderOverlay)(simul::crossplatform::DeviceContext deviceContext, int x0, int y0, int dx, int dy) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform renderPlatform) |
| void | [SetBaseSkyInterface](#SetBaseSkyInterface)(simul::sky::BaseSkyInterface s) |
| void | [SetRainDepthTextureScale](#SetRainDepthTextureScale)(float s) |
| void | [SetRandomTexture3D](#SetRandomTexture3D)(simul::crossplatform::Texture texture) |
| void | [SetWind](#SetWind)(float speed, float heading_degrees) |

The class that renders rain and snow.
  


Functions
---

### <a name="PrecipitationRenderer"/> PrecipitationRenderer()
Constructor

### <a name="~PrecipitationRenderer"/> ~PrecipitationRenderer()
Destructor

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the precipitation renderer.

### <a name="New"/>void New()
Clear the data()

### <a name="PreRenderUpdate"/>void PreRenderUpdate(simul::crossplatform::DeviceContext deviceContext, float dt_seconds)
Once per-frame update. Do this before any rendering each frame.

### <a name="RecompileShaders"/>void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.

### <a name="Render"/>void Render(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depth_tex, simul::crossplatform::Texture cubemapTexture, float max_fade_distance_metres, vec4 viewportTextureRegionXYWH, vec3 sunlight, vec3 moonlight, simul::clouds::RainMethod rainMethod, float time, bool write_blend_alpha)
Call this to draw precipitation.

### <a name="RenderOverlay"/>void RenderOverlay(simul::crossplatform::DeviceContext deviceContext, int x0, int y0, int dx, int dy)
Show the textures onscreen for debugging.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform renderPlatform)
Platform-dependent function called when initializing the precipitation renderer.

### <a name="SetBaseSkyInterface"/>void SetBaseSkyInterface(simul::sky::BaseSkyInterface s)
Set the sky and atmospherics interface.

### <a name="SetRainDepthTextureScale"/>void SetRainDepthTextureScale(float s)
Set the scale of the rain depth texture to normalize it to [0,1]

### <a name="SetRandomTexture3D"/>void SetRandomTexture3D(simul::crossplatform::Texture texture)
Provide a random 3D texture. This is set externally so the texture can be shared.

### <a name="SetWind"/>void SetWind(float speed, float heading_degrees)
Set the wind velocity.
