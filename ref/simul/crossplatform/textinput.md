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
| double | [Get](#Get)(char name, double default_) |
| float | [Get](#Get)(char name, float default_) |
| int3 | [Get](#Get)(char name, int3 default_) |
| vec2 | [Get](#Get)(char name, vec2 default_) |
| vec3 | [Get](#Get)(char name, vec3 default_) |
| vec4 | [Get](#Get)(char name, vec4 default_) |
| char  const * | [Get](#Get)(int propertyIndex) |
| simul::crossplatform::TextInput * | [GetSubElement](#GetSubElement)(char name) |
| char  const * | [GetSubElement](#GetSubElement)(int) |
| bool | [Good](#Good)() |
| bool | [Has](#Has)(char name) |


Functions
---

### <a name="Get"/>char  const * Get(char name, char default_)
Text value of the specified element.

### <a name="Get"/>bool Get(char name, bool default_)
Boolean value of the specified element.

### <a name="Get"/>int Get(char name, int default_)
Integer value of the specified element.

### <a name="Get"/>double Get(char name, double default_)
Floating-point value of the specified element.

### <a name="Get"/>float Get(char name, float default_)
Floating-point value of the specified element.

### <a name="Get"/>int3 Get(char name, int3 default_)
Integer value of the specified element.

### <a name="Get"/>vec2 Get(char name, vec2 default_)
Floating-point value of the specified element.

### <a name="Get"/>vec3 Get(char name, vec3 default_)
Floating-point value of the specified element.

### <a name="Get"/>vec4 Get(char name, vec4 default_)
Floating-point value of the specified element.

### <a name="Get"/>char  const * Get(int propertyIndex)
The property at the given index. type should be Variant::UNKNOWN at the end of the list.

### <a name="GetSubElement"/>simul::crossplatform::TextInput * GetSubElement(char name)
Sub-element with the given name. If null, the Value() should be non-null.

### <a name="GetSubElement"/>char  const * GetSubElement(int)
Sub-element with the given index, starting at zero. If null, it's past the end of the list

### <a name="Good"/>bool Good()
Returns true if the file is successfully loaded

### <a name="Has"/>bool Has(char name)
Is the specified element in the list?
