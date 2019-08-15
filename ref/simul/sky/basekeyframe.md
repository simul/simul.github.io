---
title: BaseKeyframe
layout: reference
weight: 0
---
struct BaseKeyframe
===

| Include: | Sky/BaseKeyframer.h |

The base keyframe structure, containing <a href="basekeyframe/time.html">time</a>, the time that the keyframe represents.
  


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

The base keyframe structure, containing <a href="basekeyframe/time.html">time</a>, the time that the keyframe represents.
  


Functions
---
<a name="GetColour"></a>
### simul::sky::float4 GetColour(char)
Return the colour value with the given, case-insensitive, name.
<a name="GetFloat"></a>
### float GetFloat(char name)
Return the float value with the given, case-insensitive, name.
<a name="GetInt"></a>
### int GetInt(char)
Return the integer value with the given, case-insensitive, name.
<a name="HasFloat"></a>
### bool HasFloat(char name)
Return true if the keyframe has a float value with the given, case-insensitive, name; return false otherwise.
<a name="HasInt"></a>
### bool HasInt(char name)
Return true if the keyframe has an int value with the given, case-insensitive, name; return false otherwise.
<a name="Load"></a>
### void Load(simul::sky::Input is, simul::base::MemoryInterface memoryInterface)
Load this keyframe's values from the stream.
<a name="LoadFromText"></a>
### void LoadFromText(simul::crossplatform::TextInput input)
Load from a textual input.
<a name="Save"></a>
### void Save(simul::sky::Output os)
Save this keyframe's values to the stream.
<a name="SaveToText"></a>
### void SaveToText(simul::crossplatform::TextOutput os)
Save this keyframe's values to textual output.
<a name="SetColour"></a>
### void SetColour(char, simul::sky::float4)
Set the colour value with the given, case-insensitive, name.
<a name="SetFloat"></a>
### void SetFloat(char name, float val)
Set the float value with the given, case-insensitive, name.
<a name="SetInt"></a>
### void SetInt(char, int)
Set the integer value with the given, case-insensitive, name.

Fields
---

**time**  The time this keyframe is for.

**unique_id**  A unique id. This is now persistent across Save/Load.
