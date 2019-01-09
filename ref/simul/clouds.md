---
title: clouds
layout: reference
weight: 0
---
namespace clouds
===

| Include: | Clouds/CloudRenderingOptions.h |

The function that returns how dense clouds should be at the stated position, where x, y and z are between
zero and one in the cloud volume.
  


Classes and Structures
---

| class [BaseGpuCloudGenerator](clouds/basegpucloudgenerator) |  |
| class [BaseLightningRenderer](clouds/baselightningrenderer) |  |
| class [BaseWeatherRenderer](clouds/baseweatherrenderer) |  |
| class [CellularCloudGrid](clouds/cellularcloudgrid) |  |
| class [CellularCloudNode](clouds/cellularcloudnode) |  |
| struct [CloudGeometryHelper](clouds/cloudgeometryhelper) |  |
| class [CloudGridInterface](clouds/cloudgridinterface) |  |
| class [CloudInterface](clouds/cloudinterface) |  |
| struct [CloudKeyframe](clouds/cloudkeyframe) |  |
| class [CloudKeyframer](clouds/cloudkeyframer) |  |
| class [CloudProperties](clouds/cloudproperties) |  |
| class [CloudRenderer](clouds/cloudrenderer) | Class for real-time volumetric cloud rendering.<br> |
| struct [CloudVolume](clouds/cloudvolume) |  |
| struct [DepthTextureStruct](clouds/depthtexturestruct) |  |
| class [Environment](clouds/environment) |  |
| struct [ExportLightningStrike](clouds/exportlightningstrike) |  |
| class [FastCloudNode](clouds/fastcloudnode) |  |
| class [HumidityCallbackInterface](clouds/humiditycallbackinterface) |  |
| class [MixedResolutionCompositor](clouds/mixedresolutioncompositor) |  |
| struct [PointSource](clouds/pointsource) |  |
| struct [PrecipitationRegion](clouds/precipitationregion) |  |
| class [PrecipitationRenderer](clouds/precipitationrenderer) |  |
| struct [SelectionIdentifier](clouds/selectionidentifier) |  |
| class [Skylight](clouds/skylight) |  |
| class [TimedNoise3D](clouds/timednoise3d) |  |
| class [TrueSkyRenderer](clouds/trueskyrenderer) | <br> |
| class [TwoResFramebuffer](clouds/tworesframebuffer) |  |


The function that returns how dense clouds should be at the stated position, where x, y and z are between
zero and one in the cloud volume.
  


Typedefs
---

**CloudTexelType**  By defining this typedef, we ensure that cloud texels are treated as 32-bit.

**VolumeMap**  Custom volume.

Enums
---

**TrueSkyRenderMode**  A class to manage interpolation between cloud states over time.
