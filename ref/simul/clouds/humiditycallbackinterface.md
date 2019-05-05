---
title: HumidityCallbackInterface
layout: reference
weight: 0
---
class HumidityCallbackInterface
===

| Include: | Clouds/CloudInterface.h |



Functions
---

| float | [GetHumidityMultiplier](#GetHumidityMultiplier)(float x, float y, float z) |


Functions
---

### <a name="GetHumidityMultiplier"/>float GetHumidityMultiplier(float x, float y, float z)
The function that returns how dense clouds should be at the stated position, where x, y and z are between
zero and one in the cloud volume.
