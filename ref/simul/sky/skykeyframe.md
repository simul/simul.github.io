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
  

[simul::sky::BaseKeyframe](basekeyframe.html)

Functions
---

|  | [SkyKeyframe](#SkyKeyframe)(simul::base::MemoryInterface m) |
| unsigned int | [GetTransientChecksum](#GetTransientChecksum)() |

The properties of any sky keyframe can be changed at any time. However, only HazeEccentricity
can be changed for an in-use keyframe without triggering a recalculation of the colour tables.
  


Base Classes
---
[simul::sky::BaseKeyframe](basekeyframe.html)

Functions
---
<a name="SkyKeyframe"></a>
###  SkyKeyframe(simul::base::MemoryInterface m)
< Whether to calculate the sun position from the date and time.
<a name="GetTransientChecksum"></a>
### unsigned int GetTransientChecksum()
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

**StoreAsColours**  < Temperature at sealevel, in kelvins - mainly relevant to infra-red.

**Horizon**  < If true, the keyframe is stored as a colour table, rather than generating its colours from its properties.

**automaticSunPosition**  < Whether to recalculate the Mie coefficients based on the haze at this keyframe.
