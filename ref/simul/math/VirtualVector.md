---
title: VirtualVector
layout: reference
weight: 0
---
class VirtualVector
===

| Include: | Math/Vector3.h |

VirtualVector is derived from Vector but does not manage its own data. Instead
the #PointTo method is used to give vector functionality to floating point data
anywhere in memory (as long as any alignment conditions are satisfied.)

[simul::math::Vector](Vector)

Functions
---

| void | [operator*=](#operator*=)(float f) |
| void | [Resize](#Resize)(unsigned int sz) |

VirtualVector is derived from Vector but does not manage its own data. Instead
the #PointTo method is used to give vector functionality to floating point data
anywhere in memory (as long as any alignment conditions are satisfied.)
  


Base Classes
---
[simul::math::Vector](Vector)

Functions
---

### <a name="operator*="/>void operator*=(float f)
< Make the vector be size sz.
< Make the vector be size sz.

### <a name="Resize"/>void Resize(unsigned int sz)
< Use the data at address addr for this vector.
< Use the data at address addr for this vector.
