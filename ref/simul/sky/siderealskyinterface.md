---
title: SiderealSkyInterface
layout: reference
weight: 0
---
class SiderealSkyInterface
===

| Include: | Sky/BaseSkyRenderer.h |

An abstract interface class for a sky that is calculated using sidereal data.
  


Functions
---

| void | [GetSunPosition](#GetSunPosition)(float azimuth, float elevation, double epoch_time, float latitude, float longitude) |
| float  const * | [SiderealToEarthMatrix](#SiderealToEarthMatrix)(double epoch_time, float latitude, float longitude) |

An abstract interface class for a sky that is calculated using sidereal data.
  


Functions
---

### <a name="GetSunPosition"/>void GetSunPosition(float azimuth, float elevation, double epoch_time, float latitude, float longitude)
< The shortest distance from the viewer TO the terminator, which will be in the direction TO the sun.

### <a name="SiderealToEarthMatrix"/>float  const * SiderealToEarthMatrix(double epoch_time, float latitude, float longitude)
Get a 4x4 transformation matrix to transform sidereal coordinates into azimuth and elevation.
