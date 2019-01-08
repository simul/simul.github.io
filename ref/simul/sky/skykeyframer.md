---
title: SkyKeyframer
layout: reference
weight: 0
---
class SkyKeyframer
===

| Include: | Sky/BaseAtmosphericsRenderer.h |

A class that maintains sky properties and interpolates them based on keyframe values.<br>

[simul::base::Referenced](../base/referenced)
[simul::sky::BaseKeyframer](basekeyframer)
[simul::sky::BaseSkyInterface](baseskyinterface)

Functions
---

| void | [CalcSunIrradianceAtEarth](#CalcSunIrradianceAtEarth)() |
| void | [ClearHighlightConstellations](#ClearHighlightConstellations)() |
| void | [DaytimeToClockTime](#DaytimeToClockTime)(float t, int d, int h, int m, int s, int ms) |
| float | [GetAltitudeTexCoord](#GetAltitudeTexCoord)(float h_km) |
| void | [GetGpuSkyParameters](#GetGpuSkyParameters)(simul::sky::GpuSkyParameters p, simul::sky::GpuSkyAtmosphereParameters a, simul::sky::GpuSkyInfraredParameters ir, int index) |
| void | [GetGpuSkyParameters](#GetGpuSkyParameters)(simul::sky::GpuSkyParameters p, simul::sky::GpuSkyAtmosphereParameters a, simul::sky::GpuSkyInfraredParameters ir, simul::sky::SkyKeyframe K, float daytime, float complete) |
| std::set  const | [GetHighlightConstellations](#GetHighlightConstellations)() |
| float | [GetHorizonElevation](#GetHorizonElevation)(float h_km) |
| simul::sky::LightingState  const & | [GetLightingState](#GetLightingState)() |
| float | [GetMultiplier](#GetMultiplier)(double t) |
| simul::sky::SkyKeyframe * | [GetNextModifiableKeyframe](#GetNextModifiableKeyframe)() |
| void | [GetStartDate](#GetStartDate)(int y, int m, int d) |
| unsigned int | [GetSubdivisionChecksum](#GetSubdivisionChecksum)() |
| bool | [HasFloat](#HasFloat)(char name) |
| bool | [HasInt](#HasInt)(char name) |
| void | [HighlightConstellation](#HighlightConstellation)(char) |
| void | [SetStartDate](#SetStartDate)(int y, int m, int d) |
| void | [SetUniformKeyframes](#SetUniformKeyframes)(int Steps, float range) |
| void | [UnHighlightConstellation](#UnHighlightConstellation)(char) |
| void | [Update](#Update)() |
| void | [EnsureSunAndMoonValidity](#EnsureSunAndMoonValidity)(simul::sky::SkyKeyframe K1) |

An instance of the SkyKeyframer is kept as a member of the Environment instance.
The SkyKeyframer interpolates the sky values, and passes the keyframe and interpolation data to external renderers,
e.g. <a href="baseskyrenderer">BaseSkyRenderer</a>and <a href="baseatmosphericsrenderer">BaseAtmosphericsRenderer</a>.
The generated tables are calculated for multiple altitudes - specified with SetNumAltitudes.
The SunIrradiance value determines the colour and strength of sunlight, and is expressed in physical units. The apparent size of the sun is
set using SetSunRadiusArcMinutes.
  


Base Classes
---
[simul::base::Referenced](../base/referenced)
[simul::sky::BaseKeyframer](basekeyframer)
[simul::sky::BaseSkyInterface](baseskyinterface)

Functions
---

### <a name="CalcSunIrradianceAtEarth"/>void CalcSunIrradianceAtEarth()
Calculate SunIrradiance using the solar irradiance tables outside Earth's atmosphere, based on ColourWavelengthsNm.

### <a name="ClearHighlightConstellations"/>void ClearHighlightConstellations()
Clear the highlighted constellations

### <a name="DaytimeToClockTime"/>void DaytimeToClockTime(float t, int d, int h, int m, int s, int ms)
Convert a floating-point daytime into hour, minute, second and milliseconds.

### <a name="GetAltitudeTexCoord"/>float GetAltitudeTexCoord(float h_km)
Returns the texture coordinate for the given altitude - constant per-frame.

### <a name="GetGpuSkyParameters"/>void GetGpuSkyParameters(simul::sky::GpuSkyParameters p, simul::sky::GpuSkyAtmosphereParameters a, simul::sky::GpuSkyInfraredParameters ir, int index)
Get the GPU sky parameters corresponding to the given subdivision triplet index, and factor in eclipses and brightness power modifiers.

### <a name="GetGpuSkyParameters"/>void GetGpuSkyParameters(simul::sky::GpuSkyParameters p, simul::sky::GpuSkyAtmosphereParameters a, simul::sky::GpuSkyInfraredParameters ir, simul::sky::SkyKeyframe K, float daytime, float complete)
Get the GPU sky parameters corresponding to the given keyframe at the stated time.

### <a name="GetHighlightConstellations"/>std::set  const GetHighlightConstellations()
Get the set of highlighted constellations

### <a name="GetHorizonElevation"/>float GetHorizonElevation(float h_km)
The elevation of the horizon at this altitude

### <a name="GetLightingState"/>simul::sky::LightingState  const & GetLightingState()
Get the per-frame cached lighting state

### <a name="GetMultiplier"/>float GetMultiplier(double t)
Get the calculated multiplication factor for outputs.
SunIrradiance is multiplied by this value to calculate sky colours.
Divide local irradiances by this value to get the value in physical units.
Divide radiances (i.e. rendered colours) by this value to get the radiance in physical units.

### <a name="GetNextModifiableKeyframe"/>simul::sky::SkyKeyframe * GetNextModifiableKeyframe()
The next keyframe not partially built or being used. This keyframe's properties can be modified without any pause or rebuild.

### <a name="GetStartDate"/>void GetStartDate(int y, int m, int d)
What date is referred to as time zero.

### <a name="GetSubdivisionChecksum"/>unsigned int GetSubdivisionChecksum()
This is a checksum that only changes if an in-use subdivision has modified (cycling does not change it).

### <a name="HasFloat"/>bool HasFloat(char name)
Return true if the keyframer has the floating point value with the given, case-insensitive, name; return false otherwise.

These are the properties the SkyKeyframer has:
- LatitudeRadians
- LongitudeRadians
- MaxStarMagnitude
- StarBrightness
- BackgroundBrightness
- MaxDistanceKm
- MaxAltitudeKm
- OvercastEffectStrength
- TimezoneHours
- SunRadiusArcMinutes
- MoonRadiusArcMinutes


### <a name="HasInt"/>bool HasInt(char name)
Return true if the keyframer has an integer or true/false value with the given, case-insensitive, name; return false otherwise. 

These are the properties the SkyKeyframer has:
- StartDayNumber
- NumAltitudes
- NumElevations
- NumDistances


### <a name="HighlightConstellation"/>void HighlightConstellation(char)
Highlight the named constellation in debug views:

### <a name="SetStartDate"/>void SetStartDate(int y, int m, int d)
Set the date for time=0.

### <a name="SetUniformKeyframes"/>void SetUniformKeyframes(int Steps, float range)
Create a number of evenly spaced keyframes.

### <a name="UnHighlightConstellation"/>void UnHighlightConstellation(char)
Remove the named constellation from the highlighted list

### <a name="Update"/>void Update()
Per-frame update call, this function updates the interpolation and the tables.

### <a name="EnsureSunAndMoonValidity"/>void EnsureSunAndMoonValidity(simul::sky::SkyKeyframe K1)
Apply any overrides.
