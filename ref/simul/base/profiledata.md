---
title: ProfileData
layout: reference
weight: 0
---
struct ProfileData
===

| Include: | Base/ProfilingInterface.h |

Define this to enable internal calls to the profiler, if it has been set with simul::base::SetProfilingInterface().
  



Define this to enable internal calls to the profiler, if it has been set with simul::base::SetProfilingInterface().
  


Fields
---

**maxTime**  < Time in ms taken by this event, including its children, in this instance.

**frameTime**  < The longest this event has taken in the present process.

**start**  < Time in ms taken by this event, including all the times it occurs in a frame.
