---
title: BaseWeatherRenderer
layout: reference
weight: 0
---
class BaseWeatherRenderer
===

| Include: | Clouds/BaseLightningRenderer.h |

The main base class for all weather renderers, such as SimulGLWeatherRenderer,
SimulWeatherRenderer (DX11) etc.

The derived classes of BaseWeatherRenderer create and maintain the renderers for weather
elements such as clouds, sky, rain and so on. So to use these sub-renderers it is usual to
create an instance of one of the weather renderers, and allow this instance to manage the
others.
  


Functions
---

|  | [BaseWeatherRenderer](#BaseWeatherRenderer)(simul::clouds::Environment env, simul::base::MemoryInterface m) |
| void | [CleanUpFramebuffers](#CleanUpFramebuffers)(int max_age) |
| void | [ConnectInterfaces](#ConnectInterfaces)() |
| simul::clouds::BaseWeatherRenderer * | [Create](#Create)(simul::clouds::Environment env, simul::base::MemoryInterface m) |
| void | [CreateSubObjects](#CreateSubObjects)() |
| void | [Destroy](#Destroy)(simul::clouds::BaseWeatherRenderer baseWeatherRenderer) |
| simul::sky::float4  const & | [GetAmbientLightColour](#GetAmbientLightColour)(float view_altitude_km) |
| simul::sky::BaseAtmosphericsRenderer * | [GetBaseAtmosphericsRenderer](#GetBaseAtmosphericsRenderer)() |
| simul::clouds::CloudRenderer * | [GetBaseCloudRenderer](#GetBaseCloudRenderer)() |
| simul::sky::BaseSkyRenderer * | [GetBaseSkyRenderer](#GetBaseSkyRenderer)() |
| int | [GetExportLightningStrikes](#GetExportLightningStrikes)(simul::clouds::ExportLightningStrike export_strikes, int max_s, float game_time, float real_time) |
| simul::sky::float4  const & | [GetHorizonColour](#GetHorizonColour)(float view_altitude_km) |
| simul::sky::float4  const & | [GetLightColour](#GetLightColour)(float view_altitude_km) |
| simul::clouds::BaseLightningRenderer * | [GetLightningRenderer](#GetLightningRenderer)() |
| simul::clouds::PrecipitationRenderer * | [GetPrecipitationRenderer](#GetPrecipitationRenderer)() |
| simul::sky::SkyKeyframer * | [GetSkyKeyframer](#GetSkyKeyframer)() |
| simul::clouds::TransparencyAtmospherics | [GetTransparencyAtmospherics](#GetTransparencyAtmospherics)(simul::crossplatform::ViewStruct viewStruct) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| simul::clouds::BaseWeatherRenderer  const & | [operator=](#operator=)(simul::clouds::BaseWeatherRenderer W) |
| void | [PreRenderUpdate](#PreRenderUpdate)(simul::crossplatform::DeviceContext deviceContext, float real_time) |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [RemoveView](#RemoveView)(int view_id) |
| void | [Render](#Render)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ViewStruct viewStruct2, simul::clouds::TrueSkyRenderMode renderMode, float exposure, float gamma, simul::crossplatform::Texture mainDepthTexture, simul::crossplatform::Texture cubemapTexture, simul::crossplatform::Viewport depthViewport, simul::crossplatform::Viewport viewports, vec3 cubemap_ground_colour, int amortization) |
| void | [RenderCelestialBackground](#RenderCelestialBackground)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ViewStruct viewStruct, simul::clouds::TrueSkyRenderMode renderMode, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float exposure) |
| bool | [RenderMixedResolution](#RenderMixedResolution)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ViewStruct viewStruct2, simul::crossplatform::Texture depthTexture, simul::clouds::TrueSkyRenderMode renderMode, float exposure, float gamma, simul::crossplatform::Viewport depthViewports, simul::crossplatform::Texture ambientCubemapTexture) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform renderPlatform) |
| void | [SetAllDownscale](#SetAllDownscale)(float) |
| void | [SetBlurTexture](#SetBlurTexture)(simul::crossplatform::Texture t) |
| void | [SetCubemapTransform](#SetCubemapTransform)(float m) |
| bool | [RenderLowResolutionElements](#RenderLowResolutionElements)(simul::crossplatform::DeviceContext deviceContext, float exposure, float godrays_strength, simul::clouds::TrueSkyRenderMode renderMode, simul::crossplatform::NearFarPass nearFarPass, simul::crossplatform::Texture lowResDepthTexture, simul::sky::ScatteringVolume scatteringVolume, vec4 viewportRegionXYWH, simul::crossplatform::AmortizationStruct amortizationStruct, simul::crossplatform::Texture ambientCubemapTexture) |

The main base class for all weather renderers, such as SimulGLWeatherRenderer,
SimulWeatherRenderer (DX11) etc.

The derived classes of BaseWeatherRenderer create and maintain the renderers for weather
elements such as clouds, sky, rain and so on. So to use these sub-renderers it is usual to
create an instance of one of the weather renderers, and allow this instance to manage the
others.
  


Functions
---

### <a name="BaseWeatherRenderer"/> BaseWeatherRenderer(simul::clouds::Environment env, simul::base::MemoryInterface m)
Default constructor: if env is NULL, a new Environment will be created.

### <a name="CleanUpFramebuffers"/>void CleanUpFramebuffers(int max_age)
Delete framebuffers that have not been used in max_age frames, to free GPU memory.

### <a name="ConnectInterfaces"/>void ConnectInterfaces()
Connect-up sky, clouds etc.

### <a name="Create"/>simul::clouds::BaseWeatherRenderer * Create(simul::clouds::Environment env, simul::base::MemoryInterface m)
Create a base weather renderer: if env is NULL, a new Environment will be created.

### <a name="CreateSubObjects"/>void CreateSubObjects()
Create the member sub-objects: CloudRenderer etc.

### <a name="Destroy"/>void Destroy(simul::clouds::BaseWeatherRenderer baseWeatherRenderer)
Destroy a base weather renderer.

### <a name="GetAmbientLightColour"/>simul::sky::float4  const & GetAmbientLightColour(float view_altitude_km)

### <a name="GetBaseAtmosphericsRenderer"/>simul::sky::BaseAtmosphericsRenderer * GetBaseAtmosphericsRenderer()
Get a pointer to the atmospheric renderer.

### <a name="GetBaseCloudRenderer"/>simul::clouds::CloudRenderer * GetBaseCloudRenderer()
Get a pointer to the cloud renderer.

### <a name="GetBaseSkyRenderer"/>simul::sky::BaseSkyRenderer * GetBaseSkyRenderer()
Get a pointer to the sky renderer.

### <a name="GetExportLightningStrikes"/>int GetExportLightningStrikes(simul::clouds::ExportLightningStrike export_strikes, int max_s, float game_time, float real_time)
Get lightning strikes. This calls GetExportLightningStrikes in CloudKeyframer, but also includes
a cloud density query so that lightning can't come from empty sky.

### <a name="GetHorizonColour"/>simul::sky::float4  const & GetHorizonColour(float view_altitude_km)
Set a depth texture, whose alpha values represent the depth co-ordinate. This will be used when clouds are rendered in front of terrain etc.


### <a name="GetLightColour"/>simul::sky::float4  const & GetLightColour(float view_altitude_km)

### <a name="GetLightningRenderer"/>simul::clouds::BaseLightningRenderer * GetLightningRenderer()
Get a pointer to the lightning renderer.

### <a name="GetPrecipitationRenderer"/>simul::clouds::PrecipitationRenderer * GetPrecipitationRenderer()
Get a pointer to the rain/snow renderer.

### <a name="GetSkyKeyframer"/>simul::sky::SkyKeyframer * GetSkyKeyframer()
Convenience function to get the next sky keyframe that can be modified without any recalculation.

### <a name="GetTransparencyAtmospherics"/>simul::clouds::TransparencyAtmospherics GetTransparencyAtmospherics(simul::crossplatform::ViewStruct viewStruct)
This returns a struct containing the textures and values needed to apply atmospherics to transparent objects.

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
De-initialize all API-dependent objects in the weather renderer and its member renderers.

### <a name="operator="/>simul::clouds::BaseWeatherRenderer  const & operator=(simul::clouds::BaseWeatherRenderer W)
Copy the properties of one BaseWeatherRenderer to another, including copying the properties of their sky and cloud renderers.

### <a name="PreRenderUpdate"/>void PreRenderUpdate(simul::crossplatform::DeviceContext deviceContext, float real_time)
Once per-frame update. Do this before any rendering each frame. For most platform implementations, you should set the


### <a name="RecompileShaders"/>void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.

### <a name="RemoveView"/>void RemoveView(int view_id)
Ensure that per-view objects are destroyed for the view in question: they will be rebuilt if needed later.

### <a name="Render"/>void Render(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ViewStruct viewStruct2, simul::clouds::TrueSkyRenderMode renderMode, float exposure, float gamma, simul::crossplatform::Texture mainDepthTexture, simul::crossplatform::Texture cubemapTexture, simul::crossplatform::Viewport depthViewport, simul::crossplatform::Viewport viewports, vec3 cubemap_ground_colour, int amortization)
Render the sky including atmospherics, into the current rendertarget, using a supplied depth texture.


### <a name="RenderCelestialBackground"/>void RenderCelestialBackground(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ViewStruct viewStruct, simul::clouds::TrueSkyRenderMode renderMode, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float exposure)
Draw the sun, moon and stars - call this while the depth buffer is bound.

### <a name="RenderMixedResolution"/>bool RenderMixedResolution(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ViewStruct viewStruct2, simul::crossplatform::Texture depthTexture, simul::clouds::TrueSkyRenderMode renderMode, float exposure, float gamma, simul::crossplatform::Viewport depthViewports, simul::crossplatform::Texture ambientCubemapTexture)

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform renderPlatform)
Initialize the  API-dependent objects in the weather renderer and its member renderers. This is usually needed
when the 3D view is first set-up.

### <a name="SetAllDownscale"/>void SetAllDownscale(float)
Override the downscale for all current views; does not affect the default - see SetDefaultDownscale.

### <a name="SetBlurTexture"/>void SetBlurTexture(simul::crossplatform::Texture t)
A blurred texture, to be drawn usually per-frame.

### <a name="SetCubemapTransform"/>void SetCubemapTransform(float m)
A transform for the cubemap set by SetCubemapTexture().

### <a name="RenderLowResolutionElements"/>bool RenderLowResolutionElements(simul::crossplatform::DeviceContext deviceContext, float exposure, float godrays_strength, simul::clouds::TrueSkyRenderMode renderMode, simul::crossplatform::NearFarPass nearFarPass, simul::crossplatform::Texture lowResDepthTexture, simul::sky::ScatteringVolume scatteringVolume, vec4 viewportRegionXYWH, simul::crossplatform::AmortizationStruct amortizationStruct, simul::crossplatform::Texture ambientCubemapTexture)
Renders the 2D clouds and atmospherics. If the passed depth texture is MSAA, near_pass determines whether to use the near or far depth for each depth texel.
