---
title: Sky
layout: reference
weight: 0
---
class Sky
===

| Include: | Sky/BaseSkyRenderer.h |


[simul::sky::BaseSky](/ref/simul/sky/basesky.html)

Functions
---

|  | [Sky](#Sky)(simul::base::MemoryInterface mem) |
| vec3 | [GetDirectionToMoon](#GetDirectionToMoon)(double epoch_time, float latitude, float longitude) |
| vec3 | [GetDirectionToSun](#GetDirectionToSun)(double epoch_time, float latitude, float longitude) |
| float | [GetMoonIrradianceFactor](#GetMoonIrradianceFactor)(vec3 dir_to_moon, vec3 dir_to_sun) |
| float | [GetOpticalLength](#GetOpticalLength)(float Elevation, float h_km) |
| float | [GetOzoneOpticalLength](#GetOzoneOpticalLength)(float Elevation, float h_km) |
| unsigned int | [GetTablesChecksum](#GetTablesChecksum)() |


Base Classes
---
[simul::sky::BaseSky](/ref/simul/sky/basesky.html)

Functions
---
<a name="Sky"></a>
###  Sky(simul::base::MemoryInterface mem)
The namespace and library for Simul sky functionality.
<a name="GetDirectionToMoon"></a>
### vec3 GetDirectionToMoon(double epoch_time, float latitude, float longitude)
Get the direction the moon represented as a vector
<a name="GetDirectionToSun"></a>
### vec3 GetDirectionToSun(double epoch_time, float latitude, float longitude)
Get the direction the sun represented as a vector
<a name="GetMoonIrradianceFactor"></a>
### float GetMoonIrradianceFactor(vec3 dir_to_moon, vec3 dir_to_sun)
Moon irradiance as a multiple of sun irradiance.
<a name="GetOpticalLength"></a>
### float GetOpticalLength(float Elevation, float h_km)
Get the effective optical length (equivalent length at sea level density) of a ray
cast from altitude h_kmat angle Elevationabove the horizon.
<a name="GetOzoneOpticalLength"></a>
### float GetOzoneOpticalLength(float Elevation, float h_km)
Get the effective optical length of ozone of a ray cast from altitude h_kmat angle Elevationabove the horizon.
<a name="GetTablesChecksum"></a>
### unsigned int GetTablesChecksum()
A checksum that changes any time the density, optical depth or blackbody table is recalculated.

Fields
---

Enums
---

**siderealSky**  Sky tracks the time of day, time of year, and viewing location in order to
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
![](/Images/eccentricity_low.png)

![](/Images/eccentricity_high.png)


Sky calculation is performed with ray-tracing, and the number of ray-trace steps is set using [simul::Sky::SetSteps](/ref/simul/sky/setsteps)
.
Typically 6 steps are enough, but more may be necessary for high-accuracy, especially when the sun is close to the horizon, such as in this case,
where the number of steps is too low, leading to an over-bright effect on the ground below the sun:
![](/Images/sky_steps_too_low.png)


transient_atmospheric_properties Transient Sky Properties

The main factor that changes over time in the sky is the Daytime property, between zero and one. This change can be handled by the
Sky Keyframer, which effectively performs the function of a keyframer for the sky. The Sky Keyframer will also adjust the sky's
Overcast property, a measure of how much the clouds block sunlight from reaching the lower atmosphere. The associated properties
of OvercastBaseKm and OvercastRangeKm set a base altitude and range in kilometres, at the base altitude, the full overcast
value is applied, while above the top of the overcast range, there is no loss of light.

The haze value determines how much Mie-scattered haze (i.e. mist or fog) is present. Haze is considered to have a density that falls-off
exponentially with altitude, so the HazeScaleHeightKm property determines the scaling height for this exponential. The
HazeBaseHeightKm is also used, below this height, full haze is applied.

Fog and mist are both effectively low-level clouds. Fog is defined as having visibility less than 1km, it is called mist when visibility
is between 1 and 2 km.

As time passes and the sun moves, you can use GetAzimuthToSunRadians and GetElevationToSunRadians to find its position.
The functions GetDirectionToSun and GetDirectionToMoon can also be used.
