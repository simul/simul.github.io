---
title: DeviceContext
layout: reference
weight: 0
---
struct DeviceContext
===

| Include: | Sky/BaseAtmosphericsRenderer.h |



Functions
---

| simul::crossplatform::GpuProfilingInterface * | [GetGpuProfilingInterface](#GetGpuProfilingInterface)(simul::crossplatform::DeviceContext context) |
| void | [SetGpuProfilingInterface](#SetGpuProfilingInterface)(simul::crossplatform::DeviceContext context, simul::crossplatform::GpuProfilingInterface p) |


Functions
---
<a name="GetGpuProfilingInterface"></a>
### simul::crossplatform::GpuProfilingInterface * GetGpuProfilingInterface(simul::crossplatform::DeviceContext context)
Returns a pointer to the current GPU profiler.
<a name="SetGpuProfilingInterface"></a>
### void SetGpuProfilingInterface(simul::crossplatform::DeviceContext context, simul::crossplatform::GpuProfilingInterface p)
Set the GPU profilerFuture use of SIMUL_GPU_PROFILE_START or SIMUL_COMBINED_PROFILE_START will use that profiler.
