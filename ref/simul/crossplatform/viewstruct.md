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

Fields
---

**model**  < An id unique to each rendered view, but persistent across frames.

**proj**  < The view matrix. If considered as row-major, position information is in the 4th row.

**invViewProj**  < The projection matrix, row-major.

**cam_pos**  /math::Matrix4x4 modelView;

**depthTextureStyle**  < THe viewing frustum, calculated from the proj matrix and stored for convenience using simul::crossplatform::GetFrustumFromProjectionMatrix.
