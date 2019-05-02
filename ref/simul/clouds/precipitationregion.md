---
title: PrecipitationRegion
layout: reference
weight: 0
---
struct PrecipitationRegion
===

| Include: | Clouds/BaseGpuCloudGenerator.h |

A structure defining an area where there is rain or snow.
If regionalis false, it is everywhere.
  



A structure defining an area where there is rain or snow.
If regionalis false, it is everywhere.
  


Fields
---

**lockToClouds**  < If true, rain/snow only occurs within the specified region. If false, it occurs everywhere for the keyframe.

**centre**  < If true, the region moves with the cloud wind motion, and centreKm represents an offset from this motion.

**radiusKm**  < Origin on the globe for this Precipitation Region

**rainEffectStrength**  < The radius of the region.

**edge**  < The visual strength of the rain-streak effect when rendered.

**base_radial_km**  < The edge between zero and one. Small numbers give a sharp edge to the region.
