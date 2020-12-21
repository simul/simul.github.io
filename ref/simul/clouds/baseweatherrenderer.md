---
title: BaseWeatherRenderer
layout: reference
weight: 0
---
class BaseWeatherRenderer
===

| Include: | Clouds/BaseLightningRenderer.h |



Functions
---

|  | [BaseWeatherRenderer](#BaseWeatherRenderer)(simul::clouds::Environment env, simul::base::MemoryInterface m) |
|  | [~BaseWeatherRenderer](#~BaseWeatherRenderer)() |
| void | [CleanUpFramebuffers](#CleanUpFramebuffers)(int max_age) |
| void | [CompositeCloudsToScreen](#CompositeCloudsToScreen)(simul::crossplatform::GraphicsDeviceContext deviceContext, simul::crossplatform::ViewStruct viewStruct2, simul::clouds::TrueSkyRenderMode renderMode, float exposure, float gamma, bool depth_blend, simul::crossplatform::Texture mainDepthTexture, vec4 viewportRegionXYWH, bool any_lightpass, LightingQueryResult lightingQueryResult, vec3 cubemap_ground_colour) |
| void | [ConnectInterfaces](#ConnectInterfaces)() |
| simul::clouds::BaseWeatherRenderer * | [Create](#Create)(simul::clouds::Environment env, simul::base::MemoryInterface m) |
| void | [CreateSubObjects](#CreateSubObjects)() |
| void | [Destroy](#Destroy)(simul::clouds::BaseWeatherRenderer baseWeatherRenderer) |
| simul::sky::BaseAtmosphericsRenderer * | [GetBaseAtmosphericsRenderer](#GetBaseAtmosphericsRenderer)() |
| simul::clouds::CloudRenderer * | [GetBaseCloudRenderer](#GetBaseCloudRenderer)() |
| simul::sky::BaseSkyRenderer * | [GetBaseSkyRenderer](#GetBaseSkyRenderer)() |
| simul::clouds::Environment * | [GetEnvironment](#GetEnvironment)() |
| int | [GetExportLightningStrikes](#GetExportLightningStrikes)(simul::clouds::ExportLightningStrike export_strikes, int max_s, float game_time, float real_time) |
| simul::sky::float4  const & | [GetHorizonColour](#GetHorizonColour)(float view_altitude_km) |
| simul::sky::float4  const & | [GetLightColour](#GetLightColour)(float view_altitude_km) |
| simul::clouds::BaseLightningRenderer * | [GetLightningRenderer](#GetLightningRenderer)() |
| simul::clouds::PrecipitationRenderer * | [GetPrecipitationRenderer](#GetPrecipitationRenderer)() |
| simul::crossplatform::Quaterniond | [GetSiderealTransform](#GetSiderealTransform)() |
| simul::sky::SkyKeyframer * | [GetSkyKeyframer](#GetSkyKeyframer)() |
| simul::clouds::TransparencyAtmospherics | [GetTransparencyAtmospherics](#GetTransparencyAtmospherics)(simul::crossplatform::ViewStruct viewStruct) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| simul::clouds::BaseWeatherRenderer  const & | [operator=](#operator=)(simul::clouds::BaseWeatherRenderer W) |
| void | [PreRenderUpdate](#PreRenderUpdate)(simul::crossplatform::GraphicsDeviceContext deviceContext, float real_time) |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [RemoveView](#RemoveView)(int view_id) |
| void | [Render](#Render)(simul::crossplatform::GraphicsDeviceContext deviceContext, simul::crossplatform::ViewStruct viewStruct2, simul::clouds::TrueSkyRenderMode renderMode, float exposure, float gamma, simul::crossplatform::Texture mainDepthTexture, simul::crossplatform::Texture cubemapTexture, simul::crossplatform::Viewport depthViewport, simul::crossplatform::Viewport viewports, vec3 cubemap_ground_colour, int amortization) |
| void | [RenderCelestialBackground](#RenderCelestialBackground)(simul::crossplatform::GraphicsDeviceContext deviceContext, simul::crossplatform::ViewStruct viewStruct, simul::clouds::TrueSkyRenderMode renderMode, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float exposure) |
| bool | [RenderMixedResolution](#RenderMixedResolution)(simul::crossplatform::GraphicsDeviceContext deviceContext, simul::crossplatform::ViewStruct viewStruct2, simul::crossplatform::Texture depthTexture, simul::clouds::TrueSkyRenderMode renderMode, float exposure, float gamma, simul::crossplatform::Viewport depthViewports, simul::crossplatform::Texture ambientCubemapTexture) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform renderPlatform) |
| void | [SetAllDownscale](#SetAllDownscale)(float) |
| void | [SetBlurTexture](#SetBlurTexture)(simul::crossplatform::Texture t) |
| void | [SetCubemapTransform](#SetCubemapTransform)(float m) |
| void | [SetEnvironment](#SetEnvironment)(simul::clouds::Environment env) |
| bool | [RenderLowResolutionElements](#RenderLowResolutionElements)(simul::crossplatform::GraphicsDeviceContext deviceContext, float exposure, float godrays_strength, simul::clouds::TrueSkyRenderMode renderMode, simul::crossplatform::NearFarPass nearFarPass, simul::crossplatform::Texture lowResDepthTexture, simul::sky::ScatteringVolume scatteringVolume, vec4 viewportRegionXYWH, simul::crossplatform::AmortizationStruct amortizationStruct, simul::crossplatform::Texture ambientCubemapTexture) |


Functions
---
<a name="BaseWeatherRenderer"></a>
###  BaseWeatherRenderer(simul::clouds::Environment env, simul::base::MemoryInterface m)
Default constructor: if env is NULL, a new Environment will be created.
<a name="~BaseWeatherRenderer"></a>
###  ~BaseWeatherRenderer()
The main base class for all weather renderers, such as SimulGLWeatherRenderer,
SimulWeatherRenderer (DX11) etc.

The derived classes of BaseWeatherRenderer create and maintain the renderers for weather
elements such as clouds, sky, rain and so on. So to use these sub-renderers it is usual to
create an instance of one of the weather renderers, and allow this instance to manage the
others.
<a name="CleanUpFramebuffers"></a>
### void CleanUpFramebuffers(int max_age)
Delete framebuffers that have not been used in max_age frames, to free GPU memory.
<a name="CompositeCloudsToScreen"></a>
### void CompositeCloudsToScreen(simul::crossplatform::GraphicsDeviceContext deviceContext, simul::crossplatform::ViewStruct viewStruct2, simul::clouds::TrueSkyRenderMode renderMode, float exposure, float gamma, bool depth_blend, simul::crossplatform::Texture mainDepthTexture, vec4 viewportRegionXYWH, bool any_lightpass, LightingQueryResult lightingQueryResult, vec3 cubemap_ground_colour)
This composites the clouds and other buffers to the screen.
<a name="ConnectInterfaces"></a>
### void ConnectInterfaces()
Connect-up sky, clouds etc.
<a name="Create"></a>
### simul::clouds::BaseWeatherRenderer * Create(simul::clouds::Environment env, simul::base::MemoryInterface m)
Create a base weather renderer: if env is NULL, a new Environment will be created.
<a name="CreateSubObjects"></a>
### void CreateSubObjects()
Create the member sub-objects: CloudRenderer etc.
<a name="Destroy"></a>
### void Destroy(simul::clouds::BaseWeatherRenderer baseWeatherRenderer)
Destroy a base weather renderer.
<a name="GetBaseAtmosphericsRenderer"></a>
### simul::sky::BaseAtmosphericsRenderer * GetBaseAtmosphericsRenderer()
Get a pointer to the atmospheric renderer.
<a name="GetBaseCloudRenderer"></a>
### simul::clouds::CloudRenderer * GetBaseCloudRenderer()
Get a pointer to the cloud renderer.
<a name="GetBaseSkyRenderer"></a>
### simul::sky::BaseSkyRenderer * GetBaseSkyRenderer()
Get a pointer to the sky renderer.
<a name="GetEnvironment"></a>
### simul::clouds::Environment * GetEnvironment()
Get a pointer to the current Environment
<a name="GetExportLightningStrikes"></a>
### int GetExportLightningStrikes(simul::clouds::ExportLightningStrike export_strikes, int max_s, float game_time, float real_time)
Get lightning strikes. This calls GetExportLightningStrikes in CloudKeyframer, but also includes
a cloud density query so that lightning can't come from empty sky.
<a name="GetHorizonColour"></a>
### simul::sky::float4  const & GetHorizonColour(float view_altitude_km)
Set a depth texture, whose alpha values represent the depth co-ordinate. This will be used when clouds are rendered in front of terrain etc.
Get the representative HDR colour of the horizon, as seen from the specified altitude view_altitude_km.
<a name="GetLightColour"></a>
### simul::sky::float4  const & GetLightColour(float view_altitude_km)
Get the HDR light colour, as seen from the specified altitude view_altitude_km
<a name="GetLightningRenderer"></a>
### simul::clouds::BaseLightningRenderer * GetLightningRenderer()
Get a pointer to the lightning renderer.
<a name="GetPrecipitationRenderer"></a>
### simul::clouds::PrecipitationRenderer * GetPrecipitationRenderer()
Get a pointer to the rain/snow renderer.
<a name="GetSiderealTransform"></a>
### simul::crossplatform::Quaterniond GetSiderealTransform()
Get the view matrix in sidereal space, e.g. for rendering celestial objects.
<a name="GetSkyKeyframer"></a>
### simul::sky::SkyKeyframer * GetSkyKeyframer()
Convenience function to get the next sky keyframe that can be modified without any recalculation.
<a name="GetTransparencyAtmospherics"></a>
### simul::clouds::TransparencyAtmospherics GetTransparencyAtmospherics(simul::crossplatform::ViewStruct viewStruct)
This returns a struct containing the textures and values needed to apply atmospherics to transparent objects.
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the weather renderer.
<a name="operator="></a>
### simul::clouds::BaseWeatherRenderer  const & operator=(simul::clouds::BaseWeatherRenderer W)
Copy the properties of one BaseWeatherRenderer to another, including copying the properties of their sky and cloud renderers.
<a name="PreRenderUpdate"></a>
### void PreRenderUpdate(simul::crossplatform::GraphicsDeviceContext deviceContext, float real_time)
Once per-frame update. Do this before any rendering each frame. For most platform implementations, you should set the
matrices relevant to the mainview before calling this.
<a name="RecompileShaders"></a>
### void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.
<a name="RemoveView"></a>
### void RemoveView(int view_id)
Ensure that per-view objects are destroyed for the view in question: they will be rebuilt if needed later.
<a name="Render"></a>
### void Render(simul::crossplatform::GraphicsDeviceContext deviceContext, simul::crossplatform::ViewStruct viewStruct2, simul::clouds::TrueSkyRenderMode renderMode, float exposure, float gamma, simul::crossplatform::Texture mainDepthTexture, simul::crossplatform::Texture cubemapTexture, simul::crossplatform::Viewport depthViewport, simul::crossplatform::Viewport viewports, vec3 cubemap_ground_colour, int amortization)
Render the sky including atmospherics, into the current rendertarget, using a supplied depth texture.

deviceContextis the platform-dependent render context,
viewStruct2is the view structure for alternate eye in VR,
exposureis a multiplier for the rendered sky brightness,
The view_idis an integer that distinguishes between multiple simultaneous viewports onscreen.
By convention, viewport 0 is the main view, and viewport 1 is the cubemap for reflections and lighting.
If is_cubemapis set, low-definition rendering is used.
The mainDepthTextureis a single-sampled or MSAA depth texture. You can use a simul::crossplatform::Texture-derived
class to wrapper your depth texture.
The depthViewportdetermines what part of the depth texture represents this viewport - normally (0,0,1,1).
Optional viewportsspecifies the left and right eye viewports if we're rendering both at once in VR.
<a name="RenderCelestialBackground"></a>
### void RenderCelestialBackground(simul::crossplatform::GraphicsDeviceContext deviceContext, simul::crossplatform::ViewStruct viewStruct, simul::clouds::TrueSkyRenderMode renderMode, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float exposure)
Draw the sun, moon and stars - call this while the depth buffer is bound.
<a name="RenderMixedResolution"></a>
### bool RenderMixedResolution(simul::crossplatform::GraphicsDeviceContext deviceContext, simul::crossplatform::ViewStruct viewStruct2, simul::crossplatform::Texture depthTexture, simul::clouds::TrueSkyRenderMode renderMode, float exposure, float gamma, simul::crossplatform::Viewport depthViewports, simul::crossplatform::Texture ambientCubemapTexture)
Render the sky including atmospherics as an overlay, using a supplied platform-dependent depth texture.
deviceContextis the platform-dependent render context, exposureis a multiplier for the rendered sky brightness,
The view_idis an integer that distinguishes between multiple simultaneous viewports onscreen.
By convention, viewport 0 is the main view, and viewport 1 is the cubemap for reflections and lighting.
If is_cubemapis set, low-definition rendering is used.
The mainDepthTextureis a single-sampled or MSAA depth texture. You can use a simul::crossplatform::Texture-derived
class to wrapper your depth texture.
The lowResDepthTextureis an API-dependent texture or texture resource pointer, with near far depth in the r and g, and b 0 or 1 for edges.
The depthViewportXYWHdetermines what part of the depth texture represents this viewport - normally (0,0,1,1).
Returns true if there is a lightpass.
<a name="RestoreDeviceObjects"></a>
### void RestoreDeviceObjects(simul::crossplatform::RenderPlatform renderPlatform)
Platform-dependent function called when initializing the weather renderer.
<a name="SetAllDownscale"></a>
### void SetAllDownscale(float)
Override the downscale for all current views; does not affect the default - see SetDefaultDownscale.
<a name="SetBlurTexture"></a>
### void SetBlurTexture(simul::crossplatform::Texture t)
A blurred texture, to be drawn usually per-frame.
<a name="SetCubemapTransform"></a>
### void SetCubemapTransform(float m)
A transform for the cubemap set by SetCubemapTexture().
<a name="SetEnvironment"></a>
### void SetEnvironment(simul::clouds::Environment env)
Set the Environment
<a name="RenderLowResolutionElements"></a>
### bool RenderLowResolutionElements(simul::crossplatform::GraphicsDeviceContext deviceContext, float exposure, float godrays_strength, simul::clouds::TrueSkyRenderMode renderMode, simul::crossplatform::NearFarPass nearFarPass, simul::crossplatform::Texture lowResDepthTexture, simul::sky::ScatteringVolume scatteringVolume, vec4 viewportRegionXYWH, simul::crossplatform::AmortizationStruct amortizationStruct, simul::crossplatform::Texture ambientCubemapTexture)
Renders the 2D clouds and atmospherics. If the passed depth texture is MSAA, near_pass determines whether to use the near or far depth for each depth texel.
