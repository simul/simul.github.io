---
title: TrueSkyRenderer
layout: reference
weight: 0
---
class TrueSkyRenderer
===

| Include: | Clouds/TrueSkyRenderer.h |

<br>

[simul::crossplatform::BaseRenderer](../crossplatform/baserenderer)

Functions
---

| void | [CleanupOldAllocations](#CleanupOldAllocations)(int max_age) |
| bool | [CopySkylight](#CopySkylight)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture targetTexture, float targetShValues, int shOrder, mat4 engineToSimulMatrix4x4, int updateFrequency, float blend, float exposure, float gamma, vec3 ground_colour, int amortization, bool allFaces, bool allMips) |
| void | [EnsureEffectsAreBuilt](#EnsureEffectsAreBuilt)(simul::crossplatform::RenderPlatform r) |
| void | [EnsureSkylight](#EnsureSkylight)(int cubemap_view_id, int size, int mips, simul::crossplatform::PixelFormat format, mat4 cubeToSimulMatrix, int shOrder, int updateFrequency, float blend, float exposure, float gamma, vec3 ground_colour, int amortization, bool allFaces, bool allMips) |
| int | [GetAmortization](#GetAmortization)(int view_id) |
| simul::scene::BaseSceneRenderer * | [GetSceneRenderer](#GetSceneRenderer)() |
| simul::crossplatform::HdrRenderer * | [GetSimulHDRRenderer](#GetSimulHDRRenderer)() |
| simul::clouds::BaseWeatherRenderer * | [GetSimulWeatherRenderer](#GetSimulWeatherRenderer)() |
| simul::terrain::BaseTerrainRenderer * | [GetTerrainRenderer](#GetTerrainRenderer)() |
| simul::terrain::BaseWaterRenderer * | [GetWaterRenderer](#GetWaterRenderer)() |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| bool | [ProbeSkylight](#ProbeSkylight)(simul::crossplatform::DeviceContext pContext, int cubemap_view_id, int mip_size, int face_index, uint2 pos, uint2 size, vec4 targetValuesFloat4) |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [ReloadTextures](#ReloadTextures)() |
| void | [RenderOverlays](#RenderOverlays)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture texture, float exposure, float gamma) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform r) |
| void | [SetAmortization](#SetAmortization)(int view_id, int a) |
| void | [PreRenderUpdate](#PreRenderUpdate)(simul::crossplatform::DeviceContext deviceContext) |
| void | [RenderMixedResolutionSky](#RenderMixedResolutionSky)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture, simul::crossplatform::Viewport depthViewport, float exposure, float gamma, float brightnessToUnity) |




  


Base Classes
---
[simul::crossplatform::BaseRenderer](../crossplatform/baserenderer)

Functions
---

### <a name="CleanupOldAllocations"/>void CleanupOldAllocations(int max_age)
Delete GPU allocations to save memory. By default, max age is MaxViewAgeFrames. max_age=0 clears all views.

### <a name="CopySkylight"/>bool CopySkylight(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture targetTexture, float targetShValues, int shOrder, mat4 engineToSimulMatrix4x4, int updateFrequency, float blend, float exposure, float gamma, vec3 ground_colour, int amortization, bool allFaces, bool allMips)
Update the specified texture as a cubemap, and its spherical harmonics.
Copy the specified skylight into the target texture. This texture MUST be the same size, format and mip count as
was specified for this cubemap id when GetSkylight was called.
This function has latency depending on the platform.

### <a name="EnsureEffectsAreBuilt"/>void EnsureEffectsAreBuilt(simul::crossplatform::RenderPlatform r)
Check that all shaders have been correctly compiled

### <a name="EnsureSkylight"/>void EnsureSkylight(int cubemap_view_id, int size, int mips, simul::crossplatform::PixelFormat format, mat4 cubeToSimulMatrix, int shOrder, int updateFrequency, float blend, float exposure, float gamma, vec3 ground_colour, int amortization, bool allFaces, bool allMips)
Create or update a skylight.

### <a name="GetAmortization"/>int GetAmortization(int view_id)
Get the amortization of the given frame

### <a name="GetSceneRenderer"/>simul::scene::BaseSceneRenderer * GetSceneRenderer()
Get a pointer to the scene renderer.

### <a name="GetSimulHDRRenderer"/>simul::crossplatform::HdrRenderer * GetSimulHDRRenderer()
Get a pointer to the HDR renderer.

### <a name="GetSimulWeatherRenderer"/>simul::clouds::BaseWeatherRenderer * GetSimulWeatherRenderer()
Get a pointer to the weather renderer.

### <a name="GetTerrainRenderer"/>simul::terrain::BaseTerrainRenderer * GetTerrainRenderer()
Get a pointer to the terrain renderer.

### <a name="GetWaterRenderer"/>simul::terrain::BaseWaterRenderer * GetWaterRenderer()
Get a pointer to the water renderer.

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the renderer.

### <a name="ProbeSkylight"/>bool ProbeSkylight(simul::crossplatform::DeviceContext pContext, int cubemap_view_id, int mip_size, int face_index, uint2 pos, uint2 size, vec4 targetValuesFloat4)
Get linear colours from the specified skylight. Returns true if successful.

### <a name="RecompileShaders"/>void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.

### <a name="ReloadTextures"/>void ReloadTextures()
Reload the textures

### <a name="RenderOverlays"/>void RenderOverlays(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture texture, float exposure, float gamma)
Render the active debug overlays

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform r)
Platform-dependent function called when initializing the renderer.

### <a name="SetAmortization"/>void SetAmortization(int view_id, int a)
How often to update each cloud texel; 1:always, 2:every 4 frames, n:every n^2 frames.

### <a name="PreRenderUpdate"/>void PreRenderUpdate(simul::crossplatform::DeviceContext deviceContext)
Once per-frame update. Do this before any rendering each frame.

### <a name="RenderMixedResolutionSky"/>void RenderMixedResolutionSky(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture, simul::crossplatform::Viewport depthViewport, float exposure, float gamma, float brightnessToUnity)
Render the sky.

Fields
---

**ReferenceSpectralRadiance**  Spectral radiance at r,g,b for output colour value 1.0. Multiply by output colour to get the real spectral radiance.

**override_timestep**  Should the calcrealtime action use a fixed time step?

**override_timestep_value**  The fixed time step value (in seconds)
