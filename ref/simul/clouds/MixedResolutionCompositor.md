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
Default constructor.

### <a name="~MixedResolutionCompositor"/> ~MixedResolutionCompositor()
Destructor.

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Invalidate device objects.

### <a name="RecompileShaders"/>void RecompileShaders()
Recompile shaders.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform renderPlatform)
Restore device objects.


Fields
---

**Minthreshold**  Avoid division by zero. Note: Be careful as 1 = 1m. so it will clip objects near the camera (10cm. works fine)

**renderPlatform**  The render platform.

**effect**  The depth reverse effect.

**mixedResolutionConstants**  The constant buffer for the shader effect.
