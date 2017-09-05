---
title: Cloud2DGeometryHelper
layout: reference
weight: 0
---
class Cloud2DGeometryHelper
===

| Include: | Clouds/Cloud2DGeometryHelper.h |

A helper class that generates a list of distances for rendering the cloud layer.

[simul::base::Referenced](../base/Referenced)
[simul::base::MemoryUsageInterface](../base/MemoryUsageInterface)

Functions
---

| void | [GetGrid](#GetGrid)(unsigned int el, unsigned int az) |
| unsigned int | [GetMemoryUsage](#GetMemoryUsage)() |
| simul::clouds::Cloud2DGeometryHelper::VertexVector  const & | [GetVertices](#GetVertices)() |
| void | [Initialize](#Initialize)(unsigned int max_num_layers) |
| void | [SetGrid](#SetGrid)(unsigned int el, unsigned int az) |
| void | [Update](#Update)(simul::math::Vector3 view_pos, simul::math::Vector3 wind_offset, simul::math::Vector3 view, simul::math::Vector3 up) |

A helper class that generates a list of distances for rendering the cloud layer.
  


Base Classes
---
[simul::base::Referenced](../base/Referenced)
[simul::base::MemoryUsageInterface](../base/MemoryUsageInterface)

Functions
---

### <a name="GetGrid"/>void GetGrid(unsigned int el, unsigned int az)
Get the elevation and azimuth grid sizes.
Get the elevation and azimuth grid sizes.

### <a name="GetMemoryUsage"/>unsigned int GetMemoryUsage()
Get the amount of memory this class instance uses, in bytes.
Get the amount of memory this class instance uses, in bytes.

### <a name="GetVertices"/>simul::clouds::Cloud2DGeometryHelper::VertexVector  const & GetVertices()
Get the vertex list - these are indexed by the QuadStrip struct.
Get the vertex list - these are indexed by the QuadStrip struct.

### <a name="Initialize"/>void Initialize(unsigned int max_num_layers)
Set up this Cloud2DGeometryHelper
Set up this Cloud2DGeometryHelper

### <a name="SetGrid"/>void SetGrid(unsigned int el, unsigned int az)
Set the elevation/azimuth grid sizes.
Set the elevation/azimuth grid sizes.

### <a name="Update"/>void Update(simul::math::Vector3 view_pos, simul::math::Vector3 wind_offset, simul::math::Vector3 view, simul::math::Vector3 up)
Call this function once per frame with updated view position **view_pos**, the direction the camera is pointed **view** and
the camera **up** direction.
From this information the helper calculates the values for all the slices.
Call this function once per frame with updated view position **view_pos**, the direction the camera is pointed **view** and
the camera **up** direction.
From this information the helper calculates the values for all the slices.
