---
title: clouds
layout: reference
weight: 0
---
namespace clouds
===

| Include: | Clouds/BaseGpuCloudGenerator.h |



Classes and Structures
---

| class [BaseGpuCloudGenerator](clouds/basegpucloudgenerator.html) |  |
| class [BaseLightningRenderer](clouds/baselightningrenderer.html) |  |
| class [CellularCloudGrid](clouds/cellularcloudgrid.html) |  |
| class [CellularCloudNode](clouds/cellularcloudnode.html) |  |
| struct [CloudGeometryHelper](clouds/cloudgeometryhelper.html) |  |
| class [CloudGridInterface](clouds/cloudgridinterface.html) |  |
| class [CloudInterface](clouds/cloudinterface.html) |  |
| struct [CloudKeyframe](clouds/cloudkeyframe.html) |  |
| class [CloudProperties](clouds/cloudproperties.html) |  |
| struct [CloudRenderingOptions](clouds/cloudrenderingoptions.html) | This controls the rendering of clouds.<br> |
| struct [CloudVolume](clouds/cloudvolume.html) |  |
| struct [DepthTextureStruct](clouds/depthtexturestruct.html) |  |
| struct [ExportLightningStrike](clouds/exportlightningstrike.html) |  |
| class [FastCloudNode](clouds/fastcloudnode.html) |  |
| class [HumidityCallbackInterface](clouds/humiditycallbackinterface.html) |  |
| class [MixedResolutionCompositor](clouds/mixedresolutioncompositor.html) |  |
| struct [PointSource](clouds/pointsource.html) |  |
| struct [PrecipitationRegion](clouds/precipitationregion.html) |  |
| struct [SelectionIdentifier](clouds/selectionidentifier.html) |  |
| class [Skylight](clouds/skylight.html) |  |
| class [TrueSkyRenderer](clouds/trueskyrenderer.html) | <br> |

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

Typedefs
---

**CloudTexelType**  By defining this typedef, we ensure that cloud texels are treated as 32-bit.

**VolumeMap**  Custom volume.

Enums
---

**TrueSkyRenderMode**  A class to manage interpolation between cloud states over time.
