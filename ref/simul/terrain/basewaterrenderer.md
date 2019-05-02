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
| bool | [addWaterBuoyancyObject](#addWaterBuoyancyObject)(simul::terrain::WaterBuoyancyObjectValues newObject) |
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
| vec4 | [getWaterProbeValues](#getWaterProbeValues)(int ID) |
| simul::terrain::WaterWaveletsSimulator * | [getWaterWaveletsSimulator](#getWaterWaveletsSimulator)() |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [PreRenderUpdate](#PreRenderUpdate)(simul::crossplatform::DeviceContext deviceContext, float real_time_seconds) |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [removeBoundedWaterObject](#removeBoundedWaterObject)(uint ID) |
| void | [removeWaterBuoyancyObject](#removeWaterBuoyancyObject)(int ID) |
| void | [removeWaterProbe](#removeWaterProbe)(int ID) |
| void | [Render](#Render)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture, simul::crossplatform::Texture colourTexture, simul::crossplatform::Texture cubemap, int passNo) |
| void | [RenderFlowRays](#RenderFlowRays)(simul::crossplatform::DeviceContext deviceContext, int width, int height) |
| void | [RenderTextures](#RenderTextures)(simul::crossplatform::DeviceContext deviceContext, int width, int depth) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform r) |
| void | [SetBaseSkyInterface](#SetBaseSkyInterface)(simul::sky::BaseSkyInterface si, simul::sky::AtmosphericScatteringInterface ai) |
| void | [setShoreDepthTexture](#setShoreDepthTexture)(simul::crossplatform::Texture texture) |
| void | [updateBeaufortValues](#updateBeaufortValues)(simul::terrain::localWaterValues valuesToUpdate, float scale) |
| void | [updateBoundlessOceanDensity](#updateBoundlessOceanDensity)(float height) |
| void | [updateTime](#updateTime)(float time) |
| void | [updateWaterBuoyancyObjects](#updateWaterBuoyancyObjects)(simul::crossplatform::DeviceContext deviceContext) |
| void | [updateWaterBuoyancyObjectValues](#updateWaterBuoyancyObjectValues)(simul::terrain::WaterBuoyancyObjectValues values) |
| void | [updateWaterProbes](#updateWaterProbes)(simul::crossplatform::DeviceContext deviceContext) |
| void | [updateWaterProbeValues](#updateWaterProbeValues)(simul::terrain::WaterProbeValues values) |


Functions
---

### <a name="BaseWaterRenderer"/> BaseWaterRenderer()
Constructor

### <a name="~BaseWaterRenderer"/> ~BaseWaterRenderer()
Destructor

### <a name="addBoundedWaterObject"/>void addBoundedWaterObject(simul::terrain::BoundedWaterObject newWaterObject)
Add an existing water object to the renderer

### <a name="addWaterBuoyancyObject"/>bool addWaterBuoyancyObject(simul::terrain::WaterBuoyancyObjectValues newObject)
Create a water buoyancy object

### <a name="addWaterProbe"/>bool addWaterProbe(simul::terrain::WaterProbeValues values)
Create a water probe from the given values

### <a name="createBoundedWaterObject"/>void createBoundedWaterObject(uint ID, vec3 dimension, vec3 location)
Create a bounded water object

### <a name="disableBoundlessOcean"/>void disableBoundlessOcean()
Disable boundless ocean

### <a name="enableBoundlessOcean"/>void enableBoundlessOcean(uint layerDensity, uint noOfLayers, int maxDistance)
Enable the boundless ocean with a certain maximum detail

### <a name="fillBeaufortScaleConstants"/>void fillBeaufortScaleConstants()
Static function to set the default values for the beaufort scale.

### <a name="getBoundedWaterObject"/>simul::terrain::BoundedWaterObject * getBoundedWaterObject(uint ID)
Get a pointer to a bounded water object.

### <a name="getBoundlessOceanProperties"/>simul::terrain::boundlessOceanProperties * getBoundlessOceanProperties()
Get Boundless ocean properties

### <a name="getBoundlessWaveGrid"/>simul::terrain::WaveGrid * getBoundlessWaveGrid()
Get a pointer to the wave grid used by the boundless ocean

### <a name="GetEnum"/>long long GetEnum(char n)
Get the enums of water properties. Used mainly for plugin interfacing.

### <a name="getShoreTextureParams"/>simul::terrain::shoreTexture * getShoreTextureParams()
Get the shore texture paramaters

### <a name="getWaterBuoyancyObjectResults"/>float * getWaterBuoyancyObjectResults(int ID)
Get the results of a water buoyancy object

### <a name="getWaterProbeValues"/>vec4 getWaterProbeValues(int ID)
Get the results of a water probe

### <a name="getWaterWaveletsSimulator"/>simul::terrain::WaterWaveletsSimulator * getWaterWaveletsSimulator()
Get the water wavelets simulator object

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the water renderer.

### <a name="PreRenderUpdate"/>void PreRenderUpdate(simul::crossplatform::DeviceContext deviceContext, float real_time_seconds)
Once per-frame update. Do this before any rendering each frame.

### <a name="RecompileShaders"/>void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.

### <a name="removeBoundedWaterObject"/>void removeBoundedWaterObject(uint ID)
Remove a bounded water object

### <a name="removeWaterBuoyancyObject"/>void removeWaterBuoyancyObject(int ID)
Remove a water buoyancy object

### <a name="removeWaterProbe"/>void removeWaterProbe(int ID)
Remove a water probe

### <a name="Render"/>void Render(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture, simul::crossplatform::Texture colourTexture, simul::crossplatform::Texture cubemap, int passNo)
Main Render function.

### <a name="RenderFlowRays"/>void RenderFlowRays(simul::crossplatform::DeviceContext deviceContext, int width, int height)
Visualise the path of flow rays.

### <a name="RenderTextures"/>void RenderTextures(simul::crossplatform::DeviceContext deviceContext, int width, int depth)
Render debug textures.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform r)
Platform-dependent function called when initializing the water renderer.

### <a name="SetBaseSkyInterface"/>void SetBaseSkyInterface(simul::sky::BaseSkyInterface si, simul::sky::AtmosphericScatteringInterface ai)
Set the sky and atmospherics interface to allow the renderer to use the correct lighting values.

### <a name="setShoreDepthTexture"/>void setShoreDepthTexture(simul::crossplatform::Texture texture)
Set the shore depth texture

### <a name="updateBeaufortValues"/>void updateBeaufortValues(simul::terrain::localWaterValues valuesToUpdate, float scale)
Set the water parameters according the beaufort scale.

### <a name="updateBoundlessOceanDensity"/>void updateBoundlessOceanDensity(float height)
Update the ocean surface detail according to how far away from the surface you are.

### <a name="updateTime"/>void updateTime(float time)
Set the time.

### <a name="updateWaterBuoyancyObjects"/>void updateWaterBuoyancyObjects(simul::crossplatform::DeviceContext deviceContext)
Caluculate water buoyancy object vaues

### <a name="updateWaterBuoyancyObjectValues"/>void updateWaterBuoyancyObjectValues(simul::terrain::WaterBuoyancyObjectValues values)
Update the values of a specific water buoyancy object

### <a name="updateWaterProbes"/>void updateWaterProbes(simul::crossplatform::DeviceContext deviceContext)
Caluculate the water probe results

### <a name="updateWaterProbeValues"/>void updateWaterProbeValues(simul::terrain::WaterProbeValues values)
Update the values of a specific water probe
