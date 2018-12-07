---
title: Sky
layout: reference
weight: 0
---
class Sky
===

| Include: | Sky/BaseSkyRenderer.h |

Sky tracks the time of day, time of year, and viewing location in order to
calculate the relative position of the sun in the sky and hence the lighting.
If you set the year, it can even calculate the position of the moon.
TimeStep() advances the time of day, or you can use SetTime(), or SetHourOfTheDay().

There are three components to an atmosphere in a Simul sky. Most of the colour is determined by the
air density, which is a fixed function of altitude. The air scatters light with Rayleigh scattering, which has three
colour components. You can adjust this scattering using SetDefaultRayleigh(). This value is multiplied
by the density scale to get the final Rayleigh scattering coefficients ( use GetRayleigh() ).

There may also be haze, usually concentrated toward the ground. Haze scatters light differently to air,
it performs Mie scattering, which has a different angular dependence to Rayleigh scattering.

The sky may be overcast, in which case less light reaches the lower altitudes. To achieve this effect, use
SetOvercast(), SetOvercastBaseKm(), and SetOvercastRangeKm() with values obtained from the cloud node.

Finally, Ozone may be present at higher altitudes. Use SetOzoneLevel() to define the amount of ozone (default 0.001),
and SetOzoneLayerAltitude() to determine the altitude where it peaks, in km (default 22km).

The properties of PlanetRadius, AtmosphereThickness and LookupTableSize are generally set only once, or left at their defaults, as
any change will cause a recalculation of the lookup tables. The same goes for Density, which is the ratio of atmospheric density
at sea level to the standard Earth atmosphere.

Other permanent properties can be changed without recalculating the lookups, although it is best to do so infrequently. These include

The MieEccentricity is a value that affects how strongly Mie-scattered light through haze is dispersed. If eccentricity is high (close to 1),
the scattering is preferentially forward, leading to a glow around the sun, whereas if it is low, the haze is distributed more evenly.

  

[simul::sky::BaseSky]()

Functions
---

| float | [GetMoonIrradianceFactor](#GetMoonIrradianceFactor)(vec3 dir_to_moon, vec3 dir_to_sun) |
| float | [GetOpticalLength](#GetOpticalLength)(float Elevation, float h_km) |
| float | [GetOzoneOpticalLength](#GetOzoneOpticalLength)(float Elevation, float h_km) |
| unsigned int | [GetTablesChecksum](#GetTablesChecksum)() |

Sky tracks the time of day, time of year, and viewing location in order to
calculate the relative position of the sun in the sky and hence the lighting.
If you set the year, it can even calculate the position of the moon.
TimeStep() advances the time of day, or you can use SetTime(), or SetHourOfTheDay().

There are three components to an atmosphere in a Simul sky. Most of the colour is determined by the
air density, which is a fixed function of altitude. The air scatters light with Rayleigh scattering, which has three
colour components. You can adjust this scattering using SetDefaultRayleigh(). This value is multiplied
by the density scale to get the final Rayleigh scattering coefficients ( use GetRayleigh() ).

There may also be haze, usually concentrated toward the ground. Haze scatters light differently to air,
it performs Mie scattering, which has a different angular dependence to Rayleigh scattering.

The sky may be overcast, in which case less light reaches the lower altitudes. To achieve this effect, use
SetOvercast(), SetOvercastBaseKm(), and SetOvercastRangeKm() with values obtained from the cloud node.

Finally, Ozone may be present at higher altitudes. Use SetOzoneLevel() to define the amount of ozone (default 0.001),
and SetOzoneLayerAltitude() to determine the altitude where it peaks, in km (default 22km).

The properties of PlanetRadius, AtmosphereThickness and LookupTableSize are generally set only once, or left at their defaults, as
any change will cause a recalculation of the lookup tables. The same goes for Density, which is the ratio of atmospheric density
at sea level to the standard Earth atmosphere.

Other permanent properties can be changed without recalculating the lookups, although it is best to do so infrequently. These include

The MieEccentricity is a value that affects how strongly Mie-scattered light through haze is dispersed. If eccentricity is high (close to 1),
the scattering is preferentially forward, leading to a glow around the sun, whereas if it is low, the haze is distributed more evenly.

  


Base Classes
---
[simul::sky::BaseSky]()

Functions
---

### <a name="GetMoonIrradianceFactor"/>float GetMoonIrradianceFactor(vec3 dir_to_moon, vec3 dir_to_sun)
Moon irradiance as a multiple of sun irradiance.

### <a name="GetOpticalLength"/>float GetOpticalLength(float Elevation, float h_km)
Get the effective optical length (equivalent length at sea level density) of a ray


### <a name="GetOzoneOpticalLength"/>float GetOzoneOpticalLength(float Elevation, float h_km)

### <a name="GetTablesChecksum"/>unsigned int GetTablesChecksum()
A checksum that changes any time the density, optical depth or blackbody table is recalculated.

Fields
---

Enums
---

**siderealSky**  The namespace and library for Simul sky functionality.
