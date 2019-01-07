---
title: GpuProfiler
layout: reference
weight: 0
---
class GpuProfiler
===

| Include: | Platform/CrossPlatform/GpuProfiler.h |


The Simul GPU profiler. Usage is as follows:

* On initialization, when you have a device pointer:

                simul::crossplatform::GpuProfiler::GetGlobalProfiler().Initialize(pd3dDevice);

* On shutdown, or whenever the device is changed or lost:

                simul::crossplatform::GpuProfiler::GetGlobalProfiler().Uninitialize();

* Per-frame, at the start of the frame:

                simul::base::SetGpuProfilingInterface(deviceContext.platform_context,&simul::crossplatform::GpuProfiler::GetGlobalProfiler());
                SIMUL_COMBINED_PROFILE_STARTFRAME(deviceContext.platform_context)

*  Wrap these around anything you want to measure:

                SIMUL_COMBINED_PROFILE_START(deviceContext,"Element name")
                SIMUL_COMBINED_PROFILE_END(deviceContext)

* At frame-end:

                SIMUL_COMBINED_PROFILE_END(deviceContext)

* To obtain the profiling results - pass true if you want HTML output:

                const char *text=simul::dx11::Profiler::GetGlobalProfiler().GetDebugText(as_html);

  

[simul::crossplatform::GpuProfilingInterface](gpuprofilinginterface)

Functions
---

| void | [EndFrame](#EndFrame)(simul::crossplatform::DeviceContext deviceContext) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform r) |
| void | [StartFrame](#StartFrame)(simul::crossplatform::DeviceContext deviceContext) |


The Simul GPU profiler. Usage is as follows:

* On initialization, when you have a device pointer:

                simul::crossplatform::GpuProfiler::GetGlobalProfiler().Initialize(pd3dDevice);

* On shutdown, or whenever the device is changed or lost:

                simul::crossplatform::GpuProfiler::GetGlobalProfiler().Uninitialize();

* Per-frame, at the start of the frame:

                simul::base::SetGpuProfilingInterface(deviceContext.platform_context,&simul::crossplatform::GpuProfiler::GetGlobalProfiler());
                SIMUL_COMBINED_PROFILE_STARTFRAME(deviceContext.platform_context)

*  Wrap these around anything you want to measure:

                SIMUL_COMBINED_PROFILE_START(deviceContext,"Element name")
                SIMUL_COMBINED_PROFILE_END(deviceContext)

* At frame-end:

                SIMUL_COMBINED_PROFILE_END(deviceContext)

* To obtain the profiling results - pass true if you want HTML output:

                const char *text=simul::dx11::Profiler::GetGlobalProfiler().GetDebugText(as_html);

  


Base Classes
---
[simul::crossplatform::GpuProfilingInterface](gpuprofilinginterface)

Functions
---

### <a name="EndFrame"/>void EndFrame(simul::crossplatform::DeviceContext deviceContext)
Call this after all timeable events in a frame have completed. It is acceptable
to call EndFrame() without having first called StartFrame() - this has no effect.

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Call this when the profiler is to be shut-down, or the device pointer has been lost or changed.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform r)
Call this when the profiler is to be initialized with a device pointer - must be done before use.

### <a name="StartFrame"/>void StartFrame(simul::crossplatform::DeviceContext deviceContext)
Call this before any timeable events in a frame.
