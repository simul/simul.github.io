---
title: CellularCloudNode
layout: reference
weight: 0
---
class CellularCloudNode
===

| Include: | Clouds/CellularCloudNode.h |

Don't create a CellularCloudNode directly, instead, use the derived class FastCloudNode.
  

[simul::clouds::CellularCloudGrid](cellularcloudgrid.html)
[simul::base::Referenced](../base/referenced.html)

Functions
---

| void | [GetExtents](#GetExtents)(simul::math::Vector3 X1, simul::math::Vector3 X2, float cloud_base_z, float w, float h) |
| simul::math::NoiseInterface * | [GetNoiseInterface](#GetNoiseInterface)() |
| simul::math::Vector3 | [GetOrigin](#GetOrigin)(simul::math::Vector3 windOffset, float cloud_base_z, float w) |
| float  const * | [GetTransformLightspaceToCloudspaceMatrix](#GetTransformLightspaceToCloudspaceMatrix)(unsigned int axis, simul::math::Vector3 dir, simul::math::Vector3 origin, simul::math::Vector3 scales, float cloud_base_z, float w, float h) |
| float  const * | [GetTransformToLightspaceMatrix](#GetTransformToLightspaceMatrix)(unsigned int axis, simul::math::Vector3 dir, simul::math::Vector3 origin, simul::math::Vector3 scales) |
| bool | [NeedsRelight](#NeedsRelight)() |
| void | [SetRecalculate](#SetRecalculate)(bool r) |
| void | [SetRelight](#SetRelight)() |
| std::istream  & | [StateStreamIn](#StateStreamIn)(std::istream is) |
| std::ostream  & | [StateStreamOut](#StateStreamOut)(std::ostream os) |
| std::istream  & | [StreamIn](#StreamIn)(std::istream is) |
| std::ostream  & | [StreamOut](#StreamOut)(std::ostream os) |

Don't create a CellularCloudNode directly, instead, use the derived class FastCloudNode.
  


Base Classes
---
[simul::clouds::CellularCloudGrid](cellularcloudgrid.html)
[simul::base::Referenced](../base/referenced.html)

Functions
---
<a name="GetExtents"></a>
### void GetExtents(simul::math::Vector3 X1, simul::math::Vector3 X2, float cloud_base_z, float w, float h)
Get the physical extents of the cloud volume in the x, y and z directions.
<a name="GetNoiseInterface"></a>
### simul::math::NoiseInterface * GetNoiseInterface()
Get a pointer to the noise memory interface
<a name="GetOrigin"></a>
### simul::math::Vector3 GetOrigin(simul::math::Vector3 windOffset, float cloud_base_z, float w)
Get the effective origin in world co-ordinates, including wind offsets:
<a name="GetTransformLightspaceToCloudspaceMatrix"></a>
### float  const * GetTransformLightspaceToCloudspaceMatrix(unsigned int axis, simul::math::Vector3 dir, simul::math::Vector3 origin, simul::math::Vector3 scales, float cloud_base_z, float w, float h)
Get a 4x4 matrix to transform from lightspace to cloudspace.
<a name="GetTransformToLightspaceMatrix"></a>
### float  const * GetTransformToLightspaceMatrix(unsigned int axis, simul::math::Vector3 dir, simul::math::Vector3 origin, simul::math::Vector3 scales)
Get a 4x4 matrix to transform from real space to lightspace.
<a name="NeedsRelight"></a>
### bool NeedsRelight()
Have properties changed that cause relighting to be necessary - either the light has moved
or the cloud density grid has changed.
<a name="SetRecalculate"></a>
### void SetRecalculate(bool r)
Recalculate and reinitialise the cloud grid with updated values
<a name="SetRelight"></a>
### void SetRelight()
Force relighting of the volume. Usually unnecessary.
<a name="StateStreamIn"></a>
### std::istream  & StateStreamIn(std::istream is)
Stream/load from the std::isteam is.
<a name="StateStreamOut"></a>
### std::ostream  & StateStreamOut(std::ostream os)
Stream/save to the std::osteam os.
<a name="StreamIn"></a>
### std::istream  & StreamIn(std::istream is)
Stream/load from the std::isteam is.
<a name="StreamOut"></a>
### std::ostream  & StreamOut(std::ostream os)
Stream/save to the std::osteam os.
