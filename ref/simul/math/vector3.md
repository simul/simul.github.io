---
title: Vector3
layout: reference
weight: 0
---
class Vector3
===

| Include: | Platform/CrossPlatform/CameraInterface.h |



Functions
---

|  | [Vector3](#Vector3)(simul::math::Vector3 v) |
|  | [Vector3](#Vector3)(float a, float b, float c) |
|  | [Vector3](#Vector3)(float x) |
| void | [AddLarger](#AddLarger)(simul::math::Vector v) |
| void | [DefineValues](#DefineValues)(float x) |
| float * | [FloatPointer](#FloatPointer)(unsigned int idx) |
| float | [Magnitude](#Magnitude)() |
| bool | [NonZero](#NonZero)() |
| bool | [Normalize](#Normalize)() |
| float  & | [operator()](#operator())(unsigned int index) |
| float | [operator()](#operator())(unsigned int index) |
| void | [operator*=](#operator*=)(simul::math::Vector3 v) |
| void | [operator*=](#operator*=)(float f) |
| void | [operator+=](#operator+=)(simul::math::Vector3 v) |
| void | [operator+=](#operator+=)(float f) |
| simul::math::Vector3 | [operator-](#operator-)() |
| void | [operator-=](#operator-=)(float f) |
| void | [operator/=](#operator/=)(float f) |
| void | [operator/=](#operator/=)(simul::math::Vector3 v) |
| bool | [operator==](#operator==)(simul::math::Vector3 v) |
| bool | [operator>](#operator>)(float R) |
| float | [SquareSize](#SquareSize)() |
| bool | [Unit](#Unit)() |
| void | [Zero](#Zero)() |


Functions
---

### <a name="Vector3"/> Vector3(simul::math::Vector3 v)
< Default constructor, values are set to zero.

### <a name="Vector3"/> Vector3(float a, float b, float c)
< Copy constructor.

### <a name="Vector3"/> Vector3(float x)
< Constructor, values are set to (a,b,c).

### <a name="AddLarger"/>void AddLarger(simul::math::Vector v)
Add the first three elements of Vector v to this - v should have 3 or more elements.

### <a name="DefineValues"/>void DefineValues(float x)
< Set the values to (x,y,z).

### <a name="FloatPointer"/>float * FloatPointer(unsigned int idx)
Return the address of the array of values. In most implementations, equal to the address of the Vector3 (the this pointer).

### <a name="Magnitude"/>float Magnitude()
< Is the magnitude of the vector greater than scalar R?

### <a name="NonZero"/>bool NonZero()
Return true if any value is non-zero.

### <a name="Normalize"/>bool Normalize()
Scale the vector so its magnitude is unity.

### <a name="operator()"/>float  & operator()(unsigned int index)
Return the value at index index, which should be 0, 1 or 2.

### <a name="operator()"/>float operator()(unsigned int index)
Return the value at index index, which should be 0, 1 or 2.

### <a name="operator*="/>void operator*=(simul::math::Vector3 v)
< Add v to this.

### <a name="operator*="/>void operator*=(float f)
< Add f to each element.

### <a name="operator+="/>void operator+=(simul::math::Vector3 v)
< Subtract v from this.

### <a name="operator+="/>void operator+=(float f)
< Subtract f from each element.

### <a name="operator-"/>simul::math::Vector3 operator-()
< Multiply this vector by the scalar f.

### <a name="operator-="/>void operator-=(float f)
< Add v to this.

### <a name="operator/="/>void operator/=(float f)
< The negative of this vector.

### <a name="operator/="/>void operator/=(simul::math::Vector3 v)
< Divide this vector by the scalar f.

### <a name="operator=="/>bool operator==(simul::math::Vector3 v)
Is this vector equal to v?

### <a name="operator>"/>bool operator>(float R)
< Divide each component of the vector by the corresponding component of v.

### <a name="SquareSize"/>float SquareSize()
< Magnitude, or length of the vector.

### <a name="Unit"/>bool Unit()
Scale the vector so its magnitude is unity.

### <a name="Zero"/>void Zero()
< Set the values to (x[0],x[1],x[2]).
