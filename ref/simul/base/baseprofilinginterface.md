---
title: BaseProfilingInterface
layout: reference
weight: 0
---
class BaseProfilingInterface
===

| Include: | Base/ProfilingInterface.h |

A virtual interface base class for classes that can profile for performance.
  


Functions
---

| char  const * | [GetDebugText](#GetDebugText)(simul::base::TextStyle st) |
| simul::base::ProfileData  const * | [GetEvent](#GetEvent)(simul::base::ProfileData, int) |
| int | [GetMaxLevel](#GetMaxLevel)() |
| void | [SetMaxLevel](#SetMaxLevel)(int m) |
| void | [StartFrame](#StartFrame)() |

A virtual interface base class for classes that can profile for performance.
  


Functions
---

### <a name="GetDebugText"/>char  const * GetDebugText(simul::base::TextStyle st)
Gets the profiling report as text.


### <a name="GetEvent"/>simul::base::ProfileData  const * GetEvent(simul::base::ProfileData, int)
Get profile data for the event at index i. Returns NULL for i<0 or i>= number of events.
Null parent means the top-level events.

### <a name="GetMaxLevel"/>int GetMaxLevel()
Call this to get the maximum level of the profiling tree.

### <a name="SetMaxLevel"/>void SetMaxLevel(int m)
Call this to set the maximum level of the profiling tree.

### <a name="StartFrame"/>void StartFrame()
Call this at the start of the frame to reset values.
