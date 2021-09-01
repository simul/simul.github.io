---
title: CloudLighting
layout: reference
weight: 0
---
class CloudLighting
===

| Include: | Clouds/CloudLighting.h |



Functions
---

|  | [CloudLighting](#CloudLighting)() |
|  | [~CloudLighting](#~CloudLighting)() |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [RelightBlock](#RelightBlock)(simul::crossplatform::DeviceContext deviceContext, int3 blockPos, int3 blockFill, vec3 dir_to_light, simul::clouds::CloudWindow cloudWindow, simul::clouds::CloudRenderingOptions cloudRenderingOptions, simul::crossplatform::Texture cloud_texture, simul::crossplatform::Texture light_texture, bool init) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform r) |


Functions
---
<a name="CloudLighting"></a>
###  CloudLighting()
Constructor
<a name="~CloudLighting"></a>
###  ~CloudLighting()
Destructor
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the renderer.
<a name="RecompileShaders"></a>
### void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.
<a name="RelightBlock"></a>
### void RelightBlock(simul::crossplatform::DeviceContext deviceContext, int3 blockPos, int3 blockFill, vec3 dir_to_light, simul::clouds::CloudWindow cloudWindow, simul::clouds::CloudRenderingOptions cloudRenderingOptions, simul::crossplatform::Texture cloud_texture, simul::crossplatform::Texture light_texture, bool init)
Calculate the cloud lighting
<a name="RestoreDeviceObjects"></a>
### void RestoreDeviceObjects(simul::crossplatform::RenderPlatform r)
Platform-dependent function called when initializing the renderer.
