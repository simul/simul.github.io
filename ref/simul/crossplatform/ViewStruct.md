---
title: ViewStruct
layout: reference
weight: 0
---
struct ViewStruct
===

| Include: | Sky/BaseAtmosphericsRenderer.h |

A simple struct encapsulating a view and a projection matrix.


Functions
---

| void | [Init](#Init)() |

A simple struct encapsulating a view and a projection matrix.
  


Functions
---

### <a name="Init"/>void Init()
< How to interpret any depth texture passed from outside.
MUST be called whenever view or proj change.
< How to interpret any depth texture passed from outside.
MUST be called whenever view or proj change.

Fields
---

**view** < An id unique to each rendered view, but persistent across frames. < An id unique to each rendered view, but persistent across frames.

**proj** < The view matrix. If considered as row-major, position information is in the 4th row. < The view matrix. If considered as row-major, position information is in the 4th row.

**invViewProj** < The projection matrix, row-major. < The projection matrix, row-major.

**depthTextureStyle** < THe viewing frustum, calculated from the proj matrix and stored for convenience using simul::crossplatform::GetFrustumFromProjectionMatrix. < THe viewing frustum, calculated from the proj matrix and stored for convenience using simul::crossplatform::GetFrustumFromProjectionMatrix.
