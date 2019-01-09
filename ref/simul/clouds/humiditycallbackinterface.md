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
  



A callback class to control the distribution of humidity in a cloud node. The value returned by
GetHumidityMultiplier is multiplied by the calculated cloud density.
Derive your own class from HumidityCallbackInterface and implement GetHumidityMultiplier,
then call <a href="fastcloudnode/addhumiditycallback">AddHumidityCallback </a>
to attach it to the cloud node.
  

