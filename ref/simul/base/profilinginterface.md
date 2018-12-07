---
title: ProfilingInterface
layout: reference
weight: 0
---
class ProfilingInterface
===

| Include: | Base/ProfilingInterface.h |

simul::base::DefaultProfiler inherits from ProfilingInterface to measure CPU performance.
  

[simul::base::BaseProfilingInterface](baseprofilinginterface)

Functions
---

| void | [Begin](#Begin)(char) |
| void | [End](#End)() |
| void | [EndFrame](#EndFrame)() |

simul::base::DefaultProfiler inherits from ProfilingInterface to measure CPU performance.
  


Base Classes
---
[simul::base::BaseProfilingInterface](baseprofilinginterface)

Functions
---

### <a name="Begin"/>void Begin(char)
Mark the start of a profiling block.

### <a name="End"/>void End()
Mark the end of a profiling block.

### <a name="EndFrame"/>void EndFrame()
Call this at the start of the frame to reset values.
