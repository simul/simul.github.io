---
title: SmartPtr
layout: reference
weight: 0
---
classtemplate SmartPtr
===

| Include: | Base/SmartPtr.h |

A smart pointer class that uses intrusive reference counting.
The following functions must exist for the pointed-to class:

void intrusive_ptr_add_ref(T * p);

void intrusive_ptr_release(T * p);

The usual way to do this is to have the pointed-to class inherit from simul::base::Referenced.
The object is responsible for destroying itself when its ref-count goes to zero.

For example:

class TheClass: public simul::base::Referenced
{
public:
TheClass():simul::base::Referenced()
{
}
virtual ~TheClass()
{
}
void DoSomeAction()
{
}
};

...

{
simul::base::SmartPtr<TheClass> classInstance=new TheClass;
// now the instance has a reference-count of 1.

classInstance->DoSomeAction();
...

// when the SmartPtr goes out of scope, the reference count is decremented.
// and as it's now zero, the class instance deletes itself.
}

  



A smart pointer class that uses intrusive reference counting.
The following functions must exist for the pointed-to class:

void intrusive_ptr_add_ref(T * p);

void intrusive_ptr_release(T * p);

The usual way to do this is to have the pointed-to class inherit from simul::base::Referenced.
The object is responsible for destroying itself when its ref-count goes to zero.

For example:

class TheClass: public simul::base::Referenced
{
public:
TheClass():simul::base::Referenced()
{
}
virtual ~TheClass()
{
}
void DoSomeAction()
{
}
};

...

{
simul::base::SmartPtr<TheClass> classInstance=new TheClass;
// now the instance has a reference-count of 1.

classInstance->DoSomeAction();
...

// when the SmartPtr goes out of scope, the reference count is decremented.
// and as it's now zero, the class instance deletes itself.
}

  

