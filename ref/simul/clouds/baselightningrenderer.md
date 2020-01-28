---
title: BaseLightningRenderer
layout: reference
weight: 0
---
class BaseLightningRenderer
===

| Include: | Clouds/BaseLightningRenderer.h |

The renderer for lightning.
  


Functions
---

|  | [BaseLightningRenderer](#BaseLightningRenderer)(simul::sky::BaseSkyInterface sk) |
|  | [~BaseLightningRenderer](#~BaseLightningRenderer)() |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [PreRenderUpdate](#PreRenderUpdate)(simul::crossplatform::DeviceContext deviceContext, float real_time) |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [Render](#Render)(simul::crossplatform::DeviceContext deviceContext, simul::clouds::CloudKeyframer cloudKeyframer, simul::crossplatform::Texture depth_tex, vec4 depthViewportXYWH, simul::clouds::TransparencyAtmospherics t, float brightnessToUnity, simul::clouds::BaseWeatherRenderer weatherRenderer) |
| void | [RenderOverlay](#RenderOverlay)(simul::crossplatform::DeviceContext deviceContext, simul::clouds::Storm) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform r) |

The renderer for lightning.
  


Functions
---
<a name="BaseLightningRenderer"></a>
###  BaseLightningRenderer(simul::sky::BaseSkyInterface sk)
Constructor
<a name="~BaseLightningRenderer"></a>
###  ~BaseLightningRenderer()
Destructor
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the lightning renderer.
<a name="PreRenderUpdate"></a>
### void PreRenderUpdate(simul::crossplatform::DeviceContext deviceContext, float real_time)
Once per-frame update. Do this before any rendering each frame.
<a name="RecompileShaders"></a>
### void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.
<a name="Render"></a>
### void Render(simul::crossplatform::DeviceContext deviceContext, simul::clouds::CloudKeyframer cloudKeyframer, simul::crossplatform::Texture depth_tex, vec4 depthViewportXYWH, simul::clouds::TransparencyAtmospherics t, float brightnessToUnity, simul::clouds::BaseWeatherRenderer weatherRenderer)
Main render call
<a name="RenderOverlay"></a>
### void RenderOverlay(simul::crossplatform::DeviceContext deviceContext, simul::clouds::Storm)
Render debug information
<a name="RestoreDeviceObjects"></a>
### void RestoreDeviceObjects(simul::crossplatform::RenderPlatform r)
Platform-dependent function called when initializing the lightning renderer.

Variables
---
