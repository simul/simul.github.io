---
title: BaseGpuSkyGenerator
layout: reference
weight: 0
---
class BaseGpuSkyGenerator
===

| Include: | Sky/BaseGpuSkyGenerator.h |



Functions
---

| bool | [CanPerformGPUGeneration](#CanPerformGPUGeneration)() |
| bool | [GetEnabled](#GetEnabled)() |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform) |


Functions
---

### <a name="CanPerformGPUGeneration"/>bool CanPerformGPUGeneration()
Return true if the derived class can make sky tables using the GPU.

### <a name="GetEnabled"/>bool GetEnabled()
Whether this GPU sky generator should be used to calculate the sky.")

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the Sky Generator.

### <a name="RecompileShaders"/>void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform)
Platform-dependent function called when initializing the Sky Generator.
