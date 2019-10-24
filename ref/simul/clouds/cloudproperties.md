---
title: CloudProperties
layout: reference
weight: 0
---
class CloudProperties
===

| Include: | Clouds/CloudInterface.h |

A virtual interface that returns the keyframe-independent cloud properties.
  


Functions
---

| void | [GetExtents](#GetExtents)(simul::math::Vector3 X1, simul::math::Vector3 X2, float cloud_base_z, float w, float h) |
| int | [GetGenerationNumber](#GetGenerationNumber)() |
| simul::math::Vector3 | [GetOrigin](#GetOrigin)(simul::math::Vector3, float cloud_base_z, float w) |
| float  const * | [GetTransformLightspaceToCloudspaceMatrix](#GetTransformLightspaceToCloudspaceMatrix)(unsigned int axis, simul::math::Vector3 dir, simul::math::Vector3 orig, simul::math::Vector3 scales, float cloud_base_z, float w, float h) |
| float  const * | [GetTransformToLightspaceMatrix](#GetTransformToLightspaceMatrix)(unsigned int axis, simul::math::Vector3 dir, simul::math::Vector3 orig, simul::math::Vector3 scales) |

A virtual interface that returns the keyframe-independent cloud properties.
  


Functions
---
<a name="GetExtents"></a>
### void GetExtents(simul::math::Vector3 X1, simul::math::Vector3 X2, float cloud_base_z, float w, float h)
Get the physical extents of the cloud volume in the x, y and z directions.
<a name="GetGenerationNumber"></a>
### int GetGenerationNumber()
A number that is changed every time the clouds are regenerated.
<a name="GetOrigin"></a>
### simul::math::Vector3 GetOrigin(simul::math::Vector3, float cloud_base_z, float w)
get the effective origin in world co-ordinates, including wind offsets:
<a name="GetTransformLightspaceToCloudspaceMatrix"></a>
### float  const * GetTransformLightspaceToCloudspaceMatrix(unsigned int axis, simul::math::Vector3 dir, simul::math::Vector3 orig, simul::math::Vector3 scales, float cloud_base_z, float w, float h)
Get a 4x4 matrix to transform from lightspace to cloudspace.
<a name="GetTransformToLightspaceMatrix"></a>
### float  const * GetTransformToLightspaceMatrix(unsigned int axis, simul::math::Vector3 dir, simul::math::Vector3 orig, simul::math::Vector3 scales)
Get a 4x4 matrix to transform from real space to lightspace.
