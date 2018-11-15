---
title: THREAD_TYPE
layout: reference
weight: 0
---
typedef THREAD_TYPE
===

| Include: | Base/ProfilingInterface.h |



Functions
---

| simul::base::ProfilingInterface * | [GetProfilingInterface](#GetProfilingInterface)(THREAD_TYPE thread_id) |
| void | [SetProfilingInterface](#SetProfilingInterface)(THREAD_TYPE thread_id, simul::base::ProfilingInterface p) |


Functions
---

### <a name="GetProfilingInterface"/>simul::base::ProfilingInterface * GetProfilingInterface(THREAD_TYPE thread_id)
Returns a pointer to the current CPU profiler.

### <a name="SetProfilingInterface"/>void SetProfilingInterface(THREAD_TYPE thread_id, simul::base::ProfilingInterface p)
Set the CPU profiler. Future use of SIMUL_PROFILE_START or SIMUL_COMBINED_PROFILE_START will use that profiler.
