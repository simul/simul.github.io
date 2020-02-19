---
title: BaseSkyRenderer
layout: reference
weight: 0
---
class BaseSkyRenderer
===

| Include: | Sky/BaseSkyRenderer.h |

The Sky Renderer performs the following tasks:
- Rendering stars: using RenderPointStars(void *context,float exposure)
- Rendering planets (e.g. the Moon): using RenderPlanets(void *context,float exposure)
- Rendering the sun, using RenderSun(void *context,float exposure)

See <a href="../clouds/baseweatherrenderer/render.html">BaseWeatherRenderer::Render</a>
and <a href="../clouds/baseweatherrenderer/rendermixedresolution.html">RenderMixedResolution</a>.

The rendering of the sky is no longer handled by BaseSkyRenderer or its derived classes because the
<a href="baseatmosphericsrenderer.html">atmospherics renderer</a>now does this in a single pass including both sky and atmospherics.

It is the job of the Sky Renderer to update the atmospherics textures to be used by the other render classes, and render celestial objects.

The fade tables are stored as 3D textures - an axis for distance, one for elevation, one for altitude.
The table size is given by NumElevations, NumDistances and SetNumAltitudes() of <a href="skykeyframer.html">SkyKeyframer</a>.
Try to minimize the number of altitudes required, in order to maximize performance, and
use SetAltitudeRangeKm on initialization to the range you will use.

<a href="../clouds/baseweatherrenderer/prerenderupdate.html">() BaseWeatherRenderer::PreRenderUpdate</a>
first calls <a href="baseskyrenderer/ensuretexturesareuptodate.html">EnsureTexturesAreUpToDate</a>, which fills in the fade textures
with loss and inscatter values.

Then, the sky and atmospheric scattering (atmospherics, or distance-fades) are drawn together as an overlay
after the depth-buffer has been filled by any solids in the scene
(see <a href="../clouds/baseweatherrenderer/rendermixedresolution.html">endlink</a>).

There are two main elements to realistic atmospherics: Loss, and Inscatter.

![](/images/FadeLogic.png)
""

So, for any point in screen space, we can transform it to world space using the depth value, and obtain its distance, and elevation relative to the horizon. This gives us the
lookup co-ordinates into the loss and inscatter textures. The loss value determines how much of the red,green, and blue values of that pixel are retained as light passes through the atmosphere from the distant object to the viewer.
The inscatter determines how much sunlight (or moonlight etc) is scattered in towards the viewer due to the intervening atmosphere.

Generally in Earth's nitrogen-oxygen atmosphere, more blue light than red or green is scattered. So distance white objects appear yellow, as the blue component has been scattered away. But distance black objects appear blue, because
the blue part of the sunlight shining on the intervening air has been scattered as well, and some of that blue light goes towards the viewer. This process is Rayleigh scattering. Other important effects that TrueSky simulates are
Mie scattering due to haze, Ozone absorption, and radiation due to air temperature.

Each sky renderer maintains nine fade textures. If the most recent keyframe in the sky keyframer is X, we have:

Keyframe X    | Keyframe X+1  | Keyframe X+2
------------- | ------------- | -------------
loss 0        | loss 1        | loss 2
inscatter 0   | inscatter 1   | inscatter 2
skylight 0    | skylight 1    | skylight 2

Each texture contains data for the atmospherics as seen from a complete range of altitudes.

We use textures 0 and 1 to render the scene. Texture 2 is gradually filled in over multiple frames,
so that when we reach keyframe X+1, it will be complete and can be swapped in.
All this is handled automatically by the SkyKeyframer, which in turn can use a <a href="basegpuskygenerator.html">GpuSkyGenerator</a>.
If using CPU-generated textures, the Sky Renderer asks the keyframer what new data to fill into the textures each frame. If using its own
GpuSkyGenerator, the Sky Renderer has access to these textures without the need to query the keyframer.

![](/images/FadeTable.png)
""

The fade textures are 3D, with co-ordinates representing x=altitude/max altitude, y=1+sine(elevation))/2, z=distance/max distance.
Each frame, these three pairs of 3D textures (Keyframe X and X+1) are combined into three individual 2D textures, with
x=distance/max distance, y=1+sine(elevation))/2, representing the fade colours as seen at the present time, from the current viewing altitude.

The last texel in the x direction is considered to represent infinity, irrespective of the specified MaxDistanceKm parameter,
so a distance texture coordinate of 1.0 in the inscatter and skylight textures represents the sky,
with values less than one used for atmospheric scattering over solid objects.
  

[simul::base::Referenced](../base/referenced.html)
[simul::crossplatform::BaseRenderer](../crossplatform/baserenderer.html)

Functions
---

| float | [CalcSunOcclusion](#CalcSunOcclusion)(simul::crossplatform::DeviceContext, float cloud_occlusion) |
| simul::sky::BaseGpuSkyGenerator * | [CreateGpuSkyGenerator](#CreateGpuSkyGenerator)(simul::base::MemoryInterface m) |
| void | [EnsureEffectsAreBuilt](#EnsureEffectsAreBuilt)(simul::crossplatform::RenderPlatform r) |
| void | [EnsureTexturesAreUpToDate](#EnsureTexturesAreUpToDate)(simul::crossplatform::DeviceContext deviceContext) |
| simul::sky::BaseGpuSkyGenerator * | [GetBaseGpuSkyGenerator](#GetBaseGpuSkyGenerator)() |
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
| void | [PreRenderUpdate](#PreRenderUpdate)(simul::crossplatform::DeviceContext deviceContext) |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [ReloadTextures](#ReloadTextures)() |
| bool | [Render2DFades](#Render2DFades)(simul::crossplatform::DeviceContext deviceContext, int numDist, int numElev) |
| void | [RenderCelestialDisplay](#RenderCelestialDisplay)(simul::crossplatform::DeviceContext context, float y_heading) |
| bool | [RenderFades](#RenderFades)(simul::crossplatform::DeviceContext deviceContext, int view_id, int x, int y, int w, int h) |
| void | [RenderIlluminationBuffer](#RenderIlluminationBuffer)(simul::crossplatform::DeviceContext deviceContext) |
| void | [RenderLightingQueryResultsText](#RenderLightingQueryResultsText)(simul::crossplatform::DeviceContext deviceContext, int x, int y) |
| void | [RenderPlanet](#RenderPlanet)(simul::crossplatform::DeviceContext, simul::crossplatform::ViewStruct viewStruct, simul::crossplatform::Texture tex, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float rad, float dir, float colr, bool do_lighting, float exposure) |
| void | [RenderPlanets](#RenderPlanets)(simul::crossplatform::DeviceContext, simul::crossplatform::ViewStruct viewStruct, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float exposure) |
| bool | [RenderPointStars](#RenderPointStars)(simul::crossplatform::DeviceContext, simul::crossplatform::ViewStruct viewStruct, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float, float, int) |
| void | [RenderSun](#RenderSun)(simul::crossplatform::DeviceContext, simul::crossplatform::ViewStruct viewStruct, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float exposure) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform renderPlatform) |
| void | [SaveTextures](#SaveTextures)(char) |
| void | [SetBackgroundTexture](#SetBackgroundTexture)(simul::crossplatform::Texture t) |
| void | [SetOvercastCallback](#SetOvercastCallback)(simul::sky::OvercastCallback ocb) |
| void | [SetPlanetImage](#SetPlanetImage)(simul::sky::uid u, simul::crossplatform::Texture tex, bool lighting) |
| void | [FillFadeTextureBlocks](#FillFadeTextureBlocks)(int, int, int, int, int, int, int, float, float, float) |
| void | [SetPlanet](#SetPlanet)(simul::sky::uid u, simul::sky::Moon m, simul::crossplatform::Texture tex, bool do_lighting) |

The Sky Renderer performs the following tasks:
- Rendering stars: using RenderPointStars(void *context,float exposure)
- Rendering planets (e.g. the Moon): using RenderPlanets(void *context,float exposure)
- Rendering the sun, using RenderSun(void *context,float exposure)

See <a href="../clouds/baseweatherrenderer/render.html">BaseWeatherRenderer::Render</a>
and <a href="../clouds/baseweatherrenderer/rendermixedresolution.html">RenderMixedResolution</a>.

The rendering of the sky is no longer handled by BaseSkyRenderer or its derived classes because the
<a href="baseatmosphericsrenderer.html">atmospherics renderer</a>now does this in a single pass including both sky and atmospherics.

It is the job of the Sky Renderer to update the atmospherics textures to be used by the other render classes, and render celestial objects.

The fade tables are stored as 3D textures - an axis for distance, one for elevation, one for altitude.
The table size is given by NumElevations, NumDistances and SetNumAltitudes() of <a href="skykeyframer.html">SkyKeyframer</a>.
Try to minimize the number of altitudes required, in order to maximize performance, and
use SetAltitudeRangeKm on initialization to the range you will use.

<a href="../clouds/baseweatherrenderer/prerenderupdate.html">() BaseWeatherRenderer::PreRenderUpdate</a>
first calls <a href="baseskyrenderer/ensuretexturesareuptodate.html">EnsureTexturesAreUpToDate</a>, which fills in the fade textures
with loss and inscatter values.

Then, the sky and atmospheric scattering (atmospherics, or distance-fades) are drawn together as an overlay
after the depth-buffer has been filled by any solids in the scene
(see <a href="../clouds/baseweatherrenderer/rendermixedresolution.html">endlink</a>).

There are two main elements to realistic atmospherics: Loss, and Inscatter.

![](/images/FadeLogic.png)
""

So, for any point in screen space, we can transform it to world space using the depth value, and obtain its distance, and elevation relative to the horizon. This gives us the
lookup co-ordinates into the loss and inscatter textures. The loss value determines how much of the red,green, and blue values of that pixel are retained as light passes through the atmosphere from the distant object to the viewer.
The inscatter determines how much sunlight (or moonlight etc) is scattered in towards the viewer due to the intervening atmosphere.

Generally in Earth's nitrogen-oxygen atmosphere, more blue light than red or green is scattered. So distance white objects appear yellow, as the blue component has been scattered away. But distance black objects appear blue, because
the blue part of the sunlight shining on the intervening air has been scattered as well, and some of that blue light goes towards the viewer. This process is Rayleigh scattering. Other important effects that TrueSky simulates are
Mie scattering due to haze, Ozone absorption, and radiation due to air temperature.

Each sky renderer maintains nine fade textures. If the most recent keyframe in the sky keyframer is X, we have:

Keyframe X    | Keyframe X+1  | Keyframe X+2
------------- | ------------- | -------------
loss 0        | loss 1        | loss 2
inscatter 0   | inscatter 1   | inscatter 2
skylight 0    | skylight 1    | skylight 2

Each texture contains data for the atmospherics as seen from a complete range of altitudes.

We use textures 0 and 1 to render the scene. Texture 2 is gradually filled in over multiple frames,
so that when we reach keyframe X+1, it will be complete and can be swapped in.
All this is handled automatically by the SkyKeyframer, which in turn can use a <a href="basegpuskygenerator.html">GpuSkyGenerator</a>.
If using CPU-generated textures, the Sky Renderer asks the keyframer what new data to fill into the textures each frame. If using its own
GpuSkyGenerator, the Sky Renderer has access to these textures without the need to query the keyframer.

![](/images/FadeTable.png)
""

The fade textures are 3D, with co-ordinates representing x=altitude/max altitude, y=1+sine(elevation))/2, z=distance/max distance.
Each frame, these three pairs of 3D textures (Keyframe X and X+1) are combined into three individual 2D textures, with
x=distance/max distance, y=1+sine(elevation))/2, representing the fade colours as seen at the present time, from the current viewing altitude.

The last texel in the x direction is considered to represent infinity, irrespective of the specified MaxDistanceKm parameter,
so a distance texture coordinate of 1.0 in the inscatter and skylight textures represents the sky,
with values less than one used for atmospheric scattering over solid objects.
  


Base Classes
---
[simul::base::Referenced](../base/referenced.html)
[simul::crossplatform::BaseRenderer](../crossplatform/baserenderer.html)

Functions
---
<a name="CalcSunOcclusion"></a>
### float CalcSunOcclusion(simul::crossplatform::DeviceContext, float cloud_occlusion)
Get a value, from zero to one, which represents how much of the sun is visible.
Call this when the current rendering surface is the one that has obscuring
objects like mountains etc. in it, and make sure these have already been drawn.
GetSunOcclusion executes a pseudo-render of an invisible billboard, then
uses a hardware occlusion query to see how many pixels have passed the z-test.
<a name="CreateGpuSkyGenerator"></a>
### simul::sky::BaseGpuSkyGenerator * CreateGpuSkyGenerator(simul::base::MemoryInterface m)
Override this to create a custom generator.
<a name="EnsureEffectsAreBuilt"></a>
### void EnsureEffectsAreBuilt(simul::crossplatform::RenderPlatform r)
Check that all shaders have been correctly compiled
<a name="EnsureTexturesAreUpToDate"></a>
### void EnsureTexturesAreUpToDate(simul::crossplatform::DeviceContext deviceContext)
Maintains the per-frame textures.
<a name="GetBaseGpuSkyGenerator"></a>
### simul::sky::BaseGpuSkyGenerator * GetBaseGpuSkyGenerator()
Get a pointer to the Sky Generator.
<a name="GetBaseSkyInterface"></a>
### simul::sky::BaseSkyInterface * GetBaseSkyInterface()
Get the interface to the sky object so that other classes can use it for lighting, distance fades etc.
<a name="GetIlluminationTexture"></a>
### simul::crossplatform::Texture * GetIlluminationTexture()
Get the 2D texture that represents the extent of illuminated atmosphere visible in any given direction
on a per-frame basis.
<a name="GetLightColour"></a>
### simul::sky::float4 GetLightColour(float alt_km)
Returns the current directional light colour as a float4 (x=red, y=green, z=blue, w unused), i.e. sunlight or moonlight. This is a high-dynamic range value.
<a name="GetLightingQuery"></a>
### LightingQueryResult GetLightingQuery(int id, pos)
Get the results of a lighting query, and update it for next time. If this is the first call, the returned struct will have valid=false.
<a name="GetLightTableTexture"></a>
### simul::crossplatform::Texture * GetLightTableTexture()
Get a texture that represents the variation of sunlight, moonlight, ambient and total directional light with altitude.
<a name="GetPlanet"></a>
### simul::sky::PlanetStruct * GetPlanet(int index)
Get the planet structure identified by index.
<a name="GetSiderealSkyInterface"></a>
### simul::sky::SiderealSkyInterface * GetSiderealSkyInterface()
Get the sidereal sky interface - if using one, returns NULL otherwise.
<a name="GetSkyKeyframer"></a>
### simul::sky::SkyKeyframer * GetSkyKeyframer()
Get a pointer to the fade table.
<a name="GetSunOcclusion"></a>
### float GetSunOcclusion()
Get a value, from zero to one, which represents how much of the sun is visible.
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the sky renderer.
<a name="PreRenderUpdate"></a>
### void PreRenderUpdate(simul::crossplatform::DeviceContext deviceContext)
Once per-frame update. Do this before any rendering each frame.
<a name="RecompileShaders"></a>
### void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.
<a name="ReloadTextures"></a>
### void ReloadTextures()
Platform-dependent function to reload the textures - only use this for debug purposes.
<a name="Render2DFades"></a>
### bool Render2DFades(simul::crossplatform::DeviceContext deviceContext, int numDist, int numElev)
This fills in the 2D atmospheric fade textures once per-frame from the keyframed 3D fade textures.
<a name="RenderCelestialDisplay"></a>
### void RenderCelestialDisplay(simul::crossplatform::DeviceContext context, float y_heading)
Draw sidereal and geographic information to screen
<a name="RenderFades"></a>
### bool RenderFades(simul::crossplatform::DeviceContext deviceContext, int view_id, int x, int y, int w, int h)
Draw the 2D fades to screen for debugging.
<a name="RenderIlluminationBuffer"></a>
### void RenderIlluminationBuffer(simul::crossplatform::DeviceContext deviceContext)
Perform any necessary updates to the renderer's textures - particularly the loss, inscatter and skylight textures -
at the start of a frame. This is called from simul::clouds::BaseWeatherRenderer::PreRenderUpdate().
<a name="RenderLightingQueryResultsText"></a>
### void RenderLightingQueryResultsText(simul::crossplatform::DeviceContext deviceContext, int x, int y)
Display LightingQueryResults to screen for debugging
<a name="RenderPlanet"></a>
### void RenderPlanet(simul::crossplatform::DeviceContext, simul::crossplatform::ViewStruct viewStruct, simul::crossplatform::Texture tex, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float rad, float dir, float colr, bool do_lighting, float exposure)
This is called by RenderPlanets to render a planet with texture tex, angular radius radradians, in direction dir(x,y,z), with colour colr.
If do_lightingis true, the planet will be directionally-lit - e.g. moon phases.
<a name="RenderPlanets"></a>
### void RenderPlanets(simul::crossplatform::DeviceContext, simul::crossplatform::ViewStruct viewStruct, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float exposure)
Draw planets in the sky, e.g. the Moon.
<a name="RenderPointStars"></a>
### bool RenderPointStars(simul::crossplatform::DeviceContext, simul::crossplatform::ViewStruct viewStruct, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float, float, int)
Draw the stars.
<a name="RenderSun"></a>
### void RenderSun(simul::crossplatform::DeviceContext, simul::crossplatform::ViewStruct viewStruct, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float exposure)
Draw the sun.
<a name="RestoreDeviceObjects"></a>
### void RestoreDeviceObjects(simul::crossplatform::RenderPlatform renderPlatform)
Platform-dependent function called when initializing the sky renderer.
<a name="SaveTextures"></a>
### void SaveTextures(char)
Save the current texture set to disk. Useful, but not necessary for normal operation.
<a name="SetBackgroundTexture"></a>
### void SetBackgroundTexture(simul::crossplatform::Texture t)
Get some per-frame text information for debugging - usually timing data.
<a name="SetOvercastCallback"></a>
### void SetOvercastCallback(simul::sky::OvercastCallback ocb)
Inform the sky renderer of a callback to use to get overcast information.
<a name="SetPlanetImage"></a>
### void SetPlanetImage(simul::sky::uid u, simul::crossplatform::Texture tex, bool lighting)
Set the texture for planet indexto tex
<a name="FillFadeTextureBlocks"></a>
### void FillFadeTextureBlocks(int, int, int, int, int, int, int, float, float, float)
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
<a name="SetPlanet"></a>
### void SetPlanet(simul::sky::uid u, simul::sky::Moon m, simul::crossplatform::Texture tex, bool do_lighting)
Create a planet, identified by the index, which can be any unique number.
The texture texis an API-specific texture identifier, e.g. a GLuint, or LPDIRECT3D9TEXTURE.
The angular radius will be rad, in radians. If do_lightingis true, the planet should be directionally lit by the sun
to produce phases.
