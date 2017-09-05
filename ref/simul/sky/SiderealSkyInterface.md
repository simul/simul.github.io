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

| float  const * | [SiderealToEarthMatrix](#SiderealToEarthMatrix)(double epoch_time, float latitude, float longitude) |

An abstract interface class for a sky that is calculated using sidereal data.
  


Functions
---

### <a name="SiderealToEarthMatrix"/>float  const * SiderealToEarthMatrix(double epoch_time, float latitude, float longitude)
Get a 4x4 transformation matrix to transform sidereal coordinates into azimuth and elevation.
Get a 4x4 transformation matrix to transform sidereal coordinates into azimuth and elevation.
