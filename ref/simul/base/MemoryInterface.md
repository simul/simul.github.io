---
title: MemoryInterface
layout: reference
---
class simul::base::MemoryInterface
===
void Allocate(nbytes)
------

! Allocate \a nbytes bytes of memory and return a pointer to them.
! Reimplement this in the derived class.
void Allocate(nbytes,align)
------

! Allocate \a nbytes bytes of memory, aligned to \a align and return a pointer to them. for unaligned, use align=0.
! Reimplement this in the derived class.
void AllocateTracked(,,)
------

! Reimplement this if needed in the derived class. The function_name can be ignored if you are not tracking memory allocations.
void AllocateVideoMemory(nbytes,align)
------

! Allocate \a nbytes bytes of memory, aligned to \a align and return a pointer to them. for unaligned, use align=0.
! Reimplement this in the derived class.
void AllocateVideoMemoryTracked(,,)
------

! Reimplement this if needed in the derived class. The function_name can be ignored if you are not tracking memory allocations.
void Deallocate(address)
------

! De-allocate the memory at \param address (requires that this memory was allocated with Allocate()).
! Implementations MUST ignore NULL values.
void DeallocateVideoMemory(address)
------

! \brief Free some Video memory
! Implementations MUST ignore NULL values.
int GetBytesAllocated(name)
------

char GetNameAtIndex(index)
------

int GetTotalBytesAllocated()
------

int GetTotalVideoBytesAllocated()
------

