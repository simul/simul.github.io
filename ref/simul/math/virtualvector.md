---
title: VirtualVector
layout: reference
weight: 0
---
class VirtualVector
===

| Include: | Math/Vector3.h |


[simul::math::Vector](vector)

Functions
---

|  | [VirtualVector](#VirtualVector)() |
| void | [operator*=](#operator*=)(float f) |
| void | [Resize](#Resize)(unsigned int sz) |


Base Classes
---
[simul::math::Vector](vector)

Functions
---

### <a name="VirtualVector"/> VirtualVector()
VirtualVector is derived from Vector but does not manage its own data. Instead
the #PointTo method is used to give vector functionality to floating point data
anywhere in memory (as long as any alignment conditions are satisfied.)

### <a name="operator*="/>void operator*=(float f)
< Make the vector be size sz.

### <a name="Resize"/>void Resize(unsigned int sz)
< Use the data at address addr for this vector.
