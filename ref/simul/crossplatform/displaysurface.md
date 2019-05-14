---
title: DisplaySurface
layout: reference
weight: 0
---
class DisplaySurface
===

| Include: | Platform/CrossPlatform/DisplaySurface.h |



Functions
---

| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(cp_hwnd handle, simul::crossplatform::RenderPlatform renderPlatform, bool m_vsync_enabled, int numerator, int denominator, simul::crossplatform::PixelFormat outFmt) |


Functions
---

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the display surface.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(cp_hwnd handle, simul::crossplatform::RenderPlatform renderPlatform, bool m_vsync_enabled, int numerator, int denominator, simul::crossplatform::PixelFormat outFmt)
Platform-dependent function called when initializing the display surface.

Fields
---

**mViewId**  The id assigned by the renderer to correspond to this hwnd
