---
title: TrackingAllocator
layout: reference
weight: 0
---
class TrackingAllocator
===

| Include: | Base/TrackingAllocator.h |

A pseudo allocator that tracks video memory but does not actually allocate it.
  

[simul::base::MemoryInterface](MemoryInterface)

Functions
---

| void * | [AllocateTracked](#AllocateTracked)(size_t nbytes, size_t align, char fn) |
| void | [Deallocate](#Deallocate)(void ptr) |
| void | [Shutdown](#Shutdown)() |
| void | [TrackVideoMemory](#TrackVideoMemory)(void ptr, int nbytes, char fn) |
| void | [UntrackVideoMemory](#UntrackVideoMemory)(void ptr) |

A pseudo allocator that tracks video memory but does not actually allocate it.
  


Base Classes
---
[simul::base::MemoryInterface](MemoryInterface)

Functions
---

### <a name="AllocateTracked"/>void * AllocateTracked(size_t nbytes, size_t align, char fn)

### <a name="Deallocate"/>void Deallocate(void ptr)

### <a name="Shutdown"/>void Shutdown()
Shut down and report any leaks.

### <a name="TrackVideoMemory"/>void TrackVideoMemory(void ptr, int nbytes, char fn)

### <a name="UntrackVideoMemory"/>void UntrackVideoMemory(void ptr)
Free the pointer from video memory tracking.
