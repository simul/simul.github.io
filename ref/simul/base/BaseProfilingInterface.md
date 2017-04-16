---
title: BaseProfilingInterface
layout: reference
---
class simul::base::BaseProfilingInterface
===
void Clear(p)
------

char GetDebugText(st)
------

/ Gets the profiling report as text.
/
/ \param        st Determines if the text should be returned as HTML, including colour formatting.
/
/ \return       null if it fails, else the debug text.
ProfileData GetEvent(,)
------

! Get profile data for the event at index i. Returns NULL for i&lt;0 or i&gt;= number of events.
! Null parent means the top-level events.
int GetMaxLevel()
------

! Call this to get the maximum level of the profiling tree.
void SetMaxLevel(m)
------

! Call this to set the maximum level of the profiling tree.
void StartFrame()
------

! Call this at the start of the frame to reset values.
ProfileData CreateProfileData()
------

std::string Walk(profileData,tab,parent_time,style)
------

void WalkReset(p)
------

