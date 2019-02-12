---
title: BaseAtmosphericsRenderer
layout: reference
weight: 0
---
class BaseAtmosphericsRenderer
===

| Include: | Clouds/BaseWeatherRenderer.h |


[simul::base::Referenced](../base/referenced)

Functions
---

|  | [BaseAtmosphericsRenderer](#BaseAtmosphericsRenderer)(simul::base::MemoryInterface m) |
| simul::sky::ScatteringVolume  const * | [GetScatteringVolume](#GetScatteringVolume)(int view_id) |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [SetCloudShadowTexture](#SetCloudShadowTexture)(CloudShadowStruct c) |
| void | [SetIlluminationTexture](#SetIlluminationTexture)(simul::crossplatform::Texture) |


Base Classes
---
[simul::base::Referenced](../base/referenced)

Functions
---

### <a name="BaseAtmosphericsRenderer"/> BaseAtmosphericsRenderer(simul::base::MemoryInterface m)
The graphics API-independent base class for atmospherics renderers, which draw distance fades, aerial perspective, fog and so on.

### <a name="GetScatteringVolume"/>simul::sky::ScatteringVolume  const * GetScatteringVolume(int view_id)
Get the per-frame 3D volume scattering texture for the given view id.

### <a name="RecompileShaders"/>void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.

### <a name="SetCloudShadowTexture"/>void SetCloudShadowTexture(CloudShadowStruct c)
Set the 2D cloud shadow texture to be used for lighting.

### <a name="SetIlluminationTexture"/>void SetIlluminationTexture(simul::crossplatform::Texture)
Set the texture defining the extent of illuminated inscatter. R=near, G=far, B and A unused.

Fields
---

**effect**  The HDR tonemapping hlsl effect used to render the hdr buffer to an ldr screen.
