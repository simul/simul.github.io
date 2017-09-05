---
title: PrecipitationRegion
layout: reference
weight: 0
---
struct PrecipitationRegion
===

| Include: | Clouds/BaseGpuCloudGenerator.h |

A structure defining an area where there is rain or snow.
If **regional** is false, it is everywhere.



A structure defining an area where there is rain or snow.
If **regional** is false, it is everywhere.
  


Fields
---

**lockToClouds** < If true, rain/snow only occurs within the specified region. If false, it occurs everywhere for the keyframe. < If true, rain/snow only occurs within the specified region. If false, it occurs everywhere for the keyframe.

**centreKm** < If true, the region moves with the cloud wind motion, and centreKm represents an offset from this motion. < If true, the region moves with the cloud wind motion, and centreKm represents an offset from this motion.

**radiusKm** < The centre of the region. < The centre of the region.

**rainEffectStrength** < The radius of the region. < The radius of the region.

**edge** < The visual strength of the rain-streak effect when rendered. < The visual strength of the rain-streak effect when rendered.
