---
title: Stars
layout: reference
weight: 0
---
class Stars
===

| Include: | Sky/Stars.h |

A class that stores star positions by declination, ascension and magnitude.
  


Functions
---

| int | [GetNumStars](#GetNumStars)() |
| int | [GetNumVisibleStars](#GetNumVisibleStars)() |
| simul::sky::Star  const & | [GetStar](#GetStar)(int i) |
| simul::sky::Star  const & | [GetVisibleStar](#GetVisibleStar)(int i) |
| void | [UseDefaultStars](#UseDefaultStars)() |
| void | [UseUrsaMajor](#UseUrsaMajor)(float max_magnitude) |

A class that stores star positions by declination, ascension and magnitude.
  


Functions
---
<a name="GetNumStars"></a>
### int GetNumStars()
Get the total number of stars
<a name="GetNumVisibleStars"></a>
### int GetNumVisibleStars()
Get the total number of visible stars
<a name="GetStar"></a>
### simul::sky::Star  const & GetStar(int i)
Get a star from the complete list
<a name="GetVisibleStar"></a>
### simul::sky::Star  const & GetVisibleStar(int i)
Get a star from the currently visible list
<a name="UseDefaultStars"></a>
### void UseDefaultStars()
Initialize the stars with the default stars - the stars seen from Earth.
<a name="UseUrsaMajor"></a>
### void UseUrsaMajor(float max_magnitude)
Initialize the stars with only Ursa Major as seen from Earth. Useful for testing ephemerides.
