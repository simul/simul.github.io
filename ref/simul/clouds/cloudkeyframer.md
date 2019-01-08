---
title: CloudKeyframer
layout: reference
weight: 0
---
class CloudKeyframer
===

| Include: | Clouds/BaseWeatherRenderer.h |


A class to manage interpolation between cloud states over time.
Typically, a CloudKeyframer is created and updated by its <a href="environment">Environment</a>.

If time and daytime are linked in the SkyKeyframer, time is in days, otherwise the timescale is in arbitrary units.

  

[simul::sky::OvercastCallback](../sky/overcastcallback)
[simul::sky::BaseKeyframer](../sky/basekeyframer)

Classes and Structures
---

| struct [Storm](cloudkeyframer/storm) |  |

Functions
---

| simul::clouds::CloudKeyframer::Storm * | [AddStorm](#AddStorm)(float t0, float t1, vec2 centre_km, float r_km) |
| void | [DeleteStorm](#DeleteStorm)(int i) |
| void | [DeleteStormByUniqueId](#DeleteStormByUniqueId)(unsigned int uid) |
| void | [ForceRelight](#ForceRelight)() |
| simul::clouds::CloudInterface * | [GetCloudInterface](#GetCloudInterface)() |
| float | [GetDefaultFloat](#GetDefaultFloat)(char name) |
| int | [GetDefaultInt](#GetDefaultInt)(char name) |
| int | [GetExportLightningStrikes](#GetExportLightningStrikes)(simul::clouds::ExportLightningStrike strikes, int max_s, float game_time, float real_time) |
| simul::math::Vector3 | [GetGridOrigin](#GetGridOrigin)() |
| simul::math::Vector3 | [GetInitialOffset](#GetInitialOffset)() |
| simul::clouds::CloudKeyframe  & | [GetInterpolatedKeyframe](#GetInterpolatedKeyframe)() |
| float | [GetInterpolation](#GetInterpolation)() |
| unsigned int | [GetInterpolationChecksum](#GetInterpolationChecksum)() |
| float | [GetMaximumLocalPrecipitation](#GetMaximumLocalPrecipitation)(pos) |
| simul::clouds::CloudKeyframe * | [GetNextModifiableKeyframe](#GetNextModifiableKeyframe)() |
| int | [GetNumKeyframes](#GetNumKeyframes)() |
| int | [GetNumStorms](#GetNumStorms)() |
| simul::clouds::CloudKeyframer::Storm  const * | [GetStorm](#GetStorm)(float t) |
| simul::clouds::CloudKeyframer::Storm * | [GetStorm](#GetStorm)(float t) |
| simul::clouds::CloudKeyframer::Storm * | [GetStorm](#GetStorm)(int i) |
| simul::clouds::CloudKeyframer::Storm * | [GetStormByUniqueId](#GetStormByUniqueId)(unsigned int uid) |
| simul::clouds::CloudKeyframer::Storm  const * | [GetStormByUniqueId](#GetStormByUniqueId)(unsigned int uid) |
| unsigned int | [GetSubdivisionChecksum](#GetSubdivisionChecksum)() |
| int3 | [GetTextureSizes](#GetTextureSizes)() |
| simul::clouds::CloudKeyframe * | [InsertKeyframe](#InsertKeyframe)(float t) |
| void | [Load](#Load)(simul::sky::Input is) |
| void | [New](#New)() |
| void | [RecalculateOffsets](#RecalculateOffsets)() |
| void | [Relocate](#Relocate)(pos_before, pos_after) |
| void | [Reset](#Reset)() |
| void | [Save](#Save)(simul::sky::Output os) |
| void | [SetLoopWind](#SetLoopWind)() |
| void | [SetRecalculate](#SetRecalculate)() |
| void | [SetSkyInterface](#SetSkyInterface)(simul::sky::BaseSkyInterface si) |
| void | [SetUniformKeyframes](#SetUniformKeyframes)(int StepsPerDay, float range) |
| void | [SetVolume](#SetVolume)(int id, simul::clouds::CloudVolumeType type, simul::crossplatform::Quaterniond orig, vec3 scale, vec2 rake) |
| void | [Synchronize](#Synchronize)() |
| void | [Update](#Update)(float new_time) |
| unsigned int | [GetOffsetChecksum](#GetOffsetChecksum)() |


A class to manage interpolation between cloud states over time.
Typically, a CloudKeyframer is created and updated by its <a href="environment">Environment</a>.

If time and daytime are linked in the SkyKeyframer, time is in days, otherwise the timescale is in arbitrary units.

  


Base Classes
---
[simul::sky::OvercastCallback](../sky/overcastcallback)
[simul::sky::BaseKeyframer](../sky/basekeyframer)

Functions
---

### <a name="AddStorm"/>simul::clouds::CloudKeyframer::Storm * AddStorm(float t0, float t1, vec2 centre_km, float r_km)
Add a storm between the times specified, at the given centre c, with horizontal radius r (km).

### <a name="DeleteStorm"/>void DeleteStorm(int i)
Remove the storm with index i.

### <a name="DeleteStormByUniqueId"/>void DeleteStormByUniqueId(unsigned int uid)
Remove the storm with unique id uid.

### <a name="ForceRelight"/>void ForceRelight()
For debugging purposes only.

### <a name="GetCloudInterface"/>simul::clouds::CloudInterface * GetCloudInterface()
Set the cloud interface. As the constructor needs a CloudInterface, it is not usually necessary to call this.

### <a name="GetDefaultFloat"/>float GetDefaultFloat(char name)
Return the default float value with the given, case-insensitive, name.

### <a name="GetDefaultInt"/>int GetDefaultInt(char name)
Return the default float value with the given, case-insensitive, name.

### <a name="GetExportLightningStrikes"/>int GetExportLightningStrikes(simul::clouds::ExportLightningStrike strikes, int max_s, float game_time, float real_time)
Fills the strikes array and returns how many active strikes in the storm
NOTE: right now we only consider 1 strike.

### <a name="GetGridOrigin"/>simul::math::Vector3 GetGridOrigin()
Get the origin of the render grid; this is adjusted internally when Relocate() is called.

### <a name="GetInitialOffset"/>simul::math::Vector3 GetInitialOffset()
Get the offset of the first keyframe, a mutable property determined by Relocate().

### <a name="GetInterpolatedKeyframe"/>simul::clouds::CloudKeyframe  & GetInterpolatedKeyframe()
Get the current interpolatedkeyframe, which holds the values interpolated from the two surrounding keyframes at
any given time.

### <a name="GetInterpolation"/>float GetInterpolation()
Get the interpolation - between zero and one. This is based on InterpStepTime and the sky's Daytime property.
When the interpolation reaches one, the textures will be cycled.

### <a name="GetInterpolationChecksum"/>unsigned int GetInterpolationChecksum()
Checksum for the interpolated state.

### <a name="GetMaximumLocalPrecipitation"/>float GetMaximumLocalPrecipitation(pos)
How much precipitation there is at this point. This value is only approximate - it does not account for the actual cloud cover generated on GPU,
so it only gives the maximum precipitation that is possible at this point.

### <a name="GetNextModifiableKeyframe"/>simul::clouds::CloudKeyframe * GetNextModifiableKeyframe()
The next keyframe not partially built or being used. This keyframe's properties can be modified without any pause or rebuild.

### <a name="GetNumKeyframes"/>int GetNumKeyframes()
Number of keyframes.

### <a name="GetNumStorms"/>int GetNumStorms()
The number of storms on the timeline.

### <a name="GetStorm"/>simul::clouds::CloudKeyframer::Storm  const * GetStorm(float t)
Get the storm, if any, that is active at time t.

### <a name="GetStorm"/>simul::clouds::CloudKeyframer::Storm * GetStorm(float t)
Get the storm, if any, that is active at time t.

### <a name="GetStorm"/>simul::clouds::CloudKeyframer::Storm * GetStorm(int i)
Return the storm with index i.

### <a name="GetStormByUniqueId"/>simul::clouds::CloudKeyframer::Storm * GetStormByUniqueId(unsigned int uid)
Return the storm with unique identifier uid.

### <a name="GetStormByUniqueId"/>simul::clouds::CloudKeyframer::Storm  const * GetStormByUniqueId(unsigned int uid)
Return the storm with unique identifier uid.

### <a name="GetSubdivisionChecksum"/>unsigned int GetSubdivisionChecksum()
This is a checksum that only changes if an in-use subdivision has modified (cycling does not change it).

### <a name="GetTextureSizes"/>int3 GetTextureSizes()
// REPLACING CALLBACK SEMANTICS WITH ITERATOR MODEL:

### <a name="InsertKeyframe"/>simul::clouds::CloudKeyframe * InsertKeyframe(float t)
Insert a new keyframe at time t, sorting in between the existing keyframes if needed, and return a pointer to it.

### <a name="Load"/>void Load(simul::sky::Input is)
Load from a binary stream:

### <a name="New"/>void New()
Clear keyframes.

### <a name="RecalculateOffsets"/>void RecalculateOffsets()
Check for changed offsets and recalculate.

### <a name="Relocate"/>void Relocate(pos_before, pos_after)
Relocate: to avoid numerical precision problems, relocation can be performed. Specify any position, before and after relocation.

### <a name="Reset"/>void Reset()
Force recalculation of the per-keyframe tables.

### <a name="Save"/>void Save(simul::sky::Output os)
Save to a binary stream:

### <a name="SetLoopWind"/>void SetLoopWind()
Make the wind offsets loop based on the loop time.

### <a name="SetRecalculate"/>void SetRecalculate()
Force clouds to regenerate.

### <a name="SetSkyInterface"/>void SetSkyInterface(simul::sky::BaseSkyInterface si)
Set the sky - this is used to light the clouds over time.

### <a name="SetUniformKeyframes"/>void SetUniformKeyframes(int StepsPerDay, float range)
Apply the cloud's properties to all keyframes.
Create a number of evenly spaced keyframes.

### <a name="SetVolume"/>void SetVolume(int id, simul::clouds::CloudVolumeType type, simul::crossplatform::Quaterniond orig, vec3 scale, vec2 rake)
Set the properties of a custom cloud volume:

### <a name="Synchronize"/>void Synchronize()
Restart all the frame-dependent values (mainly wind offsets), for example in order to synchronize rendering across several channels.

### <a name="Update"/>void Update(float new_time)
Once-per-frame update for the keyframer, call this with an absolute time value (not a time step).

### <a name="GetOffsetChecksum"/>unsigned int GetOffsetChecksum()
Checksum to determine whether any keyframe has altered its position due to wind speed or direction.

Enums
---
