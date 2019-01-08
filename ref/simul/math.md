---
title: math
layout: reference
weight: 0
---
namespace math
===

| Include: | Math/Decay.h |

Math is the mathematics library for Simul. It contains Vector, Matrix and
Quaternion classes, vector-matrix, vector-quat and matrix-quat functions,
and some low-level maths functions.

Static library: (SIMUL)/lib/(PLATFORM)/(COMPILER)/(ConfigurationName)/SimulMath_(RUNTIME).lib

Dynamic library: (SIMUL)/exe/(PLATFORM)/(COMPILER)/(ConfigurationName)/SimulBase_(RUNTIME).dll

The Math library depends on the Simul/Base library.
  


Classes and Structures
---

| class [Matrix](math/matrix) | A Matrix class.<br> |
| class [Matrix4x4](math/matrix4x4) |  |
| class [Noise1D](math/noise1d) |  |
| class [Noise2D](math/noise2d) |  |
| class [Noise3D](math/noise3d) |  |
| class [Quaternion](math/quaternion) |  |
| class [Vector](math/vector) |  |
| class [Vector3](math/vector3) |  |
| class [VirtualVector](math/virtualvector) |  |

Functions
---

| void | [CrossProduct](#CrossProduct)(simul::math::Vector3 result, simul::math::Vector3 v1, simul::math::Vector3 v2) |
| float | [DotProduct3](#DotProduct3)(simul::math::Vector3 v1, simul::math::Vector3 v2) |
| void | [FirstOrderDecay](#FirstOrderDecay)(float variable, float target, float rate, float dt) |
| void | [MatrixToQuaternion](#MatrixToQuaternion)(simul::math::Quaternion q, simul::math::Matrix4x4 m) |
| std::ostream  & | [operator<<](#operator<<)(std::ostream, simul::math::Vector3) |
| std::istream  & | [operator>>](#operator>>)(std::istream, simul::math::Vector3) |

Math is the mathematics library for Simul. It contains Vector, Matrix and
Quaternion classes, vector-matrix, vector-quat and matrix-quat functions,
and some low-level maths functions.

Static library: (SIMUL)/lib/(PLATFORM)/(COMPILER)/(ConfigurationName)/SimulMath_(RUNTIME).lib

Dynamic library: (SIMUL)/exe/(PLATFORM)/(COMPILER)/(ConfigurationName)/SimulBase_(RUNTIME).dll

The Math library depends on the Simul/Base library.
  


Functions
---

### <a name="CrossProduct"/>void CrossProduct(simul::math::Vector3 result, simul::math::Vector3 v1, simul::math::Vector3 v2)
Catmull-Rom interpolate with parameter talong a spline formed by vectors x0, x1, x2and x3.

### <a name="DotProduct3"/>float DotProduct3(simul::math::Vector3 v1, simul::math::Vector3 v2)
Linearly interpolate between two vectors.

### <a name="FirstOrderDecay"/>void FirstOrderDecay(float variable, float target, float rate, float dt)
Apply a first-order decay to a float variable, based on the timestep dt.

### <a name="MatrixToQuaternion"/>void MatrixToQuaternion(simul::math::Quaternion q, simul::math::Matrix4x4 m)
Assign q to be the Quaternion equivalent to rotation Matrix M. M must be 3 by 3.

### <a name="operator<<"/>std::ostream  & operator<<(std::ostream, simul::math::Vector3)
The smallest x y and z of two vectors.

### <a name="operator>>"/>std::istream  & operator>>(std::istream, simul::math::Vector3)
The largest x y and z of two vectors.
