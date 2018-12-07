---
title: SkyKeyframe
layout: reference
weight: 0
---
struct SkyKeyframe
===

| Include: | Sky/SkyInterface.h |

The properties of any sky keyframe can be changed at any time. However, only HazeEccentricity
can be changed for an in-use keyframe without triggering a recalculation of the colour tables.
  

[simul::sky::BaseKeyframe](basekeyframe)

Functions
---

|  | [SkyKeyframe](#SkyKeyframe)(simul::base::MemoryInterface m) |
| unsigned int | [GetTransientChecksum](#GetTransientChecksum)() |

The properties of any sky keyframe can be changed at any time. However, only HazeEccentricity
can be changed for an in-use keyframe without triggering a recalculation of the colour tables.
  


Base Classes
---
[simul::sky::BaseKeyframe](basekeyframe)

Functions
---

### <a name="SkyKeyframe"/> SkyKeyframe(simul::base::MemoryInterface m)
< Whether to calculate the moon position from the date and time.

### <a name="GetTransientChecksum"/>unsigned int GetTransientChecksum()
Checksum including values not needed for GPU recalculation.

Fields
---

**Mie**  < The time this keyframe represents, in a floating-point number of days from the starting midnight of the sequence. If simul::sky::SkyKeyframer::SetLinkKeyframeTimeAndDaytime is true, this is not used.

**Haze**  < The Mie scattering coefficients (x=red,y=green,z=blue). Mutable because of AutoMie.

**HazeBaseKm**  < The amount of haze, mist or fog.

**HazeScaleKm**  < The base altitude, above which haze starts to decrease in density.

**HazeEccentricity**  < The vertical scale over which haze reduces with altitude.

**GroundFog**  < The anisotropy of Mie scattering. Can be changed without recalculating tables.

**FogCeilingKm**  < Thick ground fog

**SunAzimuth**  < Upper limit of ground fog

**SunElevation**  < Horizontal angle to the sun. This will be overridden if sun position is automatic.

**MoonElevation**  < Angle of the sun above the horizon. This will be overridden if sun position is automatic.

**MoonAzimuth**  < Angle of the moon above the horizon. This will be overridden if moon position is automatic.

**SeaLevelTemperatureK**  < Horizontal angle to the moon. This will be overridden if moon position is automatic.

**StoreAsColours**  < Temperature at sealevel, in kelvins - mainly relevant to infra-red.

**Horizon**  < If true, the keyframe is stored as a colour table, rather than generating its colours from its properties.

**automaticSunPosition**  < Whether to recalculate the Mie coefficients based on the haze at this keyframe.

**automaticMoonPosition**  < Whether to calculate the sun position from the date and time.
