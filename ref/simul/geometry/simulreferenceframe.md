---
title: SimulReferenceFrame
layout: reference
weight: 0
---
class SimulReferenceFrame
===

| Include: | Geometry/ReferenceFrame.h |

The reference frame holds position, rotation, and linear and angular velocity.
Velocity is a simul::math::Vector3 which can be accessed using #GetVelocity().
Angular velocity is a simul::math::Vector3 which can be accessed using #GetAngularVelocity().
  

[simul::geometry::SimulOrientation](simulorientation.html)

Functions
---

| simul::math::Vector3  const & | [GetAngularVelocity](#GetAngularVelocity)() |
| simul::math::Vector3 | [GetLocalAngularVelocity](#GetLocalAngularVelocity)() |
| void | [LocalPositionToGlobalVelocity](#LocalPositionToGlobalVelocity)(simul::math::Vector3 ve, simul::math::Vector3 xl) |
| void | [operator=](#operator=)(simul::geometry::SimulOrientation o) |
| void | [PositionToVelocity](#PositionToVelocity)(simul::math::Vector3 ve, simul::math::Vector3 xe) |

The reference frame holds position, rotation, and linear and angular velocity.
Velocity is a simul::math::Vector3 which can be accessed using #GetVelocity().
Angular velocity is a simul::math::Vector3 which can be accessed using #GetAngularVelocity().
  


Base Classes
---
[simul::geometry::SimulOrientation](simulorientation.html)

Functions
---
<a name="GetAngularVelocity"></a>
### simul::math::Vector3  const & GetAngularVelocity()
< Return the linear velocity.
<a name="GetLocalAngularVelocity"></a>
### simul::math::Vector3 GetLocalAngularVelocity()
< Return the angular velocity.
<a name="LocalPositionToGlobalVelocity"></a>
### void LocalPositionToGlobalVelocity(simul::math::Vector3 ve, simul::math::Vector3 xl)
< From a global position of a point in this frame, return the global velocity.
<a name="operator="></a>
### void operator=(simul::geometry::SimulOrientation o)




<a name="PositionToVelocity"></a>
### void PositionToVelocity(simul::math::Vector3 ve, simul::math::Vector3 xe)
< Return the angular velocity in local co-ordinates.
