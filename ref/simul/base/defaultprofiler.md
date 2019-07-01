---
title: DefaultProfiler
layout: reference
weight: 0
---
class DefaultProfiler
===

| Include: | Base/ProfilingInterface.h |

A simple profiler using simul::base::Timer
Usage is as follows:

* Declare and initialize:

simul::base::DefaultProfiler cpuProfiler;
...
simul::base::SetProfilingInterface(&cpuProfiler);

* Per-frame, at the start of the frame:

SIMUL_COMBINED_PROFILE_STARTFRAME(deviceContext.platform_context)

*  Wrap these around anything you want to measure:

SIMUL_COMBINED_PROFILE_START(deviceContext,"Element name")
SIMUL_COMBINED_PROFILE_END(deviceContext)

* At frame-end:

SIMUL_COMBINED_PROFILE_ENDFRAME(deviceContext)

* To obtain the profiling results

cpuProfiler.SetMaxLevel(any number from 0 up);
const char *text=cpuProfiler.GetDebugText(false);

and print this text to screen.

  

[simul::base::ProfilingInterface](profilinginterface)

Functions
---

| void | [Begin](#Begin)(char txt) |
| void | [End](#End)() |
| void | [EndFrame](#EndFrame)() |

A simple profiler using simul::base::Timer
Usage is as follows:

* Declare and initialize:

simul::base::DefaultProfiler cpuProfiler;
...
simul::base::SetProfilingInterface(&cpuProfiler);

* Per-frame, at the start of the frame:

SIMUL_COMBINED_PROFILE_STARTFRAME(deviceContext.platform_context)

*  Wrap these around anything you want to measure:

SIMUL_COMBINED_PROFILE_START(deviceContext,"Element name")
SIMUL_COMBINED_PROFILE_END(deviceContext)

* At frame-end:

SIMUL_COMBINED_PROFILE_ENDFRAME(deviceContext)

* To obtain the profiling results

cpuProfiler.SetMaxLevel(any number from 0 up);
const char *text=cpuProfiler.GetDebugText(false);

and print this text to screen.

  


Base Classes
---
[simul::base::ProfilingInterface](profilinginterface)

Functions
---

### <a name="Begin"/>void Begin(char txt)
Mark the start of a profiling block.

### <a name="End"/>void End()
Allocate nbytesbytes of memory, aligned to alignand return a pointer to them.

### <a name="EndFrame"/>void EndFrame()
Call this at the start of the frame to set-up the profiler for data-gathering.
