---
title: CellularCloudNode
layout: reference
weight: 0
---
class CellularCloudNode
===

| Include: | Clouds/CellularCloudNode.h |

Don't create a CellularCloudNode directly, instead, use the derived class FastCloudNode.
  

[simul::clouds::CellularCloudGrid](CellularCloudGrid)
[simul::base::Referenced](../base/Referenced)

Functions
---

| void | [GetExtents](#GetExtents)(simul::math::Vector3 X1, simul::math::Vector3 X2, float cloud_base_z, float w, float h) |
| simul::math::Vector3 | [GetOrigin](#GetOrigin)(simul::math::Vector3 windOffset, float cloud_base_z, float w) |
| float  const * | [GetTransformLightspaceToCloudspaceMatrix](#GetTransformLightspaceToCloudspaceMatrix)(unsigned int axis, simul::math::Vector3 dir, simul::math::Vector3 origin, simul::math::Vector3 scales, float cloud_base_z, float w, float h) |
| float  const * | [GetTransformToLightspaceMatrix](#GetTransformToLightspaceMatrix)(unsigned int axis, simul::math::Vector3 dir, simul::math::Vector3 origin, simul::math::Vector3 scales) |
| bool | [NeedsRelight](#NeedsRelight)() |
| void | [SetRelight](#SetRelight)() |
| std::istream  & | [StateStreamIn](#StateStreamIn)(std::istream is) |
| std::ostream  & | [StateStreamOut](#StateStreamOut)(std::ostream os) |
| std::istream  & | [StreamIn](#StreamIn)(std::istream is) |
| std::ostream  & | [StreamOut](#StreamOut)(std::ostream os) |

Don't create a CellularCloudNode directly, instead, use the derived class FastCloudNode.
  


Base Classes
---
[simul::clouds::CellularCloudGrid](CellularCloudGrid)
[simul::base::Referenced](../base/Referenced)

Functions
---

### <a name="GetExtents"/>void GetExtents(simul::math::Vector3 X1, simul::math::Vector3 X2, float cloud_base_z, float w, float h)
Get the physical extents of the cloud volume in the x, y and z directions.

### <a name="GetOrigin"/>simul::math::Vector3 GetOrigin(simul::math::Vector3 windOffset, float cloud_base_z, float w)
get the effective origin in world co-ordinates, including wind offsets:

### <a name="GetTransformLightspaceToCloudspaceMatrix"/>float  const * GetTransformLightspaceToCloudspaceMatrix(unsigned int axis, simul::math::Vector3 dir, simul::math::Vector3 origin, simul::math::Vector3 scales, float cloud_base_z, float w, float h)
Get a 4x4 matrix to transform from lightspace to cloudspace.

### <a name="GetTransformToLightspaceMatrix"/>float  const * GetTransformToLightspaceMatrix(unsigned int axis, simul::math::Vector3 dir, simul::math::Vector3 origin, simul::math::Vector3 scales)
Get a 4x4 matrix to transform from real space to lightspace.

### <a name="NeedsRelight"/>bool NeedsRelight()
Have properties changed that cause relighting to be necessary - either the light has moved
or the cloud density grid has changed.

### <a name="SetRelight"/>void SetRelight()
Force relighting of the volume. Usually unnecessary.

### <a name="StateStreamIn"/>std::istream  & StateStreamIn(std::istream is)
Stream/load from the std::isteam is.

### <a name="StateStreamOut"/>std::ostream  & StateStreamOut(std::ostream os)
Stream/save to the std::osteam os.

### <a name="StreamIn"/>std::istream  & StreamIn(std::istream is)
Stream/load from the std::isteam is.

### <a name="StreamOut"/>std::ostream  & StreamOut(std::ostream os)
Stream/save to the std::osteam os.
