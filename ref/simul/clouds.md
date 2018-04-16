---
title: clouds
layout: reference
weight: 0
---
namespace clouds
===

| Include: | Clouds/Base2DCloudRenderer.h |

The namespace corresponding to the Clouds module.<br>


Classes and Structures
---

| class [BaseCloudRenderer](clouds/BaseCloudRenderer) | Class for real-time volumetric cloud rendering.<br> |
| class [BaseGpuCloudGenerator](clouds/BaseGpuCloudGenerator) |  |
| class [BaseLightningRenderer](clouds/BaseLightningRenderer) |  |
| class [BasePrecipitationRenderer](clouds/BasePrecipitationRenderer) |  |
| class [BaseWeatherRenderer](clouds/BaseWeatherRenderer) |  |
| class [CellularCloudGrid](clouds/CellularCloudGrid) |  |
| class [CellularCloudNode](clouds/CellularCloudNode) |  |
| struct [CloudGeometryHelper](clouds/CloudGeometryHelper) |  |
| class [CloudGridInterface](clouds/CloudGridInterface) |  |
| class [CloudInterface](clouds/CloudInterface) |  |
| struct [CloudKeyframe](clouds/CloudKeyframe) |  |
| class [CloudKeyframer](clouds/CloudKeyframer) |  |
| class [CloudProperties](clouds/CloudProperties) |  |
| struct [CloudRenderingOptions](clouds/CloudRenderingOptions) | This controls the rendering of clouds.<br> |
| struct [CloudVolume](clouds/CloudVolume) |  |
| struct [DepthTextureStruct](clouds/DepthTextureStruct) |  |
| class [Environment](clouds/Environment) |  |
| class [FastCloudNode](clouds/FastCloudNode) |  |
| class [HumidityCallbackInterface](clouds/HumidityCallbackInterface) |  |
| class [MixedResolutionCompositor](clouds/MixedResolutionCompositor) |  |
| struct [PointSource](clouds/PointSource) |  |
| struct [PrecipitationRegion](clouds/PrecipitationRegion) |  |
| struct [SelectionIdentifier](clouds/SelectionIdentifier) |  |
| class [Skylight](clouds/Skylight) |  |
| class [TimedNoise3D](clouds/TimedNoise3D) |  |
| class [TrueSkyRenderer](clouds/TrueSkyRenderer) | <br> |
| class [TwoResFramebuffer](clouds/TwoResFramebuffer) |  |

Functions
---

| vec3 | [TransformPosition](#TransformPosition)(simul::crossplatform::Quaterniond old_origin, simul::crossplatform::Quaterniond new_origin, vec3 old_pos) |

library: (SIMUL)/lib/(PLATFORM)/(COMPILER)/(ConfigurationName)/Clouds.lib

The Clouds library depends on the Base, Math, and Sky libraries.

  


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
