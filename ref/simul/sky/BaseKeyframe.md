---
title: BaseKeyframe
layout: reference
weight: 0
---
struct BaseKeyframe
===

| Include: | Sky/BaseKeyframer.h |

The base keyframe structure, containing time, the time that the keyframe represents.
  


Functions
---

| simul::sky::float4 | [GetColour](#GetColour)(char) |
| float | [GetFloat](#GetFloat)(char name) |
| int | [GetInt](#GetInt)(char) |
| bool | [HasFloat](#HasFloat)(char name) |
| bool | [HasInt](#HasInt)(char name) |
| void | [Load](#Load)(simul::sky::Input is, simul::base::MemoryInterface memoryInterface) |
| void | [LoadFromText](#LoadFromText)(simul::crossplatform::TextInput input) |
| void | [Save](#Save)(simul::sky::Output os) |
| void | [SaveToText](#SaveToText)(simul::crossplatform::TextOutput os) |
| void | [SetColour](#SetColour)(char, simul::sky::float4) |
| void | [SetFloat](#SetFloat)(char name, float val) |
| void | [SetInt](#SetInt)(char, int) |

The base keyframe structure, containing time, the time that the keyframe represents.
  


Functions
---

### <a name="GetColour"/>simul::sky::float4 GetColour(char)
Return the colour value with the given, case-insensitive, name.

### <a name="GetFloat"/>float GetFloat(char name)
Return the float value with the given, case-insensitive, name.

### <a name="GetInt"/>int GetInt(char)
Return the integer value with the given, case-insensitive, name.

### <a name="HasFloat"/>bool HasFloat(char name)
Return true if the keyframe has a float value with the given, case-insensitive, name; return false otherwise.

### <a name="HasInt"/>bool HasInt(char name)
Return true if the keyframe has an int value with the given, case-insensitive, name; return false otherwise.

### <a name="Load"/>void Load(simul::sky::Input is, simul::base::MemoryInterface memoryInterface)
Load this keyframe's values from the stream.

### <a name="LoadFromText"/>void LoadFromText(simul::crossplatform::TextInput input)
Load from a textual input.

### <a name="Save"/>void Save(simul::sky::Output os)
Save this keyframe's values to the stream.

### <a name="SaveToText"/>void SaveToText(simul::crossplatform::TextOutput os)
Save this keyframe's values to textual output.

### <a name="SetColour"/>void SetColour(char, simul::sky::float4)
Set the colour value with the given, case-insensitive, name.

### <a name="SetFloat"/>void SetFloat(char name, float val)
Set the float value with the given, case-insensitive, name.

### <a name="SetInt"/>void SetInt(char, int)
Set the integer value with the given, case-insensitive, name.

Fields
---

**time**  The time this keyframe is for.

**unique_id**  A unique id. This is now persistent across Save/Load.
