---
title: BaseGpuCloudGenerator
layout: reference
weight: 0
---
class BaseGpuCloudGenerator
===

| Include: | Clouds/BaseGpuCloudGenerator.h |

Base class for generating cloud volumes on the GPU.
  


Functions
---

| bool | [CanPerformGPULighting](#CanPerformGPULighting)() |
| void | [FillDensityGrid](#FillDensityGrid)(simul::crossplatform::DeviceContext deviceContext, int index, simul::clouds::GpuCloudsParameters params, int start_texel, int texels, simul::crossplatform::Texture finalTexture, simul::clouds::CloudClass cloudClass) |
| int | [GetDensityGridsize](#GetDensityGridsize)(int grid) |
| simul::crossplatform::Texture * | [Make3DNoiseTexture](#Make3DNoiseTexture)(simul::crossplatform::DeviceContext deviceContext, int noise_size, float noise_src_ptr, int generation_number) |
| void | [RenderSimulationTextures](#RenderSimulationTextures)(simul::crossplatform::DeviceContext context, int x0, int y0, int width, int height) |

Base class for generating cloud volumes on the GPU.
  


Functions
---
<a name="CanPerformGPULighting"></a>
### bool CanPerformGPULighting()
Return true if the derived class can relight clouds using the GPU.
<a name="FillDensityGrid"></a>
### void FillDensityGrid(simul::crossplatform::DeviceContext deviceContext, int index, simul::clouds::GpuCloudsParameters params, int start_texel, int texels, simul::crossplatform::Texture finalTexture, simul::clouds::CloudClass cloudClass)
Fill a 3D grid with floating point cloud densities, and return an API-specific
identifier to the texture that it's stored in.
We pass the start texel and the number of texels to fill, which should both be a whole multiple of grid[0]
<a name="GetDensityGridsize"></a>
### int GetDensityGridsize(int grid)
Get the size, in floats, needed to allocate a texture of the size specified in grid[3].
This depends on what float renderbuffer formats are supported.
<a name="Make3DNoiseTexture"></a>
### simul::crossplatform::Texture * Make3DNoiseTexture(simul::crossplatform::DeviceContext deviceContext, int noise_size, float noise_src_ptr, int generation_number)
Create an API-specific noise texture, and return its pointer/identifier etc. as a void pointer.
<a name="RenderSimulationTextures"></a>
### void RenderSimulationTextures(simul::crossplatform::DeviceContext context, int x0, int y0, int width, int height)
For onscreen debug
