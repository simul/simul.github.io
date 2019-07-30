---
title: MixedResolutionCompositor
layout: reference
weight: 0
---
class MixedResolutionCompositor
===

| Include: | Clouds/MixedResolutionCompositor.h |

A class to render mixed-resolution depth buffers.
  


Functions
---

|  | [MixedResolutionCompositor](#MixedResolutionCompositor)() |
|  | [~MixedResolutionCompositor](#~MixedResolutionCompositor)() |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform renderPlatform) |

A class to render mixed-resolution depth buffers.
  


Functions
---

### <a name="MixedResolutionCompositor"/> MixedResolutionCompositor()
Constructor.

### <a name="~MixedResolutionCompositor"/> ~MixedResolutionCompositor()
Destructor.

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the water Compositor.

### <a name="RecompileShaders"/>void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform renderPlatform)
Platform-dependent function called when initializing the Compositor.

Fields
---

**Minthreshold**  Avoid division by zero. Note: Be careful as 1 = 1m. so it will clip objects near the camera (10cm. works fine)

**renderPlatform**  The render platform.

**effect**  The depth reverse effect.

**mixedResolutionConstants**  The constant buffer for the shader effect.
