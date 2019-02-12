---
title: BaseSkyRenderer
layout: reference
weight: 0
---
class BaseSkyRenderer
===

| Include: | Clouds/BaseWeatherRenderer.h |


[simul::base::Referenced](../base/referenced)
[simul::crossplatform::BaseRenderer](../crossplatform/baserenderer)

Functions
---

|  | [BaseSkyRenderer](#BaseSkyRenderer)(simul::sky::SkyKeyframer sk, simul::base::MemoryInterface m) |
| float | [CalcSunOcclusion](#CalcSunOcclusion)(simul::crossplatform::DeviceContext, float cloud_occlusion) |
| simul::sky::BaseGpuSkyGenerator * | [CreateGpuSkyGenerator](#CreateGpuSkyGenerator)(simul::base::MemoryInterface m) |
| void | [EnableMoon](#EnableMoon)(bool val) |
| void | [EnsureTexturesAreUpToDate](#EnsureTexturesAreUpToDate)(simul::crossplatform::DeviceContext deviceContext) |
| simul::sky::float4 | [GetAmbientColour](#GetAmbientColour)(float alt_km) |
| simul::sky::BaseSkyInterface * | [GetBaseSkyInterface](#GetBaseSkyInterface)() |
| simul::crossplatform::Texture * | [GetIlluminationTexture](#GetIlluminationTexture)() |
| simul::sky::float4 | [GetLightColour](#GetLightColour)(float alt_km) |
| LightingQueryResult | [GetLightingQuery](#GetLightingQuery)(int id, pos) |
| simul::crossplatform::Texture * | [GetLightTableTexture](#GetLightTableTexture)() |
| simul::sky::PlanetStruct * | [GetPlanet](#GetPlanet)(int index) |
| simul::sky::SiderealSkyInterface * | [GetSiderealSkyInterface](#GetSiderealSkyInterface)() |
| simul::sky::SkyKeyframer * | [GetSkyKeyframer](#GetSkyKeyframer)() |
| float | [GetSunOcclusion](#GetSunOcclusion)() |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| bool | [IsMoonEnabled](#IsMoonEnabled)() |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [ReloadTextures](#ReloadTextures)() |
| bool | [Render2DFades](#Render2DFades)(simul::crossplatform::DeviceContext deviceContext, int numDist, int numElev) |
| void | [RenderCelestialDisplay](#RenderCelestialDisplay)(simul::crossplatform::DeviceContext context, float y_heading) |
| bool | [RenderFades](#RenderFades)(simul::crossplatform::DeviceContext deviceContext, int view_id, int x, int y, int w, int h) |
| void | [RenderIlluminationBuffer](#RenderIlluminationBuffer)(simul::crossplatform::DeviceContext deviceContext) |
| void | [RenderPlanet](#RenderPlanet)(simul::crossplatform::DeviceContext, simul::crossplatform::ViewStruct viewStruct, simul::crossplatform::Texture tex, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float rad, float dir, float colr, bool do_lighting, float exposure) |
| void | [RenderPlanets](#RenderPlanets)(simul::crossplatform::DeviceContext, simul::crossplatform::ViewStruct viewStruct, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float exposure) |
| bool | [RenderPointStars](#RenderPointStars)(simul::crossplatform::DeviceContext, simul::crossplatform::ViewStruct viewStruct, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float, float) |
| void | [RenderSun](#RenderSun)(simul::crossplatform::DeviceContext, simul::crossplatform::ViewStruct viewStruct, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float exposure) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform renderPlatform) |
| void | [SaveTextures](#SaveTextures)(char) |
| void | [SetBackgroundTexture](#SetBackgroundTexture)(simul::crossplatform::Texture t) |
| void | [SetMoonTexture](#SetMoonTexture)(simul::crossplatform::Texture t) |
| void | [SetOvercastCallback](#SetOvercastCallback)(simul::sky::OvercastCallback ocb) |
| void | [SetPlanet](#SetPlanet)(int index, simul::crossplatform::Texture tex, float rad, bool do_lighting) |
| void | [SetPlanetColour](#SetPlanetColour)(int index, float c3) |
| void | [SetPlanetDirection](#SetPlanetDirection)(int index, float pos) |
| void | [SetPlanetImage](#SetPlanetImage)(int index, simul::crossplatform::Texture tex) |
| void | [SetPlanetRadius](#SetPlanetRadius)(int index, float radians) |
| void | [FillFadeTextureBlocks](#FillFadeTextureBlocks)(int, int, int, int, int, int, int, float, float, float) |


Base Classes
---
[simul::base::Referenced](../base/referenced)
[simul::crossplatform::BaseRenderer](../crossplatform/baserenderer)

Functions
---

### <a name="BaseSkyRenderer"/> BaseSkyRenderer(simul::sky::SkyKeyframer sk, simul::base::MemoryInterface m)
The Sky Renderer performs the following tasks:
- Rendering stars: using RenderPointStars(void *context,float exposure)
- Rendering planets (e.g. the Moon): using RenderPlanets(void *context,float exposure)
- Rendering the sun, using RenderSun(void *context,float exposure)

See 

### <a name="CalcSunOcclusion"/>float CalcSunOcclusion(simul::crossplatform::DeviceContext, float cloud_occlusion)
Get a value, from zero to one, which represents how much of the sun is visible.
Call this when the current rendering surface is the one that has obscuring
objects like mountains etc. in it, and make sure these have already been drawn.
GetSunOcclusion executes a pseudo-render of an invisible billboard, then
uses a hardware occlusion query to see how many pixels have passed the z-test.

### <a name="CreateGpuSkyGenerator"/>simul::sky::BaseGpuSkyGenerator * CreateGpuSkyGenerator(simul::base::MemoryInterface m)
Override this to create a custom generator.

### <a name="EnableMoon"/>void EnableMoon(bool val)
The moon is distinct from other planets because its position is taken from the skyInterface. When the moon is enabled, it will be added
to the planets list and updated automatically.

### <a name="EnsureTexturesAreUpToDate"/>void EnsureTexturesAreUpToDate(simul::crossplatform::DeviceContext deviceContext)
Maintains the per-frame textures.

### <a name="GetAmbientColour"/>simul::sky::float4 GetAmbientColour(float alt_km)
Returns the current ambient light colour as a float4 (x=red, y=green, z=blue, w unused), i.e. sunlight or moonlight. This is a high-dynamic range value.

### <a name="GetBaseSkyInterface"/>simul::sky::BaseSkyInterface * GetBaseSkyInterface()
Get the interface to the sky object so that other classes can use it for lighting, distance fades etc.

### <a name="GetIlluminationTexture"/>simul::crossplatform::Texture * GetIlluminationTexture()
Get the 2D texture that represents the extent of illuminated atmosphere visible in any given direction
on a per-frame basis.

### <a name="GetLightColour"/>simul::sky::float4 GetLightColour(float alt_km)
Returns the current directional light colour as a float4 (x=red, y=green, z=blue, w unused), i.e. sunlight or moonlight. This is a high-dynamic range value.

### <a name="GetLightingQuery"/>LightingQueryResult GetLightingQuery(int id, pos)
Get the results of a lighting query, and update it for next time. If this is the first call, the returned struct will have valid=false.

### <a name="GetLightTableTexture"/>simul::crossplatform::Texture * GetLightTableTexture()
Get a texture that represents the variation of sunlight, moonlight, ambient and total directional light with altitude.

### <a name="GetPlanet"/>simul::sky::PlanetStruct * GetPlanet(int index)
Get the planet structure identified by index.

### <a name="GetSiderealSkyInterface"/>simul::sky::SiderealSkyInterface * GetSiderealSkyInterface()
Get the sidereal sky interface - if using one, returns NULL otherwise.

### <a name="GetSkyKeyframer"/>simul::sky::SkyKeyframer * GetSkyKeyframer()
Get a pointer to the fade table.

### <a name="GetSunOcclusion"/>float GetSunOcclusion()
Get a value, from zero to one, which represents how much of the sun is visible.

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the sky renderer.

### <a name="IsMoonEnabled"/>bool IsMoonEnabled()
Is the moon being shown?

### <a name="RecompileShaders"/>void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.

### <a name="ReloadTextures"/>void ReloadTextures()
Platform-dependent function to reload the textures - only use this for debug purposes.

### <a name="Render2DFades"/>bool Render2DFades(simul::crossplatform::DeviceContext deviceContext, int numDist, int numElev)
This fills in the 2D atmospheric fade textures once per-frame from the keyframed 3D fade textures.

### <a name="RenderCelestialDisplay"/>void RenderCelestialDisplay(simul::crossplatform::DeviceContext context, float y_heading)
Draw sidereal and geographic information to screen

### <a name="RenderFades"/>bool RenderFades(simul::crossplatform::DeviceContext deviceContext, int view_id, int x, int y, int w, int h)
Draw the 2D fades to screen for debugging.

### <a name="RenderIlluminationBuffer"/>void RenderIlluminationBuffer(simul::crossplatform::DeviceContext deviceContext)
Perform any necessary updates to the renderer's textures - particularly the loss, inscatter and skylight textures -
at the start of a frame. This is called from simul::clouds::BaseWeatherRenderer::PreRenderUpdate().

### <a name="RenderPlanet"/>void RenderPlanet(simul::crossplatform::DeviceContext, simul::crossplatform::ViewStruct viewStruct, simul::crossplatform::Texture tex, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float rad, float dir, float colr, bool do_lighting, float exposure)
This is called by RenderPlanets to render a planet with texture tex, angular radius radradians, in direction dir(x,y,z), with colour colr.
If do_lightingis true, the planet will be directionally-lit - e.g. moon phases.

### <a name="RenderPlanets"/>void RenderPlanets(simul::crossplatform::DeviceContext, simul::crossplatform::ViewStruct viewStruct, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float exposure)
Draw planets in the sky, e.g. the Moon.

### <a name="RenderPointStars"/>bool RenderPointStars(simul::crossplatform::DeviceContext, simul::crossplatform::ViewStruct viewStruct, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float, float)
Draw the stars.

### <a name="RenderSun"/>void RenderSun(simul::crossplatform::DeviceContext, simul::crossplatform::ViewStruct viewStruct, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float exposure)
Draw the sun.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform renderPlatform)
Platform-dependent function called when initializing the sky renderer.

### <a name="SaveTextures"/>void SaveTextures(char)
Save the current texture set to disk. Useful, but not necessary for normal operation.

### <a name="SetBackgroundTexture"/>void SetBackgroundTexture(simul::crossplatform::Texture t)
Get some per-frame text information for debugging - usually timing data.

### <a name="SetMoonTexture"/>void SetMoonTexture(simul::crossplatform::Texture t)
Override the Moon texture

### <a name="SetOvercastCallback"/>void SetOvercastCallback(simul::sky::OvercastCallback ocb)
Inform the sky renderer of a callback to use to get overcast information.

### <a name="SetPlanet"/>void SetPlanet(int index, simul::crossplatform::Texture tex, float rad, bool do_lighting)
Create a planet, identified by the index, which can be any unique number.
The texture texis an API-specific texture identifier, e.g. a GLuint, or LPDIRECT3D9TEXTURE.
The angular radius will be rad, in radians. If do_lightingis true, the planet should be directionally lit by the sun
to produce phases.

### <a name="SetPlanetColour"/>void SetPlanetColour(int index, float c3)
Set the colour of the planet identified by index.

### <a name="SetPlanetDirection"/>void SetPlanetDirection(int index, float pos)
Set the direction to the planet identified by index.

### <a name="SetPlanetImage"/>void SetPlanetImage(int index, simul::crossplatform::Texture tex)
Set the texture for planet indexto tex, an API-specific texture identifier, e.g. a GLuint, a DX9 LPDIRECT3D9TEXTURE, or DX11 ShaderResourceView.

### <a name="SetPlanetRadius"/>void SetPlanetRadius(int index, float radians)
Set the angular radius of the planet identified by index.

### <a name="FillFadeTextureBlocks"/>void FillFadeTextureBlocks(int, int, int, int, int, int, int, float, float, float)
Inform the derived class that the loss and inscatter textures texture_index, either 0, 1 or 2, at altitude
index alt_index, (not used if not using multiple altitudes) should fill a block of texels
starting at x, y, z, and wwide, llong, ddeep, with the values in the array uint32_array,
with the values in the arrays loss_float4_array and inscatter_float4_array, each of which contains
four times num_texels floats. The first number is the value for texel_index, rather than the start of the whole table.
Each group of four represents the r,g,b and a of a colour value, and the values may be greater
than one, so floating point textures are preferred.
Only one of FillFadeTexturesSequentially and FillFadeTextureBlocks need be implemented, depending on the graphics API.
Some API's permit transfer of data sequentially in memory to textures (e.g. DirectX 9), some expect cuboid blocks of
texels to be filled (e.g. OpenGL). The unwanted function should be implemented as a stub, with an assert() or some other
fail condition, to make sure it is never called.
