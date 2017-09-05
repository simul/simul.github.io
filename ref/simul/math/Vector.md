---
title: Vector
layout: reference
weight: 0
---
class Vector
===

| Include: | Math/Matrix.h |

A resizeable vector class


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

A resizeable vector class
  


Functions
---

### <a name="Append"/>void Append(float s)
< Insert a value at Idx, shifting succeeding values up one place.
< Insert a value at Idx, shifting succeeding values up one place.

### <a name="CheckEdges"/>void CheckEdges()
< Increase vector size by one, putting s on the end.
< Increase vector size by one, putting s on the end.

### <a name="CheckNAN"/>void CheckNAN()
< Divide by the vector's magnitude.
< Divide by the vector's magnitude.

### <a name="Clear"/>void Clear()
< Is any value not a number?
< Is any value not a number?

### <a name="ContainsNAN"/>bool ContainsNAN()
< Set all values to zero.
< Set all values to zero.

### <a name="Cut"/>void Cut(unsigned int Idx)
Remove the value at Idx, shift the remainder down one place.
Remove the value at Idx, shift the remainder down one place.

### <a name="CutUnordered"/>void CutUnordered(unsigned int Idx)
< Remove the value at Idx, shifting values after it back one place.
< Remove the value at Idx, shifting values after it back one place.

### <a name="FloatPointer"/>float * FloatPointer()
< Resize to zero and free the memory which was used.
< Resize to zero and free the memory which was used.

### <a name="Insert"/>void Insert(unsigned int Idx)
Insert a value at Idx.
Insert a value at Idx.

### <a name="operator()"/>float  & operator()(unsigned int index)
The float at position given by index.
The float at position given by index.

### <a name="operator()"/>float operator()(unsigned int index)
The float at position given by index.
The float at position given by index.

### <a name="operator*="/>void operator*=(float f)
Multiply this vector by a scalar
Multiply this vector by a scalar

### <a name="operator>"/>bool operator>(float R)
< Multiply by f.
< Multiply by f.

### <a name="Resize"/>void Resize(unsigned int s)
Change the vector size.
Change the vector size.

### <a name="Unit"/>bool Unit()
Scale the vector so its magnitude is unity.
Scale the vector so its magnitude is unity.

### <a name="Zero"/>void Zero()
Set all values to zero.
Set all values to zero.
