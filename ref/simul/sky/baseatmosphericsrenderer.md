---
title: BaseAtmosphericsRenderer
layout: reference
weight: 0
---
class BaseAtmosphericsRenderer
===

| Include: | Sky/BaseAtmosphericsRenderer.h |

The graphics API-independent base class for atmospherics renderers, which draw distance fades, aerial perspective, fog and so on.
  

[simul::base::Referenced](../base/referenced.html)

Functions
---

| void | [EnsureEffectsAreBuilt](#EnsureEffectsAreBuilt)(simul::crossplatform::RenderPlatform r) |
| simul::sky::ScatteringVolume  const * | [GetScatteringVolume](#GetScatteringVolume)(int view_id) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [PreRenderUpdate](#PreRenderUpdate)(simul::crossplatform::DeviceContext) |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform r) |
| void | [SetCameraPosition](#SetCameraPosition)(float pos) |
| void | [SetCloudShadowTexture](#SetCloudShadowTexture)(CloudShadowStruct c) |
| void | [SetFogDensity](#SetFogDensity)(float d) |
| void | [SetFogHeightKm](#SetFogHeightKm)(float h_km) |
| void | [SetIlluminationTexture](#SetIlluminationTexture)(simul::crossplatform::Texture) |
| void | [SetSkyInterface](#SetSkyInterface)(simul::sky::SkyKeyframer si) |

The graphics API-independent base class for atmospherics renderers, which draw distance fades, aerial perspective, fog and so on.
  


Base Classes
---
[simul::base::Referenced](../base/referenced.html)

Functions
---
<a name="EnsureEffectsAreBuilt"></a>
### void EnsureEffectsAreBuilt(simul::crossplatform::RenderPlatform r)
Check that all shaders have been correctly compiled
<a name="GetScatteringVolume"></a>
### simul::sky::ScatteringVolume  const * GetScatteringVolume(int view_id)
Get the per-frame 3D volume scattering texture for the given view id.
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the atmospherics renderer.
<a name="PreRenderUpdate"></a>
### void PreRenderUpdate(simul::crossplatform::DeviceContext)
Once per-frame update. Do this before any rendering each frame.
<a name="RecompileShaders"></a>
### void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.
<a name="RestoreDeviceObjects"></a>
### void RestoreDeviceObjects(simul::crossplatform::RenderPlatform r)
Platform-dependent function called when initializing the atmospherics renderer.
<a name="SetCameraPosition"></a>
### void SetCameraPosition(float pos)
Get the current location of the camera
<a name="SetCloudShadowTexture"></a>
### void SetCloudShadowTexture(CloudShadowStruct c)
Set the 2D cloud shadow texture to be used for lighting.
<a name="SetFogDensity"></a>
### void SetFogDensity(float d)
Set the density of the fog
<a name="SetFogHeightKm"></a>
### void SetFogHeightKm(float h_km)
Set the height of the fog
<a name="SetIlluminationTexture"></a>
### void SetIlluminationTexture(simul::crossplatform::Texture)
Set the texture defining the extent of illuminated inscatter. R=near, G=far, B and A unused.
<a name="SetSkyInterface"></a>
### void SetSkyInterface(simul::sky::SkyKeyframer si)
Set the sky and atmospherics interface to allow the renderer to use the correct lighting values.

Fields
---

**effect**  The HDR tonemapping hlsl effect used to render the hdr buffer to an ldr screen.
