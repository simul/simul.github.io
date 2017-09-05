---
title: BaseFramebuffer
layout: reference
weight: 0
---
class BaseFramebuffer
===

| Include: | Clouds/MixedResolutionCompositor.h |

A base class for API-dependent framebuffer classes.


Functions
---

| void | [Activate](#Activate)(simul::crossplatform::DeviceContext) |
| void | [ActivateColour](#ActivateColour)(simul::crossplatform::DeviceContext, viewportXYWH) |
| void | [ActivateViewport](#ActivateViewport)(simul::crossplatform::DeviceContext, float viewportX, float viewportY, float viewportW, float viewportH) |
| void | [CalcSphericalHarmonics](#CalcSphericalHarmonics)(simul::crossplatform::DeviceContext deviceContext) |
| void | [Clear](#Clear)(simul::crossplatform::DeviceContext context, float R, float G, float B, float A, float depth, int mask) |
| void | [ClearColour](#ClearColour)(simul::crossplatform::DeviceContext context, float, float, float, float) |
| bool | [CreateBuffers](#CreateBuffers)() |
| void | [Deactivate](#Deactivate)(simul::crossplatform::DeviceContext) |
| void | [DeactivateDepth](#DeactivateDepth)(simul::crossplatform::DeviceContext) |
| simul::crossplatform::Texture * | [GetDepthTexture](#GetDepthTexture)() |
| int | [GetHeight](#GetHeight)() |
| simul::crossplatform::Texture * | [GetTexture](#GetTexture)() |
| int | [GetWidth](#GetWidth)() |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| bool | [IsColourActive](#IsColourActive)() |
| bool | [IsDepthActive](#IsDepthActive)() |
| bool | [IsValid](#IsValid)() |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform r) |
| void | [SetAsCubemap](#SetAsCubemap)(int face_size, int num_mips, simul::crossplatform::PixelFormat f) |
| void | [setDefaultRenderTargets](#setDefaultRenderTargets)(simul::crossplatform::ApiRenderTarget, simul::crossplatform::ApiDepthRenderTarget, uint32_t viewportLeft, uint32_t viewportTop, uint32_t viewportRight, uint32_t viewportBottom) |
| void | [SetDepthFormat](#SetDepthFormat)(simul::crossplatform::PixelFormat) |
| void | [SetFormat](#SetFormat)(simul::crossplatform::PixelFormat) |
| void | [SetUseFastRAM](#SetUseFastRAM)(bool, bool) |
| void | [SetWidthAndHeight](#SetWidthAndHeight)(int w, int h, int num_mips) |

A base class for API-dependent framebuffer classes.
  


Functions
---

### <a name="Activate"/>void Activate(simul::crossplatform::DeviceContext)
Activate the framebuffer - must be followed after rendering by a call to 
Activate the framebuffer - must be followed after rendering by a call to 

### <a name="ActivateColour"/>void ActivateColour(simul::crossplatform::DeviceContext, viewportXYWH)
Activate the colour part of this framebuffer, without depth - must be followed after rendering by a call to 
Activate the colour part of this framebuffer, without depth - must be followed after rendering by a call to 

### <a name="ActivateViewport"/>void ActivateViewport(simul::crossplatform::DeviceContext, float viewportX, float viewportY, float viewportW, float viewportH)
Activate the framebuffer and set the viewport- must be followed after rendering by a call to 
Activate the framebuffer and set the viewport- must be followed after rendering by a call to 

### <a name="CalcSphericalHarmonics"/>void CalcSphericalHarmonics(simul::crossplatform::DeviceContext deviceContext)
Calculate the spherical harmonics of this cubemap and store the result internally.
Changing the number of bands will resize the internal storeage.
Calculate the spherical harmonics of this cubemap and store the result internally.
Changing the number of bands will resize the internal storeage.

### <a name="Clear"/>void Clear(simul::crossplatform::DeviceContext context, float R, float G, float B, float A, float depth, int mask)
Clear the colour and depth buffers if present.
Clear the colour and depth buffers if present.

### <a name="ClearColour"/>void ClearColour(simul::crossplatform::DeviceContext context, float, float, float, float)
Set the size of the framebuffer in pixel height and width.
Set the size of the framebuffer in pixel height and width.

### <a name="CreateBuffers"/>bool CreateBuffers()
Call this if needed (not usually) to ensure that the buffers are created.
Call this if needed (not usually) to ensure that the buffers are created.

### <a name="Deactivate"/>void Deactivate(simul::crossplatform::DeviceContext)
Deactivate the framebuffer - must be preceded a call to 
Deactivate the framebuffer - must be preceded a call to 

### <a name="DeactivateDepth"/>void DeactivateDepth(simul::crossplatform::DeviceContext)
Deactivate only the depth buffer, so it can be used as a texture for rendering to the colour buffer.
Deactivate only the depth buffer, so it can be used as a texture for rendering to the colour buffer.

### <a name="GetDepthTexture"/>simul::crossplatform::Texture * GetDepthTexture()
Get the texture for the depth buffer target.
Get the texture for the depth buffer target.

### <a name="GetHeight"/>int GetHeight()
Get the dimension of the surface
Get the dimension of the surface

### <a name="GetTexture"/>simul::crossplatform::Texture * GetTexture()
Get the texture for the colour buffer target.
Get the texture for the colour buffer target.

### <a name="GetWidth"/>int GetWidth()
Get the dimension of the surface
Get the dimension of the surface

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Call this when the API-dependent device has been lost or is shutting down.
Call this when the API-dependent device has been lost or is shutting down.

### <a name="IsColourActive"/>bool IsColourActive()
Return true if the framebuffer's colour buffer has been activated and not yet deactivated.
Return true if the framebuffer's colour buffer has been activated and not yet deactivated.

### <a name="IsDepthActive"/>bool IsDepthActive()
Return true if the framebuffer's depth buffer has been activated and not yet deactivated.
Return true if the framebuffer's depth buffer has been activated and not yet deactivated.

### <a name="IsValid"/>bool IsValid()
Return true if the API-dependent objects have been updated to match the properties.
Return true if the API-dependent objects have been updated to match the properties.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform r)
Call this when the API-dependent device has been created.
Call this when the API-dependent device has been created.

### <a name="SetAsCubemap"/>void SetAsCubemap(int face_size, int num_mips, simul::crossplatform::PixelFormat f)
Set this to be a cubemap framebuffer, so that its texture object will be a cubemap. Equivalent to SetWidthAndHeight.
Set this to be a cubemap framebuffer, so that its texture object will be a cubemap. Equivalent to SetWidthAndHeight.

### <a name="setDefaultRenderTargets"/>void setDefaultRenderTargets(simul::crossplatform::ApiRenderTarget, simul::crossplatform::ApiDepthRenderTarget, uint32_t viewportLeft, uint32_t viewportTop, uint32_t viewportRight, uint32_t viewportBottom)
Set the RT's to restore to, once all Simul Framebuffers are deactivated. This must be called at least once,
as
Set the RT's to restore to, once all Simul Framebuffers are deactivated. This must be called at least once,
as

### <a name="SetDepthFormat"/>void SetDepthFormat(simul::crossplatform::PixelFormat)
Set the API-dependent colour depth format for this framebuffer. Across all API's, setting 0 means no rendering to depth.
Set the API-dependent colour depth format for this framebuffer. Across all API's, setting 0 means no rendering to depth.

### <a name="SetFormat"/>void SetFormat(simul::crossplatform::PixelFormat)
Set the API-dependent colour buffer format for this framebuffer. Across all API's, setting 0 means no rendering to colour.
Set the API-dependent colour buffer format for this framebuffer. Across all API's, setting 0 means no rendering to colour.

### <a name="SetUseFastRAM"/>void SetUseFastRAM(bool, bool)
Some hardware has fast RAM that's good for framebuffers.
Some hardware has fast RAM that's good for framebuffers.

### <a name="SetWidthAndHeight"/>void SetWidthAndHeight(int w, int h, int num_mips)
Set the size of the framebuffer.
Set the size of the framebuffer.

Fields
---

**Width** The size of the buffer The size of the buffer

**Height** The size of the buffer The size of the buffer

**buffer_texture** The depth buffer. The depth buffer.
