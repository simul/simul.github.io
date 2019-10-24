---
title: Referenced
layout: reference
weight: 0
---
class Referenced
===

| Include: | Base/Referenced.h |

Base class for classes that use reference-counting. This class handles the reference counts
and deletes the instance when the count reaches zero. Designed to be used with
simul::base::SmartPtr.
  


Functions
---

| void | [intrusive_ptr_add_ref](#intrusive_ptr_add_ref)() |
| void | [intrusive_ptr_release](#intrusive_ptr_release)() |
| int | [referenceCount](#referenceCount)() |
| void | [PrepareToDestroy](#PrepareToDestroy)() |

Base class for classes that use reference-counting. This class handles the reference counts
and deletes the instance when the count reaches zero. Designed to be used with
simul::base::SmartPtr.
  


Functions
---
<a name="intrusive_ptr_add_ref"></a>
### void intrusive_ptr_add_ref()
Increment the reference count by one.
<a name="intrusive_ptr_release"></a>
### void intrusive_ptr_release()
Decrement the reference count by one, delete if zero.
<a name="referenceCount"></a>
### int referenceCount()
Return the number of pointers referencing this object.
<a name="PrepareToDestroy"></a>
### void PrepareToDestroy()
Enact all destruction code that needs to rely on the derived class's virtual functions
because destructors can't use virtuals properly.
