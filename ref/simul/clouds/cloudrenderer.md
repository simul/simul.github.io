---
title: CloudRenderer
layout: reference
weight: 0
---
class CloudRenderer
===

| Include: | Clouds/BaseWeatherRenderer.h |



Functions
---

|  | [CloudRenderer](#CloudRenderer)(simul::clouds::Environment e, simul::base::MemoryInterface mem) |
|  | [~CloudRenderer](#~CloudRenderer)() |
| void | [DrawCrossSectionOnSphere](#DrawCrossSectionOnSphere)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Effect editEffect, simul::crossplatform::Texture t, vec2 texcOffset, vec3 origin, vec4 orient_quat, float qsize, float sph_rad, vec4 colour) |
| void | [EnsureEffectsAreBuilt](#EnsureEffectsAreBuilt)(simul::crossplatform::RenderPlatform renderPlatform) |
| simul::clouds::BaseGpuCloudGenerator * | [GetBaseGpuCloudGenerator](#GetBaseGpuCloudGenerator)() |
| simul::clouds::CloudGeometryHelper * | [GetCloudGeometryHelper](#GetCloudGeometryHelper)(int view_id) |
| simul::clouds::CloudRenderingOptions  & | [GetCloudRenderingOptions](#GetCloudRenderingOptions)() |
| float  const * | [GetCloudScales](#GetCloudScales)() |
| char  const * | [GetDebugText](#GetDebugText)() |
| LineQueryResult | [GetLineQuery](#GetLineQuery)(int id, vec3 pos1_km, vec3 pos2_km) |
| int | [GetMaxSlices](#GetMaxSlices)(int viewport_id) |
| VolumeQueryResult | [GetPointQuery](#GetPointQuery)(int id, vec3 pos_km) |
| VolumeQueryResult | [GetPointQuery](#GetPointQuery)(int id) |
| int | [GetQueryIdForViewId](#GetQueryIdForViewId)(int view_id) |
| simul::crossplatform::Texture * | [GetRandomTexture3D](#GetRandomTexture3D)() |
| float | [GetSunOcclusion](#GetSunOcclusion)(simul::crossplatform::DeviceContext deviceContext, simul::math::Vector3 cam_pos) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| bool | [IsCameraAboveCloudBase](#IsCameraAboveCloudBase)(simul::math::Vector3 cam_pos) |
| void | [MakeCloudShadowTexture](#MakeCloudShadowTexture)() |
| void | [PreRenderUpdate](#PreRenderUpdate)(simul::crossplatform::DeviceContext deviceContext, float real_time) |
| void | [RecompileShaders](#RecompileShaders)() |
| bool | [Render](#Render)(simul::crossplatform::DeviceContext deviceContext, float exposure, simul::clouds::TrueSkyRenderMode renderMode, simul::crossplatform::NearFarPass nearFarPass, simul::crossplatform::Texture depth_tex, simul::sky::ScatteringVolume scatteringVolume, bool write_alpha, vec4 viewportTextureRegionXYWH, simul::crossplatform::AmortizationStruct amortizationStruct, simul::clouds::TwoResFramebuffer fb, simul::sky::LocalFadeTextures localFadeTextures, simul::crossplatform::Texture ambientCubemap) |
| void | [RenderCloudGrid](#RenderCloudGrid)(simul::crossplatform::DeviceContext deviceContext, simul::clouds::CloudKeyframer ck) |
| void | [RenderCloudShadowTexture](#RenderCloudShadowTexture)(simul::crossplatform::DeviceContext deviceContext) |
| void | [RenderCloudVolumes](#RenderCloudVolumes)(simul::crossplatform::DeviceContext deviceContext, simul::clouds::CloudKeyframer ck) |
| void | [RenderCrossSections](#RenderCrossSections)(simul::crossplatform::DeviceContext context) |
| void | [RenderQueries](#RenderQueries)(simul::crossplatform::DeviceContext deviceContext) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform renderPlatform) |
| void | [SetEnableStorms](#SetEnableStorms)(bool s) |
| void | [SetEnvironment](#SetEnvironment)(simul::clouds::Environment e) |
| void | [SetExternalCloudTexture](#SetExternalCloudTexture)(simul::crossplatform::Texture) |
| void | [SetMaxFadeAltitudeKm](#SetMaxFadeAltitudeKm)(float ma_km) |
| void | [SetMaxFadeDistanceKm](#SetMaxFadeDistanceKm)(float dist_km) |
| void | [SetMaxSlices](#SetMaxSlices)(int viewport_id, int maxs) |
| void | [SetNoiseTextureProperties](#SetNoiseTextureProperties)(int size, int freq, int octaves, float persistence) |
| void | [SetPointLight](#SetPointLight)(int id, vec3 pos, float min_radius, float max_radius, vec3 irradiance) |


Functions
---
<a name="CloudRenderer"></a>
###  CloudRenderer(simul::clouds::Environment e, simul::base::MemoryInterface mem)
Constructor: An external keyframer is provided, and an optional memory manager.
<a name="~CloudRenderer"></a>
###  ~CloudRenderer()
Destructor
<a name="DrawCrossSectionOnSphere"></a>
### void DrawCrossSectionOnSphere(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Effect editEffect, simul::crossplatform::Texture t, vec2 texcOffset, vec3 origin, vec4 orient_quat, float qsize, float sph_rad, vec4 colour)
Show the cloud volume window on the lat-long sphere.
<a name="EnsureEffectsAreBuilt"></a>
### void EnsureEffectsAreBuilt(simul::crossplatform::RenderPlatform renderPlatform)
If possible, build all shader effect variations.
<a name="GetBaseGpuCloudGenerator"></a>
### simul::clouds::BaseGpuCloudGenerator * GetBaseGpuCloudGenerator()
Get a pointer to the Cloud Generator
<a name="GetCloudGeometryHelper"></a>
### simul::clouds::CloudGeometryHelper * GetCloudGeometryHelper(int view_id)
Returns a new geometry helper.
<a name="GetCloudRenderingOptions"></a>
### simul::clouds::CloudRenderingOptions  & GetCloudRenderingOptions()
Get a pointer to the current cloud rendering options
<a name="GetCloudScales"></a>
### float  const * GetCloudScales()
Get the xyz scales of the clouds in metres.
<a name="GetDebugText"></a>
### char  const * GetDebugText()
Get some per-frame text information for debugging - usually timing data.
<a name="GetLineQuery"></a>
### LineQueryResult GetLineQuery(int id, vec3 pos1_km, vec3 pos2_km)
Set, or create a cloud query. This returns the previous results of the same query.
<a name="GetMaxSlices"></a>
### int GetMaxSlices(int viewport_id)
Cloud rendering detail is determined by the number of slices. See SetMaxSlices.
<a name="GetPointQuery"></a>
### VolumeQueryResult GetPointQuery(int id, vec3 pos_km)
Set, or create a cloud query. This returns the previous results of the same query.
<a name="GetPointQuery"></a>
### VolumeQueryResult GetPointQuery(int id)
Get results of a cloud query.
<a name="GetQueryIdForViewId"></a>
### int GetQueryIdForViewId(int view_id)
Get the query id for the specified view. If Render() has been called for the view, the query should have a valid set of results for the last frame rendered.
<a name="GetRandomTexture3D"></a>
### simul::crossplatform::Texture * GetRandomTexture3D()
Get the random 3D texture.
<a name="GetSunOcclusion"></a>
### float GetSunOcclusion(simul::crossplatform::DeviceContext deviceContext, simul::math::Vector3 cam_pos)
Get a value for how much the sun is blocked from the clouds.
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Call this Platform-dependent function when the 3D device has been lost.
<a name="IsCameraAboveCloudBase"></a>
### bool IsCameraAboveCloudBase(simul::math::Vector3 cam_pos)
Return true if the camera is above the cloudbase altitude.
<a name="MakeCloudShadowTexture"></a>
### void MakeCloudShadowTexture()
Get an API-dependent identifier for the cloud's 2D shadow.
<a name="PreRenderUpdate"></a>
### void PreRenderUpdate(simul::crossplatform::DeviceContext deviceContext, float real_time)
Once per-frame update. Do this before any rendering each frame. Called by BaseWeatherRenderer.
<a name="RecompileShaders"></a>
### void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.
<a name="Render"></a>
### bool Render(simul::crossplatform::DeviceContext deviceContext, float exposure, simul::clouds::TrueSkyRenderMode renderMode, simul::crossplatform::NearFarPass nearFarPass, simul::crossplatform::Texture depth_tex, simul::sky::ScatteringVolume scatteringVolume, bool write_alpha, vec4 viewportTextureRegionXYWH, simul::crossplatform::AmortizationStruct amortizationStruct, simul::clouds::TwoResFramebuffer fb, simul::sky::LocalFadeTextures localFadeTextures, simul::crossplatform::Texture ambientCubemap)
Platform-dependent render function.
<a name="RenderCloudGrid"></a>
### void RenderCloudGrid(simul::crossplatform::DeviceContext deviceContext, simul::clouds::CloudKeyframer ck)
Render the cloud grid for debugging purposes
<a name="RenderCloudShadowTexture"></a>
### void RenderCloudShadowTexture(simul::crossplatform::DeviceContext deviceContext)
The cloud shadow texture:
Centred on the viewer
Aligned to the sun.
Output is km in front of or behind the view pos where shadow starts
<a name="RenderCloudVolumes"></a>
### void RenderCloudVolumes(simul::crossplatform::DeviceContext deviceContext, simul::clouds::CloudKeyframer ck)
Render the cloud volumes for debugging purposes
<a name="RenderCrossSections"></a>
### void RenderCrossSections(simul::crossplatform::DeviceContext context)
Show the cloud volumes onscreen by cross section.
<a name="RenderQueries"></a>
### void RenderQueries(simul::crossplatform::DeviceContext deviceContext)
Draw the queries in 3D
<a name="RestoreDeviceObjects"></a>
### void RestoreDeviceObjects(simul::crossplatform::RenderPlatform renderPlatform)
Platform-dependent function to generate device objects for the renderer.
<a name="SetEnableStorms"></a>
### void SetEnableStorms(bool s)
Where supported, enable lightning generation.
<a name="SetEnvironment"></a>
### void SetEnvironment(simul::clouds::Environment e)
Set the sky interface.
<a name="SetExternalCloudTexture"></a>
### void SetExternalCloudTexture(simul::crossplatform::Texture)
Where we create the main volume texture for rendering elsewhere, we pass it in here.
This permits ESRAM on XboxOne for example, in a game engine.
<a name="SetMaxFadeAltitudeKm"></a>
### void SetMaxFadeAltitudeKm(float ma_km)
Altitude for fade texture lookups:
<a name="SetMaxFadeDistanceKm"></a>
### void SetMaxFadeDistanceKm(float dist_km)
Distance for fade texture lookups:
<a name="SetMaxSlices"></a>
### void SetMaxSlices(int viewport_id, int maxs)
Cloud rendering detail is determined by the number of slices. If not set the value from the CloudKeyframer will be used (GetDefaultNumSlices), but each viewport id can have a separate setting.
<a name="SetNoiseTextureProperties"></a>
### void SetNoiseTextureProperties(int size, int freq, int octaves, float persistence)
Adjust the noise texture
<a name="SetPointLight"></a>
### void SetPointLight(int id, vec3 pos, float min_radius, float max_radius, vec3 irradiance)
Place a point light source.

Fields
---

**ShouldRenderCloudShadowTexture** Class for real-time volumetric cloud rendering.
 There should exist a "trueSKY space", where the origin(0,0,0 Cartesian) is at global mean sea level, and an arbitrary point on the Earth's surface.
The Z axis points up, the X and Y axes are arbitrary (for reasons described below). To avoid singularities, this point, and the orientation of its axes
should be represented by a double-precision quaternion, which represents the rotation from (say) latitude and longitude zero with X pointing East and Y pointing North.

The Volume Window is a deformed cuboid, its upper and lower surfaces matching the Earth's curvature. On the GPU, it is a 3D texture.

This trueSKY space moves in steps equivalent to one horizontal texel. The function CloudRenderer::MoveCloudWindow(x,y) does this.
This should be done when the chosen viewpoint (this is up to you) moves more than a texel in any horizontal direction. This way, we need only update the edges as the window moves.

**last_interpolation_checksum**  A checksum to see if the interpolated cloud volume is out of date. This may fail every frame if time is moving continuously - that's ok.
