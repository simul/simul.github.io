---
title: Timer
layout: reference
weight: 0
---
class Timer
===

| Include: | Base/Timer.h |

A microsecond timer.<br>


Functions
---

| float | [FinishTime](#FinishTime)() |
| void | [StartTime](#StartTime)() |
| float | [UpdateTime](#UpdateTime)() |
| float | [UpdateTimeSum](#UpdateTimeSum)() |

Provides timing to microsecond accuracy; results are reported in milliseconds.
  


Functions
---
<a name="FinishTime"></a>
### float FinishTime()
Stop timing: record the end of an event. The value Time can now be read.
<a name="StartTime"></a>
### void StartTime()
Start timing: record the start of an event.
<a name="UpdateTime"></a>
### float UpdateTime()
Update the value of Time and continue timing.
<a name="UpdateTimeSum"></a>
### float UpdateTimeSum()
Update the value of Time and continue timing.
