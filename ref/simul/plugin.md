---
title: plugin
layout: reference
weight: 0
---
namespace plugin
===

| Include: | Plugins/TrueSkyPluginRender/PluginTrueSkyRenderer.h |



Classes and Structures
---

| struct [ExternalTexture](plugin/externaltexture.html) |  |
| struct [Query](plugin/query.html) |  |
| class [TrackingAllocator](plugin/trackingallocator.html) |  |

Functions
---

| simul::sky::uid | [GetCloudLayerUIDByIndex](#GetCloudLayerUIDByIndex)(int index) |
| simul::sky::uid | [GetInterpolatedCloudKeyframeUniqueId](#GetInterpolatedCloudKeyframeUniqueId)(int layer) |
| simul::sky::uid | [GetInterpolatedSkyKeyframeUniqueId](#GetInterpolatedSkyKeyframeUniqueId)() |
| int | [GetNumStorms](#GetNumStorms)() |
| simul::sky::uid | [GetStormAtTime](#GetStormAtTime)(float t) |
| simul::sky::uid | [GetStormByIndex](#GetStormByIndex)(int i) |
| bool | [StaticAddWaterBuoyancyObject](#StaticAddWaterBuoyancyObject)(simul::terrain::WaterMeshObjectValues newObject) |
| bool | [StaticAddWaterMaskObject](#StaticAddWaterMaskObject)(simul::terrain::waterMaskingObject newObject) |
| bool | [StaticAddWaterParticleGenerator](#StaticAddWaterParticleGenerator)(simul::terrain::particleGeneratorValues newGenerator, simul::terrain::particleGeneratorType newGeneratorType, simul::plugin::ExternalTexture customPlaneTexture) |
| bool | [StaticAddWaterProbe](#StaticAddWaterProbe)(simul::terrain::WaterProbeValues values) |
| void | [StaticCloudLineQuery](#StaticCloudLineQuery)(int id, float startpos, float endpos, LineQueryResult res) |
| void | [StaticCloudPointQuery](#StaticCloudPointQuery)(int id, float pos, VolumeQueryResult res) |
| int | [StaticCopySkylight](#StaticCopySkylight)(void pContext, int cube_id, float shValues, int shOrder, void targetTex, mat4 engineToSimulMatrix4x4, int updateFrequency, float blend, float copy_exposure, float copy_gamma) |
| int | [StaticCopySkylight2](#StaticCopySkylight2)(void pContext, int cube_id, float shValues, int shOrder, void targetTex, mat4 engineToSimulMatrix4x4, int updateFrequency, float blend, float copy_exposure, float copy_gamma, vec3 ground_colour) |
| bool | [StaticCreateBoundedWaterObject](#StaticCreateBoundedWaterObject)(int ID, float dimension, float location) |
| void | [StaticEnableLogging](#StaticEnableLogging)(char logfile) |
| void | [StaticExecuteDeferredRendering](#StaticExecuteDeferredRendering)() |
| void | [StaticExportCloudLayerToGeometry](#StaticExportCloudLayerToGeometry)(char filenameUtf8, int index) |
| bool | [StaticFillColourTable](#StaticFillColourTable)(simul::sky::uid uid, int x, int y, int z, float target) |
| int | [StaticGet](#StaticGet)(long long num, simul::base::Variant v) |
| long long | [StaticGetEnum](#StaticGetEnum)(char name) |
| void * | [StaticGetEnvironment](#StaticGetEnvironment)() |
| float | [StaticGetFloatAtPosition](#StaticGetFloatAtPosition)(long long enum_, float pos, int uid) |
| int | [StaticGetLightningBolts](#StaticGetLightningBolts)(simul::clouds::ExportLightningStrike s, int maxnum) |
| int | [StaticGetOrAddView](#StaticGetOrAddView)(void ident) |
| int | [StaticGetRender](#StaticGetRender)(char name, int numparams, simul::base::Variant params) |
| bool | [StaticGetRenderBool](#StaticGetRenderBool)(char name) |
| float | [StaticGetRenderFloat](#StaticGetRenderFloat)(char name) |
| float | [StaticGetRenderFloatAtPosition](#StaticGetRenderFloatAtPosition)(char name, float pos) |
| int | [StaticGetRenderInt](#StaticGetRenderInt)(char name, int numparams, simul::base::Variant params) |
| simul::plugin::PluginTrueSkyRenderer * | [StaticGetRenderInterfaceInstance](#StaticGetRenderInterfaceInstance)() |
| int | [StaticGetRenderString](#StaticGetRenderString)(char name, char str, int len) |
| bool | [StaticGetWaterBool](#StaticGetWaterBool)(char name, int ID) |
| float * | [StaticGetWaterBuoyancyObjectResults](#StaticGetWaterBuoyancyObjectResults)(int ID) |
| float | [StaticGetWaterFloat](#StaticGetWaterFloat)(char name, int ID) |
| int | [StaticGetWaterInt](#StaticGetWaterInt)(char name, int ID) |
| void | [StaticGetWaterProbeValues](#StaticGetWaterProbeValues)(int ID, vec4 values) |
| bool | [StaticGetWaterVector](#StaticGetWaterVector)(char name, int ID, float) |
| bool | [StaticHasRenderFloat](#StaticHasRenderFloat)(char name) |
| bool | [StaticHasRenderInt](#StaticHasRenderInt)(char name) |
| int | [StaticInitInterface](#StaticInitInterface)() |
| void | [StaticLightingQuery](#StaticLightingQuery)(int id, float pos, LightingQueryResult res) |
| int | [StaticOnDeviceChanged](#StaticOnDeviceChanged)(void device) |
| void | [StaticPopPath](#StaticPopPath)(char type) |
| int | [StaticProbeSkylight](#StaticProbeSkylight)(void pContext, int cube_id, int mip_size, int face_index, int x, int y, int w, int h, float targetValues) |
| void | [StaticProcessQueries](#StaticProcessQueries)(int num, simul::plugin::Query queries) |
| void | [StaticPushPath](#StaticPushPath)(char type, char value) |
| void | [StaticRemoveBoundedWaterObject](#StaticRemoveBoundedWaterObject)(int ID) |
| void | [StaticRemoveView](#StaticRemoveView)(int view_id) |
| void | [StaticRemoveWaterBuoyancyObject](#StaticRemoveWaterBuoyancyObject)(int ID) |
| void | [StaticRemoveWaterMaskObject](#StaticRemoveWaterMaskObject)(int ID) |
| void | [StaticRemoveWaterParticleGenerator](#StaticRemoveWaterParticleGenerator)(int ID) |
| void | [StaticRemoveWaterProbe](#StaticRemoveWaterProbe)(int ID) |
| simul::sky::uid | [StaticRenderCreateCloudKeyframer](#StaticRenderCreateCloudKeyframer)(char name) |
| simul::sky::uid | [StaticRenderDeleteCloudKeyframer](#StaticRenderDeleteCloudKeyframer)(simul::sky::uid uid) |
| void | [StaticRenderDeleteKeyframe](#StaticRenderDeleteKeyframe)(simul::sky::uid uid) |
| int | [StaticRenderFrame](#StaticRenderFrame)(void device, void pContext, int view_id, float viewMatrix4x4, float projMatrix4x4, void depthTexture, void colourTarget, simul::crossplatform::Viewport depthViewports, simul::crossplatform::Viewport viewports, simul::plugin::RenderStyle s, float exposure, float gamma, int framenumber, simul::crossplatform::MultiResConstants pMultiResConstants) |
| simul::sky::uid | [StaticRenderGetKeyframeByIndex](#StaticRenderGetKeyframeByIndex)(int layer, int index) |
| int | [StaticRenderGetNumKeyframes](#StaticRenderGetNumKeyframes)(int layer) |
| simul::sky::uid | [StaticRenderInsertKeyframe](#StaticRenderInsertKeyframe)(int layer, float t) |
| bool | [StaticRenderKeyframeGetBool](#StaticRenderKeyframeGetBool)(simul::sky::uid uid, char name) |
| float | [StaticRenderKeyframeGetFloat](#StaticRenderKeyframeGetFloat)(simul::sky::uid uid, char name) |
| int | [StaticRenderKeyframeGetInt](#StaticRenderKeyframeGetInt)(simul::sky::uid uid, char name) |
| bool | [StaticRenderKeyframeHasBool](#StaticRenderKeyframeHasBool)(simul::sky::uid uid, char name) |
| bool | [StaticRenderKeyframeHasFloat](#StaticRenderKeyframeHasFloat)(simul::sky::uid uid, char name) |
| bool | [StaticRenderKeyframeHasInt](#StaticRenderKeyframeHasInt)(simul::sky::uid uid, char name) |
| float | [StaticRenderKeyframerGetFloat](#StaticRenderKeyframerGetFloat)(simul::sky::uid uid, char name) |
| int | [StaticRenderKeyframerGetInt](#StaticRenderKeyframerGetInt)(simul::sky::uid uid, char name) |
| void | [StaticRenderKeyframerSetFloat](#StaticRenderKeyframerSetFloat)(simul::sky::uid uid, char name, float value) |
| void | [StaticRenderKeyframerSetInt](#StaticRenderKeyframerSetInt)(simul::sky::uid uid, char name, int value) |
| void | [StaticRenderKeyframeSetBool](#StaticRenderKeyframeSetBool)(simul::sky::uid uid, char name, bool value) |
| void | [StaticRenderKeyframeSetFloat](#StaticRenderKeyframeSetFloat)(simul::sky::uid uid, char name, float value) |
| void | [StaticRenderKeyframeSetInt](#StaticRenderKeyframeSetInt)(simul::sky::uid uid, char name, int value) |
| void | [StaticRenderOverlays](#StaticRenderOverlays)(void device, void pContext, void externalDepthTexture, float viewMatrix4x4, float projMatrix4x4, int view_id, void colourTarget, simul::crossplatform::Viewport viewports) |
| int | [StaticSet](#StaticSet)(long long num, simul::base::Variant v) |
| void | [StaticSetDebugOutputCallback](#StaticSetDebugOutputCallback)(DebugOutputCallback) |
| int | [StaticSetExternalDynamicValues](#StaticSetExternalDynamicValues)(simul::plugin::ExternalDynamicValues D) |
| int | [StaticSetExternalRenderValues](#StaticSetExternalRenderValues)(simul::plugin::ExternalRenderValues C) |
| void | [StaticSetGraphicsDevice](#StaticSetGraphicsDevice)(void device, simul::crossplatform::RenderPlatformType deviceType, UnityGfxDeviceEventType eventType) |
| void | [StaticSetGraphicsDeviceAndContext](#StaticSetGraphicsDeviceAndContext)(void device, void context, simul::crossplatform::RenderPlatformType deviceType, UnityGfxDeviceEventType eventType) |
| void | [StaticSetKeyframerMapTexture](#StaticSetKeyframerMapTexture)(simul::sky::uid uid, char PNGName) |
| void | [StaticSetMatrix4x4](#StaticSetMatrix4x4)(char name, float matrix4x4) |
| void | [StaticSetMemoryInterface](#StaticSetMemoryInterface)(simul::base::MemoryInterface) |
| void | [StaticSetPointLight](#StaticSetPointLight)(int id, pos, float min_radius, float max_radius, irradiance) |
| void | [StaticSetRender](#StaticSetRender)(char name, int num_params, simul::base::Variant params) |
| void | [StaticSetRenderBool](#StaticSetRenderBool)(char name, bool value) |
| void | [StaticSetRenderFloat](#StaticSetRenderFloat)(char name, float value) |
| void | [StaticSetRenderInt](#StaticSetRenderInt)(char name, int value) |
| void | [StaticSetRenderString](#StaticSetRenderString)(char name, char value) |
| int | [StaticSetRenderTexture](#StaticSetRenderTexture)(char name, void texturePtr) |
| int | [StaticSetSequence](#StaticSetSequence)(std::string SequenceInput) |
| int | [StaticSetSequence2](#StaticSetSequence2)(char txt) |
| int | [StaticSetSequenceTxt](#StaticSetSequenceTxt)(char txt) |
| void | [StaticSetWaterBool](#StaticSetWaterBool)(char name, int ID, bool value) |
| void | [StaticSetWaterFloat](#StaticSetWaterFloat)(char name, int ID, float value) |
| void | [StaticSetWaterInt](#StaticSetWaterInt)(char name, int ID, int value) |
| void | [StaticSetWaterVector](#StaticSetWaterVector)(char name, int ID, float value) |
| int | [StaticShutDownInterface](#StaticShutDownInterface)() |
| int | [StaticSpawnLightning](#StaticSpawnLightning)(startpos, endpos, float magnitude, colour) |
| bool | [StaticTriggerAction](#StaticTriggerAction)(char name) |
| void | [StaticUpdateWaterBuoyancyObjectValues](#StaticUpdateWaterBuoyancyObjectValues)(simul::terrain::WaterMeshObjectValues values) |
| void | [StaticUpdateWaterMaskObjectValues](#StaticUpdateWaterMaskObjectValues)(simul::terrain::waterMaskingObject values) |
| void | [StaticUpdateWaterParticleGeneratorValues](#StaticUpdateWaterParticleGeneratorValues)(simul::terrain::particleGeneratorValues values, simul::terrain::particleGeneratorType generatorType, simul::plugin::ExternalTexture customPlaneTexture) |
| void | [StaticUpdateWaterProbeValues](#StaticUpdateWaterProbeValues)(simul::terrain::WaterProbeValues values) |
| int | [StaticWaterSet](#StaticWaterSet)(long long num, int ID, simul::base::Variant v) |
| void | [UnitySetGraphicsDevice](#UnitySetGraphicsDevice)(void device, simul::crossplatform::RenderPlatformType deviceType, UnityGfxDeviceEventType eventType) |


Functions
---
<a name="GetCloudLayerUIDByIndex"></a>
### simul::sky::uid GetCloudLayerUIDByIndex(int index)
Get the UID of a Cloud Layer by Index (Starting at 0)
<a name="GetInterpolatedCloudKeyframeUniqueId"></a>
### simul::sky::uid GetInterpolatedCloudKeyframeUniqueId(int layer)
Get the ID of the current interpolated cloud keyframe on the given layer
<a name="GetInterpolatedSkyKeyframeUniqueId"></a>
### simul::sky::uid GetInterpolatedSkyKeyframeUniqueId()
Get the ID of the current interpolated sky keyframe
<a name="GetNumStorms"></a>
### int GetNumStorms()
Get the total number of storms
<a name="GetStormAtTime"></a>
### simul::sky::uid GetStormAtTime(float t)
Get a storm ID, if it exists, at time t
<a name="GetStormByIndex"></a>
### simul::sky::uid GetStormByIndex(int i)
Get a storm ID with index i
<a name="StaticAddWaterBuoyancyObject"></a>
### bool StaticAddWaterBuoyancyObject(simul::terrain::WaterMeshObjectValues newObject)
Create a water buoyancy object with a given struct that holds an array of vertices
<a name="StaticAddWaterMaskObject"></a>
### bool StaticAddWaterMaskObject(simul::terrain::waterMaskingObject newObject)
Create a water masking object
<a name="StaticAddWaterParticleGenerator"></a>
### bool StaticAddWaterParticleGenerator(simul::terrain::particleGeneratorValues newGenerator, simul::terrain::particleGeneratorType newGeneratorType, simul::plugin::ExternalTexture customPlaneTexture)
Create a particle generator
<a name="StaticAddWaterProbe"></a>
### bool StaticAddWaterProbe(simul::terrain::WaterProbeValues values)
Create a water probe
<a name="StaticCloudLineQuery"></a>
### void StaticCloudLineQuery(int id, float startpos, float endpos, LineQueryResult res)
Perform a query of the cloud properties along a given vector in world space
<a name="StaticCloudPointQuery"></a>
### void StaticCloudPointQuery(int id, float pos, VolumeQueryResult res)
Perform a query of the cloud properties at a given point in world space
<a name="StaticCopySkylight"></a>
### int StaticCopySkylight(void pContext, int cube_id, float shValues, int shOrder, void targetTex, mat4 engineToSimulMatrix4x4, int updateFrequency, float blend, float copy_exposure, float copy_gamma)
(DEPRECATED) Update a skylight cubemap, and return the latest result.
<a name="StaticCopySkylight2"></a>
### int StaticCopySkylight2(void pContext, int cube_id, float shValues, int shOrder, void targetTex, mat4 engineToSimulMatrix4x4, int updateFrequency, float blend, float copy_exposure, float copy_gamma, vec3 ground_colour)
(DEPRECATED) Update a skylight cubemap, and return the latest result.
<a name="StaticCreateBoundedWaterObject"></a>
### bool StaticCreateBoundedWaterObject(int ID, float dimension, float location)
Create a bounded water object with a given ID
<a name="StaticEnableLogging"></a>
### void StaticEnableLogging(char logfile)
Pass a specific char pointer to write log output to.
<a name="StaticExecuteDeferredRendering"></a>
### void StaticExecuteDeferredRendering()
Render all the deferred contexts.
<a name="StaticExportCloudLayerToGeometry"></a>
### void StaticExportCloudLayerToGeometry(char filenameUtf8, int index)
Exports the cloud layer as geometry
<a name="StaticFillColourTable"></a>
### bool StaticFillColourTable(simul::sky::uid uid, int x, int y, int z, float target)
Set the current atmosphric scattering colour to a constant colour
<a name="StaticGet"></a>
### int StaticGet(long long num, simul::base::Variant v)
Get thevalue corresponding to the given enum.
<a name="StaticGetEnum"></a>
### long long StaticGetEnum(char name)
Get the enum of a specific value
<a name="StaticGetEnvironment"></a>
### void * StaticGetEnvironment()
Returns the simul::clouds::Environment pointer.
<a name="StaticGetFloatAtPosition"></a>
### float StaticGetFloatAtPosition(long long enum_, float pos, int uid)
Get a float value at a specific point within worldspace (enum version)
<a name="StaticGetLightningBolts"></a>
### int StaticGetLightningBolts(simul::clouds::ExportLightningStrike s, int maxnum)
Get the properties of a lightning bolt that is currently active in the scene
<a name="StaticGetOrAddView"></a>
### int StaticGetOrAddView(void ident)
Ensure that a view is created, unique to the ident that was passed.
So this ident must be unique to each of the active views in the external engine.
Return
---
The trueSKY id for that view.
<a name="StaticGetRender"></a>
### int StaticGetRender(char name, int numparams, simul::base::Variant params)
(DEPRECATED) Get an int value.
<a name="StaticGetRenderBool"></a>
### bool StaticGetRenderBool(char name)
Get a string value.
<a name="StaticGetRenderFloat"></a>
### float StaticGetRenderFloat(char name)
Get a float value.
<a name="StaticGetRenderFloatAtPosition"></a>
### float StaticGetRenderFloatAtPosition(char name, float pos)
Get a float value at a specific point within worldspace
<a name="StaticGetRenderInt"></a>
### int StaticGetRenderInt(char name, int numparams, simul::base::Variant params)
Get an int value.
<a name="StaticGetRenderInterfaceInstance"></a>
### simul::plugin::PluginTrueSkyRenderer * StaticGetRenderInterfaceInstance()
Get a pointer to the plugin renderer
<a name="StaticGetRenderString"></a>
### int StaticGetRenderString(char name, char str, int len)
Get a string value.
<a name="StaticGetWaterBool"></a>
### bool StaticGetWaterBool(char name, int ID)
Get a bool for a specfic water object
<a name="StaticGetWaterBuoyancyObjectResults"></a>
### float * StaticGetWaterBuoyancyObjectResults(int ID)
Get the results of a water buoyancy object
<a name="StaticGetWaterFloat"></a>
### float StaticGetWaterFloat(char name, int ID)
Get a float for a specfic water object
<a name="StaticGetWaterInt"></a>
### int StaticGetWaterInt(char name, int ID)
Get an int for a specfic water object
<a name="StaticGetWaterProbeValues"></a>
### void StaticGetWaterProbeValues(int ID, vec4 values)
Get the results of a water probe
<a name="StaticGetWaterVector"></a>
### bool StaticGetWaterVector(char name, int ID, float)
Get a vector for a specfic water object
<a name="StaticHasRenderFloat"></a>
### bool StaticHasRenderFloat(char name)
Check if this version of trueSky has a given float value
<a name="StaticHasRenderInt"></a>
### bool StaticHasRenderInt(char name)
Check if this version of trueSky has a given int value
<a name="StaticInitInterface"></a>
### int StaticInitInterface()
Ensure that the renderer is initialized. Subsequent calls have no effect.
<a name="StaticLightingQuery"></a>
### void StaticLightingQuery(int id, float pos, LightingQueryResult res)
Perform a query of the atmosphric light properties at a given point in world space
<a name="StaticOnDeviceChanged"></a>
### int StaticOnDeviceChanged(void device)
Assign the platform GPU device pointer.
<a name="StaticPopPath"></a>
### void StaticPopPath(char type)
Pop a path from a stack, either "TexturePath", or "ShaderPath".
<a name="StaticProbeSkylight"></a>
### int StaticProbeSkylight(void pContext, int cube_id, int mip_size, int face_index, int x, int y, int w, int h, float targetValues)
Probe a rectangular area of a skylight cubemap.
<a name="StaticProcessQueries"></a>
### void StaticProcessQueries(int num, simul::plugin::Query queries)
Process currently active queries
<a name="StaticPushPath"></a>
### void StaticPushPath(char type, char value)
Push a path for trueSKY to use. Must be "TexturePath", "ShaderPath", or "ShaderBinaryPath". The latter is not a stack.
<a name="StaticRemoveBoundedWaterObject"></a>
### void StaticRemoveBoundedWaterObject(int ID)
Remove a bounded water object with a given ID
<a name="StaticRemoveView"></a>
### void StaticRemoveView(int view_id)
Free up the specified view and its resources.
<a name="StaticRemoveWaterBuoyancyObject"></a>
### void StaticRemoveWaterBuoyancyObject(int ID)
Remove a water buoyancy object
<a name="StaticRemoveWaterMaskObject"></a>
### void StaticRemoveWaterMaskObject(int ID)
Remove a water masking object
<a name="StaticRemoveWaterParticleGenerator"></a>
### void StaticRemoveWaterParticleGenerator(int ID)
Remove a particle generator
<a name="StaticRemoveWaterProbe"></a>
### void StaticRemoveWaterProbe(int ID)
Remove a water probe
<a name="StaticRenderCreateCloudKeyframer"></a>
### simul::sky::uid StaticRenderCreateCloudKeyframer(char name)
Create a new Cloud Keyframer
<a name="StaticRenderDeleteCloudKeyframer"></a>
### simul::sky::uid StaticRenderDeleteCloudKeyframer(simul::sky::uid uid)
Delete a Cloud Keyframer
<a name="StaticRenderDeleteKeyframe"></a>
### void StaticRenderDeleteKeyframe(simul::sky::uid uid)
Delete a keyframe with ID uid
<a name="StaticRenderFrame"></a>
### int StaticRenderFrame(void device, void pContext, int view_id, float viewMatrix4x4, float projMatrix4x4, void depthTexture, void colourTarget, simul::crossplatform::Viewport depthViewports, simul::crossplatform::Viewport viewports, simul::plugin::RenderStyle s, float exposure, float gamma, int framenumber, simul::crossplatform::MultiResConstants pMultiResConstants)
(DEPRECATED)Render trueSKY to the current render target.
<a name="StaticRenderGetKeyframeByIndex"></a>
### simul::sky::uid StaticRenderGetKeyframeByIndex(int layer, int index)
Get a cloud keyframe on a given layer by index
<a name="StaticRenderGetNumKeyframes"></a>
### int StaticRenderGetNumKeyframes(int layer)
Get the number of keyframes on a given layer
<a name="StaticRenderInsertKeyframe"></a>
### simul::sky::uid StaticRenderInsertKeyframe(int layer, float t)
Insert a keyframe on a layer at time t
<a name="StaticRenderKeyframeGetBool"></a>
### bool StaticRenderKeyframeGetBool(simul::sky::uid uid, char name)
Get a bool value for a given keyframe
<a name="StaticRenderKeyframeGetFloat"></a>
### float StaticRenderKeyframeGetFloat(simul::sky::uid uid, char name)
Get a float value for a given keyframe
<a name="StaticRenderKeyframeGetInt"></a>
### int StaticRenderKeyframeGetInt(simul::sky::uid uid, char name)
Get an int value for a given keyframe
<a name="StaticRenderKeyframeHasBool"></a>
### bool StaticRenderKeyframeHasBool(simul::sky::uid uid, char name)
Has the keyframe with the given ID got the given bool value
<a name="StaticRenderKeyframeHasFloat"></a>
### bool StaticRenderKeyframeHasFloat(simul::sky::uid uid, char name)
Has the keyframe with the given ID got the given float value
<a name="StaticRenderKeyframeHasInt"></a>
### bool StaticRenderKeyframeHasInt(simul::sky::uid uid, char name)
Has the keyframe with the given ID got the given int value
<a name="StaticRenderKeyframerGetFloat"></a>
### float StaticRenderKeyframerGetFloat(simul::sky::uid uid, char name)
Get a float value for a given Layer
<a name="StaticRenderKeyframerGetInt"></a>
### int StaticRenderKeyframerGetInt(simul::sky::uid uid, char name)
Get an int value for a given Layer
<a name="StaticRenderKeyframerSetFloat"></a>
### void StaticRenderKeyframerSetFloat(simul::sky::uid uid, char name, float value)
Set a float value for a given Layer
<a name="StaticRenderKeyframerSetInt"></a>
### void StaticRenderKeyframerSetInt(simul::sky::uid uid, char name, int value)
Set an int value for a given Layer
<a name="StaticRenderKeyframeSetBool"></a>
### void StaticRenderKeyframeSetBool(simul::sky::uid uid, char name, bool value)
Set a bool value for a given keyframe
<a name="StaticRenderKeyframeSetFloat"></a>
### void StaticRenderKeyframeSetFloat(simul::sky::uid uid, char name, float value)
Set a float value for a given keyframe
<a name="StaticRenderKeyframeSetInt"></a>
### void StaticRenderKeyframeSetInt(simul::sky::uid uid, char name, int value)
Set an int value for a given keyframe
<a name="StaticRenderOverlays"></a>
### void StaticRenderOverlays(void device, void pContext, void externalDepthTexture, float viewMatrix4x4, float projMatrix4x4, int view_id, void colourTarget, simul::crossplatform::Viewport viewports)
Render the debug overlays.
<a name="StaticSet"></a>
### int StaticSet(long long num, simul::base::Variant v)
Set the value corresponding to the given enum.
<a name="StaticSetDebugOutputCallback"></a>
### void StaticSetDebugOutputCallback(DebugOutputCallback)
Provide a function that trueSKY can use to output debug warnings, information, and errors.
<a name="StaticSetExternalDynamicValues"></a>
### int StaticSetExternalDynamicValues(simul::plugin::ExternalDynamicValues D)
Set all values that can be changed at runtime
<a name="StaticSetExternalRenderValues"></a>
### int StaticSetExternalRenderValues(simul::plugin::ExternalRenderValues C)
Set all values that are not recommened to update at runtime
<a name="StaticSetGraphicsDevice"></a>
### void StaticSetGraphicsDevice(void device, simul::crossplatform::RenderPlatformType deviceType, UnityGfxDeviceEventType eventType)
Device event handler.
<a name="StaticSetGraphicsDeviceAndContext"></a>
### void StaticSetGraphicsDeviceAndContext(void device, void context, simul::crossplatform::RenderPlatformType deviceType, UnityGfxDeviceEventType eventType)
Device event handler.
<a name="StaticSetKeyframerMapTexture"></a>
### void StaticSetKeyframerMapTexture(simul::sky::uid uid, char PNGName)
Set the map texture of a CLoud Keyframer
<a name="StaticSetMatrix4x4"></a>
### void StaticSetMatrix4x4(char name, float matrix4x4)
Set a Matrix value.
<a name="StaticSetMemoryInterface"></a>
### void StaticSetMemoryInterface(simul::base::MemoryInterface)
Provide memory allocator for CPU and (on some platforms) GPU memory.
<a name="StaticSetPointLight"></a>
### void StaticSetPointLight(int id, pos, float min_radius, float max_radius, irradiance)
Create a light source at a given point in worldspace
<a name="StaticSetRender"></a>
### void StaticSetRender(char name, int num_params, simul::base::Variant params)
(DEPRECATED) Set an int value.
<a name="StaticSetRenderBool"></a>
### void StaticSetRenderBool(char name, bool value)
Set a bool value.
<a name="StaticSetRenderFloat"></a>
### void StaticSetRenderFloat(char name, float value)
Set a float value.
<a name="StaticSetRenderInt"></a>
### void StaticSetRenderInt(char name, int value)
(DEPRECATED) Set an int value.
<a name="StaticSetRenderString"></a>
### void StaticSetRenderString(char name, char value)
Set a string value.
<a name="StaticSetRenderTexture"></a>
### int StaticSetRenderTexture(char name, void texturePtr)
Set a texture for truesky to render to. Need to define the valid name of the output.
<a name="StaticSetSequence"></a>
### int StaticSetSequence(std::string SequenceInput)
Loads the sequence as a std::string.
<a name="StaticSetSequence2"></a>
### int StaticSetSequence2(char txt)
Loads the sequence as a c string.
<a name="StaticSetSequenceTxt"></a>
### int StaticSetSequenceTxt(char txt)
Loads the given sequence
<a name="StaticSetWaterBool"></a>
### void StaticSetWaterBool(char name, int ID, bool value)
Set a bool for a specfic water object
<a name="StaticSetWaterFloat"></a>
### void StaticSetWaterFloat(char name, int ID, float value)
Set a float for a specfic water object
<a name="StaticSetWaterInt"></a>
### void StaticSetWaterInt(char name, int ID, int value)
Set an int for a specfic water object
<a name="StaticSetWaterVector"></a>
### void StaticSetWaterVector(char name, int ID, float value)
Set a vector for a specfic water object
<a name="StaticShutDownInterface"></a>
### int StaticShutDownInterface()
Shut down the renderer and free all resources.
<a name="StaticSpawnLightning"></a>
### int StaticSpawnLightning(startpos, endpos, float magnitude, colour)
Spawn a lightning strike at a given start, endpoint, magnitude and colour
<a name="StaticTriggerAction"></a>
### bool StaticTriggerAction(char name)
Trigger an action.
<a name="StaticUpdateWaterBuoyancyObjectValues"></a>
### void StaticUpdateWaterBuoyancyObjectValues(simul::terrain::WaterMeshObjectValues values)
Update the properties of a water buoyancy object
<a name="StaticUpdateWaterMaskObjectValues"></a>
### void StaticUpdateWaterMaskObjectValues(simul::terrain::waterMaskingObject values)
Update the values of a specific water buoyancy object
<a name="StaticUpdateWaterParticleGeneratorValues"></a>
### void StaticUpdateWaterParticleGeneratorValues(simul::terrain::particleGeneratorValues values, simul::terrain::particleGeneratorType generatorType, simul::plugin::ExternalTexture customPlaneTexture)
Update the values of a specific water particle generator
<a name="StaticUpdateWaterProbeValues"></a>
### void StaticUpdateWaterProbeValues(simul::terrain::WaterProbeValues values)
Update the properties of a water object
<a name="StaticWaterSet"></a>
### int StaticWaterSet(long long num, int ID, simul::base::Variant v)
Set the water value corresponding to the given enum.
<a name="UnitySetGraphicsDevice"></a>
### void UnitySetGraphicsDevice(void device, simul::crossplatform::RenderPlatformType deviceType, UnityGfxDeviceEventType eventType)
Unity-specific device event. Calls StaticSetGraphicsDevice() if needed.

Enums
---

**RenderStyle**  Different rendering styles
