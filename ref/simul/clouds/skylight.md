---
title: Skylight
layout: reference
weight: 0
---
class Skylight
===

| Include: | Clouds/Skylight.h |

A class to capture light from the sky in real time for diffuse and specular lighting.
  


Functions
---

| bool | [GetSphericalHarmonics](#GetSphericalHarmonics)(simul::crossplatform::DeviceContext deviceContext, float targetShValues) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| bool | [Probe](#Probe)(simul::crossplatform::DeviceContext deviceContext, int mip_size, int face_index, uint2 pos, uint2 size, vec4 targetValuesFloat4) |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [Render](#Render)(simul::crossplatform::GraphicsDeviceContext parentDeviceContext, simul::clouds::BaseWeatherRenderer baseWeatherRenderer, int cube_id, simul::crossplatform::BaseFramebuffer fb, int faceIndex, mat4 engineToSimulMatrix4x4, float blend, float exposure, float gamma) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform r) |
| void | [ShowDebug](#ShowDebug)(simul::crossplatform::GraphicsDeviceContext deviceContext, int X, int Y, int w) |
| void | [Update](#Update)(simul::crossplatform::GraphicsDeviceContext deviceContext, simul::clouds::BaseWeatherRenderer weatherRenderer) |

A class to capture light from the sky in real time for diffuse and specular lighting.
  


Functions
---
<a name="GetSphericalHarmonics"></a>
### bool GetSphericalHarmonics(simul::crossplatform::DeviceContext deviceContext, float targetShValues)
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Free the GPU objects.
<a name="Probe"></a>
### bool Probe(simul::crossplatform::DeviceContext deviceContext, int mip_size, int face_index, uint2 pos, uint2 size, vec4 targetValuesFloat4)
<a name="RecompileShaders"></a>
### void RecompileShaders()
Recompile the shaders for this class.
<a name="Render"></a>
### void Render(simul::crossplatform::GraphicsDeviceContext parentDeviceContext, simul::clouds::BaseWeatherRenderer baseWeatherRenderer, int cube_id, simul::crossplatform::BaseFramebuffer fb, int faceIndex, mat4 engineToSimulMatrix4x4, float blend, float exposure, float gamma)
Fill in the texture.
<a name="RestoreDeviceObjects"></a>
### void RestoreDeviceObjects(simul::crossplatform::RenderPlatform r)
Initialize GPU objects.
<a name="ShowDebug"></a>
### void ShowDebug(simul::crossplatform::GraphicsDeviceContext deviceContext, int X, int Y, int w)
Show debug displays onscreen.
<a name="Update"></a>
### void Update(simul::crossplatform::GraphicsDeviceContext deviceContext, simul::clouds::BaseWeatherRenderer weatherRenderer)
Update the skylight per-frame.
