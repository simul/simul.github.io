---
title: Texture
layout: reference
weight: 0
---
class Texture
===

| Include: | Clouds/BaseCloudRenderer.h |

A Texture base class.
  


Functions
---

| void | [activateRenderTarget](#activateRenderTarget)(simul::crossplatform::DeviceContext deviceContext, int array_index, int mip_index) |
| ID3D11RenderTargetView * | [AsD3D11RenderTargetView](#AsD3D11RenderTargetView)(int, int) |
| ID3D11ShaderResourceView * | [AsD3D11ShaderResourceView](#AsD3D11ShaderResourceView)(simul::crossplatform::ShaderResourceType, int, int) |
| ID3D11UnorderedAccessView * | [AsD3D11UnorderedAccessView](#AsD3D11UnorderedAccessView)(int, int) |
| sce::Gnm::Texture * | [AsGnmTexture](#AsGnmTexture)(simul::crossplatform::ShaderResourceType, int, int) |
| void | [ClearDepthStencil](#ClearDepthStencil)(simul::crossplatform::DeviceContext deviceContext, float, int) |
| void | [ClearFence](#ClearFence)() |
| void | [deactivateRenderTarget](#deactivateRenderTarget)(simul::crossplatform::DeviceContext deviceContext) |
| bool | [ensureTexture2DSizeAndFormat](#ensureTexture2DSizeAndFormat)(simul::crossplatform::RenderPlatform renderPlatform, int w, int l, simul::crossplatform::PixelFormat f, bool computable, bool rendertarget, bool depthstencil, int num_samples, int aa_quality, bool wrap, vec4 clear, float clearDepth, uint clearStencil) |
| bool | [ensureTexture3DSizeAndFormat](#ensureTexture3DSizeAndFormat)(simul::crossplatform::RenderPlatform renderPlatform, int w, int l, int d, simul::crossplatform::PixelFormat frmt, bool computable, int mips, bool rendertargets) |
| bool | [ensureTextureArraySizeAndFormat](#ensureTextureArraySizeAndFormat)(simul::crossplatform::RenderPlatform renderPlatform, int w, int l, int num, int mips, simul::crossplatform::PixelFormat f, bool computable, bool rendertarget, bool cubemap) |
| void | [GenerateMips](#GenerateMips)(simul::crossplatform::DeviceContext deviceContext) |
| unsigned long long | [GetFence](#GetFence)() |
| simul::crossplatform::PixelFormat | [GetFormat](#GetFormat)() |
| int | [GetSampleCount](#GetSampleCount)() |
| void | [InitFromExternalTexture2D](#InitFromExternalTexture2D)(simul::crossplatform::RenderPlatform renderPlatform, void t, void srv, bool make_rt, bool setDepthStencil) |
| bool | [IsDepthStencil](#IsDepthStencil)() |
| bool | [IsUnfenceable](#IsUnfenceable)() |
| void | [MoveToFastRAM](#MoveToFastRAM)() |
| void | [MoveToSlowRAM](#MoveToSlowRAM)() |
| int | [NumFaces](#NumFaces)() |
| void | [SetFence](#SetFence)(unsigned long long) |
| void | [setTexels](#setTexels)(simul::crossplatform::DeviceContext deviceContext, void src, int texel_index, int num_texels) |
| void | [SetUnfenceable](#SetUnfenceable)(bool v) |

A Texture base class.
  


Functions
---

### <a name="activateRenderTarget"/>void activateRenderTarget(simul::crossplatform::DeviceContext deviceContext, int array_index, int mip_index)
Activate as a rendertarget - must call deactivateRenderTarget afterwards.

### <a name="AsD3D11RenderTargetView"/>ID3D11RenderTargetView * AsD3D11RenderTargetView(int, int)
Returns the RTV specified by layer,mip. Layer -1 means all layers at the given mip, while mip -1 defaults to mip zero.

### <a name="AsD3D11ShaderResourceView"/>ID3D11ShaderResourceView * AsD3D11ShaderResourceView(simul::crossplatform::ShaderResourceType, int, int)
Returns the SRV specified by layer,mip. The type t ensures that the assigned resource is compatible (UNKNWON matches anything).
Layer -1 means all layers at the given mip, while mip -1 defaults to the whole texture/layer.

### <a name="AsD3D11UnorderedAccessView"/>ID3D11UnorderedAccessView * AsD3D11UnorderedAccessView(int, int)
Returns the UAV specified by layer,mip. Layer -1 means all layers at the given mip, while mip -1 defaults to mip zero.

### <a name="AsGnmTexture"/>sce::Gnm::Texture * AsGnmTexture(simul::crossplatform::ShaderResourceType, int, int)
Returns the GnmTexture specified by layer,mip. Default values of -1 mean "all".

### <a name="ClearDepthStencil"/>void ClearDepthStencil(simul::crossplatform::DeviceContext deviceContext, float, int)
Clear the depth stencil

### <a name="ClearFence"/>void ClearFence()
Clear the fence: this texture is ok to use now.

### <a name="deactivateRenderTarget"/>void deactivateRenderTarget(simul::crossplatform::DeviceContext deviceContext)
Deactivate as a rendertarget.

### <a name="ensureTexture2DSizeAndFormat"/>bool ensureTexture2DSizeAndFormat(simul::crossplatform::RenderPlatform renderPlatform, int w, int l, simul::crossplatform::PixelFormat f, bool computable, bool rendertarget, bool depthstencil, int num_samples, int aa_quality, bool wrap, vec4 clear, float clearDepth, uint clearStencil)

### <a name="ensureTexture3DSizeAndFormat"/>bool ensureTexture3DSizeAndFormat(simul::crossplatform::RenderPlatform renderPlatform, int w, int l, int d, simul::crossplatform::PixelFormat frmt, bool computable, int mips, bool rendertargets)
Initialize as a volume texture.

### <a name="ensureTextureArraySizeAndFormat"/>bool ensureTextureArraySizeAndFormat(simul::crossplatform::RenderPlatform renderPlatform, int w, int l, int num, int mips, simul::crossplatform::PixelFormat f, bool computable, bool rendertarget, bool cubemap)
Initialize as an array texture if necessary. Returns true if the texture was initialized, or false if it was already in the required format.

### <a name="GenerateMips"/>void GenerateMips(simul::crossplatform::DeviceContext deviceContext)
Generate the mipmaps automatically.

### <a name="GetFence"/>unsigned long long GetFence()
Get the current fence on this texture; it should not be used until the API has passed this fence.

### <a name="GetFormat"/>simul::crossplatform::PixelFormat GetFormat()
Get the crossplatform pixel format.

### <a name="GetSampleCount"/>int GetSampleCount()
If the texture is multisampled, this returns the samples per texel. Zero means it is not an MS texture,
while 1 means it is MS, even though the sample count is unity.

### <a name="InitFromExternalTexture2D"/>void InitFromExternalTexture2D(simul::crossplatform::RenderPlatform renderPlatform, void t, void srv, bool make_rt, bool setDepthStencil)
Initialize this object as a wrapper around a native, platform-specific texture. The interpretations of t and srv are platform-dependent.

### <a name="IsDepthStencil"/>bool IsDepthStencil()
Get whether texture is a depth stencil

### <a name="IsUnfenceable"/>bool IsUnfenceable()
Is the texture "unfenceable": if so, it need never be checked for fences, either because it is constant,
or because we don't care if it's not been updated.

### <a name="MoveToFastRAM"/>void MoveToFastRAM()
Asynchronously move this texture to fast RAM.
Some hardware has "fast RAM" that we can prefetch textures into.

### <a name="MoveToSlowRAM"/>void MoveToSlowRAM()
Asynchronously move this texture to slow RAM.

### <a name="NumFaces"/>int NumFaces()
The number of "faces": either equal to the array size, or in the case of a cubemap, six times that number.

### <a name="SetFence"/>void SetFence(unsigned long long)
Set the fence on this texture: it cannot be used until the fence has been triggered by the rendering API.

### <a name="setTexels"/>void setTexels(simul::crossplatform::DeviceContext deviceContext, void src, int texel_index, int num_texels)
Set the texture data from CPU memory.

### <a name="SetUnfenceable"/>void SetUnfenceable(bool v)
Set whether to never check for fences on this texture.
