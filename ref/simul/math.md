---
title: math
layout: reference
weight: 0
---
namespace math
===

| Include: | Math/GeometricFunctions.h |



Classes and Structures
---

| class [Matrix](math/matrix) | A Matrix class.<br> |
| class [Matrix4x4](math/matrix4x4) |  |
| class [Noise1D](math/noise1d) |  |
| class [Noise2D](math/noise2d) |  |
| class [Noise3D](math/noise3d) |  |
| class [VirtualVector](math/virtualvector) |  |

Functions
---

| void | [CrossProduct](#CrossProduct)(simul::math::Vector3 result, simul::math::Vector3 v1, simul::math::Vector3 v2) |
| float | [DotProduct3](#DotProduct3)(simul::math::Vector3 v1, simul::math::Vector3 v2) |
| void | [FirstOrderDecay](#FirstOrderDecay)(float variable, float target, float rate, float dt) |
| std::ostream  & | [operator<<](#operator<<)(std::ostream, simul::math::Vector3) |
| std::istream  & | [operator>>](#operator>>)(std::istream, simul::math::Vector3) |


Functions
---

### <a name="CrossProduct"/>void CrossProduct(simul::math::Vector3 result, simul::math::Vector3 v1, simul::math::Vector3 v2)
Catmull-Rom interpolate with parameter talong a spline formed by vectors x0, x1, x2and x3.

### <a name="DotProduct3"/>float DotProduct3(simul::math::Vector3 v1, simul::math::Vector3 v2)
Linearly interpolate between two vectors.

### <a name="FirstOrderDecay"/>void FirstOrderDecay(float variable, float target, float rate, float dt)
Apply a first-order decay to a float variable, based on the timestep dt.

### <a name="operator<<"/>std::ostream  & operator<<(std::ostream, simul::math::Vector3)
The smallest x y and z of two vectors.

### <a name="operator>>"/>std::istream  & operator>>(std::istream, simul::math::Vector3)
The largest x y and z of two vectors.
