---
title: CloudKeyframe
layout: reference
weight: 0
---
struct CloudKeyframe
===

| Include: | Clouds/CloudKeyframe.h |

The keyframe structure for clouds, used by simul::clouds::CloudKeyframer.
  

[simul::sky::BaseKeyframe](../sky/basekeyframe.html)

Functions
---

|  | [CloudKeyframe](#CloudKeyframe)() |
| simul::crossplatform::Quaterniond | [GetAbsoluteOrientation](#GetAbsoluteOrientation)(simul::crossplatform::Quaterniond rel) |
| float | [GetFloat](#GetFloat)(char name) |
| int | [GetInt](#GetInt)(char name) |
| simul::crossplatform::Quaterniond | [GetPrecipitationCentre](#GetPrecipitationCentre)() |
| unsigned int | [GetPropertiesChecksum](#GetPropertiesChecksum)() |
| bool | [HasFloat](#HasFloat)(char name) |
| bool | [HasInt](#HasInt)(char name) |
| void | [SetFloat](#SetFloat)(char name, float val) |
| void | [SetInt](#SetInt)(char name, int val) |

The keyframe structure for clouds, used by simul::clouds::CloudKeyframer.
  


Base Classes
---
[simul::sky::BaseKeyframe](../sky/basekeyframe.html)

Functions
---
<a name="CloudKeyframe"></a>
###  CloudKeyframe()
< States for cloud volumes listed in the keyframer.
<a name="GetAbsoluteOrientation"></a>
### simul::crossplatform::Quaterniond GetAbsoluteOrientation(simul::crossplatform::Quaterniond rel)
From a relative orientation, get the absolute orientation.
<a name="GetFloat"></a>
### float GetFloat(char name)
Get a float with the given, case-insensitive, name
<a name="GetInt"></a>
### int GetInt(char name)
Get an int with the given, case-insensitive, name
<a name="GetPrecipitationCentre"></a>
### simul::crossplatform::Quaterniond GetPrecipitationCentre()
Depending on precipitationRegion.lockToClouds, precipitationRegion.CentreKm is either absolute or relative.
So this function is used to access the true centre position of the rain region.
<a name="GetPropertiesChecksum"></a>
### unsigned int GetPropertiesChecksum()
Check for properties that, if altered in the keyframe, would require regeneration of
the cloud volume:
<a name="HasFloat"></a>
### bool HasFloat(char name)
Return true if the keyframe has a float value with the given, case-insensitive, name; return false otherwise. 

The properties are:
- cloudiness
- distributionBaseLayer
- distributionTransition
- upperDensity
- localDensity
- windSpeed
- windDirection
- windHeading
- windHeadingDegrees
- persistence
- cloudBase
- cloudHeight
- cloudWidth
- cloudWidthKm
- cloudWidthMetres
- directLight
- indirectLight
- ambientLight
- lightAsymmetry
- precipitation
- fractalAmplitude
- edgeSharpness
- churn
- extinction
- rainToSnow
- precipitationWindEffect
- precipitationWaver
- diffusivity
- cache_built
- lightning
- maxDensityGm3
- baseNoiseFactor
- offsetx
- offsety
- rainCentreXKm
- rainCentreYKm
- rainRadiusKm
- rainEdge
- rainEffectStrength
- simulation
- WorleyNoise
- WorleyScale
- EdgeWorleyNoise
- scalekm
- scalekm.x
- scalekm.y
- scalekm.z
- EdgeWorleyScale

<a name="HasInt"></a>
### bool HasInt(char name)
Return true if the keyframe has an integer or true/false value with the given, case-insensitive, name; return false otherwise. 

- Octaves
- RegionalPrecipitation
- LockRainToClouds

<a name="SetFloat"></a>
### void SetFloat(char name, float val)
Set a float with the given, case-insensitive, name
<a name="SetInt"></a>
### void SetInt(char name, int val)
Set an int with the given, case-insensitive, name

Fields
---

**cloudiness**  < The base altitude of this Precipitation Region from the centre of the planet.

**distribution_base_layer**  < The density of the cloud layer at this time.

**distribution_transition**  < Start of the transition from the cloud base to the upper cloud (0 to 1)

**upper_density**  < The transition from the cloud base to the upper cloud (0 to 1)

**wind_speed**  < The proportion of cloud density retained in the upper layer, above the distribution_transition.

**wind_direction**  < The wind speed in m/s

**cloud_base_km**  < The wind direction

**cloud_height_km**  < The base altitude of this cloud layer.

**cloud_width_km**  < The height of the cloud layer, above its base altitude.

**scale_km**  < The width of the cloud layer in km, or the repeat-length.

**octaves**  < For non-repeating clouds, the shape scale

**persistence**  < The number of noise octaves used to generate the clouds; default 3.

**fractal_amplitude**  < The fractal persistence for generating the clouds, default 0.45.

**edge_sharpness**  < The strength of the fractal edge effect.

**churn**  < The sharpness to be applied in rendering a the boundary.

**precipitation**  < The strength of the cloud edge churning effect - larger values for more turbulent clouds.

**rain_to_snow**  < The amount of rain/snow etc.

**diffusivity**  < If zero, precipitation is interpreted as rain. If one, it is snow.

**max_density_gm3**  < How much the edges of clouds should be diffused.

**base_noise_factor**  < Grams per cubic metre. Default is 0.5

**offsetKm**  < What proportion of noise is applied at the cloudbase, between 0 and 1.0.

**octaves_f**  < The calculated position offset of this keyframe due to the accumulation of wind motion (see 

**simulation**  < Only used for interpolation - changes will be ignored. See 

**worley_noise**  < If 1.0, cloud volume is simulated. If 0.0, it is generated by fractal.

**worley_scale**  < How much Worley (cell) noise to apply in cloud generation.

**edge_worley_noise**  < Scale of the Worley noise. Will be locked to an integer if clouds are wrapping.

**origin**  < The strength of the fractal worley edge noise.

**precipitationRegion**  < Origin on the globe for this layer.

**cloudVolumeStates**  < Where rain/snow is found.
