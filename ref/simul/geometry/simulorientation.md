---
title: SimulOrientation
layout: reference
weight: 0
---
class SimulOrientation
===

| Include: | Geometry/Orientation.h |

The orientation holds position and rotation.
Position is a vector which can be accessed using #GetPosition().
Rotation is stored as a quaternion q.
To transform use #LocalToGlobalPosition, #GlobalToLocalPosition,
#LocalToGlobalDirection and #GlobalToLocalDirection.
  


Functions
---

| void | [Define](#Define)(simul::math::Quaternion s) |
| void | [DefineFromAircraftEuler](#DefineFromAircraftEuler)(float a, float b, float c, int vertical_axis) |
| void | [GlobalToLocalDirection](#GlobalToLocalDirection)(simul::math::Vector3 xl, simul::math::Vector3 xg) |
| void | [GlobalToLocalPosition](#GlobalToLocalPosition)(simul::math::Vector3 xl, simul::math::Vector3 xg) |
| void | [LocalMove](#LocalMove)(simul::math::Vector3 offset) |
| void | [LocalRotate](#LocalRotate)(float angle, simul::math::Vector3 axis) |
| void | [LocalRotate](#LocalRotate)(simul::math::Vector3 dir_sin) |
| void | [LocalToGlobalDirection](#LocalToGlobalDirection)(simul::math::Vector3 dg, simul::math::Vector3 dl) |
| void | [LocalToGlobalPosition](#LocalToGlobalPosition)(simul::math::Vector3 xg, simul::math::Vector3 xl) |
| void | [LocalTranslate](#LocalTranslate)(simul::math::Vector3 DX) |
| void | [Move](#Move)(simul::math::Vector3 offset) |
| void | [QuaternionFromClassical](#QuaternionFromClassical)(float a, float b, float c) |
| void | [Rotate](#Rotate)(float angle, simul::math::Vector3 axis) |
| void | [RotateLinear](#RotateLinear)(float angle, simul::math::Vector3 axis) |
| void | [SetPosition](#SetPosition)(simul::math::Vector3 X) |
| void | [Translate](#Translate)(simul::math::Vector3 DX) |
| simul::math::Vector3  const & | [Tx](#Tx)() |
| simul::math::Vector3  const & | [Ty](#Ty)() |
| simul::math::Vector3  const & | [Tz](#Tz)() |
| void | [y](#y)(simul::math::Vector3 Y) |
| void | [z](#z)(simul::math::Vector3 Z) |

The orientation holds position and rotation.
Position is a vector which can be accessed using #GetPosition().
Rotation is stored as a quaternion q.
To transform use #LocalToGlobalPosition, #GlobalToLocalPosition,
#LocalToGlobalDirection and #GlobalToLocalDirection.
  


Functions
---
<a name="Define"></a>
### void Define(simul::math::Quaternion s)
< Rotate the orientation approximately angle radians about the global axis, axis.
<a name="DefineFromAircraftEuler"></a>
### void DefineFromAircraftEuler(float a, float b, float c, int vertical_axis)
< Move the position in global co-ordinates by DX.
<a name="GlobalToLocalDirection"></a>
### void GlobalToLocalDirection(simul::math::Vector3 xl, simul::math::Vector3 xg)
Transform a direction from global to local co-ordinates.
<a name="GlobalToLocalPosition"></a>
### void GlobalToLocalPosition(simul::math::Vector3 xl, simul::math::Vector3 xg)
Transform a position from global to local co-ordinates.
<a name="LocalMove"></a>
### void LocalMove(simul::math::Vector3 offset)
< Move the orientation by offsetin global co-ordinates.
<a name="LocalRotate"></a>
### void LocalRotate(float angle, simul::math::Vector3 axis)
< Rotate the orientation by angleradians about the global axis, axis.
<a name="LocalRotate"></a>
### void LocalRotate(simul::math::Vector3 dir_sin)
< Rotate the orientation by angleradians about the local axis, axis.
<a name="LocalToGlobalDirection"></a>
### void LocalToGlobalDirection(simul::math::Vector3 dg, simul::math::Vector3 dl)
Transform a local direction to a global one.
<a name="LocalToGlobalPosition"></a>
### void LocalToGlobalPosition(simul::math::Vector3 xg, simul::math::Vector3 xl)
Transform a position from local to global co-ordinates.
Note QuaternionToMatrix() is not called - must be certain that the matrix is valid
before using functions like this.
<a name="LocalTranslate"></a>
### void LocalTranslate(simul::math::Vector3 DX)
< Move the position in global co-ordinates by DX.
<a name="Move"></a>
### void Move(simul::math::Vector3 offset)
< Rotate the orientation by the angle whose sine is the magnitude of dir_sin, on the axis of its direction.
<a name="QuaternionFromClassical"></a>
### void QuaternionFromClassical(float a, float b, float c)
< Set rotation from the Aircraft Euler angles, yaw pitch and roll.
<a name="Rotate"></a>
### void Rotate(float angle, simul::math::Vector3 axis)
< Return the oriented z-axis.
<a name="RotateLinear"></a>
### void RotateLinear(float angle, simul::math::Vector3 axis)
< Move the orientation by offsetin local co-ordinates.
<a name="SetPosition"></a>
### void SetPosition(simul::math::Vector3 X)
< Get a reference to the position.
<a name="Translate"></a>
### void Translate(simul::math::Vector3 DX)
< Set the position in global co-ordinates to equal X.
<a name="Tx"></a>
### simul::math::Vector3  const & Tx()
< Put the oriented z-axis in vector Z.
<a name="Ty"></a>
### simul::math::Vector3  const & Ty()
< Return the oriented x-axis.
<a name="Tz"></a>
### simul::math::Vector3  const & Tz()
< Return the oriented y-axis.
<a name="y"></a>
### void y(simul::math::Vector3 Y)
< Put the oriented x-axis in vector X.
<a name="z"></a>
### void z(simul::math::Vector3 Z)
< Put the oriented y-axis in vector Y.
