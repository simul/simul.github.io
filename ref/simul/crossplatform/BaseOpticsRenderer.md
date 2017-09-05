---
title: BaseOpticsRenderer
layout: reference
weight: 0
---
class BaseOpticsRenderer
===

| Include: | Platform/CrossPlatform/BaseOpticsRenderer.h |

A base class for rendering optical effects such as lens flare.


Functions
---

| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [RenderFlare](#RenderFlare)(simul::crossplatform::DeviceContext devicContext, float exposure, float dir, float light) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform r) |

A base class for rendering optical effects such as lens flare.
  


Functions
---

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
To be called when the rendering device is no longer valid.
To be called when the rendering device is no longer valid.

### <a name="RenderFlare"/>void RenderFlare(simul::crossplatform::DeviceContext devicContext, float exposure, float dir, float light)
Render the lens flares based on the given direction to the light, and its colour.
Render the lens flares based on the given direction to the light, and its colour.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform r)
To be called when a rendering device has been initialized.
To be called when a rendering device has been initialized.
