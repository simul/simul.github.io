---
title: Timer
layout: reference
---
class simul::base::Timer
===
float AbsoluteTimeMS()
------

float FinishTime()
------

! Stop timing: record the end of an event. The value Time can now be read.
void StartTime()
------

! Start timing: record the start of an event.
float UpdateTime()
------

! Update the value of Time and continue timing.
float UpdateTimeSum()
------

! Update the value of Time and continue timing.
