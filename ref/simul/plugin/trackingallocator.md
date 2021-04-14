---
title: TrackingAllocator
layout: reference
weight: 0
---
class TrackingAllocator
===

| Include: | PlugIns/TrueSkyPluginRender/TrackingAllocator.h |

A pseudo allocator that tracks video memory but does not actually allocate it.
  

[simul::base::MemoryInterface](../base/memoryinterface.html)

Functions
---

| void * | [AllocateTracked](#AllocateTracked)(size_t nbytes, size_t align, char fn) |
| void | [Deallocate](#Deallocate)(void ptr) |
| void | [TrackVideoMemory](#TrackVideoMemory)(void ptr, size_t nbytes, char fn) |
| void | [UntrackVideoMemory](#UntrackVideoMemory)(void ptr) |

A pseudo allocator that tracks video memory but does not actually allocate it.
  


Base Classes
---
[simul::base::MemoryInterface](../base/memoryinterface.html)

Functions
---
<a name="AllocateTracked"></a>
### void * AllocateTracked(size_t nbytes, size_t align, char fn)
Allocate nbytesbytes of memory, aligned to alignand return a pointer to them.
<a name="Deallocate"></a>
### void Deallocate(void ptr)
De-allocate the memory at address(requires that this memory was allocated with Allocate()).
<a name="TrackVideoMemory"></a>
### void TrackVideoMemory(void ptr, size_t nbytes, char fn)
Track (but don't allocate) nbytesbytes of memory.
<a name="UntrackVideoMemory"></a>
### void UntrackVideoMemory(void ptr)
Free the pointer from video memory tracking.
