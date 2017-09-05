---
title: SiderealSky
layout: reference
weight: 0
---
class SiderealSky
===

| Include: | Sky/SiderealSky.h |

A class that calculates the positions of sun, moon and stars.

[simul::sky::SiderealSkyInterface](SiderealSkyInterface)

Functions
---

| int | [DaysInTheYear](#DaysInTheYear)(int y) |
| void | [GetDate](#GetDate)(int y, int M, int D, int day_of_the_year) |
| double | [GetDayNumberFromDate](#GetDayNumberFromDate)(int year, int month, int day) |

A class that calculates the positions of sun, moon and stars.
  


Base Classes
---
[simul::sky::SiderealSkyInterface](SiderealSkyInterface)

Functions
---

### <a name="DaysInTheYear"/>int DaysInTheYear(int y)
How many days in the specified year.
How many days in the specified year.

### <a name="GetDate"/>void GetDate(int y, int M, int D, int day_of_the_year)
Get the month and day.
Get the month and day.

### <a name="GetDayNumberFromDate"/>double GetDayNumberFromDate(int year, int month, int day)
Convert year, month and day into a Julian Day Number.
Convert year, month and day into a Julian Day Number.
