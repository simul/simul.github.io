---
title: Skylight
layout: reference
weight: 0
---
class Skylight
===

| Include: | Clouds/TrueSkyRenderer.h |



Functions
---

| bool | [GetSphericalHarmonics](#GetSphericalHarmonics)(simul::crossplatform::DeviceContext deviceContext, float targetShValues) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| bool | [Probe](#Probe)(simul::crossplatform::DeviceContext deviceContext, int mip_size, int face_index, uint2 pos, uint2 size, vec4 targetValuesFloat4) |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [Render](#Render)(simul::crossplatform::DeviceContext parentDeviceContext, simul::clouds::BaseWeatherRenderer baseWeatherRenderer, int cube_id, simul::crossplatform::BaseFramebuffer fb, int faceIndex, mat4 engineToSimulMatrix4x4, float blend, float exposure, float gamma) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform r) |
| void | [ShowDebug](#ShowDebug)(simul::crossplatform::DeviceContext deviceContext, int X, int Y, int w) |
| void | [Update](#Update)(simul::crossplatform::DeviceContext deviceContext, simul::clouds::BaseWeatherRenderer weatherRenderer) |


Functions
---

### <a name="GetSphericalHarmonics"/>bool GetSphericalHarmonics(simul::crossplatform::DeviceContext deviceContext, float targetShValues)

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Free the GPU objects.

### <a name="Probe"/>bool Probe(simul::crossplatform::DeviceContext deviceContext, int mip_size, int face_index, uint2 pos, uint2 size, vec4 targetValuesFloat4)

### <a name="RecompileShaders"/>void RecompileShaders()
Recompile the shaders for this class.

### <a name="Render"/>void Render(simul::crossplatform::DeviceContext parentDeviceContext, simul::clouds::BaseWeatherRenderer baseWeatherRenderer, int cube_id, simul::crossplatform::BaseFramebuffer fb, int faceIndex, mat4 engineToSimulMatrix4x4, float blend, float exposure, float gamma)
Fill in the texture.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform r)
Initialize GPU objects.

### <a name="ShowDebug"/>void ShowDebug(simul::crossplatform::DeviceContext deviceContext, int X, int Y, int w)
Show debug displays onscreen.

### <a name="Update"/>void Update(simul::crossplatform::DeviceContext deviceContext, simul::clouds::BaseWeatherRenderer weatherRenderer)
Update the skylight per-frame.
