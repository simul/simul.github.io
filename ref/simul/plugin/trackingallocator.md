---
title: TrackingAllocator
layout: reference
weight: 0
---
class TrackingAllocator
===

| Include: | PlugIns/TrueSkyPluginRender/TrackingAllocator.h |

A pseudo allocator that tracks video memory but does not actually allocate it.
  

[simul::base::MemoryInterface](../base/memoryinterface)

Functions
---

| void * | [AllocateTracked](#AllocateTracked)(size_t nbytes, size_t align, char fn) |
| void | [Deallocate](#Deallocate)(void ptr) |
| void | [TrackVideoMemory](#TrackVideoMemory)(void ptr, int nbytes, char fn) |
| void | [UntrackVideoMemory](#UntrackVideoMemory)(void ptr) |

A pseudo allocator that tracks video memory but does not actually allocate it.
  


Base Classes
---
[simul::base::MemoryInterface](../base/memoryinterface)

Functions
---

### <a name="AllocateTracked"/>void * AllocateTracked(size_t nbytes, size_t align, char fn)

### <a name="Deallocate"/>void Deallocate(void ptr)

### <a name="TrackVideoMemory"/>void TrackVideoMemory(void ptr, int nbytes, char fn)

### <a name="UntrackVideoMemory"/>void UntrackVideoMemory(void ptr)
Free the pointer from video memory tracking.
