---
title: BaseKeyframer
layout: reference
weight: 0
---
class BaseKeyframer
===

| Include: | Sky/BaseKeyframer.h |

The base class for keyframers. A keyframer stores a list of keyframes, each representing the state at
a particular time.
  


Functions
---

| void | [BumpKeyframe](#BumpKeyframe)(simul::sky::BaseKeyframe K, float time_scale) |
| void | [DeleteKeyframe](#DeleteKeyframe)(int i) |
| bool | [DeleteKeyframeByUniqueId](#DeleteKeyframeByUniqueId)(unsigned int id) |
| std::vector | [GetAllModifiableKeyframes](#GetAllModifiableKeyframes)() |
| int | [GetCurrentSubdivision](#GetCurrentSubdivision)() |
| float | [GetDefaultFloat](#GetDefaultFloat)(char name) |
| int | [GetDefaultInt](#GetDefaultInt)(char name) |
| float | [GetFloat](#GetFloat)(char, simul::base::Variant params) |
| int | [GetInt](#GetInt)(char, simul::base::Variant params) |
| simul::sky::BaseKeyframe * | [GetKeyframe](#GetKeyframe)(int i) |
| simul::sky::BaseKeyframe  const * | [GetKeyframe](#GetKeyframe)(int i) |
| int | [GetKeyframeAtTime](#GetKeyframeAtTime)(double t) |
| simul::sky::BaseKeyframe * | [GetKeyframeByUniqueId](#GetKeyframeByUniqueId)(unsigned int id) |
| simul::sky::BaseKeyframe  const * | [GetKeyframeByUniqueId](#GetKeyframeByUniqueId)(unsigned int id) |
| int | [GetKeyframeIndexByUniqueId](#GetKeyframeIndexByUniqueId)(unsigned int id) |
| float | [GetKeyframeTime](#GetKeyframeTime)(int i) |
| unsigned int | [GetKeyframeUidAfterTime](#GetKeyframeUidAfterTime)(double t) |
| unsigned int | [GetKeyframeUidAtOrBeforeTime](#GetKeyframeUidAtOrBeforeTime)(double t) |
| int | [GetNumKeyframes](#GetNumKeyframes)() |
| bool | [HasFloat](#HasFloat)(char) |
| bool | [HasInt](#HasInt)(char) |
| simul::sky::BaseKeyframe * | [InsertKeyframe](#InsertKeyframe)(float time) |
| void | [Load](#Load)(simul::sky::Input is) |
| void | [LoadFromText](#LoadFromText)(simul::crossplatform::TextInput input) |
| void | [Save](#Save)(simul::sky::Output os) |
| void | [SaveToText](#SaveToText)(simul::crossplatform::TextOutput os, bool include_keyframes) |
| void | [SetFloat](#SetFloat)(char, float) |
| void | [SortKeyframes](#SortKeyframes)() |

The base class for keyframers. A keyframer stores a list of keyframes, each representing the state at
a particular time.
  


Functions
---

### <a name="BumpKeyframe"/>void BumpKeyframe(simul::sky::BaseKeyframe K, float time_scale)
Check if this keyframe is too close to any others. This is done by seeing if it's closer than time_scale.
If so, the specified keyframe is moved away.

### <a name="DeleteKeyframe"/>void DeleteKeyframe(int i)
Delete the specified keyframe.

### <a name="DeleteKeyframeByUniqueId"/>bool DeleteKeyframeByUniqueId(unsigned int id)
Delete the keyframe if it exists (return true), else return false;

### <a name="GetAllModifiableKeyframes"/>std::vector GetAllModifiableKeyframes()
Get a list of all the keyframes not currently among the three in-use.

### <a name="GetCurrentSubdivision"/>int GetCurrentSubdivision()
Returns the index of the current keyframe.

### <a name="GetDefaultFloat"/>float GetDefaultFloat(char name)
Return the default float value with the given, case-insensitive, name.

### <a name="GetDefaultInt"/>int GetDefaultInt(char name)
Return the default int value with the given, case-insensitive, name.

### <a name="GetFloat"/>float GetFloat(char, simul::base::Variant params)
Text-based interface - returns the named value if it exists.

### <a name="GetInt"/>int GetInt(char, simul::base::Variant params)
Text-based interface - returns the named value if it exists.

### <a name="GetKeyframe"/>simul::sky::BaseKeyframe * GetKeyframe(int i)
Get a pointer to the i'th keyframe.

### <a name="GetKeyframe"/>simul::sky::BaseKeyframe  const * GetKeyframe(int i)
Get a pointer to the i'th keyframe.

### <a name="GetKeyframeAtTime"/>int GetKeyframeAtTime(double t)
Get the keyframe BEFORE or AT time t:

### <a name="GetKeyframeByUniqueId"/>simul::sky::BaseKeyframe * GetKeyframeByUniqueId(unsigned int id)
Get a pointer to the keyframe with the specified id, or NULL if there is no such keyframe.

### <a name="GetKeyframeByUniqueId"/>simul::sky::BaseKeyframe  const * GetKeyframeByUniqueId(unsigned int id)
Get a pointer to the keyframe with the specified id, or NULL if there is no such keyframe.

### <a name="GetKeyframeIndexByUniqueId"/>int GetKeyframeIndexByUniqueId(unsigned int id)
Get an index for the keyframe with the specified id, or NULL if there is no such keyframe.

### <a name="GetKeyframeTime"/>float GetKeyframeTime(int i)
Time of a particular keyframe.

### <a name="GetKeyframeUidAfterTime"/>unsigned int GetKeyframeUidAfterTime(double t)
Get the keyframe After time t:

### <a name="GetKeyframeUidAtOrBeforeTime"/>unsigned int GetKeyframeUidAtOrBeforeTime(double t)
Get the keyframe uid BEFORE or AT time t:

### <a name="GetNumKeyframes"/>int GetNumKeyframes()
Number of keyframes.

### <a name="HasFloat"/>bool HasFloat(char)
Text-based interface - returns true if the keyframer has a floating point value of the given name.

### <a name="HasInt"/>bool HasInt(char)
Text-based interface - returns true if the keyframer has a value of the given name.

### <a name="InsertKeyframe"/>simul::sky::BaseKeyframe * InsertKeyframe(float time)
Insert a keyframe at the given time and return a pointer to it.

### <a name="Load"/>void Load(simul::sky::Input is)
Stream/load from the std::isteam is.

### <a name="LoadFromText"/>void LoadFromText(simul::crossplatform::TextInput input)
Load from a textual input.

### <a name="Save"/>void Save(simul::sky::Output os)
Stream/save  to the std::osteam os.

### <a name="SaveToText"/>void SaveToText(simul::crossplatform::TextOutput os, bool include_keyframes)
Save this keyframer's values to textual output.

### <a name="SetFloat"/>void SetFloat(char, float)
Text-based interface - sets the named value if it exists.

### <a name="SortKeyframes"/>void SortKeyframes()
Make sure the keyframes are in ascending order of time.
