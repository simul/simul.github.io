---
title: GpuProfilingInterface
layout: reference
weight: 0
---
class GpuProfilingInterface
===

| Include: | Platform/CrossPlatform/GpuProfiler.h |

A virtual interface base class for GPU performance measurement.
  

[simul::base::BaseProfilingInterface](../base/baseprofilinginterface.html)

Functions
---

| void | [Begin](#Begin)(simul::crossplatform::DeviceContext deviceContext, char) |
| void | [End](#End)(simul::crossplatform::DeviceContext deviceContext) |
| void | [EndFrame](#EndFrame)(simul::crossplatform::DeviceContext deviceContext) |
| char  const * | [GetDebugText](#GetDebugText)(simul::base::TextStyle st) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [StartFrame](#StartFrame)(simul::crossplatform::DeviceContext deviceContext) |

A virtual interface base class for GPU performance measurement.
  


Base Classes
---
[simul::base::BaseProfilingInterface](../base/baseprofilinginterface.html)

Functions
---
<a name="Begin"></a>
### void Begin(simul::crossplatform::DeviceContext deviceContext, char)
Mark the start of a render profiling block. Some API's require a context pointer.
<a name="End"></a>
### void End(simul::crossplatform::DeviceContext deviceContext)
Mark the end of the current render profiling block.
<a name="EndFrame"></a>
### void EndFrame(simul::crossplatform::DeviceContext deviceContext)
Call this at the end of the frame to prepare the data to be read.
<a name="GetDebugText"></a>
### char  const * GetDebugText(simul::base::TextStyle st)
Get the timing text per-frame.
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the profiler.
<a name="StartFrame"></a>
### void StartFrame(simul::crossplatform::DeviceContext deviceContext)
Call this at the start of the frame to reset values.
