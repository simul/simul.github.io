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

| class [Noise1D](math/noise1d) |  |
| class [Noise2D](math/noise2d) |  |
| class [Noise3D](math/noise3d) |  |
| class [Quaternion](math/quaternion) |  |
| class [VirtualVector](math/virtualvector) |  |

Functions
---

| void | [CrossProduct](#CrossProduct)(simul::math::Vector3 result, simul::math::Vector3 v1, simul::math::Vector3 v2) |
| float | [DotProduct3](#DotProduct3)(simul::math::Vector3 v1, simul::math::Vector3 v2) |
| void | [MatrixToQuaternion](#MatrixToQuaternion)(simul::math::Quaternion q, simul::math::Matrix4x4 M) |
| std::ostream  & | [operator<<](#operator<<)(std::ostream, simul::math::Vector3) |
| std::istream  & | [operator>>](#operator>>)(std::istream, simul::math::Vector3) |


Functions
---

### <a name="CrossProduct"/>void CrossProduct(simul::math::Vector3 result, simul::math::Vector3 v1, simul::math::Vector3 v2)
Catmull-Rom interpolate with parameter talong a spline formed by vectors x0, x1, x2and x3.

### <a name="DotProduct3"/>float DotProduct3(simul::math::Vector3 v1, simul::math::Vector3 v2)
Linearly interpolate between two vectors.

### <a name="MatrixToQuaternion"/>void MatrixToQuaternion(simul::math::Quaternion q, simul::math::Matrix4x4 M)
Assign q to be the Quaternion equivalent to rotation Matrix M. M must be 3 by 3.

### <a name="operator<<"/>std::ostream  & operator<<(std::ostream, simul::math::Vector3)
The smallest x y and z of two vectors.

### <a name="operator>>"/>std::istream  & operator>>(std::istream, simul::math::Vector3)
The largest x y and z of two vectors.
