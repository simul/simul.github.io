---
title: Quaternion
layout: reference
weight: 0
---
classtemplate Quaternion
===

| Include: | Platform/CrossPlatform/Quaterniond.h |

Quaternion template class to represent rotations.
  


Functions
---

| tvector3<T> | [operator/](#operator/)(tvector3<T> vec) |
| simul::crossplatform::Quaternion | [operator!](#operator!)() |
| simul::crossplatform::Quaternion  & | [operator=](#operator=)(simul::crossplatform::Quaternion q) |

Quaternion template class to represent rotations.
  


Functions
---
<a name="operator/"></a>
### tvector3<T> operator/(tvector3<T> vec)
Equivalent to (!this)* vec
<a name="operator!"></a>
### simul::crossplatform::Quaternion operator!()
The inverse, or opposite of the Quaternion, representing an equal rotation
in the opposite direction.
<a name="operator="></a>
### simul::crossplatform::Quaternion  & operator=(simul::crossplatform::Quaternion q)
Assignment operator. Set this Quaternion equal to q.
