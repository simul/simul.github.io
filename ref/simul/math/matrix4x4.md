---
title: Matrix4x4
layout: reference
weight: 0
---
class Matrix4x4
===

| Include: | Math/Matrix.h |

A fixed-size 4 by 4 matrix class.
It is used mainly for transformations - see SimulOrientation.
  


Functions
---

| simul::math::Matrix4x4 | [IdentityMatrix](#IdentityMatrix)() |
| void | [ResetToUnitMatrix](#ResetToUnitMatrix)() |
| void | [ReverseY](#ReverseY)(simul::math::Matrix4x4 dest) |
| void | [Set](#Set)(const float []) |
| void | [SwapYAndZ](#SwapYAndZ)(simul::math::Matrix4x4 dest) |
| bool | [SymmetricInverse3x3](#SymmetricInverse3x3)(simul::math::Matrix4x4 Result) |

A fixed-size 4 by 4 matrix class.
It is used mainly for transformations - see SimulOrientation.
  


Functions
---

### <a name="IdentityMatrix"/>simul::math::Matrix4x4 IdentityMatrix()
< Make a unit matrix.

### <a name="ResetToUnitMatrix"/>void ResetToUnitMatrix()
< Set all values to zero.

### <a name="ReverseY"/>void ReverseY(simul::math::Matrix4x4 dest)
Reverse the Y values of a transformation matrix - i.e. multiply the off-diagonal terms of the second row and column by -1.

### <a name="Set"/>void Set(const float [])
< Make a unit matrix.

### <a name="SwapYAndZ"/>void SwapYAndZ(simul::math::Matrix4x4 dest)
Simply exchange the Y and Z values of a transformation matrix.

### <a name="SymmetricInverse3x3"/>bool SymmetricInverse3x3(simul::math::Matrix4x4 Result)
< Set the 16 values.
