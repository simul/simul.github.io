---
title: geometry
layout: reference
weight: 0
---
namespace geometry
===

| Include: | Geometry/Geometry.h |

Geometry is a small library that contains orientation and reference frame classes.<br>


Classes and Structures
---

| class [SimulOrientation](geometry/SimulOrientation) | The orientation holds position and rotation.<br>Position is a vector which can be accessed using #GetPosition().<br>Rotation is stored as a quaternion q.<br>To transform use #LocalToGlobalPosition, #GlobalToLocalPosition,<br>#LocalToGlobalDirection and #GlobalToLocalDirection. |
| class [SimulReferenceFrame](geometry/SimulReferenceFrame) | The reference frame holds position, rotation, and linear and angular velocity.<br>Velocity is a simul::math::Vector3 which can be accessed using #GetVelocity().<br>Angular velocity is a simul::math::Vector3 which can be accessed using #GetAngularVelocity(). |


The main classes are simul::geometry::SimulOrientation and simul::geometry::SimulReferenceFrame.

Static library: (SIMUL)/lib/(PLATFORM)/(COMPILER)/(ConfigurationName)/Geometry_(RUNTIME).lib

Dynamic library: (SIMUL)/exe/(PLATFORM)/(COMPILER)/(ConfigurationName)/Geometry_(RUNTIME).dll

The Geometry library depends on the Simul/Math and Simul/Base libraries.
  

