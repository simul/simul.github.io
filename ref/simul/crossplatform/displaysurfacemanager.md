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
  

[simul::crossplatform::DisplaySurfaceManagerInterface](displaysurfacemanagerinterface.html)

Functions
---

| void | [AddWindow](#AddWindow)(cp_hwnd h, simul::crossplatform::PixelFormat pfm) |
| void | [EndFrame](#EndFrame)(bool clear) |
| void | [RemoveWindow](#RemoveWindow)(cp_hwnd h) |
| void | [RenderAll](#RenderAll)(bool clear_list) |

A class for multiple swap chains (i.e. rendering windows) to share the same device.
With each graphics window it manages (identified by HWND's), WindowManager creates and manages a SwapChain instance.
  


Base Classes
---
[simul::crossplatform::DisplaySurfaceManagerInterface](displaysurfacemanagerinterface.html)

Functions
---
<a name="AddWindow"></a>
### void AddWindow(cp_hwnd h, simul::crossplatform::PixelFormat pfm)
Add a window. Creates a new Swap Chain.
<a name="EndFrame"></a>
### void EndFrame(bool clear)
<a name="RemoveWindow"></a>
### void RemoveWindow(cp_hwnd h)
Removes the window and destroys its associated Swap Chain.
<a name="RenderAll"></a>
### void RenderAll(bool clear_list)
Call from rendering thread.
