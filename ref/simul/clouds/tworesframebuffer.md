---
title: TwoResFramebuffer
layout: reference
weight: 0
---
class TwoResFramebuffer
===

| Include: | Clouds/BaseWeatherRenderer.h |

A framebuffer class for mixed-resolution rendering.
  


Functions
---

| void | [ActivateLowRes](#ActivateLowRes)(simul::crossplatform::DeviceContext) |
| void | [CompleteFrame](#CompleteFrame)(long long framenumber) |
| void | [DeactivateDepth](#DeactivateDepth)(simul::crossplatform::DeviceContext) |
| void | [DeactivateLowRes](#DeactivateLowRes)(simul::crossplatform::DeviceContext) |
| uint4 | [GetCubeIntegerFrustumRange](#GetCubeIntegerFrustumRange)(int i) |
| simul::crossplatform::Texture * | [GetStochasticDepthTexture](#GetStochasticDepthTexture)(int idx) |
| simul::crossplatform::Texture * | [GetUpdateTexture](#GetUpdateTexture)(int idx) |
| void | [RenderDepthBuffers](#RenderDepthBuffers)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture, simul::crossplatform::Viewport viewport, int x0, int y0, int dx, int dy) |
| void | [Swap](#Swap)() |
| void | [UpdatePixelOffset](#UpdatePixelOffset)(simul::crossplatform::ViewStruct viewStruct) |

A framebuffer class for mixed-resolution rendering.
  


Functions
---

### <a name="ActivateLowRes"/>void ActivateLowRes(simul::crossplatform::DeviceContext)
Activate BOTH low-resolution framebuffers - far in target 0, near in target 1. Must be followed by DeactivatelLowRes after rendering.

### <a name="CompleteFrame"/>void CompleteFrame(long long framenumber)
This must be called to ensure that the amortization struct is up to date.

### <a name="DeactivateDepth"/>void DeactivateDepth(simul::crossplatform::DeviceContext)
Deactivate the depth buffer

### <a name="DeactivateLowRes"/>void DeactivateLowRes(simul::crossplatform::DeviceContext)
Deactivate both low-res framebuffers.

### <a name="GetCubeIntegerFrustumRange"/>uint4 GetCubeIntegerFrustumRange(int i)
Get the range in terms of the buffer size as integers.

### <a name="GetStochasticDepthTexture"/>simul::crossplatform::Texture * GetStochasticDepthTexture(int idx)
Returns the low-res depth texture.

### <a name="GetUpdateTexture"/>simul::crossplatform::Texture * GetUpdateTexture(int idx)
A texture that shows what texels are up to date. Where the value is zero, we should fill all the values.

### <a name="RenderDepthBuffers"/>void RenderDepthBuffers(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture, simul::crossplatform::Viewport viewport, int x0, int y0, int dx, int dy)
Debugging onscreen info:

\param [in,out] deviceContext   Context for the device.
\param  depthTexture                    The main depth texture.
\param  viewport                                The viewport in use for the depth texture.
\param  x0                                              The left edge of area to use for the debug display.
\param  y0                                              The top of this debug display.
\param  dx                                              The width of the display.
\param  dy                                              The height of the display.

### <a name="Swap"/>void Swap()
Swap stochastic texture buffers.

### <a name="UpdatePixelOffset"/>void UpdatePixelOffset(simul::crossplatform::ViewStruct viewStruct)
Update the pixel offset for the specified view.

Fields
---

**pixelOffset**  Offset in pixels from top-left of the low-res view to top-left of the full-res.
