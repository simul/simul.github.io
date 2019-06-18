---
title: TwoResFramebuffer
layout: reference
weight: 0
---
class TwoResFramebuffer
===

| Include: | Clouds/MixedResolutionCompositor.h |



Functions
---

|  | [TwoResFramebuffer](#TwoResFramebuffer)() |
| void | [CompleteFrame](#CompleteFrame)(long long framenumber) |
| void | [DeactivateDepth](#DeactivateDepth)(simul::crossplatform::DeviceContext) |
| uint4 | [GetCubeIntegerFrustumRange](#GetCubeIntegerFrustumRange)(int i) |
| simul::crossplatform::Texture * | [GetStochasticDepthTexture](#GetStochasticDepthTexture)(int idx) |
| simul::crossplatform::Texture * | [GetUpdateTexture](#GetUpdateTexture)(int idx) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [RenderDepthBuffers](#RenderDepthBuffers)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture, simul::crossplatform::Viewport viewport, int x0, int y0, int dx, int dy) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform) |
| void | [SetCubeFrustumRange](#SetCubeFrustumRange)(int i, vec4 r) |
| void | [SetProjection](#SetProjection)(float p) |
| void | [Swap](#Swap)() |
| void | [UpdatePixelOffset](#UpdatePixelOffset)(simul::crossplatform::ViewStruct viewStruct) |


Functions
---

### <a name="TwoResFramebuffer"/> TwoResFramebuffer()
A framebuffer class for mixed-resolution rendering.

### <a name="CompleteFrame"/>void CompleteFrame(long long framenumber)
This must be called to ensure that the amortization struct is up to date.

### <a name="DeactivateDepth"/>void DeactivateDepth(simul::crossplatform::DeviceContext)
Deactivate the depth buffer

### <a name="GetCubeIntegerFrustumRange"/>uint4 GetCubeIntegerFrustumRange(int i)
Get the range in terms of the buffer size as integers.

### <a name="GetStochasticDepthTexture"/>simul::crossplatform::Texture * GetStochasticDepthTexture(int idx)
Returns the low-res depth texture.

### <a name="GetUpdateTexture"/>simul::crossplatform::Texture * GetUpdateTexture(int idx)
A texture that shows what texels are up to date. Where the value is zero, we should fill all the values.

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the water framebuffer.

### <a name="RenderDepthBuffers"/>void RenderDepthBuffers(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture depthTexture, simul::crossplatform::Viewport viewport, int x0, int y0, int dx, int dy)
Debugging onscreen info:

[in,out] deviceContext   Context for the device.
depthTextureThe main depth texture.
viewportThe viewport in use for the depth texture.
x0The left edge of area to use for the debug display.
y0The top of this debug display.
dxThe width of the display.
dyThe height of the display.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform)
Platform-dependent function called when initializing the framebuffer.

### <a name="SetCubeFrustumRange"/>void SetCubeFrustumRange(int i, vec4 r)
Set the range of the cubemap that's in the current frustum.

### <a name="SetProjection"/>void SetProjection(float p)
Assign the current frame's projection matrix for this buffer. Just for debugging.

### <a name="Swap"/>void Swap()
Swap stochastic texture buffers.

### <a name="UpdatePixelOffset"/>void UpdatePixelOffset(simul::crossplatform::ViewStruct viewStruct)
Update the pixel offset for the specified view.

Fields
---

**pixelOffset**  Offset in pixels from top-left of the low-res view to top-left of the full-res.
