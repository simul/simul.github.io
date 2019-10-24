---
title: Vector
layout: reference
weight: 0
---
class Vector
===

| Include: | Math/Matrix.h |



Functions
---

| void | [Append](#Append)(float s) |
| void | [CheckEdges](#CheckEdges)() |
| void | [CheckNAN](#CheckNAN)() |
| void | [Clear](#Clear)() |
| bool | [ContainsNAN](#ContainsNAN)() |
| void | [Cut](#Cut)(unsigned int Idx) |
| void | [CutUnordered](#CutUnordered)(unsigned int Idx) |
| float * | [FloatPointer](#FloatPointer)() |
| void | [Insert](#Insert)(unsigned int Idx) |
| float  & | [operator()](#operator())(unsigned int index) |
| float | [operator()](#operator())(unsigned int index) |
| void | [operator*=](#operator*=)(float f) |
| bool | [operator>](#operator>)(float R) |
| void | [Resize](#Resize)(unsigned int s) |
| bool | [Unit](#Unit)() |
| void | [Zero](#Zero)() |
| void | [ChangeSize](#ChangeSize)(unsigned int s) |


Functions
---
<a name="Append"></a>
### void Append(float s)
< Insert a value at Idx, shifting succeeding values up one place.
<a name="CheckEdges"></a>
### void CheckEdges()
< Increase vector size by one, putting s on the end.
<a name="CheckNAN"></a>
### void CheckNAN()
< Divide by the vector's magnitude.
<a name="Clear"></a>
### void Clear()
< Is any value not a number?
<a name="ContainsNAN"></a>
### bool ContainsNAN()
< Set all values to zero.
<a name="Cut"></a>
### void Cut(unsigned int Idx)
Remove the value at Idx, shift the remainder down one place.
<a name="CutUnordered"></a>
### void CutUnordered(unsigned int Idx)
< Remove the value at Idx, shifting values after it back one place.
<a name="FloatPointer"></a>
### float * FloatPointer()
< Resize to zero and free the memory which was used.
<a name="Insert"></a>
### void Insert(unsigned int Idx)
Insert a value at Idx.
<a name="operator()"></a>
### float  & operator()(unsigned int index)
The float at position given by index.
<a name="operator()"></a>
### float operator()(unsigned int index)
The float at position given by index.
<a name="operator*="></a>
### void operator*=(float f)
Multiply this vector by a scalar
<a name="operator>"></a>
### bool operator>(float R)
< Multiply by f.
<a name="Resize"></a>
### void Resize(unsigned int s)
Change the vector size.
<a name="Unit"></a>
### bool Unit()
Scale the vector so its magnitude is unity.
<a name="Zero"></a>
### void Zero()
Set all values to zero.
<a name="ChangeSize"></a>
### void ChangeSize(unsigned int s)
< Resize the vector, allocating memory if s>size.

Fields
---

**Values**  A resizeable vector class
