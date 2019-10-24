---
title: MemoryInterface
layout: reference
weight: 0
---
class MemoryInterface
===

| Include: | Base/MemoryInterface.h |

Inherit from MemoryInterface to take control of memory allocation for any class that uses
this interface as a resource.
  


Functions
---

| void * | [Allocate](#Allocate)(size_t nbytes) |
| void * | [Allocate](#Allocate)(size_t nbytes, size_t align) |
| void * | [AllocateTracked](#AllocateTracked)(size_t, size_t, char) |
| void * | [AllocateVideoMemory](#AllocateVideoMemory)(size_t nbytes, size_t align) |
| void * | [AllocateVideoMemoryTracked](#AllocateVideoMemoryTracked)(size_t, size_t, char) |
| void | [Deallocate](#Deallocate)(void address) |
| void | [DeallocateVideoMemory](#DeallocateVideoMemory)(void) |

Inherit from MemoryInterface to take control of memory allocation for any class that uses
this interface as a resource.
  


Functions
---
<a name="Allocate"></a>
### void * Allocate(size_t nbytes)
Allocate nbytes bytes of memory and return a pointer to them.
Reimplement this in the derived class.
<a name="Allocate"></a>
### void * Allocate(size_t nbytes, size_t align)
Allocate nbytes bytes of memory, aligned to align and return a pointer to them. for unaligned, use align=0.
Reimplement this in the derived class.
<a name="AllocateTracked"></a>
### void * AllocateTracked(size_t, size_t, char)
Reimplement this if needed in the derived class. The function_name can be ignored if you are not tracking memory allocations.
<a name="AllocateVideoMemory"></a>
### void * AllocateVideoMemory(size_t nbytes, size_t align)
Allocate nbytes bytes of memory, aligned to align and return a pointer to them. for unaligned, use align=0.
Reimplement this in the derived class.
<a name="AllocateVideoMemoryTracked"></a>
### void * AllocateVideoMemoryTracked(size_t, size_t, char)
Reimplement this if needed in the derived class. The function_name can be ignored if you are not tracking memory allocations.
<a name="Deallocate"></a>
### void Deallocate(void address)
De-allocate the memory at address(requires that this memory was allocated with Allocate()).
Implementations MUST ignore NULL values.
<a name="DeallocateVideoMemory"></a>
### void DeallocateVideoMemory(void)
Free some Video memory

Implementations MUST ignore NULL values.
