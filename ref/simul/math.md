---
title: math
layout: reference
weight: 0
---
namespace math
===

| Include: | Math/Decay.h |



Classes and Structures
---

| class [Matrix](math/matrix) | A Matrix class.<br> |
| class [Noise1D](math/noise1d) |  |
| class [Noise2D](math/noise2d) |  |
| class [Noise3D](math/noise3d) |  |
| class [VirtualVector](math/virtualvector) |  |

Functions
---

| void | [AddDoublePrecross](#AddDoublePrecross)(simul::math::Matrix4x4 M, float f, simul::math::Vector3 v) |
| void | [CrossProduct](#CrossProduct)(simul::math::Vector3 result, simul::math::Vector3 v1, simul::math::Vector3 v2) |
| float | [DotProduct3](#DotProduct3)(simul::math::Vector3 v1, simul::math::Vector3 v2) |
| void | [FirstOrderDecay](#FirstOrderDecay)(float variable, float target, float rate, float dt) |
| void | [MatrixToQuaternion](#MatrixToQuaternion)(simul::math::Quaternion q, simul::math::Matrix4x4 M) |
| void | [Multiply3](#Multiply3)(simul::math::Vector3 V2, simul::math::Matrix4x4 M, simul::math::Vector3 V1) |
| void | [MultiplyAndAdd](#MultiplyAndAdd)(simul::math::Vector3 V2, simul::math::Matrix4x4 M, simul::math::Vector3 V1) |
| void | [MultiplyAndSubtract](#MultiplyAndSubtract)(simul::math::Vector3 V2, simul::math::Matrix4x4 M, simul::math::Vector3 V1) |
| std::ostream  & | [operator<<](#operator<<)(std::ostream, simul::math::Vector3) |
| std::istream  & | [operator>>](#operator>>)(std::istream, simul::math::Vector3) |
| void | [Precross](#Precross)(simul::math::Matrix4x4 M, simul::math::Vector3 v) |
| void | [SubtractDoublePrecross](#SubtractDoublePrecross)(simul::math::Matrix4x4 M, float f, simul::math::Vector3 v) |


Functions
---

### <a name="AddDoublePrecross"/>void AddDoublePrecross(simul::math::Matrix4x4 M, float f, simul::math::Vector3 v)
< Make a unit matrix.

### <a name="CrossProduct"/>void CrossProduct(simul::math::Vector3 result, simul::math::Vector3 v1, simul::math::Vector3 v2)
Catmull-Rom interpolate with parameter talong a spline formed by vectors x0, x1, x2and x3.

### <a name="DotProduct3"/>float DotProduct3(simul::math::Vector3 v1, simul::math::Vector3 v2)
Linearly interpolate between two vectors.

### <a name="FirstOrderDecay"/>void FirstOrderDecay(float variable, float target, float rate, float dt)
Apply a first-order decay to a float variable, based on the timestep dt.

### <a name="MatrixToQuaternion"/>void MatrixToQuaternion(simul::math::Quaternion q, simul::math::Matrix4x4 M)
Assign q to be the Quaternion equivalent to rotation Matrix M. M must be 3 by 3.

### <a name="Multiply3"/>void Multiply3(simul::math::Vector3 V2, simul::math::Matrix4x4 M, simul::math::Vector3 V1)
Simply exchange the Y and Z values of a transformation matrix.

### <a name="MultiplyAndAdd"/>void MultiplyAndAdd(simul::math::Vector3 V2, simul::math::Matrix4x4 M, simul::math::Vector3 V1)
< Set the 16 values.

### <a name="MultiplyAndSubtract"/>void MultiplyAndSubtract(simul::math::Vector3 V2, simul::math::Matrix4x4 M, simul::math::Vector3 V1)
< Make a unit matrix.

### <a name="operator<<"/>std::ostream  & operator<<(std::ostream, simul::math::Vector3)
The smallest x y and z of two vectors.

### <a name="operator>>"/>std::istream  & operator>>(std::istream, simul::math::Vector3)
The largest x y and z of two vectors.

### <a name="Precross"/>void Precross(simul::math::Matrix4x4 M, simul::math::Vector3 v)
Reverse the Y values of a transformation matrix - i.e. multiply the off-diagonal terms of the second row and column by -1.

### <a name="SubtractDoublePrecross"/>void SubtractDoublePrecross(simul::math::Matrix4x4 M, float f, simul::math::Vector3 v)
< Set all values to zero.
