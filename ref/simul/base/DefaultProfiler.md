---
title: DefaultProfiler
layout: reference
---
class simul::base::DefaultProfiler
===
[ProfilingInterface](ProfilingInterface)
void Begin(txt)
------

! Mark the start of a profiling block.
ProfileData CreateProfileData()
------

void End()
------

! Allocate \a nbytes bytes of memory, aligned to \a align and return a pointer to them.
void EndFrame()
------

! Call this at the start of the frame to set-up the profiler for data-gathering.
bool GetCounter(i,str,t)
------

ProfileData GetEvent(parent,i)
------

void ResetMaximums()
------

float WalkOverhead(p,level)
------

