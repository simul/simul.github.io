---
title: SkyKeyframer
layout: reference
weight: 0
---
class SkyKeyframer
===

| Include: | Sky/BaseAtmosphericsRenderer.h |


[simul::sky::BaseKeyframer](basekeyframer.html)
[simul::sky::BaseSkyInterface](baseskyinterface.html)

Functions
---

|  | [SkyKeyframer](#SkyKeyframer)(simul::base::MemoryInterface mem, int num_elev, int num_dist, float max_dist_km) |
| void | [CalcSunIrradianceAtEarth](#CalcSunIrradianceAtEarth)() |
| void | [ClearHighlightConstellations](#ClearHighlightConstellations)() |
| void | [DaytimeToClockTime](#DaytimeToClockTime)(float t, int d, int h, int m, int s, int ms) |
| void | [DeleteKeyframe](#DeleteKeyframe)(int i) |
| float | [GetAltitudeTexCoord](#GetAltitudeTexCoord)(float h_km) |
| vec3 | [GetDirectionToSun](#GetDirectionToSun)(int keyframe) |
| float | [GetFloat](#GetFloat)(char name, simul::base::Variant params) |
| vec3 | [GetGeocentricDirectionToMoon](#GetGeocentricDirectionToMoon)(simul::sky::uid u) |
| void | [GetGpuSkyParameters](#GetGpuSkyParameters)(simul::sky::GpuSkyParameters p, simul::sky::GpuSkyAtmosphereParameters a, simul::sky::GpuSkyInfraredParameters ir, int index) |
| void | [GetGpuSkyParameters](#GetGpuSkyParameters)(simul::sky::GpuSkyParameters p, simul::sky::GpuSkyAtmosphereParameters a, simul::sky::GpuSkyInfraredParameters ir, simul::sky::SkyKeyframe K, float daytime, float complete) |
| std::set  const | [GetHighlightConstellations](#GetHighlightConstellations)() |
| float | [GetHorizonElevation](#GetHorizonElevation)(float h_km) |
| int | [GetInt](#GetInt)(char name, simul::base::Variant params) |
| simul::sky::SkyKeyframe * | [GetInterpolatedKeyframe](#GetInterpolatedKeyframe)() |
| simul::sky::LightingState  const & | [GetLightingState](#GetLightingState)() |
| simul::sky::SkyKeyframe * | [GetNextModifiableKeyframe](#GetNextModifiableKeyframe)() |
| void | [GetStartDate](#GetStartDate)(int y, int m, int d) |
| unsigned int | [GetSubdivisionChecksum](#GetSubdivisionChecksum)() |
| bool | [HasFloat](#HasFloat)(char name) |
| bool | [HasInt](#HasInt)(char name) |
| void | [HighlightConstellation](#HighlightConstellation)(char) |
| void | [OverrideMoonDirection](#OverrideMoonDirection)(float az, float el) |
| void | [OverrideSunDirection](#OverrideSunDirection)(float az, float el) |
| void | [Set](#Set)(char name, simul::base::Variant params) |
| void | [SetFloat](#SetFloat)(char name, float val) |
| void | [SetInt](#SetInt)(char name, int val) |
| void | [SetStartDate](#SetStartDate)(int y, int m, int d) |
| void | [SetUniformKeyframes](#SetUniformKeyframes)(int Steps, float range) |
| void | [UnHighlightConstellation](#UnHighlightConstellation)(char) |
| void | [Update](#Update)() |
| void | [EnsureSunAndMoonValidity](#EnsureSunAndMoonValidity)(simul::sky::SkyKeyframe K1) |


Base Classes
---
[simul::sky::BaseKeyframer](basekeyframer.html)
[simul::sky::BaseSkyInterface](baseskyinterface.html)

Functions
---
<a name="SkyKeyframer"></a>
###  SkyKeyframer(simul::base::MemoryInterface mem, int num_elev, int num_dist, float max_dist_km)
A class that maintains sky properties and interpolates them based on keyframe values.

An instance of the SkyKeyframer is kept as a member of the Environment instance.
The SkyKeyframer interpolates the sky values, and passes the keyframe and interpolation data to external renderers,
e.g. 
<a name="CalcSunIrradianceAtEarth"></a>
### void CalcSunIrradianceAtEarth()
Calculate SunIrradiance using the solar irradiance tables outside Earth's atmosphere, based on ColourWavelengthsNm.
<a name="ClearHighlightConstellations"></a>
### void ClearHighlightConstellations()
Clear the highlighted constellations
<a name="DaytimeToClockTime"></a>
### void DaytimeToClockTime(float t, int d, int h, int m, int s, int ms)
Convert a floating-point daytime into hour, minute, second and milliseconds.
<a name="DeleteKeyframe"></a>
### void DeleteKeyframe(int i)
Delete a skykeyframe with the given ID
<a name="GetAltitudeTexCoord"></a>
### float GetAltitudeTexCoord(float h_km)
Returns the texture coordinate for the given altitude - constant per-frame.
<a name="GetDirectionToSun"></a>
### vec3 GetDirectionToSun(int keyframe)
Get the direction the sun represented as a vector
<a name="GetFloat"></a>
### float GetFloat(char name, simul::base::Variant params)
Get a float with the given, case-insensitive, name
<a name="GetGeocentricDirectionToMoon"></a>
### vec3 GetGeocentricDirectionToMoon(simul::sky::uid u)
Direction in Earth-centred equatorial co-ordinates, where Z=Earth's North axis, X is 90 deg East and Y is 180 degrees.
<a name="GetGpuSkyParameters"></a>
### void GetGpuSkyParameters(simul::sky::GpuSkyParameters p, simul::sky::GpuSkyAtmosphereParameters a, simul::sky::GpuSkyInfraredParameters ir, int index)
Get the GPU sky parameters corresponding to the given subdivision triplet index, and factor in eclipses and brightness power modifiers.
<a name="GetGpuSkyParameters"></a>
### void GetGpuSkyParameters(simul::sky::GpuSkyParameters p, simul::sky::GpuSkyAtmosphereParameters a, simul::sky::GpuSkyInfraredParameters ir, simul::sky::SkyKeyframe K, float daytime, float complete)
Get the GPU sky parameters corresponding to the given keyframe at the stated time.
<a name="GetHighlightConstellations"></a>
### std::set  const GetHighlightConstellations()
Get the set of highlighted constellations
<a name="GetHorizonElevation"></a>
### float GetHorizonElevation(float h_km)
The elevation of the horizon at this altitude
<a name="GetInt"></a>
### int GetInt(char name, simul::base::Variant params)
Get an int with the given, case-insensitive, name
<a name="GetInterpolatedKeyframe"></a>
### simul::sky::SkyKeyframe * GetInterpolatedKeyframe()
Get the current interpolatedkeyframe, which holds the values interpolated from the two surrounding keyframes at
any given time.
<a name="GetLightingState"></a>
### simul::sky::LightingState  const & GetLightingState()
Get the per-frame cached lighting state
<a name="GetNextModifiableKeyframe"></a>
### simul::sky::SkyKeyframe * GetNextModifiableKeyframe()
The next keyframe not partially built or being used. This keyframe's properties can be modified without any pause or rebuild.
<a name="GetStartDate"></a>
### void GetStartDate(int y, int m, int d)
What date is referred to as time zero.
<a name="GetSubdivisionChecksum"></a>
### unsigned int GetSubdivisionChecksum()
This is a checksum that only changes if an in-use subdivision has modified (cycling does not change it).
<a name="HasFloat"></a>
### bool HasFloat(char name)
Return true if the keyframer has the floating point value with the given, case-insensitive, name; return false otherwise.

These are the properties the SkyKeyframer has:
- LatitudeRadians
- LongitudeRadians
- LatitudeDegrees
- LongitudeDegrees
- MaxStarMagnitude
- MinimumStarPixelSize
- MaxDistanceKm
- MaxAltitudeKm
- atmosphereThicknessKm
- planetRadiusKm
- MaxSunRadiance
- BrightnessPower
- OzoneStrength
- Emissivity
- MoonAlbedo
- TimezoneHours
- SunRadiusArcMinutes
- MoonRadiusArcMinutes
- sunazimuth
- sunelevation
- moonazimuth
- moonelevation
- sunazimuthdegrees
- sunelevationdegrees
- moonazimuthdegrees
- moonelevationdegrees
- sunirradiance
- colourwavelengthsnm

<a name="HasInt"></a>
### bool HasInt(char name)
Return true if the keyframer has an integer or true/false value with the given, case-insensitive, name; return false otherwise. 

These are the properties the SkyKeyframer has:
- StoreAsColours
- AutoMie
- numColourAltitudes
- numColourElevations
- numColourDistances
- AutomaticSunPosition

<a name="HighlightConstellation"></a>
### void HighlightConstellation(char)
Highlight the named constellation in debug views:
<a name="OverrideMoonDirection"></a>
### void OverrideMoonDirection(float az, float el)
Set the current direction of the moon by it's Azimuth and Elevation
<a name="OverrideSunDirection"></a>
### void OverrideSunDirection(float az, float el)
Set the current direction of the sun by it's Azimuth and Elevation
<a name="Set"></a>
### void Set(char name, simul::base::Variant params)
Set a value with the given enum
<a name="SetFloat"></a>
### void SetFloat(char name, float val)
Set a float with the given, case-insensitive, name
<a name="SetInt"></a>
### void SetInt(char name, int val)
Set an int with the given, case-insensitive, name
<a name="SetStartDate"></a>
### void SetStartDate(int y, int m, int d)
Set the date for time=0.
<a name="SetUniformKeyframes"></a>
### void SetUniformKeyframes(int Steps, float range)
Create a number of evenly spaced keyframes.
<a name="UnHighlightConstellation"></a>
### void UnHighlightConstellation(char)
Remove the named constellation from the highlighted list
<a name="Update"></a>
### void Update()
Per-frame update call, this function updates the interpolation and the tables.
<a name="EnsureSunAndMoonValidity"></a>
### void EnsureSunAndMoonValidity(simul::sky::SkyKeyframe K1)
Apply any overrides.
