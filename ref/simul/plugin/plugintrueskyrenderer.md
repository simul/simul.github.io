---
title: PluginTrueSkyRenderer
layout: reference
weight: 0
---
class PluginTrueSkyRenderer
===

| Include: | PlugIns/TrueSkyPluginRender/PluginTrueSkyRenderer.h |


[simul::clouds::TrueSkyRenderer](../clouds/trueskyrenderer)

Functions
---

|  | [PluginTrueSkyRenderer](#PluginTrueSkyRenderer)() |
|  | [~PluginTrueSkyRenderer](#~PluginTrueSkyRenderer)() |
| bool | [AddWaterBuoyancyObject](#AddWaterBuoyancyObject)(simul::terrain::WaterBuoyancyObjectValues newObject) |
| bool | [AddWaterProbe](#AddWaterProbe)(simul::terrain::WaterProbeValues values) |
| void | [CloudLineQuery](#CloudLineQuery)(int id, float startpos, float endpos, LineQueryResult res) |
| void | [CloudSphereInteraction](#CloudSphereInteraction)(int id, float pos, float vel, float radius) |
| bool | [CreateBoundedWaterObject](#CreateBoundedWaterObject)(uint ID, simul::math::Vector3 dimension, simul::math::Vector3 location) |
| void | [DeleteKeyframe](#DeleteKeyframe)(unsigned int uid) |
| void | [ExportCloudLayer](#ExportCloudLayer)(char filenameUtf8) |
| void | [Get](#Get)(long long Enum, simul::base::Variant v) |
| bool | [GetBool](#GetBool)(char name) |
| void | [GetCloudPointQuery](#GetCloudPointQuery)(int id, float pos, VolumeQueryResult res) |
| long long | [GetEnum](#GetEnum)(char name) |
| simul::clouds::Environment * | [GetEnvironment](#GetEnvironment)() |
| float | [GetFloat](#GetFloat)(char name) |
| float | [GetFloatAtPosition](#GetFloatAtPosition)(simul::plugin::FloatAtPosition f, float pos, int uid) |
| float | [GetFloatAtPosition](#GetFloatAtPosition)(char name, float pos) |
| int | [GetInt](#GetInt)(char name, int numparams, simul::base::Variant params) |
| unsigned int | [GetInterpolatedCloudKeyframeUniqueId](#GetInterpolatedCloudKeyframeUniqueId)(int layer) |
| unsigned int | [GetInterpolatedSkyKeyframeUniqueId](#GetInterpolatedSkyKeyframeUniqueId)() |
| unsigned int | [GetKeyframeByIndex](#GetKeyframeByIndex)(int layer, int index) |
| int | [GetLightningBolts](#GetLightningBolts)(simul::clouds::ExportLightningStrike s, int maxnum) |
| int | [GetNumKeyframes](#GetNumKeyframes)(int layer) |
| int | [GetNumStorms](#GetNumStorms)() |
| unsigned int | [GetStormAtTime](#GetStormAtTime)(float t) |
| unsigned int | [GetStormByIndex](#GetStormByIndex)(int i) |
| char  const * | [GetString](#GetString)(char name, int len) |
| bool | [GetWaterBool](#GetWaterBool)(char name, uint ID) |
| float * | [GetWaterBuoyancyObjectResults](#GetWaterBuoyancyObjectResults)(int ID) |
| long long | [GetWaterEnum](#GetWaterEnum)(char name) |
| float | [GetWaterFloat](#GetWaterFloat)(char name, uint ID) |
| int | [GetWaterInt](#GetWaterInt)(char name, uint ID) |
| vec4 | [GetWaterProbeValues](#GetWaterProbeValues)(int ID) |
| float * | [GetWaterVector](#GetWaterVector)(char name, uint ID) |
| bool | [HasFloat](#HasFloat)(char name) |
| bool | [HasInt](#HasInt)(char name) |
| unsigned int | [InsertKeyframe](#InsertKeyframe)(int layer, float time) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| bool | [KeyframeGetBool](#KeyframeGetBool)(unsigned int uid, char name) |
| float | [KeyframeGetFloat](#KeyframeGetFloat)(unsigned int uid, char name) |
| int | [KeyframeGetInt](#KeyframeGetInt)(unsigned int uid, char name) |
| bool | [KeyframeHasBool](#KeyframeHasBool)(unsigned int uid, char name) |
| bool | [KeyframeHasFloat](#KeyframeHasFloat)(unsigned int uid, char name) |
| bool | [KeyframeHasInt](#KeyframeHasInt)(unsigned int uid, char name) |
| void | [KeyframeSetBool](#KeyframeSetBool)(unsigned int uid, char name, bool value) |
| void | [KeyframeSetFloat](#KeyframeSetFloat)(unsigned int uid, char name, float value) |
| void | [KeyframeSetInt](#KeyframeSetInt)(unsigned int uid, char name, int value) |
| void | [LightingQuery](#LightingQuery)(int id, float pos, LightingQueryResult res) |
| void | [ProcessQueries](#ProcessQueries)(int num, simul::plugin::Query queries) |
| void | [RemoveBoundedWaterObject](#RemoveBoundedWaterObject)(uint ID) |
| void | [RemoveWaterBuoyancyObject](#RemoveWaterBuoyancyObject)(int ID) |
| void | [RemoveWaterProbe](#RemoveWaterProbe)(int ID) |
| int | [RenderFrame](#RenderFrame)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture, simul::crossplatform::Texture colourTargetTexture, simul::crossplatform::Viewport depthViewport, simul::crossplatform::Viewport viewports, simul::plugin::RenderStyle s, float exposure, float gamma, int framenumber) |
| void | [RenderOverlays](#RenderOverlays)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture) |
| void | [Set](#Set)(long long Enum, simul::base::Variant v) |
| void | [SetBool](#SetBool)(char name, bool value) |
| void | [SetCloudPlacementTexture](#SetCloudPlacementTexture)(int id, void texture, vec2 pos_km, vec2 ext_km) |
| void | [SetFloat](#SetFloat)(char name, float value) |
| void | [SetInt](#SetInt)(char name, int value) |
| void | [SetMatrix4x4](#SetMatrix4x4)(char name, float matrix4x4) |
| void | [SetPointLight](#SetPointLight)(int id, pos, float min_radius, float max_radius, irradiance) |
| void | [SetString](#SetString)(char name, char value) |
| void | [SetTexture](#SetTexture)(char name, void tex, int w, int l) |
| void | [SetWater](#SetWater)(long long Enum, int ID, simul::base::Variant v) |
| void | [SetWaterBool](#SetWaterBool)(char name, int ID, bool value) |
| void | [SetWaterFloat](#SetWaterFloat)(char name, int ID, float value) |
| void | [SetWaterInt](#SetWaterInt)(char name, int ID, int value) |
| void | [SetWaterVector](#SetWaterVector)(char name, int ID, float value) |
| int | [SpawnLightning](#SpawnLightning)(startpos, endpos, float magnitude, colour, float duration) |
| bool | [TriggerAction](#TriggerAction)(char name) |
| void | [UpdateProfilingText](#UpdateProfilingText)() |
| void | [UpdateWaterBuoyancyObjectValues](#UpdateWaterBuoyancyObjectValues)(simul::terrain::WaterBuoyancyObjectValues values) |
| void | [UpdateWaterProbeValues](#UpdateWaterProbeValues)(simul::terrain::WaterProbeValues values) |


Base Classes
---
[simul::clouds::TrueSkyRenderer](../clouds/trueskyrenderer)

Functions
---

### <a name="PluginTrueSkyRenderer"/> PluginTrueSkyRenderer()
Constructor

### <a name="~PluginTrueSkyRenderer"/> ~PluginTrueSkyRenderer()
Destructor

### <a name="AddWaterBuoyancyObject"/>bool AddWaterBuoyancyObject(simul::terrain::WaterBuoyancyObjectValues newObject)
Create a water buoyancy object with a given struct that holds an array of vertices

### <a name="AddWaterProbe"/>bool AddWaterProbe(simul::terrain::WaterProbeValues values)
Create a bounded water object with a given ID

### <a name="CloudLineQuery"/>void CloudLineQuery(int id, float startpos, float endpos, LineQueryResult res)
Fill in a query structure based on cloud properties from startpos to endpos.

### <a name="CloudSphereInteraction"/>void CloudSphereInteraction(int id, float pos, float vel, float radius)
update a sphere that will push clouds aside.

### <a name="CreateBoundedWaterObject"/>bool CreateBoundedWaterObject(uint ID, simul::math::Vector3 dimension, simul::math::Vector3 location)
Create a bounded water object with a given ID

### <a name="DeleteKeyframe"/>void DeleteKeyframe(unsigned int uid)
Delete a keyframe with ID uid

### <a name="ExportCloudLayer"/>void ExportCloudLayer(char filenameUtf8)
Exports the cloud layer as geometry

### <a name="Get"/>void Get(long long Enum, simul::base::Variant v)
Get a value corresponding to the given enum.

### <a name="GetBool"/>bool GetBool(char name)
Returns a boolean value. See 

### <a name="GetCloudPointQuery"/>void GetCloudPointQuery(int id, float pos, VolumeQueryResult res)
Fill in a query structure based on cloud properties at a position.

### <a name="GetEnum"/>long long GetEnum(char name)
Get the enum that corresponds to a given name. A return value of zero means the name was not found.

### <a name="GetEnvironment"/>simul::clouds::Environment * GetEnvironment()
Returns the environment object.

### <a name="GetFloat"/>float GetFloat(char name)
Returns a floating point value - see 

### <a name="GetFloatAtPosition"/>float GetFloatAtPosition(simul::plugin::FloatAtPosition f, float pos, int uid)
Property at a given position.

### <a name="GetFloatAtPosition"/>float GetFloatAtPosition(char name, float pos)
Property at a given position.

### <a name="GetInt"/>int GetInt(char name, int numparams, simul::base::Variant params)
Returns an integer value - see 

### <a name="GetInterpolatedCloudKeyframeUniqueId"/>unsigned int GetInterpolatedCloudKeyframeUniqueId(int layer)
Get the ID of the current interpolated cloud keyframe on the given layer

### <a name="GetInterpolatedSkyKeyframeUniqueId"/>unsigned int GetInterpolatedSkyKeyframeUniqueId()
Get the ID of the current interpolated sky keyframe

### <a name="GetKeyframeByIndex"/>unsigned int GetKeyframeByIndex(int layer, int index)
Get a cloud keyframe on a given layer by index

### <a name="GetLightningBolts"/>int GetLightningBolts(simul::clouds::ExportLightningStrike s, int maxnum)
Get the properties of a lightning bolt that is currently active in the scene

### <a name="GetNumKeyframes"/>int GetNumKeyframes(int layer)
Get the number of keyframes on a given layer

### <a name="GetNumStorms"/>int GetNumStorms()
Get the total number of storms

### <a name="GetStormAtTime"/>unsigned int GetStormAtTime(float t)
Get a storm ID, if it exists, at time t

### <a name="GetStormByIndex"/>unsigned int GetStormByIndex(int i)
Get a storm ID with index i

### <a name="GetString"/>char  const * GetString(char name, int len)
Returns a string - nameshould be "ConstellationNames", "HighlightConstellationNames", "memory" or "profiling".

### <a name="GetWaterBool"/>bool GetWaterBool(char name, uint ID)
Get a bool for a specfic water object

### <a name="GetWaterBuoyancyObjectResults"/>float * GetWaterBuoyancyObjectResults(int ID)
Get the results of a water buoyancy object

### <a name="GetWaterEnum"/>long long GetWaterEnum(char name)
Get the Water enum that corresponds to a given name. A return value of zero means the name was not found.

### <a name="GetWaterFloat"/>float GetWaterFloat(char name, uint ID)
Get a float for a specfic water object

### <a name="GetWaterInt"/>int GetWaterInt(char name, uint ID)
Get an int for a specfic water object

### <a name="GetWaterProbeValues"/>vec4 GetWaterProbeValues(int ID)
Get the results of a water probe

### <a name="GetWaterVector"/>float * GetWaterVector(char name, uint ID)
Get a vector for a specfic water object

### <a name="HasFloat"/>bool HasFloat(char name)
Does the named parameter exist?

### <a name="HasInt"/>bool HasInt(char name)
Does the named parameter exist?

### <a name="InsertKeyframe"/>unsigned int InsertKeyframe(int layer, float time)
Insert a keyframe on a layer at time t

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the plugin renderer.

### <a name="KeyframeGetBool"/>bool KeyframeGetBool(unsigned int uid, char name)
Fet a bool value for a given keyframe

### <a name="KeyframeGetFloat"/>float KeyframeGetFloat(unsigned int uid, char name)
Get a bool value for a given keyframe

### <a name="KeyframeGetInt"/>int KeyframeGetInt(unsigned int uid, char name)
Get a int value for a given keyframe

### <a name="KeyframeHasBool"/>bool KeyframeHasBool(unsigned int uid, char name)
Has the keyframe with the given ID got the given bool value

### <a name="KeyframeHasFloat"/>bool KeyframeHasFloat(unsigned int uid, char name)
Has the keyframe with the given ID got the given float value

### <a name="KeyframeHasInt"/>bool KeyframeHasInt(unsigned int uid, char name)
Has the keyframe with the given ID got the given int value

### <a name="KeyframeSetBool"/>void KeyframeSetBool(unsigned int uid, char name, bool value)
Set a bool value for a given keyframe

### <a name="KeyframeSetFloat"/>void KeyframeSetFloat(unsigned int uid, char name, float value)
Set a float value for a given keyframe

### <a name="KeyframeSetInt"/>void KeyframeSetInt(unsigned int uid, char name, int value)
Set a int value for a given keyframe

### <a name="LightingQuery"/>void LightingQuery(int id, float pos, LightingQueryResult res)
Fill in a structure with lighting values at the given position

### <a name="ProcessQueries"/>void ProcessQueries(int num, simul::plugin::Query queries)
Called on the render thread, this will process queries from outside the plugin.

### <a name="RemoveBoundedWaterObject"/>void RemoveBoundedWaterObject(uint ID)
Remove a bounded water object with a given ID

### <a name="RemoveWaterBuoyancyObject"/>void RemoveWaterBuoyancyObject(int ID)
Remove a water buoyancy object

### <a name="RemoveWaterProbe"/>void RemoveWaterProbe(int ID)
Remove a bounded water object with a given ID

### <a name="RenderFrame"/>int RenderFrame(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture, simul::crossplatform::Texture colourTargetTexture, simul::crossplatform::Viewport depthViewport, simul::crossplatform::Viewport viewports, simul::plugin::RenderStyle s, float exposure, float gamma, int framenumber)
Main render function

### <a name="RenderOverlays"/>void RenderOverlays(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture)
Render the debug textures

### <a name="Set"/>void Set(long long Enum, simul::base::Variant v)
Set the value corresponding to the given enum.

### <a name="SetBool"/>void SetBool(char name, bool value)
Set a boolean value. Valid names are: "ShowFades", "ShowCelestialDisplay", "ShowCompositing", "ShowCloudCrossSections"
, "Show2DCloudTextures", "RenderSky"/"EnableRendering", and "ReverseDepth".

### <a name="SetCloudPlacementTexture"/>void SetCloudPlacementTexture(int id, void texture, vec2 pos_km, vec2 ext_km)
A mask for cloud position

### <a name="SetFloat"/>void SetFloat(char name, float value)
Sets a floating point value. nameshould be "Time", "Gamma", "Exposure", or "SimpleCloudShadowing".

### <a name="SetInt"/>void SetInt(char name, int value)
Sets an integer value. nameshould be "CloudSteps", or "Downscale".

### <a name="SetMatrix4x4"/>void SetMatrix4x4(char name, float matrix4x4)
Sets a matrix value.

### <a name="SetPointLight"/>void SetPointLight(int id, pos, float min_radius, float max_radius, irradiance)
For the next frame, put a light source at the specified position, with the specified irradiance. The radius specifies
the size of the source.

### <a name="SetString"/>void SetString(char name, char value)
Set a string value. namemust be "LicenceKey".

### <a name="SetTexture"/>void SetTexture(char name, void tex, int w, int l)
Setting texture properties.

### <a name="SetWater"/>void SetWater(long long Enum, int ID, simul::base::Variant v)
Set the water value corresponding to the given enum.

### <a name="SetWaterBool"/>void SetWaterBool(char name, int ID, bool value)
Set a bool for a specfic water object

### <a name="SetWaterFloat"/>void SetWaterFloat(char name, int ID, float value)
Set a float for a specfic water object

### <a name="SetWaterInt"/>void SetWaterInt(char name, int ID, int value)
Set an int for a specfic water object

### <a name="SetWaterVector"/>void SetWaterVector(char name, int ID, float value)
Set a vector for a specfic water object

### <a name="SpawnLightning"/>int SpawnLightning(startpos, endpos, float magnitude, colour, float duration)
A class that provides an interface between the trueSKY renderer and an external engine.

### <a name="TriggerAction"/>bool TriggerAction(char name)
Trigger an action. nameshould be "RecompileShaders".

### <a name="UpdateProfilingText"/>void UpdateProfilingText()
Called once per frame, updates every 256 frames.

### <a name="UpdateWaterBuoyancyObjectValues"/>void UpdateWaterBuoyancyObjectValues(simul::terrain::WaterBuoyancyObjectValues values)
Update the properties of a water buoyancy object

### <a name="UpdateWaterProbeValues"/>void UpdateWaterProbeValues(simul::terrain::WaterProbeValues values)
Update the properties of a water object
