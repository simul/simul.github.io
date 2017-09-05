---
title: SkyTexturesCallback
layout: reference
weight: 0
---
class SkyTexturesCallback
===

| Include: | Sky/SkyTexturesCallback.h |

A callback virtual base class that fade tables use. A fade table is any class derived from FadeTableInterface, and it<br>uses these callback functions to tell your platform-specific renderer how to create and modify the sky and fade textures.<br>Usually you would derive your sky-rendering class from SkyTexturesCallback, and implement these functions. See, for example,<br>the DirectX implementation of SimulSkyRenderer.


Functions
---

| void | [CycleTexturesForward](#CycleTexturesForward)() |
| void | [FillFadeTexturesSequentially](#FillFadeTexturesSequentially)(int texture_index, int texel_index, int num_texels, float loss_float4_array, float inscatter_float4_array) |
| void | [SetFadeTextureSize](#SetFadeTextureSize)(unsigned int width_num_distances, unsigned int height_num_elevations, unsigned int num_altitudes) |
| void | [SetSkyTextureSize](#SetSkyTextureSize)(unsigned int size) |

A callback virtual base class that fade tables use. A fade table is any class derived from FadeTableInterface, and it
uses these callback functions to tell your platform-specific renderer how to create and modify the sky and fade textures.
Usually you would derive your sky-rendering class from SkyTexturesCallback, and implement these functions. See, for example,
the DirectX implementation of SimulSkyRenderer.
  


Functions
---

### <a name="CycleTexturesForward"/>void CycleTexturesForward()
Inform the derived class that the textures should be cycled forward - i.e. texture 2 becomes 1, 3 becomes 2 and 1 becomes 3.
This is done when interpolation has crossed over a step boundary.
Inform the derived class that the textures should be cycled forward - i.e. texture 2 becomes 1, 3 becomes 2 and 1 becomes 3.
This is done when interpolation has crossed over a step boundary.

### <a name="FillFadeTexturesSequentially"/>void FillFadeTexturesSequentially(int texture_index, int texel_index, int num_texels, float loss_float4_array, float inscatter_float4_array)
Inform the derived class that the texture 
**texture_index**, either 0, 1 or 2, at altitude
index 
**alt_index**, (not used if not using multiple altitudes) should have 
**num_texels** texels
filled starting at 
**texel_index**, with the values in the arrays 
**loss_float4_array** and 
**inscatter_float4_array**, each of which contains four times 
**num_texels** floats. The first number is
the value for 
**texel_index**, rather than the start of the whole table.
Each group of four represents the r,g,b and a of a colour value, and the values may be greater
than one, so floating point textures are preferred.
Only one of FillFadeTexturesSequentially and FillFadeTextureBlocks need be implemented, depending on the graphics API.
Some API's permit transfer of data sequentially in memory to textures (e.g. DirectX 9), some expect cuboid blocks of
texels to be filled (e.g. OpenGL). The unwanted function should be implemented as a stub, with an assert() or some other
fail condition, to make sure it is never called.
Inform the derived class that the texture 
**texture_index**, either 0, 1 or 2, at altitude
index 
**alt_index**, (not used if not using multiple altitudes) should have 
**num_texels** texels
filled starting at 
**texel_index**, with the values in the arrays 
**loss_float4_array** and 
**inscatter_float4_array**, each of which contains four times 
**num_texels** floats. The first number is
the value for 
**texel_index**, rather than the start of the whole table.
Each group of four represents the r,g,b and a of a colour value, and the values may be greater
than one, so floating point textures are preferred.
Only one of FillFadeTexturesSequentially and FillFadeTextureBlocks need be implemented, depending on the graphics API.
Some API's permit transfer of data sequentially in memory to textures (e.g. DirectX 9), some expect cuboid blocks of
texels to be filled (e.g. OpenGL). The unwanted function should be implemented as a stub, with an assert() or some other
fail condition, to make sure it is never called.

### <a name="SetFadeTextureSize"/>void SetFadeTextureSize(unsigned int width_num_distances, unsigned int height_num_elevations, unsigned int num_altitudes)
Inform the derived class of the table or texture size. All three tables should be sized to these parameters.
If a sunlight texture is used (see FillSunlightTexture), make this a 1D texture of size 
**num_altitudes**.
Inform the derived class of the table or texture size. All three tables should be sized to these parameters.
If a sunlight texture is used (see FillSunlightTexture), make this a 1D texture of size 
**num_altitudes**.

### <a name="SetSkyTextureSize"/>void SetSkyTextureSize(unsigned int size)
Inform the derived class of the table or texture size. All three tables should be sized to these parameters.
Inform the derived class of the table or texture size. All three tables should be sized to these parameters.
