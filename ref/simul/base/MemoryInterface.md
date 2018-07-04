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

### <a name="Allocate"/>void * Allocate(size_t nbytes)

### <a name="Allocate"/>void * Allocate(size_t nbytes, size_t align)

### <a name="AllocateTracked"/>void * AllocateTracked(size_t, size_t, char)
Reimplement this if needed in the derived class. The function_name can be ignored if you are not tracking memory allocations.

### <a name="AllocateVideoMemory"/>void * AllocateVideoMemory(size_t nbytes, size_t align)

### <a name="AllocateVideoMemoryTracked"/>void * AllocateVideoMemoryTracked(size_t, size_t, char)
Reimplement this if needed in the derived class. The function_name can be ignored if you are not tracking memory allocations.

### <a name="Deallocate"/>void Deallocate(void address)

### <a name="DeallocateVideoMemory"/>void DeallocateVideoMemory(void)
Free some Video memory

Implementations MUST ignore NULL values.
