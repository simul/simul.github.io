---
title: SkyTexturesCallback
layout: reference
weight: 0
---
class SkyTexturesCallback
===

| Include: | Sky/SkyTexturesCallback.h |

A callback virtual base class that fade tables use. A fade table is any class derived from FadeTableInterface, and it
uses these callback functions to tell your platform-specific renderer how to create and modify the sky and fade textures.
Usually you would derive your sky-rendering class from SkyTexturesCallback, and implement these functions. See, for example,
the DirectX implementation of SimulSkyRenderer.
  


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

### <a name="FillFadeTexturesSequentially"/>void FillFadeTexturesSequentially(int texture_index, int texel_index, int num_texels, float loss_float4_array, float inscatter_float4_array)

### <a name="SetFadeTextureSize"/>void SetFadeTextureSize(unsigned int width_num_distances, unsigned int height_num_elevations, unsigned int num_altitudes)
Inform the derived class of the table or texture size. All three tables should be sized to these parameters.


### <a name="SetSkyTextureSize"/>void SetSkyTextureSize(unsigned int size)
Inform the derived class of the table or texture size. All three tables should be sized to these parameters.
