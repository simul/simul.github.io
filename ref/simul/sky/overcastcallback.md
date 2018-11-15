---
title: OvercastCallback
layout: reference
weight: 0
---
class OvercastCallback
===

| Include: | Sky/BaseSkyRenderer.h |

A virtual callback class for skies to get overcast information from cloud classes.
  


Functions
---

| simul::sky::OvercastStruct | [GetOvercastData](#GetOvercastData)(double time) |

A virtual callback class for skies to get overcast information from cloud classes.
  


Functions
---

### <a name="GetOvercastData"/>simul::sky::OvercastStruct GetOvercastData(double time)
For the specified time, get how overcast the sky will be, where the transition starts (e.g. the cloudbase), and what altitude it occurs over (e.g. how tall the clouds are).
