---
title: Referenced
layout: reference
---
class simul::base::Referenced
===
void intrusive_ptr_add_ref()
------

! Increment the reference count by one.
void intrusive_ptr_release()
------

! Decrement the reference count by one, delete if zero.
Referenced operator=()
------

int referenceCount()
------

! Return the number of pointers referencing this object.
void PrepareToDestroy()
------

! Enact all destruction code that needs to rely on the derived class's virtual functions
! because destructors can't use virtuals properly.
