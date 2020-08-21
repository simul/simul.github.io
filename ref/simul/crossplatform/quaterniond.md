---
title: Quaterniond
layout: reference
weight: 0
---
typedef Quaterniond
===

| Include: | Platform/CrossPlatform/Quaterniond.h |



Functions
---

| simul::crossplatform::Quaterniond | [TransformOrientationByOffsetXY](#TransformOrientationByOffsetXY)(simul::crossplatform::Quaterniond origin, vec2 local_offset_radians) |
| vec3 | [TransformPosition](#TransformPosition)(simul::crossplatform::Quaterniond old_origin, simul::crossplatform::Quaterniond new_origin, vec3 old_pos, double radius) |


Functions
---
<a name="TransformOrientationByOffsetXY"></a>
### simul::crossplatform::Quaterniond TransformOrientationByOffsetXY(simul::crossplatform::Quaterniond origin, vec2 local_offset_radians)
Rotate an orientation by a specified offset in its local x and y axes.
<a name="TransformPosition"></a>
### vec3 TransformPosition(simul::crossplatform::Quaterniond old_origin, simul::crossplatform::Quaterniond new_origin, vec3 old_pos, double radius)
Transform a position in a previous frame of reference into a new frame. Assumes Earth radius 6378km, origin at sea level.
