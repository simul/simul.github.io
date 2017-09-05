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
Default constructor.

### <a name="~MixedResolutionCompositor"/> ~MixedResolutionCompositor()
Destructor.
Destructor.

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Invalidate device objects.
Invalidate device objects.

### <a name="RecompileShaders"/>void RecompileShaders()
Recompile shaders.
Recompile shaders.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform renderPlatform)
Restore device objects.

\param [in,out] renderPlatform  If non-null, the render platform.

Fields
---

**renderPlatform** The render platform. The render platform.

**effect** The depth reverse effect. The depth reverse effect.

**mixedResolutionConstants** The constant buffer for the shader effect. The constant buffer for the shader effect.
