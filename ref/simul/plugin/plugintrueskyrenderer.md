---
title: PluginTrueSkyRenderer
layout: reference
weight: 0
---
class PluginTrueSkyRenderer
===

| Include: | Plugins/TrueSkyPluginRender/PluginTrueSkyRenderer.h |


[simul::clouds::TrueSkyRenderer](../clouds/trueskyrenderer.html)

Functions
---

|  | [PluginTrueSkyRenderer](#PluginTrueSkyRenderer)() |
|  | [~PluginTrueSkyRenderer](#~PluginTrueSkyRenderer)() |
| bool | [AddWaterBuoyancyObject](#AddWaterBuoyancyObject)(simul::terrain::WaterMeshObjectValues newObject) |
| bool | [AddWaterMaskObject](#AddWaterMaskObject)(simul::terrain::waterMaskingObject newObject) |
| bool | [AddWaterProbe](#AddWaterProbe)(simul::terrain::WaterProbeValues values) |
| void | [CloudLineQuery](#CloudLineQuery)(int id, float startpos, float endpos, LineQueryResult res) |
| void | [CloudSphereInteraction](#CloudSphereInteraction)(int id, float pos, float vel, float radius) |
| bool | [CreateBoundedWaterObject](#CreateBoundedWaterObject)(uint ID, simul::math::Vector3 dimension, simul::math::Vector3 location) |
| void | [DeleteKeyframe](#DeleteKeyframe)(simul::sky::uid uid) |
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
| simul::sky::uid | [GetInterpolatedCloudKeyframeUniqueId](#GetInterpolatedCloudKeyframeUniqueId)(int layer) |
| simul::sky::uid | [GetInterpolatedSkyKeyframeUniqueId](#GetInterpolatedSkyKeyframeUniqueId)() |
| simul::sky::uid | [GetKeyframeByIndex](#GetKeyframeByIndex)(int layer, int index) |
| int | [GetLightningBolts](#GetLightningBolts)(simul::clouds::ExportLightningStrike s, int maxnum) |
| int | [GetNumKeyframes](#GetNumKeyframes)(int layer) |
| int | [GetNumStorms](#GetNumStorms)() |
| simul::sky::uid | [GetStormAtTime](#GetStormAtTime)(float t) |
| simul::sky::uid | [GetStormByIndex](#GetStormByIndex)(int i) |
| char  const * | [GetString](#GetString)(char name, int len) |
| bool | [GetWaterBool](#GetWaterBool)(char name, uint ID) |
| float * | [GetWaterBuoyancyObjectResults](#GetWaterBuoyancyObjectResults)(int ID) |
| long long | [GetWaterEnum](#GetWaterEnum)(char name) |
| float | [GetWaterFloat](#GetWaterFloat)(char name, uint ID) |
| int | [GetWaterInt](#GetWaterInt)(char name, uint ID) |
| vec4 | [GetWaterProbeValues](#GetWaterProbeValues)(int ID) |
| bool | [GetWaterVector](#GetWaterVector)(char name, uint ID, vec3) |
| bool | [HasFloat](#HasFloat)(char name) |
| bool | [HasInt](#HasInt)(char name) |
| simul::sky::uid | [InsertKeyframe](#InsertKeyframe)(int layer, float time) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| bool | [KeyframeGetBool](#KeyframeGetBool)(simul::sky::uid uid, char name) |
| float | [KeyframeGetFloat](#KeyframeGetFloat)(simul::sky::uid uid, char name) |
| int | [KeyframeGetInt](#KeyframeGetInt)(simul::sky::uid uid, char name) |
| bool | [KeyframeHasBool](#KeyframeHasBool)(simul::sky::uid uid, char name) |
| bool | [KeyframeHasFloat](#KeyframeHasFloat)(simul::sky::uid uid, char name) |
| bool | [KeyframeHasInt](#KeyframeHasInt)(simul::sky::uid uid, char name) |
| void | [KeyframeSetBool](#KeyframeSetBool)(simul::sky::uid uid, char name, bool value) |
| void | [KeyframeSetFloat](#KeyframeSetFloat)(simul::sky::uid uid, char name, float value) |
| void | [KeyframeSetInt](#KeyframeSetInt)(simul::sky::uid uid, char name, int value) |
| void | [LightingQuery](#LightingQuery)(int id, float pos, LightingQueryResult res) |
| void | [ProcessQueries](#ProcessQueries)(int num, simul::plugin::Query queries) |
| void | [RemoveBoundedWaterObject](#RemoveBoundedWaterObject)(uint ID) |
| void | [RemoveWaterBuoyancyObject](#RemoveWaterBuoyancyObject)(int ID) |
| void | [RemoveWaterMaskObject](#RemoveWaterMaskObject)(int ID) |
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
| void | [SetTexture](#SetTexture)(char name, void tex, int w, int l, simul::crossplatform::PixelFormat pixelFormat) |
| void | [SetWater](#SetWater)(long long Enum, int ID, simul::base::Variant v) |
| void | [SetWaterBool](#SetWaterBool)(char name, int ID, bool value) |
| void | [SetWaterFloat](#SetWaterFloat)(char name, int ID, float value) |
| void | [SetWaterInt](#SetWaterInt)(char name, int ID, int value) |
| void | [SetWaterVector](#SetWaterVector)(char name, int ID, float value) |
| int | [SpawnLightning](#SpawnLightning)(startpos, endpos, float magnitude, colour, float duration) |
| bool | [TriggerAction](#TriggerAction)(char name) |
| void | [UpdateProfilingText](#UpdateProfilingText)() |
| void | [UpdateWaterBuoyancyObjectValues](#UpdateWaterBuoyancyObjectValues)(simul::terrain::WaterMeshObjectValues values) |
| void | [UpdateWaterMaskObjectValues](#UpdateWaterMaskObjectValues)(simul::terrain::waterMaskingObject values) |
| void | [UpdateWaterProbeValues](#UpdateWaterProbeValues)(simul::terrain::WaterProbeValues values) |


Base Classes
---
[simul::clouds::TrueSkyRenderer](../clouds/trueskyrenderer.html)

Functions
---
<a name="PluginTrueSkyRenderer"></a>
###  PluginTrueSkyRenderer()
Constructor
<a name="~PluginTrueSkyRenderer"></a>
###  ~PluginTrueSkyRenderer()
Destructor
<a name="AddWaterBuoyancyObject"></a>
### bool AddWaterBuoyancyObject(simul::terrain::WaterMeshObjectValues newObject)
Create a water buoyancy object with a given struct that holds an array of vertices
<a name="AddWaterMaskObject"></a>
### bool AddWaterMaskObject(simul::terrain::waterMaskingObject newObject)
Create a water masking object
<a name="AddWaterProbe"></a>
### bool AddWaterProbe(simul::terrain::WaterProbeValues values)
Create a bounded water object with a given ID
<a name="CloudLineQuery"></a>
### void CloudLineQuery(int id, float startpos, float endpos, LineQueryResult res)
Fill in a query structure based on cloud properties from startpos to endpos.
<a name="CloudSphereInteraction"></a>
### void CloudSphereInteraction(int id, float pos, float vel, float radius)
update a sphere that will push clouds aside.
<a name="CreateBoundedWaterObject"></a>
### bool CreateBoundedWaterObject(uint ID, simul::math::Vector3 dimension, simul::math::Vector3 location)
Create a bounded water object with a given ID
<a name="DeleteKeyframe"></a>
### void DeleteKeyframe(simul::sky::uid uid)
Delete a keyframe with ID uid
<a name="ExportCloudLayer"></a>
### void ExportCloudLayer(char filenameUtf8)
Exports the cloud layer as geometry
<a name="Get"></a>
### void Get(long long Enum, simul::base::Variant v)
Get a value corresponding to the given enum.
<a name="GetBool"></a>
### bool GetBool(char name)
Returns a boolean value. See 
<a name="GetCloudPointQuery"></a>
### void GetCloudPointQuery(int id, float pos, VolumeQueryResult res)
Fill in a query structure based on cloud properties at a position.
<a name="GetEnum"></a>
### long long GetEnum(char name)
Get the enum that corresponds to a given name. A return value of zero means the name was not found.
<a name="GetEnvironment"></a>
### simul::clouds::Environment * GetEnvironment()
Returns the environment object.
<a name="GetFloat"></a>
### float GetFloat(char name)
Returns a floating point value - see 
<a name="GetFloatAtPosition"></a>
### float GetFloatAtPosition(simul::plugin::FloatAtPosition f, float pos, int uid)
Property at a given position.
<a name="GetFloatAtPosition"></a>
### float GetFloatAtPosition(char name, float pos)
Property at a given position.
<a name="GetInt"></a>
### int GetInt(char name, int numparams, simul::base::Variant params)
Returns an integer value - see 
<a name="GetInterpolatedCloudKeyframeUniqueId"></a>
### simul::sky::uid GetInterpolatedCloudKeyframeUniqueId(int layer)
Get the ID of the current interpolated cloud keyframe on the given layer
<a name="GetInterpolatedSkyKeyframeUniqueId"></a>
### simul::sky::uid GetInterpolatedSkyKeyframeUniqueId()
Get the ID of the current interpolated sky keyframe
<a name="GetKeyframeByIndex"></a>
### simul::sky::uid GetKeyframeByIndex(int layer, int index)
Get a cloud keyframe on a given layer by index
<a name="GetLightningBolts"></a>
### int GetLightningBolts(simul::clouds::ExportLightningStrike s, int maxnum)
Get the properties of a lightning bolt that is currently active in the scene
<a name="GetNumKeyframes"></a>
### int GetNumKeyframes(int layer)
Get the number of keyframes on a given layer
<a name="GetNumStorms"></a>
### int GetNumStorms()
Get the total number of storms
<a name="GetStormAtTime"></a>
### simul::sky::uid GetStormAtTime(float t)
Get a storm ID, if it exists, at time t
<a name="GetStormByIndex"></a>
### simul::sky::uid GetStormByIndex(int i)
Get a storm ID with index i
<a name="GetString"></a>
### char  const * GetString(char name, int len)
Returns a string - nameshould be "ConstellationNames", "HighlightConstellationNames", "memory" or "profiling".
<a name="GetWaterBool"></a>
### bool GetWaterBool(char name, uint ID)
Get a bool for a specfic water object
<a name="GetWaterBuoyancyObjectResults"></a>
### float * GetWaterBuoyancyObjectResults(int ID)
Get the results of a water buoyancy object
<a name="GetWaterEnum"></a>
### long long GetWaterEnum(char name)
Get the Water enum that corresponds to a given name. A return value of zero means the name was not found.
<a name="GetWaterFloat"></a>
### float GetWaterFloat(char name, uint ID)
Get a float for a specfic water object
<a name="GetWaterInt"></a>
### int GetWaterInt(char name, uint ID)
Get an int for a specfic water object
<a name="GetWaterProbeValues"></a>
### vec4 GetWaterProbeValues(int ID)
Get the results of a water probe
<a name="GetWaterVector"></a>
### bool GetWaterVector(char name, uint ID, vec3)
Get a vector for a specfic water object
<a name="HasFloat"></a>
### bool HasFloat(char name)
Does the named parameter exist?
<a name="HasInt"></a>
### bool HasInt(char name)
Does the named parameter exist?
<a name="InsertKeyframe"></a>
### simul::sky::uid InsertKeyframe(int layer, float time)
Insert a keyframe on a layer at time t
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the plugin renderer.
<a name="KeyframeGetBool"></a>
### bool KeyframeGetBool(simul::sky::uid uid, char name)
Fet a bool value for a given keyframe
<a name="KeyframeGetFloat"></a>
### float KeyframeGetFloat(simul::sky::uid uid, char name)
Get a bool value for a given keyframe
<a name="KeyframeGetInt"></a>
### int KeyframeGetInt(simul::sky::uid uid, char name)
Get a int value for a given keyframe
<a name="KeyframeHasBool"></a>
### bool KeyframeHasBool(simul::sky::uid uid, char name)
Has the keyframe with the given ID got the given bool value
<a name="KeyframeHasFloat"></a>
### bool KeyframeHasFloat(simul::sky::uid uid, char name)
Has the keyframe with the given ID got the given float value
<a name="KeyframeHasInt"></a>
### bool KeyframeHasInt(simul::sky::uid uid, char name)
Has the keyframe with the given ID got the given int value
<a name="KeyframeSetBool"></a>
### void KeyframeSetBool(simul::sky::uid uid, char name, bool value)
Set a bool value for a given keyframe
<a name="KeyframeSetFloat"></a>
### void KeyframeSetFloat(simul::sky::uid uid, char name, float value)
Set a float value for a given keyframe
<a name="KeyframeSetInt"></a>
### void KeyframeSetInt(simul::sky::uid uid, char name, int value)
Set a int value for a given keyframe
<a name="LightingQuery"></a>
### void LightingQuery(int id, float pos, LightingQueryResult res)
Fill in a structure with lighting values at the given position
<a name="ProcessQueries"></a>
### void ProcessQueries(int num, simul::plugin::Query queries)
Called on the render thread, this will process queries from outside the plugin.
<a name="RemoveBoundedWaterObject"></a>
### void RemoveBoundedWaterObject(uint ID)
Remove a bounded water object with a given ID
<a name="RemoveWaterBuoyancyObject"></a>
### void RemoveWaterBuoyancyObject(int ID)
Remove a water buoyancy object
<a name="RemoveWaterMaskObject"></a>
### void RemoveWaterMaskObject(int ID)
Remove a water masking object
<a name="RemoveWaterProbe"></a>
### void RemoveWaterProbe(int ID)
Remove a bounded water object with a given ID
<a name="RenderFrame"></a>
### int RenderFrame(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture, simul::crossplatform::Texture colourTargetTexture, simul::crossplatform::Viewport depthViewport, simul::crossplatform::Viewport viewports, simul::plugin::RenderStyle s, float exposure, float gamma, int framenumber)
Main render function
<a name="RenderOverlays"></a>
### void RenderOverlays(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture)
Render the debug textures
<a name="Set"></a>
### void Set(long long Enum, simul::base::Variant v)
Set the value corresponding to the given enum.
<a name="SetBool"></a>
### void SetBool(char name, bool value)
Set a boolean value. Valid names are: "ShowFades", "ShowCelestialDisplay", "ShowCompositing", "ShowCloudCrossSections"
, "Show2DCloudTextures", "RenderSky"/"EnableRendering", and "ReverseDepth".
<a name="SetCloudPlacementTexture"></a>
### void SetCloudPlacementTexture(int id, void texture, vec2 pos_km, vec2 ext_km)
A mask for cloud position
<a name="SetFloat"></a>
### void SetFloat(char name, float value)
Sets a floating point value. nameshould be "Time", "Gamma", "Exposure", or "SimpleCloudShadowing".
<a name="SetInt"></a>
### void SetInt(char name, int value)
Sets an integer value. nameshould be "CloudSteps", or "Downscale".
<a name="SetMatrix4x4"></a>
### void SetMatrix4x4(char name, float matrix4x4)
Sets a matrix value.
<a name="SetPointLight"></a>
### void SetPointLight(int id, pos, float min_radius, float max_radius, irradiance)
For the next frame, put a light source at the specified position, with the specified irradiance. The radius specifies
the size of the source.
<a name="SetString"></a>
### void SetString(char name, char value)
Set a string value. namemust be "LicenceKey".
<a name="SetTexture"></a>
### void SetTexture(char name, void tex, int w, int l, simul::crossplatform::PixelFormat pixelFormat)
Setting texture properties.
<a name="SetWater"></a>
### void SetWater(long long Enum, int ID, simul::base::Variant v)
Set the water value corresponding to the given enum.
<a name="SetWaterBool"></a>
### void SetWaterBool(char name, int ID, bool value)
Set a bool for a specfic water object
<a name="SetWaterFloat"></a>
### void SetWaterFloat(char name, int ID, float value)
Set a float for a specfic water object
<a name="SetWaterInt"></a>
### void SetWaterInt(char name, int ID, int value)
Set an int for a specfic water object
<a name="SetWaterVector"></a>
### void SetWaterVector(char name, int ID, float value)
Set a vector for a specfic water object
<a name="SpawnLightning"></a>
### int SpawnLightning(startpos, endpos, float magnitude, colour, float duration)
A class that provides an interface between the trueSKY renderer and an external engine.
<a name="TriggerAction"></a>
### bool TriggerAction(char name)
Trigger an action. nameshould be "RecompileShaders".
<a name="UpdateProfilingText"></a>
### void UpdateProfilingText()
Called once per frame, updates every 256 frames.
<a name="UpdateWaterBuoyancyObjectValues"></a>
### void UpdateWaterBuoyancyObjectValues(simul::terrain::WaterMeshObjectValues values)
Update the properties of a water buoyancy object
<a name="UpdateWaterMaskObjectValues"></a>
### void UpdateWaterMaskObjectValues(simul::terrain::waterMaskingObject values)
Update the values of a specific water buoyancy object
<a name="UpdateWaterProbeValues"></a>
### void UpdateWaterProbeValues(simul::terrain::WaterProbeValues values)
Update the properties of a water object
