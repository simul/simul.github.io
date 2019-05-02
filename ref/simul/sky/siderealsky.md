---
title: SiderealSky
layout: reference
weight: 0
---
class SiderealSky
===

| Include: | Sky/SiderealSky.h |

A class that calculates the positions of sun, moon and stars.
  

[simul::sky::SiderealSkyInterface](siderealskyinterface)

Functions
---

| int | [DaysInTheYear](#DaysInTheYear)(int y) |
| void | [GetDate](#GetDate)(int y, int M, int D, int day_of_the_year) |
| double | [GetDayNumberFromDate](#GetDayNumberFromDate)(int year, int month, int day) |
| void | [GetMoonPosition](#GetMoonPosition)(float azimuth, float elevation, double epoch_time, float latitude, float longitude) |
| void | [GetSunPosition](#GetSunPosition)(float azimuth, float elevation, double epoch_time, float latitude, float longitude) |

A class that calculates the positions of sun, moon and stars.
  


Base Classes
---
[simul::sky::SiderealSkyInterface](siderealskyinterface)

Functions
---

### <a name="DaysInTheYear"/>int DaysInTheYear(int y)
How many days in the specified year.

### <a name="GetDate"/>void GetDate(int y, int M, int D, int day_of_the_year)
Get the month and day.

### <a name="GetDayNumberFromDate"/>double GetDayNumberFromDate(int year, int month, int day)
Convert year, month and day into a Julian Day Number.

### <a name="GetMoonPosition"/>void GetMoonPosition(float azimuth, float elevation, double epoch_time, float latitude, float longitude)
Get the position of the moon in the sky with regards to its Azimuth and Elevation

### <a name="GetSunPosition"/>void GetSunPosition(float azimuth, float elevation, double epoch_time, float latitude, float longitude)
Get the position of the sun in the sky with regards to its Azimuth and Elevation
