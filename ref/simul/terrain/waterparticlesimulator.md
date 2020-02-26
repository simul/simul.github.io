---
title: WaterParticleSimulator
layout: reference
weight: 0
---
class WaterParticleSimulator
===

| Include: | Terrain/WaterParticleSimulator.h |



Functions
---

| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform renderPlatform) |


Functions
---
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the wavelets simulator.
<a name="RecompileShaders"></a>
### void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.
<a name="RestoreDeviceObjects"></a>
### void RestoreDeviceObjects(simul::crossplatform::RenderPlatform renderPlatform)
Platform-dependent function called when initializing the wavelets simulator.
