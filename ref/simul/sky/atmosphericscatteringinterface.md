---
title: AtmosphericScatteringInterface
layout: reference
weight: 0
---
class AtmosphericScatteringInterface
===

| Include: | Sky/BaseGpuSkyGenerator.h |



Functions
---

| simul::sky::float4 | [GetAnisotropicInscatterFactor](#GetAnisotropicInscatterFactor)(bool include_sunlight, float alt_km, float elevation, float min_dist_km, float max_dist_km, vec3 sun_irradiance, vec3 moon_albedo, simul::sky::float4 starlight, vec3 dir_to_sun, std::map moonDirections, simul::sky::HazeStruct hazeStruct, simul::sky::float4 wavelengthsNm, simul::sky::OvercastStruct overcast, bool earth_test, int steps) |
| simul::sky::float4 | [GetBlackbodyInscatter](#GetBlackbodyInscatter)(float alt_km, float elevation, float min_dist_km, float max_dist_km, vec3 sun_irradiance, vec3 moon_albedo, simul::sky::float4 starlight, vec3 dir_to_sun, std::map moonDirections, simul::sky::HazeStruct hazeStruct, simul::sky::float4 wavelengthsNm, bool earth_test, int steps, float emissivity) |
| simul::sky::float4 | [GetColourLossFactor](#GetColourLossFactor)(vec3 view_pos_km, vec3 pos_km, simul::sky::HazeStruct hazeStruct, bool earth_test, int steps) |
| vec3 | [GetDirectionToSun](#GetDirectionToSun)(double epoch_time, float latitude, float longitude) |
| float | [GetDistanceToEarth](#GetDistanceToEarth)(float Elevation, float h_km) |
| float | [GetDistanceToSpace](#GetDistanceToSpace)(float Elevation, float h_km) |
| simul::sky::EarthShadow | [GetEarthShadow](#GetEarthShadow)(float h_km, vec3 lightDir) |
| float | [GetHazeFactorAtAltitude](#GetHazeFactorAtAltitude)(float alt_km, simul::sky::HazeStruct hazeStruct) |
| float | [GetHazeForVisibilityDistance](#GetHazeForVisibilityDistance)(float view_alt_km, float horiz_dist_km, simul::sky::HazeStruct hazeStruct) |
| simul::sky::float4 | [GetInscatterAngularMultiplier](#GetInscatterAngularMultiplier)(float cosine, float mie_factor, simul::sky::HazeStruct hazeStruct) |
| simul::sky::float4 | [GetIsotropicColourLossFactor](#GetIsotropicColourLossFactor)(float alt_km, float elevation, float min_dist_km, float max_dist_km, simul::sky::HazeStruct hazeStruct, bool earth_test, int steps, bool blackbody, float emissivity) |
| simul::sky::float4 | [GetIsotropicInscatter](#GetIsotropicInscatter)(float alt_km, float elevation, float min_dist_km, float max_dist_km, vec3 sun_irradiance, vec3 moon_albedo, simul::sky::float4 starlight, vec3 dir_to_sun, std::map moonDirections, simul::sky::HazeStruct hazeStruct, simul::sky::float4 wavelengthsNm, simul::sky::OvercastStruct overcast, bool earth_test, int steps) |
| vec3 | [GetLocalMoonIrradianceFactor](#GetLocalMoonIrradianceFactor)(simul::sky::Moon m, float altitude_km, vec3 dir_to_moon, vec3 dir_to_sun, simul::sky::HazeStruct hazeStruct) |
| vec3 | [GetLocalSunIrradiance](#GetLocalSunIrradiance)(float altitude_km, vec3 sun_irradiance, vec3 dir_to_sun, simul::sky::HazeStruct hazeStruct) |
| float | [GetMoonIrradianceFactor](#GetMoonIrradianceFactor)(simul::sky::Moon m, vec3 dir_to_moon, vec3 dir_to_sun) |
| float | [GetOvercastAtAltitude](#GetOvercastAtAltitude)(simul::sky::OvercastStruct overcast, float alt_km) |
| float | [GetOzoneAtAltitude](#GetOzoneAtAltitude)(float alt_km) |
| float  const & | [GetPlanetRadius](#GetPlanetRadius)() |
| float | [GetVisibilityDistance](#GetVisibilityDistance)(float view_alt_km, simul::sky::HazeStruct hazeStruct) |
| void | [SetPlanetRadius](#SetPlanetRadius)(float value) |


Functions
---
<a name="GetAnisotropicInscatterFactor"></a>
### simul::sky::float4 GetAnisotropicInscatterFactor(bool include_sunlight, float alt_km, float elevation, float min_dist_km, float max_dist_km, vec3 sun_irradiance, vec3 moon_albedo, simul::sky::float4 starlight, vec3 dir_to_sun, std::map moonDirections, simul::sky::HazeStruct hazeStruct, simul::sky::float4 wavelengthsNm, simul::sky::OvercastStruct overcast, bool earth_test, int steps)
Get the inscatter factor in the xyz - the 3-element factor which is multiplied by the 3-element factor Beta to get the inscattered colour.
In the w element is the haze factor.
This excludes skylight and starlight, which are not considered to be strongly anisotropic. See GetIsotropicInscatter().
<a name="GetBlackbodyInscatter"></a>
### simul::sky::float4 GetBlackbodyInscatter(float alt_km, float elevation, float min_dist_km, float max_dist_km, vec3 sun_irradiance, vec3 moon_albedo, simul::sky::float4 starlight, vec3 dir_to_sun, std::map moonDirections, simul::sky::HazeStruct hazeStruct, simul::sky::float4 wavelengthsNm, bool earth_test, int steps, float emissivity)
Get the radiance due to blackbody radiation.
<a name="GetColourLossFactor"></a>
### simul::sky::float4 GetColourLossFactor(vec3 view_pos_km, vec3 pos_km, simul::sky::HazeStruct hazeStruct, bool earth_test, int steps)
When an object has initial colour c, multiply each member of cby the corresponding member of
the loss factor to get the colour as seen by the viewer.
<a name="GetDirectionToSun"></a>
### vec3 GetDirectionToSun(double epoch_time, float latitude, float longitude)

Get the direction to the sun.
<a name="GetDistanceToEarth"></a>
### float GetDistanceToEarth(float Elevation, float h_km)
From the specified altitude h_km, and in the direction of Elevation, how far is it in Km to the surface?
<a name="GetDistanceToSpace"></a>
### float GetDistanceToSpace(float Elevation, float h_km)
Considering the atmosphere as a shell of thickness GetAtmosphereThickness(), from altitude h_km,
this function returns how far a ray cast at angle Elevationabove the horizon would travel
to reach the outer radius of the shell.
<a name="GetEarthShadow"></a>
### simul::sky::EarthShadow GetEarthShadow(float h_km, vec3 lightDir)
The Earth's shadow, as seen from the given altitude.
<a name="GetHazeFactorAtAltitude"></a>
### float GetHazeFactorAtAltitude(float alt_km, simul::sky::HazeStruct hazeStruct)
Get the amount of haze present at altitude alt_kmcompared to the amount at sea level. This value is
independent of the overall Haze multiplier ( see GetHaze() ).
<a name="GetHazeForVisibilityDistance"></a>
### float GetHazeForVisibilityDistance(float view_alt_km, float horiz_dist_km, simul::sky::HazeStruct hazeStruct)
Get the haze that will produce the required visibility distance in the horizontal direction.
<a name="GetInscatterAngularMultiplier"></a>
### simul::sky::float4 GetInscatterAngularMultiplier(float cosine, float mie_factor, simul::sky::HazeStruct hazeStruct)
Get the multiplier for an inscatter factor that gives the total inscatter, where cosineis the cosine between
the angle to the sun and the ray direction, mie_factoris the proportional haze factor (stored int the w element of the inscatter factor)
and alt_kmis the viewing altitude in km.
<a name="GetIsotropicColourLossFactor"></a>
### simul::sky::float4 GetIsotropicColourLossFactor(float alt_km, float elevation, float min_dist_km, float max_dist_km, simul::sky::HazeStruct hazeStruct, bool earth_test, int steps, bool blackbody, float emissivity)
Get the loss factor of an object at position pos_kmseen from view_pos_km.
When an object has initial colour c, multiply each member of cby the corresponding member of
the loss factor to get the colour as seen by the viewer.
<a name="GetIsotropicInscatter"></a>
### simul::sky::float4 GetIsotropicInscatter(float alt_km, float elevation, float min_dist_km, float max_dist_km, vec3 sun_irradiance, vec3 moon_albedo, simul::sky::float4 starlight, vec3 dir_to_sun, std::map moonDirections, simul::sky::HazeStruct hazeStruct, simul::sky::float4 wavelengthsNm, simul::sky::OvercastStruct overcast, bool earth_test, int steps)
Get the approximate isotropic inscatter, i.e. the inscatter without a dependence on the angle to the strongest light source. In particular,
this includes skylight and starlight.
<a name="GetLocalMoonIrradianceFactor"></a>
### vec3 GetLocalMoonIrradianceFactor(simul::sky::Moon m, float altitude_km, vec3 dir_to_moon, vec3 dir_to_sun, simul::sky::HazeStruct hazeStruct)
Get the moonlight that reaches the altitude altitude_km.
<a name="GetLocalSunIrradiance"></a>
### vec3 GetLocalSunIrradiance(float altitude_km, vec3 sun_irradiance, vec3 dir_to_sun, simul::sky::HazeStruct hazeStruct)
Get the sunlight that reaches the altitude altitude_km.
<a name="GetMoonIrradianceFactor"></a>
### float GetMoonIrradianceFactor(simul::sky::Moon m, vec3 dir_to_moon, vec3 dir_to_sun)
Get the moonlight irradiance in space.
<a name="GetOvercastAtAltitude"></a>
### float GetOvercastAtAltitude(simul::sky::OvercastStruct overcast, float alt_km)
Get the strength of the overcast effect at a given altitude, determined by Overcast, OvercastBaseKm, and OvercastRangeKm.
<a name="GetOzoneAtAltitude"></a>
### float GetOzoneAtAltitude(float alt_km)
Get the amount of ozone present at altitude alt_km. This is a dimensionless number.
<a name="GetPlanetRadius"></a>
### float  const & GetPlanetRadius()
Calculate Rayleigh coefficients for air using colour wavelengths ColourWavelengthsNm.
<a name="GetVisibilityDistance"></a>
### float GetVisibilityDistance(float view_alt_km, simul::sky::HazeStruct hazeStruct)
From the altitude specified, the distance in km to 10% visibility (mainly a factor of fog/haze).
<a name="SetPlanetRadius"></a>
### void SetPlanetRadius(float value)
An abstract interface class for skies.
