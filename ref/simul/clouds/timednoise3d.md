---
title: TimedNoise3D
layout: reference
weight: 0
---
class TimedNoise3D
===

| Include: | Clouds/TimedNoise3D.h |

A 3D noise generator used for cloud volumes, where the value returned depends on normalized spatial co-ordinates, and on normalized time.
  

[simul::math::Noise3D](../math/noise3d)

Functions
---

| void | [SetTime](#SetTime)(float t) |

A 3D noise generator used for cloud volumes, where the value returned depends on normalized spatial co-ordinates, and on normalized time.
  


Base Classes
---
[simul::math::Noise3D](../math/noise3d)

Functions
---

### <a name="SetTime"/>void SetTime(float t)
Set the current time value for noise lookups (normalized to have a period of one).
