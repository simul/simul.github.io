---
title: View
layout: reference
weight: 0
---
class View
===

| Include: | Platform/CrossPlatform/View.h |

A class that encapsulates the generated mixed-resolution depth textures, and (optionally) a framebuffer with colour and depth.
One instance of View will be created and maintained for each live 3D view.
  


Functions
---

|  | [View](#View)() |
|  | [~View](#~View)() |
| simul::crossplatform::Texture * | [GetResolvedHDRBuffer](#GetResolvedHDRBuffer)() |
| int | [GetScreenHeight](#GetScreenHeight)() |
| int | [GetScreenWidth](#GetScreenWidth)() |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform renderPlatform) |
| void | [SetExternalFramebuffer](#SetExternalFramebuffer)(bool ext) |
| void | [SetResolution](#SetResolution)(int w, int h) |

A class that encapsulates the generated mixed-resolution depth textures, and (optionally) a framebuffer with colour and depth.
One instance of View will be created and maintained for each live 3D view.
  


Functions
---

### <a name="View"/> View()
Default constructor.

### <a name="~View"/> ~View()
Destructor.

### <a name="GetResolvedHDRBuffer"/>simul::crossplatform::Texture * GetResolvedHDRBuffer()
Gets resolved HDR buffer.

### <a name="GetScreenHeight"/>int GetScreenHeight()
Gets screen height.

### <a name="GetScreenWidth"/>int GetScreenWidth()
Gets screen width.

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the view.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform renderPlatform)
Platform-dependent function called when initializing the view.

### <a name="SetExternalFramebuffer"/>void SetExternalFramebuffer(bool ext)
Sets external framebuffer.

### <a name="SetResolution"/>void SetResolution(int w, int h)
Sets the resolution.

Fields
---

**viewType**  Type of view.

**ScreenWidth**  Width of the screen.

**ScreenHeight**  Height of the screen.

**useExternalFramebuffer**  True to use external framebuffer.

**hdrFramebuffer**  A framebuffer with depth.

**resolvedTexture**  The resolved texture.

**renderPlatform**  The render platform.
