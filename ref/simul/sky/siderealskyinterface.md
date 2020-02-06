---
title: SiderealSkyInterface
layout: reference
weight: 0
---
class SiderealSkyInterface
===

| Include: | Sky/BaseSkyRenderer.h |



Functions
---

| void | [GetSunPosition](#GetSunPosition)(float azimuth, float elevation, double epoch_time, float latitude, float longitude) |
| float  const * | [SiderealToEarthMatrix](#SiderealToEarthMatrix)(double epoch_time, float latitude, float longitude) |


Functions
---
<a name="GetSunPosition"></a>
### void GetSunPosition(float azimuth, float elevation, double epoch_time, float latitude, float longitude)
An abstract interface class for a sky that is calculated using sidereal data.
<a name="SiderealToEarthMatrix"></a>
### float  const * SiderealToEarthMatrix(double epoch_time, float latitude, float longitude)
Get a 4x4 transformation matrix to transform sidereal coordinates into azimuth and elevation.
