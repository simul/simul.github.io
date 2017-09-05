---
title: math
layout: reference
weight: 0
---
namespace math
===

| Include: | Math/Decay.h |

Math is the mathematics library for Simul. It contains Vector, Matrix and<br>Quaternion classes, vector-matrix, vector-quat and matrix-quat functions,<br>and some low-level maths functions.<br>


Classes and Structures
---

| class [Matrix](math/Matrix) |  Matrix class.<br> |
| class [Matrix4x4](math/Matrix4x4) | A fixed-size 4 by 4 matrix class.<br>It is used mainly for transformations - see SimulOrientation. |
| class [Noise1D](math/Noise1D) | A 3D Perlin noise class. |
| class [Noise2D](math/Noise2D) | A 3D Perlin noise class. |
| class [Noise3D](math/Noise3D) | A 3D Perlin noise class. |
| class [Quaternion](math/Quaternion) | Quaternion class to represent rotations. |
| class [Vector](math/Vector) | A resizeable vector class |
| class [Vector3](math/Vector3) | A 3-element vector class |
| class [VirtualVector](math/VirtualVector) | VirtualVector is derived from Vector but does not manage its own data. Instead<br>the #PointTo method is used to give vector functionality to floating point data<br>anywhere in memory (as long as any alignment conditions are satisfied.) |

Functions
---

| void | [FirstOrderDecay](#FirstOrderDecay)(float variable, float target, float rate, float dt) |

Static library: (SIMUL)/lib/(PLATFORM)/(COMPILER)/(ConfigurationName)/SimulMath_(RUNTIME).lib

Dynamic library: (SIMUL)/exe/(PLATFORM)/(COMPILER)/(ConfigurationName)/SimulBase_(RUNTIME).dll

The Math library depends on the Simul/Base library.
  


Functions
---

### <a name="FirstOrderDecay"/>void FirstOrderDecay(float variable, float target, float rate, float dt)
Apply a first-order decay to a float variable, based on the timestep dt.
Apply a first-order decay to a float variable, based on the timestep dt.
