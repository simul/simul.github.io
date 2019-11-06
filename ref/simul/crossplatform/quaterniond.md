---
title: Quaterniond
layout: reference
weight: 0
---
class Quaterniond
===

| Include: | Sky/BaseKeyframer.h |



Functions
---

| simul::crossplatform::Quaterniond | [operator!](#operator!)() |
| vec3d | [operator/](#operator/)(vec3d vec) |
| simul::crossplatform::Quaterniond  & | [operator=](#operator=)(simul::crossplatform::Quaterniond q) |


Functions
---
<a name="operator!"></a>
### simul::crossplatform::Quaterniond operator!()
The inverse, or opposite of the Quaterniond, representing an equal rotation
in the opposite direction.
<a name="operator/"></a>
### vec3d operator/(vec3d vec)
Equivalent to (!this)* vec
<a name="operator="></a>
### simul::crossplatform::Quaterniond  & operator=(simul::crossplatform::Quaterniond q)
Assignment operator. Set this Quaterniond equal to q.

Fields
---

**x**  Quaterniond class to represent rotations.
