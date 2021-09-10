---
title: CloudKeyframer
layout: reference
weight: 0
---
class CloudKeyframer
===

| Include: | Clouds/BaseWeatherRenderer.h |


[simul::sky::OvercastCallback](../sky/overcastcallback.html)
[simul::sky::BaseKeyframer](../sky/basekeyframer.html)

Functions
---

|  | [CloudKeyframer](#CloudKeyframer)(simul::base::MemoryInterface mem, bool make2d) |
|  | [~CloudKeyframer](#~CloudKeyframer)() |
| simul::clouds::Storm * | [AddStorm](#AddStorm)(float t0, float t1, simul::crossplatform::Quaterniond origin, float r_km) |
| void | [DeleteKeyframe](#DeleteKeyframe)(int i) |
| void | [DeleteKeyframeByUID](#DeleteKeyframeByUID)(simul::sky::uid uid) |
| void | [DeleteStorm](#DeleteStorm)(int i) |
| void | [DeleteStormByUniqueId](#DeleteStormByUniqueId)(simul::sky::uid uid) |
| void | [ForceRelight](#ForceRelight)() |
| simul::clouds::CloudInterface * | [GetCloudInterface](#GetCloudInterface)() |
| float | [GetDefaultFloat](#GetDefaultFloat)(char name) |
| int | [GetDefaultInt](#GetDefaultInt)(char name) |
| int | [GetExportLightningStrikes](#GetExportLightningStrikes)(simul::clouds::ExportLightningStrike strikes, int max_s, float game_time, float real_time, simul::clouds::CloudWindow w) |
| float | [GetFloat](#GetFloat)(char name, simul::base::Variant params) |
| simul::math::Vector3 | [GetGridOrigin](#GetGridOrigin)() |
| simul::math::Vector3 | [GetInitialOffset](#GetInitialOffset)() |
| int | [GetInt](#GetInt)(char name, simul::base::Variant params) |
| simul::clouds::CloudKeyframe  & | [GetInterpolatedKeyframe](#GetInterpolatedKeyframe)() |
| float | [GetInterpolation](#GetInterpolation)() |
| unsigned int | [GetInterpolationChecksum](#GetInterpolationChecksum)() |
| simul::sky::BaseKeyframe * | [GetKeyframe](#GetKeyframe)(int i) |
| simul::clouds::LightningProperties  const & | [GetLightningProperties](#GetLightningProperties)(float game_time, float real_time, simul::clouds::CloudWindow window) |
| float | [GetMaximumLocalPrecipitation](#GetMaximumLocalPrecipitation)(pos) |
| simul::clouds::CloudKeyframe * | [GetNextModifiableKeyframe](#GetNextModifiableKeyframe)() |
| int | [GetNumKeyframes](#GetNumKeyframes)() |
| int | [GetNumStorms](#GetNumStorms)() |
| simul::clouds::Storm  const * | [GetStorm](#GetStorm)(float t) |
| simul::clouds::Storm * | [GetStorm](#GetStorm)(float t) |
| simul::clouds::Storm * | [GetStorm](#GetStorm)(int i) |
| simul::clouds::Storm * | [GetStormByUniqueId](#GetStormByUniqueId)(simul::sky::uid uid) |
| simul::clouds::Storm  const * | [GetStormByUniqueId](#GetStormByUniqueId)(simul::sky::uid uid) |
| unsigned int | [GetSubdivisionChecksum](#GetSubdivisionChecksum)() |
| int3 | [GetTextureSizes](#GetTextureSizes)() |
| simul::math::Vector3 | [GetWindOffsetKm](#GetWindOffsetKm)() |
| bool | [HasFloat](#HasFloat)(char name) |
| bool | [HasInt](#HasInt)(char name) |
| simul::clouds::CloudKeyframe * | [InsertKeyframe](#InsertKeyframe)(float t) |
| void | [Load](#Load)(simul::sky::Input is) |
| void | [LoadFromText](#LoadFromText)(simul::crossplatform::TextInput input) |
| void | [New](#New)() |
| simul::clouds::CloudKeyframer  const & | [operator=](#operator=)(simul::clouds::CloudKeyframer SK) |
| void | [RecalculateOffsets](#RecalculateOffsets)() |
| void | [Relocate](#Relocate)(pos_before, pos_after) |
| void | [RemoveVolume](#RemoveVolume)(simul::sky::uid id) |
| void | [Reset](#Reset)() |
| void | [Save](#Save)(simul::sky::Output os) |
| void | [SaveToText](#SaveToText)(simul::crossplatform::TextOutput output, bool include_keyframes) |
| void | [SetFloat](#SetFloat)(char name, float val) |
| void | [SetInt](#SetInt)(char name, int val) |
| void | [SetLoopWind](#SetLoopWind)() |
| void | [SetRecalculate](#SetRecalculate)() |
| void | [SetSkyInterface](#SetSkyInterface)(simul::sky::BaseSkyInterface si) |
| void | [SetUniformKeyframes](#SetUniformKeyframes)(int StepsPerDay, float range) |
| void | [SetVolume](#SetVolume)(simul::sky::uid id, simul::clouds::CloudVolumeType type, simul::crossplatform::Quaterniond orig, vec2 lscale, vec2 uscale, vec2 rake, vec2 height_range_km) |
| void | [Synchronize](#Synchronize)() |
| void | [Update](#Update)(float new_time) |
| unsigned int | [GetOffsetChecksum](#GetOffsetChecksum)() |


Base Classes
---
[simul::sky::OvercastCallback](../sky/overcastcallback.html)
[simul::sky::BaseKeyframer](../sky/basekeyframer.html)

Functions
---
<a name="CloudKeyframer"></a>
###  CloudKeyframer(simul::base::MemoryInterface mem, bool make2d)
Constructor
<a name="~CloudKeyframer"></a>
###  ~CloudKeyframer()
Destructor
<a name="AddStorm"></a>
### simul::clouds::Storm * AddStorm(float t0, float t1, simul::crossplatform::Quaterniond origin, float r_km)
Add a storm between the times specified, at the given centre c, with horizontal radius r (km).
<a name="DeleteKeyframe"></a>
### void DeleteKeyframe(int i)
Remove a keyframe
<a name="DeleteKeyframeByUID"></a>
### void DeleteKeyframeByUID(simul::sky::uid uid)
Remove Keyframe by UID
<a name="DeleteStorm"></a>
### void DeleteStorm(int i)
Remove the storm with index i.
<a name="DeleteStormByUniqueId"></a>
### void DeleteStormByUniqueId(simul::sky::uid uid)
Remove the storm with unique id uid.
<a name="ForceRelight"></a>
### void ForceRelight()
For debugging purposes only.
<a name="GetCloudInterface"></a>
### simul::clouds::CloudInterface * GetCloudInterface()
Set the cloud interface. As the constructor needs a CloudInterface, it is not usually necessary to call this.
<a name="GetDefaultFloat"></a>
### float GetDefaultFloat(char name)
Return the default float value with the given, case-insensitive, name.
<a name="GetDefaultInt"></a>
### int GetDefaultInt(char name)
Return the default int value with the given, case-insensitive, name.
<a name="GetExportLightningStrikes"></a>
### int GetExportLightningStrikes(simul::clouds::ExportLightningStrike strikes, int max_s, float game_time, float real_time, simul::clouds::CloudWindow w)
Fills the strikes array and returns how many active strikes in the storm
NOTE: right now we only consider 1 strike.
<a name="GetFloat"></a>
### float GetFloat(char name, simul::base::Variant params)
Get a float with the given, case-insensitive, name
<a name="GetGridOrigin"></a>
### simul::math::Vector3 GetGridOrigin()
Get the origin of the render grid; this is adjusted internally when Relocate() is called.
<a name="GetInitialOffset"></a>
### simul::math::Vector3 GetInitialOffset()
Get the offset of the first keyframe, a mutable property determined by Relocate().
<a name="GetInt"></a>
### int GetInt(char name, simul::base::Variant params)
Get an int with the given, case-insensitive, name
<a name="GetInterpolatedKeyframe"></a>
### simul::clouds::CloudKeyframe  & GetInterpolatedKeyframe()
Get the current interpolatedkeyframe, which holds the values interpolated from the two surrounding keyframes at
any given time.
<a name="GetInterpolation"></a>
### float GetInterpolation()
Get the interpolation - between zero and one. This is based on InterpStepTime and the sky's Daytime property.
When the interpolation reaches one, the textures will be cycled.
<a name="GetInterpolationChecksum"></a>
### unsigned int GetInterpolationChecksum()
Checksum for the interpolated state.
<a name="GetKeyframe"></a>
### simul::sky::BaseKeyframe * GetKeyframe(int i)
Get a pointer to the keyframe with the given ID
<a name="GetLightningProperties"></a>
### simul::clouds::LightningProperties  const & GetLightningProperties(float game_time, float real_time, simul::clouds::CloudWindow window)
Get the properties of the currently active lightning strike
<a name="GetMaximumLocalPrecipitation"></a>
### float GetMaximumLocalPrecipitation(pos)
How much precipitation there is at this point. This value is only approximate - it does not account for the actual cloud cover generated on GPU,
so it only gives the maximum precipitation that is possible at this point.
<a name="GetNextModifiableKeyframe"></a>
### simul::clouds::CloudKeyframe * GetNextModifiableKeyframe()
The next keyframe not partially built or being used. This keyframe's properties can be modified without any pause or rebuild.
<a name="GetNumKeyframes"></a>
### int GetNumKeyframes()
Number of keyframes.
<a name="GetNumStorms"></a>
### int GetNumStorms()
The number of storms on the timeline.
<a name="GetStorm"></a>
### simul::clouds::Storm  const * GetStorm(float t)
Get the storm, if any, that is active at time t.
<a name="GetStorm"></a>
### simul::clouds::Storm * GetStorm(float t)
Get the storm, if any, that is active at time t.
<a name="GetStorm"></a>
### simul::clouds::Storm * GetStorm(int i)
Return the storm with index i.
<a name="GetStormByUniqueId"></a>
### simul::clouds::Storm * GetStormByUniqueId(simul::sky::uid uid)
Return the storm with unique identifier uid.
<a name="GetStormByUniqueId"></a>
### simul::clouds::Storm  const * GetStormByUniqueId(simul::sky::uid uid)
Return the storm with unique identifier uid.
<a name="GetSubdivisionChecksum"></a>
### unsigned int GetSubdivisionChecksum()
This is a checksum that only changes if an in-use subdivision has modified (cycling does not change it).
<a name="GetTextureSizes"></a>
### int3 GetTextureSizes()
// REPLACING CALLBACK SEMANTICS WITH ITERATOR MODEL:
<a name="GetWindOffsetKm"></a>
### simul::math::Vector3 GetWindOffsetKm()
Get the current offset of the cloud window due to wind.
<a name="HasFloat"></a>
### bool HasFloat(char name)
Return true if the keyframe has a float value with the given, case-insensitive, name; return false otherwise.
<a name="HasInt"></a>
### bool HasInt(char name)
Return true if the keyframe has an int value with the given, case-insensitive, name; return false otherwise.
<a name="InsertKeyframe"></a>
### simul::clouds::CloudKeyframe * InsertKeyframe(float t)
Insert a new keyframe at time t, sorting in between the existing keyframes if needed, and return a pointer to it.
<a name="Load"></a>
### void Load(simul::sky::Input is)
Load from a binary stream:
<a name="LoadFromText"></a>
### void LoadFromText(simul::crossplatform::TextInput input)
Load from a text file
<a name="New"></a>
### void New()
Clear keyframes.
<a name="operator="></a>
### simul::clouds::CloudKeyframer  const & operator=(simul::clouds::CloudKeyframer SK)

A class to manage interpolation between cloud states over time.
Typically, a CloudKeyframer is created and updated by its 
<a name="RecalculateOffsets"></a>
### void RecalculateOffsets()
Check for changed offsets and recalculate.
<a name="Relocate"></a>
### void Relocate(pos_before, pos_after)
Relocate: to avoid numerical precision problems, relocation can be performed. Specify any position, before and after relocation.
<a name="RemoveVolume"></a>
### void RemoveVolume(simul::sky::uid id)
Remove a custom cloud volume
<a name="Reset"></a>
### void Reset()
Force recalculation of the per-keyframe tables.
<a name="Save"></a>
### void Save(simul::sky::Output os)
Save to a binary stream:
<a name="SaveToText"></a>
### void SaveToText(simul::crossplatform::TextOutput output, bool include_keyframes)
Save to a text file
<a name="SetFloat"></a>
### void SetFloat(char name, float val)
Set a float with the given, case-insensitive, name
<a name="SetInt"></a>
### void SetInt(char name, int val)
Set an int with the given, case-insensitive, name
<a name="SetLoopWind"></a>
### void SetLoopWind()
Make the wind offsets loop based on the loop time.
<a name="SetRecalculate"></a>
### void SetRecalculate()
Force clouds to regenerate.
<a name="SetSkyInterface"></a>
### void SetSkyInterface(simul::sky::BaseSkyInterface si)
Set the sky - this is used to light the clouds over time.
<a name="SetUniformKeyframes"></a>
### void SetUniformKeyframes(int StepsPerDay, float range)
Create a number of evenly spaced keyframes.
<a name="SetVolume"></a>
### void SetVolume(simul::sky::uid id, simul::clouds::CloudVolumeType type, simul::crossplatform::Quaterniond orig, vec2 lscale, vec2 uscale, vec2 rake, vec2 height_range_km)
Set the properties of a custom cloud volume:
<a name="Synchronize"></a>
### void Synchronize()
Restart all the frame-dependent values (mainly wind offsets), for example in order to synchronize rendering across several channels.
<a name="Update"></a>
### void Update(float new_time)
Once-per-frame update for the keyframer, call this with an absolute time value (not a time step).
<a name="GetOffsetChecksum"></a>
### unsigned int GetOffsetChecksum()
Checksum to determine whether any keyframe has altered its position due to wind speed or direction.

Enums
---
