---
title: DisplaySurfaceManager
layout: reference
weight: 0
---
class DisplaySurfaceManager
===

| Include: | Platform/CrossPlatform/DisplaySurfaceManager.h |

A class for multiple swap chains (i.e. rendering windows) to share the same device.
With each graphics window it manages (identified by HWND's), WindowManager creates and manages a SwapChain instance.
  

[simul::crossplatform::DisplaySurfaceManagerInterface](DisplaySurfaceManagerInterface)

Functions
---

| void | [AddWindow](#AddWindow)(cp_hwnd h) |
| void | [EndFrame](#EndFrame)() |
| void | [RemoveWindow](#RemoveWindow)(cp_hwnd h) |

A class for multiple swap chains (i.e. rendering windows) to share the same device.
With each graphics window it manages (identified by HWND's), WindowManager creates and manages a SwapChain instance.
  


Base Classes
---
[simul::crossplatform::DisplaySurfaceManagerInterface](DisplaySurfaceManagerInterface)

Functions
---

### <a name="AddWindow"/>void AddWindow(cp_hwnd h)
Add a window. Creates a new Swap Chain.

### <a name="EndFrame"/>void EndFrame()

### <a name="RemoveWindow"/>void RemoveWindow(cp_hwnd h)
Removes the window and destroys its associated Swap Chain.
