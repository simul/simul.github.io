---
title: MemoryInterfaceAllocator
layout: reference
---
classtemplate simul::base::MemoryInterfaceAllocator
===
[]()
MemoryInterfaceAllocator<T>::pointer address(r)
------

address
MemoryInterfaceAllocator<T>::const_pointer address(r)
------

MemoryInterfaceAllocator<T>::pointer allocate(cnt,)
------

memory allocation
void deallocate(p,)
------

MemoryInterfaceAllocator<T>::size_type max_size()
------

but because it causes so much trouble with Windows platforms, we just do this:
void construct(p,t)
------

construction/destruction
void destroy(p)
------

bool operator==()
------

bool operator!=(a)
------

