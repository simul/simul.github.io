---
title: ProfilingInterface
layout: reference
weight: 0
---
class ProfilingInterface
===

| Include: | Clouds/CloudKeyframer.h |


[simul::base::BaseProfilingInterface](baseprofilinginterface)

Functions
---

|  | [ProfilingInterface](#ProfilingInterface)() |
| void | [Begin](#Begin)(char) |
| void | [End](#End)() |
| void | [EndFrame](#EndFrame)() |


Base Classes
---
[simul::base::BaseProfilingInterface](baseprofilinginterface)

Functions
---

### <a name="ProfilingInterface"/> ProfilingInterface()
simul::base::DefaultProfiler inherits from ProfilingInterface to measure CPU performance.

### <a name="Begin"/>void Begin(char)
Mark the start of a profiling block.

### <a name="End"/>void End()
Mark the end of a profiling block.

### <a name="EndFrame"/>void EndFrame()
Call this at the start of the frame to reset values.
