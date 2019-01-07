---
title: OpticalLengthInterface
layout: reference
weight: 0
---
class OpticalLengthInterface
===

| Include: | Sky/SkyInterface.h |

An abstract interface class for skies that can calculate optical lengths.
  


Functions
---

| float | [GetHazeFactorOpticalLength](#GetHazeFactorOpticalLength)(float Elevation, float h_km, simul::sky::HazeStruct hazeStruct) |
| float | [GetOpticalLength](#GetOpticalLength)(float Elevation, float h_km) |
| float | [GetOzoneOpticalLength](#GetOzoneOpticalLength)(float Elevation, float h_km) |

An abstract interface class for skies that can calculate optical lengths.
  


Functions
---

### <a name="GetHazeFactorOpticalLength"/>float GetHazeFactorOpticalLength(float Elevation, float h_km, simul::sky::HazeStruct hazeStruct)
Get the effective optical length of haze of a ray cast from altitude \a
h_km at angle \a Elevation above the horizon.

### <a name="GetOpticalLength"/>float GetOpticalLength(float Elevation, float h_km)
Get the effective optical length (equivalent length at sea level density) of a ray
cast from altitude \a h_km at angle \a Elevation above the horizon.

### <a name="GetOzoneOpticalLength"/>float GetOzoneOpticalLength(float Elevation, float h_km)
Get the effective optical length of ozone of a ray cast from altitude \a
h_km at angle \a Elevation above the horizon.
