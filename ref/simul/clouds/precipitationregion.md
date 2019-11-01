---
title: PrecipitationRegion
layout: reference
weight: 0
---
struct PrecipitationRegion
===

| Include: | Clouds/CloudKeyframe.h |

A structure defining an area where there is rain or snow.
If regionalis false, it is everywhere.
  



A structure defining an area where there is rain or snow.
If regionalis false, it is everywhere.
  


Fields
---

**lockToClouds**  < If true, rain/snow only occurs within the specified region. If false, it occurs everywhere in the cloud keyframe.

**centre**  < If true, the movement of the region takes into account the wind's speed and heading.

**radiusKm**  < Origin on the globe for this Precipitation Region

**rainEffectStrength**  < The radius of the region.

**edge**  < The visual strength of the virga effect when rendered.

**base_radial_km**  < The edge between zero and one. Small numbers give a sharp edge to the region.
