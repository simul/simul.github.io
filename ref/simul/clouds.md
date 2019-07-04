---
title: clouds
layout: reference
weight: 0
---
namespace clouds
===

| Include: | Clouds/Clouds.h |

The namespace corresponding to the Clouds module.<br>


Classes and Structures
---

| class [CellularCloudGrid](clouds/cellularcloudgrid) |  |
| class [CellularCloudNode](clouds/cellularcloudnode) |  |
| class [CloudGridInterface](clouds/cloudgridinterface) |  |
| class [CloudInterface](clouds/cloudinterface) |  |
| class [CloudProperties](clouds/cloudproperties) |  |
| struct [ExportLightningStrike](clouds/exportlightningstrike) |  |
| class [FastCloudNode](clouds/fastcloudnode) |  |
| class [HumidityCallbackInterface](clouds/humiditycallbackinterface) |  |
| class [TimedNoise3D](clouds/timednoise3d) |  |

Functions
---

| vec3 | [TransformPosition](#TransformPosition)(simul::crossplatform::Quaterniond old_origin, simul::crossplatform::Quaterniond new_origin, vec3 old_pos) |

library: (SIMUL)/lib/(PLATFORM)/(COMPILER)/(ConfigurationName)/Clouds.lib

The Clouds library depends on the Base, Math, and Sky libraries.
![](/Images/CloudsInheritance.png)


  


Functions
---

### <a name="TransformPosition"/>vec3 TransformPosition(simul::crossplatform::Quaterniond old_origin, simul::crossplatform::Quaterniond new_origin, vec3 old_pos)
Transform a position in a previous frame of reference into a new frame. Assumes Earth radius 6378km, origin at sea level.
