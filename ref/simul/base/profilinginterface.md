---
title: ProfilingInterface
layout: reference
weight: 0
---
class ProfilingInterface
===

| Include: | Base/ProfilingInterface.h |

simul::base::DefaultProfiler inherits from ProfilingInterface to measure CPU performance.
  

[simul::base::BaseProfilingInterface](baseprofilinginterface.html)

Functions
---

|  | [ProfilingInterface](#ProfilingInterface)() |
| void | [Begin](#Begin)(char) |
| void | [End](#End)() |
| void | [EndFrame](#EndFrame)() |

simul::base::DefaultProfiler inherits from ProfilingInterface to measure CPU performance.
  


Base Classes
---
[simul::base::BaseProfilingInterface](baseprofilinginterface.html)

Functions
---
<a name="ProfilingInterface"></a>
###  ProfilingInterface()
Constructor
<a name="Begin"></a>
### void Begin(char)
Mark the start of a profiling block.
<a name="End"></a>
### void End()
Mark the end of a profiling block.
<a name="EndFrame"></a>
### void EndFrame()
Call this at the start of the frame to reset values.
