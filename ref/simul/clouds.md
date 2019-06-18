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

| class [BaseGpuCloudGenerator](clouds/basegpucloudgenerator) |  |
| class [BaseLightningRenderer](clouds/baselightningrenderer) |  |
| class [CellularCloudGrid](clouds/cellularcloudgrid) |  |
| class [CellularCloudNode](clouds/cellularcloudnode) |  |
| struct [CloudGeometryHelper](clouds/cloudgeometryhelper) |  |
| class [CloudGridInterface](clouds/cloudgridinterface) |  |
| class [CloudInterface](clouds/cloudinterface) |  |
| struct [CloudKeyframe](clouds/cloudkeyframe) |  |
| class [CloudKeyframer](clouds/cloudkeyframer) |  |
| class [CloudProperties](clouds/cloudproperties) |  |
| class [CloudRenderer](clouds/cloudrenderer) | Class for real-time volumetric cloud rendering.<br> |
| struct [CloudRenderingOptions](clouds/cloudrenderingoptions) | This controls the rendering of clouds.<br> |
| struct [CloudVolume](clouds/cloudvolume) |  |
| struct [DepthTextureStruct](clouds/depthtexturestruct) |  |
| class [DoLightSteps](clouds/dolightsteps) |  |
| struct [ExportLightningStrike](clouds/exportlightningstrike) |  |
| class [FastCloudNode](clouds/fastcloudnode) |  |
| class [MixedResolutionCompositor](clouds/mixedresolutioncompositor) |  |
| struct [PointSource](clouds/pointsource) |  |
| struct [PrecipitationRegion](clouds/precipitationregion) |  |
| class [PrecipitationRenderer](clouds/precipitationrenderer) |  |
| struct [SelectionIdentifier](clouds/selectionidentifier) |  |
| class [Skylight](clouds/skylight) |  |
| class [TimedNoise3D](clouds/timednoise3d) |  |
| class [TrueSkyRenderer](clouds/trueskyrenderer) | <br> |

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

Typedefs
---

**CloudTexelType**  By defining this typedef, we ensure that cloud texels are treated as 32-bit.

**VolumeMap**  Custom volume.

Enums
---

**TrueSkyRenderMode**  A class to manage interpolation between cloud states over time.
