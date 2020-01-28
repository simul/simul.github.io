---
title: TextInput
layout: reference
weight: 0
---
class TextInput
===

| Include: | Platform/CrossPlatform/TextInputOutput.h |



Functions
---

| char  const * | [Get](#Get)(char name, char default_) |
| bool | [Get](#Get)(char name, bool default_) |
| int | [Get](#Get)(char name, int default_) |
| long long | [Get](#Get)(char name, long long default_) |
| unsigned long long | [Get](#Get)(char name, unsigned long long default_) |
| double | [Get](#Get)(char name, double default_) |
| float | [Get](#Get)(char name, float default_) |
| int3 | [Get](#Get)(char name, int3 default_) |
| vec2 | [Get](#Get)(char name, vec2 default_) |
| vec3 | [Get](#Get)(char name, vec3 default_) |
| vec4 | [Get](#Get)(char name, vec4 default_) |
| simul::crossplatform::Quaterniond | [Get](#Get)(char name, simul::crossplatform::Quaterniond default_) |
| char  const * | [Get](#Get)(int propertyIndex) |
| simul::crossplatform::TextInput * | [GetSubElement](#GetSubElement)(char name) |
| char  const * | [GetSubElement](#GetSubElement)(int) |
| bool | [Good](#Good)() |
| bool | [Has](#Has)(char name) |


Functions
---
<a name="Get"></a>
### char  const * Get(char name, char default_)
Text value of the specified element.
<a name="Get"></a>
### bool Get(char name, bool default_)
Boolean value of the specified element.
<a name="Get"></a>
### int Get(char name, int default_)
Integer value of the specified element.
<a name="Get"></a>
### long long Get(char name, long long default_)
64-bit integer value of the specified element.
<a name="Get"></a>
### unsigned long long Get(char name, unsigned long long default_)
64-bit integer value of the specified element.
<a name="Get"></a>
### double Get(char name, double default_)
Floating-point value of the specified element.
<a name="Get"></a>
### float Get(char name, float default_)
Floating-point value of the specified element.
<a name="Get"></a>
### int3 Get(char name, int3 default_)
Integer value of the specified element.
<a name="Get"></a>
### vec2 Get(char name, vec2 default_)
Floating-point value of the specified element.
<a name="Get"></a>
### vec3 Get(char name, vec3 default_)
Floating-point value of the specified element.
<a name="Get"></a>
### vec4 Get(char name, vec4 default_)
Floating-point value of the specified element.
<a name="Get"></a>
### simul::crossplatform::Quaterniond Get(char name, simul::crossplatform::Quaterniond default_)
Floating-point value of the specified element.
<a name="Get"></a>
### char  const * Get(int propertyIndex)
The property at the given index. type should be Variant::UNKNOWN at the end of the list.
<a name="GetSubElement"></a>
### simul::crossplatform::TextInput * GetSubElement(char name)
Sub-element with the given name. If null, the Value() should be non-null.
<a name="GetSubElement"></a>
### char  const * GetSubElement(int)
Sub-element with the given index, starting at zero. If null, it's past the end of the list
<a name="Good"></a>
### bool Good()
Returns true if the file is successfully loaded
<a name="Has"></a>
### bool Has(char name)
Is the specified element in the list?
