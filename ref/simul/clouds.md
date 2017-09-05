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
| class [BaseGpuCloudGenerator](clouds/BaseGpuCloudGenerator) | Base class for generating cloud volumes on the GPU. |
| class [BaseLightningRenderer](clouds/BaseLightningRenderer) | The renderer for lightning. |
| class [BasePrecipitationRenderer](clouds/BasePrecipitationRenderer) | The class that renders rain and snow. |
| class [BaseWeatherRenderer](clouds/BaseWeatherRenderer) | The main base class for all weather renderers, such as SimulGLWeatherRenderer,<br>SimulWeatherRenderer (DX11) etc.<br> |
| class [CellularCloudGrid](clouds/CellularCloudGrid) | A cellular automata grid of cloud densities.<br>Don't create a CellularCloudGrid directly, instead, create a FastCloudNode. |
| class [CellularCloudNode](clouds/CellularCloudNode) | Don't create a CellularCloudNode directly, instead, use the derived class FastCloudNode. |
| class [Cloud2DGeometryHelper](clouds/Cloud2DGeometryHelper) | A helper class that generates a list of distances for rendering the cloud layer. |
| struct [CloudGeometryHelper](clouds/CloudGeometryHelper) | A helper class |
| class [CloudGridInterface](clouds/CloudGridInterface) | The virtual interface for controlling and reading a grid of cloud data. |
| class [CloudInterface](clouds/CloudInterface) | The virtual interface for controlling and reading cloud data. |
| struct [CloudKeyframe](clouds/CloudKeyframe) | The keyframe structure for clouds, used by simul::clouds::CloudKeyframer. |
| class [CloudKeyframer](clouds/CloudKeyframer) | A class to manage interpolation between cloud states over time.<br>Typically, a CloudKeyframer is created and updated by its ::clouds::Environment Environment\endlink.<br> |
| class [CloudProperties](clouds/CloudProperties) | A virtual interface that returns the keyframe-independent cloud properties. |
| struct [CloudRenderingOptions](clouds/CloudRenderingOptions) | This controls the rendering of clouds.<br> |
| struct [CloudVolume](clouds/CloudVolume) | Custom volume. the transform matrix and scales are in km. |
| class [Environment](clouds/Environment) | The main class that manages environment data. Usually, you will create a single instance of Environment, which will persist while your<br>         3D game or simulation world is active.<br> |
| class [FastCloudNode](clouds/FastCloudNode) | Create an instance of FastCloudNode to generate cloud data for rendering.<br>This class can use a custom memory allocator, because it is derived from<br>a ResourceUser<> of simul::base::MemoryInterface. To use this feature<br>call SetResource( simul::base::MemoryInterface *) with a pointer to a<br>an instance of a class derived from MemoryInterface. |
| class [HumidityCallbackInterface](clouds/HumidityCallbackInterface) | A callback class to control the distribution of humidity in a cloud node. The value returned by<br>GetHumidityMultiplier is multiplied by the calculated cloud density.<br>Derive your own class from HumidityCallbackInterface and implement GetHumidityMultiplier,<br>then call ::clouds::FastCloudNode::AddHumidityCallback AddHumidityCallback  attach it to the cloud node. |
| class [MixedResolutionCompositor](clouds/MixedResolutionCompositor) | A class to render mixed-resolution depth buffers. |
| struct [PointSource](clouds/PointSource) | A point light source |
| struct [PrecipitationRegion](clouds/PrecipitationRegion) | A structure defining an area where there is rain or snow.<br>If **regional** is false, it is everywhere. |
| struct [SelectionIdentifier](clouds/SelectionIdentifier) | A struct to identify selections of keyframes, layers etc. |
| class [Skylight](clouds/Skylight) | A class to capture light from the sky in real time for diffuse and specular lighting. |
| class [TimedNoise3D](clouds/TimedNoise3D) | A 3D noise generator used for cloud volumes, where the value returned depends on normalized spatial co-ordinates, and on normalized time. |
| class [TwoResFramebuffer](clouds/TwoResFramebuffer) | A framebuffer class for mixed-resolution rendering. |

Functions
---

| vec3 | [TransformPosition](#TransformPosition)(simul::crossplatform::Quaterniond old_origin, simul::crossplatform::Quaterniond new_origin, vec3 old_pos) |

library: (SIMUL)/lib/(PLATFORM)/(COMPILER)/(ConfigurationName)/Clouds.lib

The Clouds library depends on the Base, Math, and Sky libraries.


  


Functions
---

### <a name="TransformPosition"/>vec3 TransformPosition(simul::crossplatform::Quaterniond old_origin, simul::crossplatform::Quaterniond new_origin, vec3 old_pos)
Transform a position in a previous frame of reference into a new frame. Assumes Earth radius 6378km, origin at sea level.
Transform a position in a previous frame of reference into a new frame. Assumes Earth radius 6378km, origin at sea level.

Typedefs
---

**CloudTexelType** By defining this typedef, we ensure that cloud texels are treated as 32-bit. By defining this typedef, we ensure that cloud texels are treated as 32-bit.

**VolumeMap** Custom volume. Custom volume.

Enums
---

**TrueSkyRenderMode** A class to manage interpolation between cloud states over time. A class to manage interpolation between cloud states over time.
