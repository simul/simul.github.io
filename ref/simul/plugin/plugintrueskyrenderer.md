---
title: PluginTrueSkyRenderer
layout: reference
weight: 0
---
class PluginTrueSkyRenderer
===

| Include: | PlugIns/TrueSkyPluginRender/PluginTrueSkyRenderer.h |

A class that provides an interface between the trueSKY renderer and an external engine.
  

[simul::clouds::TrueSkyRenderer](../clouds/trueskyrenderer)

Functions
---

|  | [PluginTrueSkyRenderer](#PluginTrueSkyRenderer)() |
|  | [~PluginTrueSkyRenderer](#~PluginTrueSkyRenderer)() |
| void | [CloudLineQuery](#CloudLineQuery)(int id, float startpos, float endpos, LineQueryResult res) |
| void | [CloudSphereInteraction](#CloudSphereInteraction)(int id, float pos, float vel, float radius) |
| void | [Get](#Get)(long long Enum, simul::base::Variant v) |
| bool | [GetBool](#GetBool)(char name) |
| void | [GetCloudPointQuery](#GetCloudPointQuery)(int id, float pos, VolumeQueryResult res) |
| long long | [GetEnum](#GetEnum)(char name) |
| simul::clouds::Environment * | [GetEnvironment](#GetEnvironment)() |
| float | [GetFloat](#GetFloat)(char name) |
| float | [GetFloatAtPosition](#GetFloatAtPosition)(simul::plugin::FloatAtPosition f, float pos, int uid) |
| float | [GetFloatAtPosition](#GetFloatAtPosition)(char name, float pos) |
| int | [GetInt](#GetInt)(char name, int numparams, simul::base::Variant params) |
| char  const * | [GetString](#GetString)(char name, int len) |
| long long | [GetWaterEnum](#GetWaterEnum)(char name) |
| bool | [HasFloat](#HasFloat)(char name) |
| bool | [HasInt](#HasInt)(char name) |
| void | [LightingQuery](#LightingQuery)(int id, float pos, LightingQueryResult res) |
| void | [ProcessQueries](#ProcessQueries)(int num, simul::plugin::Query queries) |
| void | [Set](#Set)(long long Enum, simul::base::Variant v) |
| void | [SetBool](#SetBool)(char name, bool value) |
| void | [SetCloudPlacementTexture](#SetCloudPlacementTexture)(int id, void texture, vec2 pos_km, vec2 ext_km) |
| void | [SetFloat](#SetFloat)(char name, float value) |
| void | [SetInt](#SetInt)(char name, int value) |
| void | [SetMatrix4x4](#SetMatrix4x4)(char name, float matrix4x4) |
| void | [SetPointLight](#SetPointLight)(int id, pos, float min_radius, float max_radius, irradiance) |
| void | [SetString](#SetString)(char name, char value) |
| void | [SetTexture](#SetTexture)(char name, void tex) |
| void | [SetWater](#SetWater)(long long Enum, int ID, simul::base::Variant v) |
| bool | [TriggerAction](#TriggerAction)(char name) |
| void | [UpdateProfilingText](#UpdateProfilingText)() |

A class that provides an interface between the trueSKY renderer and an external engine.
  


Base Classes
---
[simul::clouds::TrueSkyRenderer](../clouds/trueskyrenderer)

Functions
---

### <a name="PluginTrueSkyRenderer"/> PluginTrueSkyRenderer()
Constructor

### <a name="~PluginTrueSkyRenderer"/> ~PluginTrueSkyRenderer()
Destructor

### <a name="CloudLineQuery"/>void CloudLineQuery(int id, float startpos, float endpos, LineQueryResult res)
Fill in a query structure based on cloud properties from startpos to endpos.

### <a name="CloudSphereInteraction"/>void CloudSphereInteraction(int id, float pos, float vel, float radius)
update a sphere that will push clouds aside.

### <a name="Get"/>void Get(long long Enum, simul::base::Variant v)
Get a value corresponding to the given enum.

### <a name="GetBool"/>bool GetBool(char name)
Returns a boolean value. See \ref SetBool.

### <a name="GetCloudPointQuery"/>void GetCloudPointQuery(int id, float pos, VolumeQueryResult res)
Fill in a query structure based on cloud properties at a position.

### <a name="GetEnum"/>long long GetEnum(char name)
Get the enum that corresponds to a given name. A return value of zero means the name was not found.

### <a name="GetEnvironment"/>simul::clouds::Environment * GetEnvironment()
Returns the environment object.

### <a name="GetFloat"/>float GetFloat(char name)
Returns a floating point value - see \ref SetFloat.

### <a name="GetFloatAtPosition"/>float GetFloatAtPosition(simul::plugin::FloatAtPosition f, float pos, int uid)
Property at a given position.

### <a name="GetFloatAtPosition"/>float GetFloatAtPosition(char name, float pos)
Property at a given position.

### <a name="GetInt"/>int GetInt(char name, int numparams, simul::base::Variant params)
Returns an integer value - see \ref SetInt.

### <a name="GetString"/>char  const * GetString(char name, int len)
Returns a string - \em name should be "ConstellationNames", "HighlightConstellationNames", "memory" or "profiling".

### <a name="GetWaterEnum"/>long long GetWaterEnum(char name)
Get the Water enum that corresponds to a given name. A return value of zero means the name was not found.

### <a name="HasFloat"/>bool HasFloat(char name)
Does the named parameter exist?

### <a name="HasInt"/>bool HasInt(char name)
Does the named parameter exist?

### <a name="LightingQuery"/>void LightingQuery(int id, float pos, LightingQueryResult res)
Fill in a structure with lighting values at the given position

### <a name="ProcessQueries"/>void ProcessQueries(int num, simul::plugin::Query queries)
Called on the render thread, this will process queries from outside the plugin.

### <a name="Set"/>void Set(long long Enum, simul::base::Variant v)
Set the value corresponding to the given enum.

### <a name="SetBool"/>void SetBool(char name, bool value)
Set a boolean value. Valid names are: "ShowFades", "ShowCelestialDisplay", "ShowCompositing", "ShowCloudCrossSections"
, "Show2DCloudTextures", "RenderSky"/"EnableRendering", and "ReverseDepth".

### <a name="SetCloudPlacementTexture"/>void SetCloudPlacementTexture(int id, void texture, vec2 pos_km, vec2 ext_km)
A mask for cloud position

### <a name="SetFloat"/>void SetFloat(char name, float value)
Sets a floating point value. \em name should be "Time", "Gamma", "Exposure", or "SimpleCloudShadowing".

### <a name="SetInt"/>void SetInt(char name, int value)
Sets an integer value. \em name should be "CloudSteps", or "Downscale".

### <a name="SetMatrix4x4"/>void SetMatrix4x4(char name, float matrix4x4)
Sets a matrix value.

### <a name="SetPointLight"/>void SetPointLight(int id, pos, float min_radius, float max_radius, irradiance)
For the next frame, put a light source at the specified position, with the specified irradiance. The radius specifies
the size of the source.

### <a name="SetString"/>void SetString(char name, char value)
Set a string value. \em name must be "LicenceKey".

### <a name="SetTexture"/>void SetTexture(char name, void tex)
Setting texture properties.

### <a name="SetWater"/>void SetWater(long long Enum, int ID, simul::base::Variant v)
Set the water value corresponding to the given enum.

### <a name="TriggerAction"/>bool TriggerAction(char name)
Trigger an action. \em name should be "RecompileShaders".

### <a name="UpdateProfilingText"/>void UpdateProfilingText()
Called once per frame, updates every 256 frames.
