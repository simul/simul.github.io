---
title: CloudWindowEditor
layout: reference
weight: 0
---
class CloudWindowEditor
===

| Include: | Clouds/CloudRenderer.h |


[simul::base::BaseMouseHandler](/ref/simul/base/basemousehandler.html)

Functions
---

|  | [CloudWindowEditor](#CloudWindowEditor)() |
| simul::crossplatform::Quaterniond | [WindowPosToQuaternion](#WindowPosToQuaternion)(int2 pos) |


Base Classes
---
[simul::base::BaseMouseHandler](/ref/simul/base/basemousehandler.html)

Functions
---
<a name="CloudWindowEditor"></a>
###  CloudWindowEditor()
An onscreen editor for the CloudWindow. This handles mouse behaviour, but is renderer-independent: it is passed as a pointer to the cloud window editor render funcion.
<a name="WindowPosToQuaternion"></a>
### simul::crossplatform::Quaterniond WindowPosToQuaternion(int2 pos)
Convert from window pixel position to quaternion on the sphere.
