---
title: HumidityCallbackInterface
layout: reference
weight: 0
---
class HumidityCallbackInterface
===

| Include: | Clouds/CellularCloudNode.h |

A callback class to control the distribution of humidity in a cloud node. The value returned by
GetHumidityMultiplier is multiplied by the calculated cloud density.
Derive your own class from HumidityCallbackInterface and implement GetHumidityMultiplier,
then call <a href="fastcloudnode/addhumiditycallback">AddHumidityCallback </a>
to attach it to the cloud node.
  


Functions
---

| float | [GetHumidityMultiplier](#GetHumidityMultiplier)(float x, float y, float z) |

A callback class to control the distribution of humidity in a cloud node. The value returned by
GetHumidityMultiplier is multiplied by the calculated cloud density.
Derive your own class from HumidityCallbackInterface and implement GetHumidityMultiplier,
then call <a href="fastcloudnode/addhumiditycallback">AddHumidityCallback </a>
to attach it to the cloud node.
  


Functions
---

### <a name="GetHumidityMultiplier"/>float GetHumidityMultiplier(float x, float y, float z)
The function that returns how dense clouds should be at the stated position, where x, y and z are between
zero and one in the cloud volume.
