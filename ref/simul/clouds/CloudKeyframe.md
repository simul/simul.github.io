---
title: CloudKeyframe
layout: reference
weight: 0
---
struct CloudKeyframe
===

| Include: | Clouds/BaseGpuCloudGenerator.h |

The keyframe structure for clouds, used by simul::clouds::CloudKeyframer.

[simul::sky::BaseKeyframe](../sky/BaseKeyframe)

Functions
---

|  | [CloudKeyframe](#CloudKeyframe)() |
| vec2 | [GetPrecipitationCentreKm](#GetPrecipitationCentreKm)() |
| unsigned int | [GetPropertiesChecksum](#GetPropertiesChecksum)() |
| bool | [HasFloat](#HasFloat)(char name) |
| bool | [HasInt](#HasInt)(char name) |

The keyframe structure for clouds, used by simul::clouds::CloudKeyframer.
  


Base Classes
---
[simul::sky::BaseKeyframe](../sky/BaseKeyframe)

Functions
---

### <a name="CloudKeyframe"/> CloudKeyframe()
< Where rain/snow is found.
< Where rain/snow is found.

### <a name="GetPrecipitationCentreKm"/>vec2 GetPrecipitationCentreKm()
Depending on precipitationRegion.lockToClouds, precipitationRegion.CentreKm is either absolute or relative.
So this function is used to access the true centre position of the rain region.
Depending on precipitationRegion.lockToClouds, precipitationRegion.CentreKm is either absolute or relative.
So this function is used to access the true centre position of the rain region.

### <a name="GetPropertiesChecksum"/>unsigned int GetPropertiesChecksum()
Check for properties that, if altered in the keyframe, would require regeneration of
the cloud volume:
Check for properties that, if altered in the keyframe, would require regeneration of
the cloud volume:

### <a name="HasFloat"/>bool HasFloat(char name)
Return true if the keyframe has a float value with the given, case-insensitive, name; return false otherwise. 

The properties are:
        - cloudiness
        - distributionBaseLayer
        - distributionTransition
        - upperDensity
        - localDensity
        - windSpeed
        - windDirection
        - persistence
        - cloudBase
        - cloudHeight
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
        - diffusivity
        - max_density_gm3
        - cache_built
        - baseNoiseFactor
        - offsetx
        - offsety
        - rainCentreXKm
        - rainCentreYKm
        - rainRadiusKm
        - rainEffectStrength
        - simulation
        - worleyNoise
        - worleyScale


### <a name="HasInt"/>bool HasInt(char name)
Return true if the keyframer has an integer or true/false value with the given, case-insensitive, name; return false otherwise. 

- GridWidth
        - GridHeight
        - Use3DNoise
        - Wrap
        - NoiseResolution
        - OverrideWind
        - EdgeNoiseOctaves
        - EdgeNoiseFrequency
        - EdgeNoiseTextureSize
        - ExplicitOffsets
        - ShadowTextureSize
        - DefaultNumSlices
        - Visible
        - MeetHorizon


Fields
---

**distribution_base_layer** < The density of the cloud layer at this time. < The density of the cloud layer at this time.

**distribution_transition** < Start of the transition from the cloud base to the upper cloud (0 to 1) < Start of the transition from the cloud base to the upper cloud (0 to 1)

**upper_density** < The transition from the cloud base to the upper cloud (0 to 1) < The transition from the cloud base to the upper cloud (0 to 1)

**wind_speed** < The proportion of cloud density retained in the upper layer, above the distribution_transition. < The proportion of cloud density retained in the upper layer, above the distribution_transition.

**wind_direction** < The wind speed in m/s < The wind speed in m/s

**cloud_base_km** < The wind direction < The wind direction

**cloud_height_km** < The base altitude of this cloud layer. < The base altitude of this cloud layer.

**cloud_width_km** < The height of the cloud layer, above its base altitude. < The height of the cloud layer, above its base altitude.

**direct_light** < The width of the cloud layer in km, or the repeat-length. < The width of the cloud layer in km, or the repeat-length.

**indirect_light** < The amount of direct light to be used for rendering. < The amount of direct light to be used for rendering.

**ambient_light** < The amount of indirect or secondary light to be used for rendering. < The amount of indirect or secondary light to be used for rendering.

**light_asymmetry** < The amount of ambient light to be used for rendering. < The amount of ambient light to be used for rendering.

**octaves** < The anisotropic distribution of direct lighting, or eccentricity. < The anisotropic distribution of direct lighting, or eccentricity.

**persistence** < The number of noise octaves used to generate the clouds; default 3. < The number of noise octaves used to generate the clouds; default 3.

**fractal_amplitude** < The fractal persistence for generating the clouds, default 0.45. < The fractal persistence for generating the clouds, default 0.45.

**edge_sharpness** < The strength of the fractal edge effect, default 1.8. < The strength of the fractal edge effect, default 1.8.

**churn** < The sharpness to be applied in rendering a the boundary. < The sharpness to be applied in rendering a the boundary.

**extinction** < The strength of the cloud edge churning effect - larger values for more turbulent clouds. < The strength of the cloud edge churning effect - larger values for more turbulent clouds.

**precipitation** < The amount of light scattered per metre - larger values produce darker clouds, default 0.05. < The amount of light scattered per metre - larger values produce darker clouds, default 0.05.

**rain_to_snow** < The amount of rain/snow etc. < The amount of rain/snow etc.

**diffusivity** < If zero, precipitation is interpreted as rain. If one, it is snow. < If zero, precipitation is interpreted as rain. If one, it is snow.

**max_density_gm3** < How much the edges of clouds should be diffused. < How much the edges of clouds should be diffused.

**base_noise_factor** < Grams per cubic metre. Default is 0.5 < Grams per cubic metre. Default is 0.5

**offsetx** < What proportion of noise is applied at the cloudbase, between 0 and 1.0. < What proportion of noise is applied at the cloudbase, between 0 and 1.0.

**offsety** < The calculated position x offset of this keyframe due to the accumulation of wind motion (see  < The calculated position x offset of this keyframe due to the accumulation of wind motion (see 

**octaves_f** < The calculated position y offset of this keyframe due to the accumulation of wind motion (see  < The calculated position y offset of this keyframe due to the accumulation of wind motion (see 

**simulation** < Only used for interpolation - changes will be ignored. See  < Only used for interpolation - changes will be ignored. See 

**worley_noise** < If 1.0, cloud volume is simulated. If 0.0, it is generated by fractal. < If 1.0, cloud volume is simulated. If 0.0, it is generated by fractal.

**worley_scale** < How much Worley (cell) noise to apply in cloud generation. < How much Worley (cell) noise to apply in cloud generation.

**edge_worley_noise** < Scale of the Worley noise. Will be locked to an integer if clouds are wrapping. < Scale of the Worley noise. Will be locked to an integer if clouds are wrapping.

**masks** < The strength of the fractal worley edge noise. < The strength of the fractal worley edge noise.

**precipitationRegion** < radial masks for precise cloud placement control. < radial masks for precise cloud placement control.
