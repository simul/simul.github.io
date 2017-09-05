---
title: BaseWeatherRenderer
layout: reference
weight: 0
---
class BaseWeatherRenderer
===

| Include: | Clouds/BaseWeatherRenderer.h |

The main base class for all weather renderers, such as SimulGLWeatherRenderer,<br>SimulWeatherRenderer (DX11) etc.<br>


Functions
---

|  | [BaseWeatherRenderer](#BaseWeatherRenderer)(simul::clouds::Environment env, simul::base::MemoryInterface m) |
| void | [CleanUpFramebuffers](#CleanUpFramebuffers)(int max_age) |
| void | [ConnectInterfaces](#ConnectInterfaces)() |
| simul::clouds::BaseWeatherRenderer * | [Create](#Create)(simul::clouds::Environment env, simul::base::MemoryInterface m) |
| void | [CreateSubObjects](#CreateSubObjects)() |
| void | [Destroy](#Destroy)(simul::clouds::BaseWeatherRenderer baseWeatherRenderer) |
| simul::sky::float4  const & | [GetAmbientLightColour](#GetAmbientLightColour)(float view_altitude_km) |
| simul::clouds::BaseCloudRenderer * | [GetBaseCloudRenderer](#GetBaseCloudRenderer)() |
| simul::clouds::BasePrecipitationRenderer * | [GetBasePrecipitationRenderer](#GetBasePrecipitationRenderer)() |
| simul::sky::BaseSkyRenderer * | [GetBaseSkyRenderer](#GetBaseSkyRenderer)() |
| simul::clouds::Base2DCloudRenderer * | [GetCloud2DRenderer](#GetCloud2DRenderer)() |
| int | [GetExportLightningStrikes](#GetExportLightningStrikes)(simul::clouds::ExportLightningStrike export_strikes, int max_s, float game_time, float real_time) |
| simul::sky::float4  const & | [GetHorizonColour](#GetHorizonColour)(float view_altitude_km) |
| simul::sky::float4  const & | [GetLightColour](#GetLightColour)(float view_altitude_km) |
| simul::clouds::BaseLightningRenderer * | [GetLightningRenderer](#GetLightningRenderer)() |
| simul::sky::SkyKeyframer * | [GetSkyKeyframer](#GetSkyKeyframer)() |
| simul::clouds::TransparencyAtmospherics | [GetTransparencyAtmospherics](#GetTransparencyAtmospherics)(simul::crossplatform::ViewStruct viewStruct) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| simul::clouds::BaseWeatherRenderer  const & | [operator=](#operator=)(simul::clouds::BaseWeatherRenderer W) |
| void | [PreRenderUpdate](#PreRenderUpdate)(simul::crossplatform::DeviceContext deviceContext, float real_time) |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [RemoveView](#RemoveView)(int view_id) |
| void | [Render](#Render)(simul::crossplatform::DeviceContext deviceContext, simul::clouds::TrueSkyRenderMode renderMode, float exposure, float gamma, simul::crossplatform::Texture mainDepthTexture, simul::crossplatform::Texture cubemapTexture, simul::crossplatform::Viewport depthViewport) |
| void | [RenderCelestialBackground](#RenderCelestialBackground)(simul::crossplatform::DeviceContext deviceContext, simul::clouds::TrueSkyRenderMode renderMode, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float exposure) |
| bool | [RenderMixedResolution](#RenderMixedResolution)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture, simul::clouds::TrueSkyRenderMode renderMode, float exposure, float gamma, vec4 depthViewportXYWH, simul::crossplatform::Texture ambientCubemapTexture) |
| void | [RenderOverlays](#RenderOverlays)(simul::crossplatform::DeviceContext deviceContext, int view_id) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform renderPlatform) |
| void | [SetAllDownscale](#SetAllDownscale)(float) |
| void | [SetBlurTexture](#SetBlurTexture)(simul::crossplatform::Texture t) |
| void | [SetCubemapTransform](#SetCubemapTransform)(float m) |
| bool | [RenderLowResolutionElements](#RenderLowResolutionElements)(simul::crossplatform::DeviceContext deviceContext, float exposure, float godrays_strength, simul::clouds::TrueSkyRenderMode renderMode, simul::crossplatform::NearFarPass nearFarPass, simul::crossplatform::Texture lowResDepthTexture, simul::sky::ScatteringVolume scatteringVolume, vec4 viewportRegionXYWH, simul::crossplatform::AmortizationStruct amortizationStruct, simul::crossplatform::Texture ambientCubemapTexture) |

The derived classes of BaseWeatherRenderer create and maintain the renderers for weather
elements such as clouds, sky, rain and so on. So to use these sub-renderers it is usual to
create an instance of one of the weather renderers, and allow this instance to manage the
others.
  


Functions
---

### <a name="BaseWeatherRenderer"/> BaseWeatherRenderer(simul::clouds::Environment env, simul::base::MemoryInterface m)
Default constructor: if env is NULL, a new Environment will be created.
Default constructor: if env is NULL, a new Environment will be created.

### <a name="CleanUpFramebuffers"/>void CleanUpFramebuffers(int max_age)
Delete framebuffers that have not been used in max_age frames, to free GPU memory.
Delete framebuffers that have not been used in max_age frames, to free GPU memory.

### <a name="ConnectInterfaces"/>void ConnectInterfaces()
Connect-up sky, clouds etc.
Connect-up sky, clouds etc.

### <a name="Create"/>simul::clouds::BaseWeatherRenderer * Create(simul::clouds::Environment env, simul::base::MemoryInterface m)
Create a base weather renderer: if env is NULL, a new Environment will be created.
Create a base weather renderer: if env is NULL, a new Environment will be created.

### <a name="CreateSubObjects"/>void CreateSubObjects()
Create the member sub-objects: CloudRenderer etc.
Create the member sub-objects: CloudRenderer etc.

### <a name="Destroy"/>void Destroy(simul::clouds::BaseWeatherRenderer baseWeatherRenderer)
Destroy a base weather renderer.
Destroy a base weather renderer.

### <a name="GetAmbientLightColour"/>simul::sky::float4  const & GetAmbientLightColour(float view_altitude_km)
Get the HDR ambient colour, as seen from the specified altitude 
**view_altitude_km**
Get the HDR ambient colour, as seen from the specified altitude 
**view_altitude_km**

### <a name="GetBaseCloudRenderer"/>simul::clouds::BaseCloudRenderer * GetBaseCloudRenderer()
Get a pointer to the cloud renderer.
Get a pointer to the cloud renderer.

### <a name="GetBasePrecipitationRenderer"/>simul::clouds::BasePrecipitationRenderer * GetBasePrecipitationRenderer()
Get a pointer to the rain/snow renderer.
Get a pointer to the rain/snow renderer.

### <a name="GetBaseSkyRenderer"/>simul::sky::BaseSkyRenderer * GetBaseSkyRenderer()
Get a pointer to the sky renderer.
Get a pointer to the sky renderer.

### <a name="GetCloud2DRenderer"/>simul::clouds::Base2DCloudRenderer * GetCloud2DRenderer()
Get a pointer to the 2D (high-altitude/Cirrus) cloud renderer, or NULL if none is present.
Get a pointer to the 2D (high-altitude/Cirrus) cloud renderer, or NULL if none is present.

### <a name="GetExportLightningStrikes"/>int GetExportLightningStrikes(simul::clouds::ExportLightningStrike export_strikes, int max_s, float game_time, float real_time)
Get lightning strikes. This calls GetExportLightningStrikes in CloudKeyframer, but also includes
a cloud density query so that lightning can't come from empty sky.
Get lightning strikes. This calls GetExportLightningStrikes in CloudKeyframer, but also includes
a cloud density query so that lightning can't come from empty sky.

### <a name="GetHorizonColour"/>simul::sky::float4  const & GetHorizonColour(float view_altitude_km)
Set a depth texture, whose alpha values represent the depth co-ordinate. This will be used when clouds are rendered in front of terrain etc.
Get the representative HDR colour of the horizon, as seen from the specified altitude 
**view_altitude_km** .
Set a depth texture, whose alpha values represent the depth co-ordinate. This will be used when clouds are rendered in front of terrain etc.
Get the representative HDR colour of the horizon, as seen from the specified altitude 
**view_altitude_km** .

### <a name="GetLightColour"/>simul::sky::float4  const & GetLightColour(float view_altitude_km)
Get the HDR light colour, as seen from the specified altitude 
**view_altitude_km**
Get the HDR light colour, as seen from the specified altitude 
**view_altitude_km**

### <a name="GetLightningRenderer"/>simul::clouds::BaseLightningRenderer * GetLightningRenderer()
Get a pointer to the lightning renderer.
Get a pointer to the lightning renderer.

### <a name="GetSkyKeyframer"/>simul::sky::SkyKeyframer * GetSkyKeyframer()
Convenience function to get the next sky keyframe that can be modified without any recalculation.
Convenience function to get the next sky keyframe that can be modified without any recalculation.

### <a name="GetTransparencyAtmospherics"/>simul::clouds::TransparencyAtmospherics GetTransparencyAtmospherics(simul::crossplatform::ViewStruct viewStruct)
This returns a struct containing the textures and values needed to apply atmospherics to transparent objects.
This returns a struct containing the textures and values needed to apply atmospherics to transparent objects.

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
De-initialize all API-dependent objects in the weather renderer and its member renderers.
De-initialize all API-dependent objects in the weather renderer and its member renderers.

### <a name="operator="/>simul::clouds::BaseWeatherRenderer  const & operator=(simul::clouds::BaseWeatherRenderer W)
Copy the properties of one BaseWeatherRenderer to another, including copying the properties of their sky and cloud renderers.
Copy the properties of one BaseWeatherRenderer to another, including copying the properties of their sky and cloud renderers.

### <a name="PreRenderUpdate"/>void PreRenderUpdate(simul::crossplatform::DeviceContext deviceContext, float real_time)
Once per-frame update. Do this before any rendering each frame. For most platform implementations, you should set the
matrices relevant to the **main** view before calling this.
Once per-frame update. Do this before any rendering each frame. For most platform implementations, you should set the
matrices relevant to the **main** view before calling this.

### <a name="RecompileShaders"/>void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.
Platform-dependent function to reload the shaders - only use this for debug purposes.

### <a name="RemoveView"/>void RemoveView(int view_id)
Ensure that per-view objects are destroyed for the view in question: they will be rebuilt if needed later.
Ensure that per-view objects are destroyed for the view in question: they will be rebuilt if needed later.

### <a name="Render"/>void Render(simul::crossplatform::DeviceContext deviceContext, simul::clouds::TrueSkyRenderMode renderMode, float exposure, float gamma, simul::crossplatform::Texture mainDepthTexture, simul::crossplatform::Texture cubemapTexture, simul::crossplatform::Viewport depthViewport)
Render the sky including atmospherics, into the current rendertarget, using a supplied depth texture.

**deviceContext** is the platform-dependent render context, **exposure** is a multiplier for the rendered sky brightness,
The **view_id** is an integer that distinguishes between multiple simultaneous viewports onscreen.
By convention, viewport 0 is the main view, and viewport 1 is the cubemap for reflections and lighting.
If **is_cubemap** is set, low-definition rendering is used.
The **mainDepthTexture** is a single-sampled or MSAA depth texture. You can use a simul::crossplatform::Texture-derived
class to wrapper your depth texture.
The **depthViewport** determines what part of the depth texture represents this viewport - normally (0,0,1,1).

### <a name="RenderCelestialBackground"/>void RenderCelestialBackground(simul::crossplatform::DeviceContext deviceContext, simul::clouds::TrueSkyRenderMode renderMode, simul::crossplatform::Texture depthTexture, vec4 viewportTextureRegionXYWH, float exposure)
Draw the sun, moon and stars - call this while the depth buffer is bound.
Draw the sun, moon and stars - call this while the depth buffer is bound.

### <a name="RenderMixedResolution"/>bool RenderMixedResolution(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture, simul::clouds::TrueSkyRenderMode renderMode, float exposure, float gamma, vec4 depthViewportXYWH, simul::crossplatform::Texture ambientCubemapTexture)
**deviceContext** is the platform-dependent render context, **exposure** is a multiplier for the rendered sky brightness,
The **view_id** is an integer that distinguishes between multiple simultaneous viewports onscreen.
By convention, viewport 0 is the main view, and viewport 1 is the cubemap for reflections and lighting.
If **is_cubemap** is set, low-definition rendering is used.
The **mainDepthTexture** is a single-sampled or MSAA depth texture. You can use a simul::crossplatform::Texture-derived
class to wrapper your depth texture.
The **lowResDepthTexture** is an API-dependent texture or texture resource pointer, with near far depth in the r and g, and b 0 or 1 for edges.
The **depthViewportXYWH** determines what part of the depth texture represents this viewport - normally (0,0,1,1).
Returns true if there is a lightpass.
**deviceContext** is the platform-dependent render context, **exposure** is a multiplier for the rendered sky brightness,
The **view_id** is an integer that distinguishes between multiple simultaneous viewports onscreen.
By convention, viewport 0 is the main view, and viewport 1 is the cubemap for reflections and lighting.
If **is_cubemap** is set, low-definition rendering is used.
The **mainDepthTexture** is a single-sampled or MSAA depth texture. You can use a simul::crossplatform::Texture-derived
class to wrapper your depth texture.
The **lowResDepthTexture** is an API-dependent texture or texture resource pointer, with near far depth in the r and g, and b 0 or 1 for edges.
The **depthViewportXYWH** determines what part of the depth texture represents this viewport - normally (0,0,1,1).
Returns true if there is a lightpass.

### <a name="RenderOverlays"/>void RenderOverlays(simul::crossplatform::DeviceContext deviceContext, int view_id)
Draw the debug overlays.
Draw the debug overlays.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform renderPlatform)
Initialize the  API-dependent objects in the weather renderer and its member renderers. This is usually needed
when the 3D view is first set-up.
Initialize the  API-dependent objects in the weather renderer and its member renderers. This is usually needed
when the 3D view is first set-up.

### <a name="SetAllDownscale"/>void SetAllDownscale(float)
Override the downscale for all current views; does not affect the default - see SetDefaultDownscale.
Override the downscale for all current views; does not affect the default - see SetDefaultDownscale.

### <a name="SetBlurTexture"/>void SetBlurTexture(simul::crossplatform::Texture t)
A blurred texture, to be drawn usually per-frame.
A blurred texture, to be drawn usually per-frame.

### <a name="SetCubemapTransform"/>void SetCubemapTransform(float m)
A transform for the cubemap set by SetCubemapTexture().
A transform for the cubemap set by SetCubemapTexture().

### <a name="RenderLowResolutionElements"/>bool RenderLowResolutionElements(simul::crossplatform::DeviceContext deviceContext, float exposure, float godrays_strength, simul::clouds::TrueSkyRenderMode renderMode, simul::crossplatform::NearFarPass nearFarPass, simul::crossplatform::Texture lowResDepthTexture, simul::sky::ScatteringVolume scatteringVolume, vec4 viewportRegionXYWH, simul::crossplatform::AmortizationStruct amortizationStruct, simul::crossplatform::Texture ambientCubemapTexture)
Renders the 2D clouds and atmospherics. If the passed depth texture is MSAA, near_pass determines whether to use the near or far depth for each depth texel.
Renders the 2D clouds and atmospherics. If the passed depth texture is MSAA, near_pass determines whether to use the near or far depth for each depth texel.
