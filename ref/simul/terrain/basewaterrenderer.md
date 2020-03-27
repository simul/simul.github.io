---
title: BaseWaterRenderer
layout: reference
weight: 0
---
class BaseWaterRenderer
===

| Include: | Terrain/BaseWaterRenderer.h |



Functions
---

|  | [BaseWaterRenderer](#BaseWaterRenderer)() |
|  | [~BaseWaterRenderer](#~BaseWaterRenderer)() |
| void | [addBoundedWaterObject](#addBoundedWaterObject)(simul::terrain::BoundedWaterObject newWaterObject) |
| bool | [addWaterBuoyancyObject](#addWaterBuoyancyObject)(simul::terrain::WaterMeshObjectValues newObject) |
| bool | [addWaterMaskObject](#addWaterMaskObject)(simul::terrain::waterMaskingObject newObject) |
| bool | [addWaterProbe](#addWaterProbe)(simul::terrain::WaterProbeValues values) |
| void | [createBoundedWaterObject](#createBoundedWaterObject)(uint ID, vec3 dimension, vec3 location) |
| void | [disableBoundlessOcean](#disableBoundlessOcean)() |
| void | [enableBoundlessOcean](#enableBoundlessOcean)(uint layerDensity, uint noOfLayers, int maxDistance) |
| void | [fillBeaufortScaleConstants](#fillBeaufortScaleConstants)() |
| simul::terrain::BoundedWaterObject * | [getBoundedWaterObject](#getBoundedWaterObject)(uint ID) |
| simul::terrain::boundlessOceanProperties * | [getBoundlessOceanProperties](#getBoundlessOceanProperties)() |
| simul::terrain::WaveGrid * | [getBoundlessWaveGrid](#getBoundlessWaveGrid)() |
| long long | [GetEnum](#GetEnum)(char n) |
| simul::terrain::shoreTexture * | [getShoreTextureParams](#getShoreTextureParams)() |
| float * | [getWaterBuoyancyObjectResults](#getWaterBuoyancyObjectResults)(int ID) |
| simul::terrain::WaterParticleSimulator * | [getWaterParticleSimulator](#getWaterParticleSimulator)() |
| vec4 | [getWaterProbeValues](#getWaterProbeValues)(int ID) |
| simul::terrain::WaterWaveletsSimulator * | [getWaterWaveletsSimulator](#getWaterWaveletsSimulator)() |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [PreRenderUpdate](#PreRenderUpdate)(simul::crossplatform::DeviceContext deviceContext, float real_time_seconds) |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [removeBoundedWaterObject](#removeBoundedWaterObject)(uint ID) |
| void | [removeWaterBuoyancyObject](#removeWaterBuoyancyObject)(int ID) |
| void | [removeWaterMaskObject](#removeWaterMaskObject)(int ID) |
| void | [removeWaterProbe](#removeWaterProbe)(int ID) |
| void | [Render](#Render)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Viewport depthViewports, simul::crossplatform::Texture depthTexture, simul::crossplatform::Texture colourTexture, simul::crossplatform::Texture cubemap, int passNo, int vr) |
| void | [RenderFlowRays](#RenderFlowRays)(simul::crossplatform::DeviceContext deviceContext, int width, int height) |
| void | [RenderTextures](#RenderTextures)(simul::crossplatform::DeviceContext deviceContext, int width, int depth) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform r) |
| void | [SetBaseSkyInterface](#SetBaseSkyInterface)(simul::sky::BaseSkyInterface si, simul::sky::AtmosphericScatteringInterface ai) |
| void | [setShoreDepthTexture](#setShoreDepthTexture)(simul::crossplatform::Texture texture) |
| void | [updateBeaufortValues](#updateBeaufortValues)(simul::terrain::localWaterValues valuesToUpdate, float scale) |
| void | [updateBoundlessOceanDensity](#updateBoundlessOceanDensity)(float height) |
| void | [updateTime](#updateTime)(float time) |
| void | [updateWaterBuoyancyObjects](#updateWaterBuoyancyObjects)(simul::crossplatform::DeviceContext deviceContext) |
| void | [updateWaterBuoyancyObjectValues](#updateWaterBuoyancyObjectValues)(simul::terrain::WaterMeshObjectValues values) |
| void | [updateWaterMaskObjectValues](#updateWaterMaskObjectValues)(simul::terrain::waterMaskingObject values) |
| void | [updateWaterProbes](#updateWaterProbes)(simul::crossplatform::DeviceContext deviceContext) |
| void | [updateWaterProbeValues](#updateWaterProbeValues)(simul::terrain::WaterProbeValues values) |


Functions
---
<a name="BaseWaterRenderer"></a>
###  BaseWaterRenderer()
Constructor
<a name="~BaseWaterRenderer"></a>
###  ~BaseWaterRenderer()
Destructor
<a name="addBoundedWaterObject"></a>
### void addBoundedWaterObject(simul::terrain::BoundedWaterObject newWaterObject)
Add an existing water object to the renderer
<a name="addWaterBuoyancyObject"></a>
### bool addWaterBuoyancyObject(simul::terrain::WaterMeshObjectValues newObject)
Create a water buoyancy object
<a name="addWaterMaskObject"></a>
### bool addWaterMaskObject(simul::terrain::waterMaskingObject newObject)
Create a water masking object
<a name="addWaterProbe"></a>
### bool addWaterProbe(simul::terrain::WaterProbeValues values)
Create a water probe from the given values
<a name="createBoundedWaterObject"></a>
### void createBoundedWaterObject(uint ID, vec3 dimension, vec3 location)
Create a bounded water object
<a name="disableBoundlessOcean"></a>
### void disableBoundlessOcean()
Disable boundless ocean
<a name="enableBoundlessOcean"></a>
### void enableBoundlessOcean(uint layerDensity, uint noOfLayers, int maxDistance)
Enable the boundless ocean with a certain maximum detail
<a name="fillBeaufortScaleConstants"></a>
### void fillBeaufortScaleConstants()
Static function to set the default values for the beaufort scale.
<a name="getBoundedWaterObject"></a>
### simul::terrain::BoundedWaterObject * getBoundedWaterObject(uint ID)
Get a pointer to a bounded water object.
<a name="getBoundlessOceanProperties"></a>
### simul::terrain::boundlessOceanProperties * getBoundlessOceanProperties()
Get Boundless ocean properties
<a name="getBoundlessWaveGrid"></a>
### simul::terrain::WaveGrid * getBoundlessWaveGrid()
Get a pointer to the wave grid used by the boundless ocean
<a name="GetEnum"></a>
### long long GetEnum(char n)
Get the enums of water properties. Used mainly for plugin interfacing.
<a name="getShoreTextureParams"></a>
### simul::terrain::shoreTexture * getShoreTextureParams()
Get the shore texture paramaters
<a name="getWaterBuoyancyObjectResults"></a>
### float * getWaterBuoyancyObjectResults(int ID)
Get the results of a water buoyancy object
<a name="getWaterParticleSimulator"></a>
### simul::terrain::WaterParticleSimulator * getWaterParticleSimulator()
Get a pointer to the particle generator
<a name="getWaterProbeValues"></a>
### vec4 getWaterProbeValues(int ID)
Get the results of a water probe
<a name="getWaterWaveletsSimulator"></a>
### simul::terrain::WaterWaveletsSimulator * getWaterWaveletsSimulator()
Get the water wavelets simulator object
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the water renderer.
<a name="PreRenderUpdate"></a>
### void PreRenderUpdate(simul::crossplatform::DeviceContext deviceContext, float real_time_seconds)
Once per-frame update. Do this before any rendering each frame.
<a name="RecompileShaders"></a>
### void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.
<a name="removeBoundedWaterObject"></a>
### void removeBoundedWaterObject(uint ID)
Remove a bounded water object
<a name="removeWaterBuoyancyObject"></a>
### void removeWaterBuoyancyObject(int ID)
Remove a water buoyancy object
<a name="removeWaterMaskObject"></a>
### void removeWaterMaskObject(int ID)
Remove a water masking object
<a name="removeWaterProbe"></a>
### void removeWaterProbe(int ID)
Remove a water probe
<a name="Render"></a>
### void Render(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Viewport depthViewports, simul::crossplatform::Texture depthTexture, simul::crossplatform::Texture colourTexture, simul::crossplatform::Texture cubemap, int passNo, int vr)
Main Render function.
<a name="RenderFlowRays"></a>
### void RenderFlowRays(simul::crossplatform::DeviceContext deviceContext, int width, int height)
Visualise the path of flow rays.
<a name="RenderTextures"></a>
### void RenderTextures(simul::crossplatform::DeviceContext deviceContext, int width, int depth)
Render debug textures.
<a name="RestoreDeviceObjects"></a>
### void RestoreDeviceObjects(simul::crossplatform::RenderPlatform r)
Platform-dependent function called when initializing the water renderer.
<a name="SetBaseSkyInterface"></a>
### void SetBaseSkyInterface(simul::sky::BaseSkyInterface si, simul::sky::AtmosphericScatteringInterface ai)
Set the sky and atmospherics interface to allow the renderer to use the correct lighting values.
<a name="setShoreDepthTexture"></a>
### void setShoreDepthTexture(simul::crossplatform::Texture texture)
Set the shore depth texture
<a name="updateBeaufortValues"></a>
### void updateBeaufortValues(simul::terrain::localWaterValues valuesToUpdate, float scale)
Set the water parameters according the beaufort scale.
<a name="updateBoundlessOceanDensity"></a>
### void updateBoundlessOceanDensity(float height)
Update the ocean surface detail according to how far away from the surface you are.
<a name="updateTime"></a>
### void updateTime(float time)
Set the time.
<a name="updateWaterBuoyancyObjects"></a>
### void updateWaterBuoyancyObjects(simul::crossplatform::DeviceContext deviceContext)
Caluculate water buoyancy object vaues
<a name="updateWaterBuoyancyObjectValues"></a>
### void updateWaterBuoyancyObjectValues(simul::terrain::WaterMeshObjectValues values)
Update the values of a specific water buoyancy object
<a name="updateWaterMaskObjectValues"></a>
### void updateWaterMaskObjectValues(simul::terrain::waterMaskingObject values)
Update the values of a specific water buoyancy object
<a name="updateWaterProbes"></a>
### void updateWaterProbes(simul::crossplatform::DeviceContext deviceContext)
Caluculate the water probe results
<a name="updateWaterProbeValues"></a>
### void updateWaterProbeValues(simul::terrain::WaterProbeValues values)
Update the values of a specific water probe
