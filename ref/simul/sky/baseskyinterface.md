---
title: BaseSkyInterface
layout: reference
weight: 0
---
class BaseSkyInterface
===

| Include: | Sky/SkyInterface.h |

An abstract interface class for skies.
  


Functions
---

| simul::sky::float4 | [GetAmbientLight](#GetAmbientLight)(float altitude_km) |
| vec3 | [GetDirectionToLight](#GetDirectionToLight)(double t, float altitude_km) |
| vec3 | [GetDirectionToLight](#GetDirectionToLight)(float altitude_km) |
| vec3 | [GetDirectionToMoon](#GetDirectionToMoon)() |
| vec3 | [GetDirectionToMoon](#GetDirectionToMoon)(double t) |
| vec3 | [GetDirectionToSun](#GetDirectionToSun)() |
| vec3 | [GetDirectionToSun](#GetDirectionToSun)(double t) |
| simul::sky::EarthShadow | [GetEarthShadow](#GetEarthShadow)(float h_km, vec3 lightDir) |
| float | [GetHazeForVisibilityDistance](#GetHazeForVisibilityDistance)(float view_alt_km, float horiz_dist_km) |
| float | [GetHorizonElevation](#GetHorizonElevation)(float h_km) |
| simul::sky::float4 | [GetInscatterAngularMultiplier](#GetInscatterAngularMultiplier)(float cosine, float mie_factor, float alt_km) |
| simul::sky::float4 | [GetLocalIrradiance](#GetLocalIrradiance)(float altitude_km) |
| vec3 | [GetLocalMoonIrradiance](#GetLocalMoonIrradiance)(double t, float altitude_km) |
| vec3 | [GetLocalSunIrradiance](#GetLocalSunIrradiance)(double t, float altitude_km) |
| simul::sky::float4 | [GetMieRayleighRatio](#GetMieRayleighRatio)() |
| unsigned int | [GetSubdivisionChecksum](#GetSubdivisionChecksum)() |
| vec2 | [GetSunlightTableTransformKm](#GetSunlightTableTransformKm)() |
| float | [GetVisibilityDistance](#GetVisibilityDistance)(float view_alt_km) |

An abstract interface class for skies.
  


Functions
---
<a name="GetAmbientLight"></a>
### simul::sky::float4 GetAmbientLight(float altitude_km)
Get the ambient light irradiance at the specified altitude.
<a name="GetDirectionToLight"></a>
### vec3 GetDirectionToLight(double t, float altitude_km)
Get the direction to the current strongest light source - could be the sun or the moon.
<a name="GetDirectionToLight"></a>
### vec3 GetDirectionToLight(float altitude_km)
Get the direction to the current strongest light source - could be the sun or the moon.
<a name="GetDirectionToMoon"></a>
### vec3 GetDirectionToMoon()
Get the current direction to the Moon.
<a name="GetDirectionToMoon"></a>
### vec3 GetDirectionToMoon(double t)
Get the direction to the Moon at the given time.
<a name="GetDirectionToSun"></a>
### vec3 GetDirectionToSun()
Get the current direction to the sun.
<a name="GetDirectionToSun"></a>
### vec3 GetDirectionToSun(double t)
Get the direction to the Sun at the given time.
<a name="GetEarthShadow"></a>
### simul::sky::EarthShadow GetEarthShadow(float h_km, vec3 lightDir)
The Earth's shadow, as seen from the given altitude.
<a name="GetHazeForVisibilityDistance"></a>
### float GetHazeForVisibilityDistance(float view_alt_km, float horiz_dist_km)
Get the haze that will produce the required visibility distance in the horizontal direction.
<a name="GetHorizonElevation"></a>
### float GetHorizonElevation(float h_km)
Get the horizon elevation from a given altitude.
<a name="GetInscatterAngularMultiplier"></a>
### simul::sky::float4 GetInscatterAngularMultiplier(float cosine, float mie_factor, float alt_km)
Get the multiplier for an inscatter factor that gives the total inscatter, where cosineis the cosine between
the angle to the sun and the ray direction, mie_factoris the proportional haze factor (stored int the w element of the inscatter factor)
and alt_kmis the viewing altitude in km.
<a name="GetLocalIrradiance"></a>
### simul::sky::float4 GetLocalIrradiance(float altitude_km)
Get the sunlight that reaches the altitude altitude_km.
<a name="GetLocalMoonIrradiance"></a>
### vec3 GetLocalMoonIrradiance(double t, float altitude_km)
Get the moonlight that reaches the altitude altitude_km.
<a name="GetLocalSunIrradiance"></a>
### vec3 GetLocalSunIrradiance(double t, float altitude_km)
Get the sunlight that reaches the altitude altitude_km.
<a name="GetMieRayleighRatio"></a>
### simul::sky::float4 GetMieRayleighRatio()
Get the ratio of Mie to Rayleigh scattering at unit air and haze density. A useful helper function as some shaders use this ratio.
<a name="GetSubdivisionChecksum"></a>
### unsigned int GetSubdivisionChecksum()
< Return the temperature at the stated altitude in kelvins (subtract 273.15 to get celsius).
When this checksum changes, the atmosphere has been modified sufficiently to warrant regeneration of tables.
<a name="GetSunlightTableTransformKm"></a>
### vec2 GetSunlightTableTransformKm()
Get the transform vector to convert an altitude in km into a 1D texture coordinate for the sunlight table. x = multiplier, y=offset, so texcoord u=t.x*zkm+t.y;
<a name="GetVisibilityDistance"></a>
### float GetVisibilityDistance(float view_alt_km)
From the altitude specified, the distance in km to 10% visibility (mainly a factor of fog/haze).
