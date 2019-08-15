---
title: SphericalHarmonics
layout: reference
weight: 0
---
class SphericalHarmonics
===

| Include: | Platform/CrossPlatform/SphericalHarmonics.h |

A class that calculates spherical harmonics from a cubemap, and stores the results in a structured buffer.
  


Functions
---

| void | [CalcSphericalHarmonics](#CalcSphericalHarmonics)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture texture) |
| void | [CopyMip](#CopyMip)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture tex, int face, int mip, float blend) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| bool | [Probe](#Probe)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture buffer_texture, int mip_size, int face_index, uint2 pos, uint2 size, vec4 targetValuesFloat4) |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [RenderEnvmap](#RenderEnvmap)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture target, int cubemapIndex, float blend) |
| void | [RenderMipsByRoughness](#RenderMipsByRoughness)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture target) |
| void | [ResetBuffers](#ResetBuffers)() |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform r) |

A class that calculates spherical harmonics from a cubemap, and stores the results in a structured buffer.
  


Functions
---
<a name="CalcSphericalHarmonics"></a>
### void CalcSphericalHarmonics(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture texture)
Calculate the spherical harmonics of this cubemap and store the result internally.
Changing the number of bands will resize the internal storeage.
<a name="CopyMip"></a>
### void CopyMip(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture tex, int face, int mip, float blend)
Copy from a given mip face to the next one down, with blending or without (if blend is 0).
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the Spherical Harmonics.
<a name="Probe"></a>
### bool Probe(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture buffer_texture, int mip_size, int face_index, uint2 pos, uint2 size, vec4 targetValuesFloat4)
Probe values from cubemap.
<a name="RecompileShaders"></a>
### void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.
<a name="RenderEnvmap"></a>
### void RenderEnvmap(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture target, int cubemapIndex, float blend)
Draw a diffuse environment map to the specified framebuffer.
<a name="RenderMipsByRoughness"></a>
### void RenderMipsByRoughness(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture target)
Taking the zero mip as the initial data source, use the formula roughness=mip/max_mip to render it down to the lower mips.
<a name="ResetBuffers"></a>
### void ResetBuffers()
Make sure no invalid data is retained.
<a name="RestoreDeviceObjects"></a>
### void RestoreDeviceObjects(simul::crossplatform::RenderPlatform r)
Platform-dependent function called when initializing the Spherical Harmonics.
