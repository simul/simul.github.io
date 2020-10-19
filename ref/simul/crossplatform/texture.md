---
title: Texture
layout: reference
weight: 0
---
class Texture
===

| Include: | Sky/BaseAtmosphericsRenderer.h |



Functions
---

| void | [activateRenderTarget](#activateRenderTarget)(simul::crossplatform::GraphicsDeviceContext deviceContext, int array_index, int mip_index) |
| ID3D11RenderTargetView * | [AsD3D11RenderTargetView](#AsD3D11RenderTargetView)(int, int) |
| ID3D11ShaderResourceView * | [AsD3D11ShaderResourceView](#AsD3D11ShaderResourceView)(simul::crossplatform::ShaderResourceType, int, int) |
| ID3D11UnorderedAccessView * | [AsD3D11UnorderedAccessView](#AsD3D11UnorderedAccessView)(int, int) |
| sce::Gnm::Texture * | [AsGnmTexture](#AsGnmTexture)(simul::crossplatform::ShaderResourceType, int, int) |
| void | [ClearDepthStencil](#ClearDepthStencil)(simul::crossplatform::GraphicsDeviceContext deviceContext, float, int) |
| void | [ClearFence](#ClearFence)(simul::crossplatform::DeviceContext deviceContext) |
| void | [deactivateRenderTarget](#deactivateRenderTarget)(simul::crossplatform::GraphicsDeviceContext deviceContext) |
| bool | [ensureTexture2DSizeAndFormat](#ensureTexture2DSizeAndFormat)(simul::crossplatform::RenderPlatform renderPlatform, int w, int l, simul::crossplatform::PixelFormat f, bool computable, bool rendertarget, bool depthstencil, int num_samples, int aa_quality, bool wrap, vec4 clear, float clearDepth, uint clearStencil) |
| bool | [ensureTexture3DSizeAndFormat](#ensureTexture3DSizeAndFormat)(simul::crossplatform::RenderPlatform renderPlatform, int w, int l, int d, simul::crossplatform::PixelFormat frmt, bool computable, int mips, bool rendertargets) |
| bool | [ensureTextureArraySizeAndFormat](#ensureTextureArraySizeAndFormat)(simul::crossplatform::RenderPlatform renderPlatform, int w, int l, int num, int mips, simul::crossplatform::PixelFormat f, bool computable, bool rendertarget, bool cubemap) |
| void | [GenerateMips](#GenerateMips)(simul::crossplatform::GraphicsDeviceContext deviceContext) |
| unsigned long long | [GetFence](#GetFence)(simul::crossplatform::DeviceContext) |
| simul::crossplatform::PixelFormat | [GetFormat](#GetFormat)() |
| int | [GetSampleCount](#GetSampleCount)() |
| void | [InitFromExternalTexture2D](#InitFromExternalTexture2D)(simul::crossplatform::RenderPlatform renderPlatform, void t, void srv, int w, int l, simul::crossplatform::PixelFormat f, bool make_rt, bool setDepthStencil, bool need_srv, int numOfSamples) |
| bool | [IsDepthStencil](#IsDepthStencil)() |
| bool | [IsUnfenceable](#IsUnfenceable)() |
| void | [MoveToFastRAM](#MoveToFastRAM)() |
| void | [MoveToSlowRAM](#MoveToSlowRAM)() |
| int | [NumFaces](#NumFaces)() |
| void | [RestoreExternalTextureState](#RestoreExternalTextureState)(simul::crossplatform::DeviceContext) |
| void | [SetFence](#SetFence)(simul::crossplatform::DeviceContext, unsigned long long) |
| void | [setTexels](#setTexels)(simul::crossplatform::DeviceContext deviceContext, void src, int texel_index, int num_texels) |
| void | [SetUnfenceable](#SetUnfenceable)(bool v) |
| void | [StoreExternalState](#StoreExternalState)(simul::crossplatform::ResourceState) |


Functions
---
<a name="activateRenderTarget"></a>
### void activateRenderTarget(simul::crossplatform::GraphicsDeviceContext deviceContext, int array_index, int mip_index)
Activate as a rendertarget - must call deactivateRenderTarget afterwards.
<a name="AsD3D11RenderTargetView"></a>
### ID3D11RenderTargetView * AsD3D11RenderTargetView(int, int)
Returns the RTV specified by layer,mip. Layer -1 means all layers at the given mip, while mip -1 defaults to mip zero.
<a name="AsD3D11ShaderResourceView"></a>
### ID3D11ShaderResourceView * AsD3D11ShaderResourceView(simul::crossplatform::ShaderResourceType, int, int)
Returns the SRV specified by layer,mip. The type t ensures that the assigned resource is compatible (UNKNWON matches anything).
Layer -1 means all layers at the given mip, while mip -1 defaults to the whole texture/layer.
<a name="AsD3D11UnorderedAccessView"></a>
### ID3D11UnorderedAccessView * AsD3D11UnorderedAccessView(int, int)
Returns the UAV specified by layer,mip. Layer -1 means all layers at the given mip, while mip -1 defaults to mip zero.
<a name="AsGnmTexture"></a>
### sce::Gnm::Texture * AsGnmTexture(simul::crossplatform::ShaderResourceType, int, int)
Returns the GnmTexture specified by layer,mip. Default values of -1 mean "all".
<a name="ClearDepthStencil"></a>
### void ClearDepthStencil(simul::crossplatform::GraphicsDeviceContext deviceContext, float, int)
Clear the depth stencil
<a name="ClearFence"></a>
### void ClearFence(simul::crossplatform::DeviceContext deviceContext)
Clear the fence: this texture is ok to use now.
<a name="deactivateRenderTarget"></a>
### void deactivateRenderTarget(simul::crossplatform::GraphicsDeviceContext deviceContext)
Deactivate as a rendertarget.
<a name="ensureTexture2DSizeAndFormat"></a>
### bool ensureTexture2DSizeAndFormat(simul::crossplatform::RenderPlatform renderPlatform, int w, int l, simul::crossplatform::PixelFormat f, bool computable, bool rendertarget, bool depthstencil, int num_samples, int aa_quality, bool wrap, vec4 clear, float clearDepth, uint clearStencil)
Initialize as a standard 2D texture. Not all platforms need wrapto be specified. Returns true if modified, false otherwise.
<a name="ensureTexture3DSizeAndFormat"></a>
### bool ensureTexture3DSizeAndFormat(simul::crossplatform::RenderPlatform renderPlatform, int w, int l, int d, simul::crossplatform::PixelFormat frmt, bool computable, int mips, bool rendertargets)
Initialize as a volume texture.
<a name="ensureTextureArraySizeAndFormat"></a>
### bool ensureTextureArraySizeAndFormat(simul::crossplatform::RenderPlatform renderPlatform, int w, int l, int num, int mips, simul::crossplatform::PixelFormat f, bool computable, bool rendertarget, bool cubemap)
Initialize as an array texture if necessary. Returns true if the texture was initialized, or false if it was already in the required format.
<a name="GenerateMips"></a>
### void GenerateMips(simul::crossplatform::GraphicsDeviceContext deviceContext)
Generate the mipmaps automatically.
<a name="GetFence"></a>
### unsigned long long GetFence(simul::crossplatform::DeviceContext)
Get the current fence on this texture; it should not be used until the API has passed this fence.
<a name="GetFormat"></a>
### simul::crossplatform::PixelFormat GetFormat()
Get the crossplatform pixel format.
<a name="GetSampleCount"></a>
### int GetSampleCount()
If the texture is multisampled, this returns the samples per texel. Zero means it is not an MS texture,
while 1 means it is MS, even though the sample count is unity.
<a name="InitFromExternalTexture2D"></a>
### void InitFromExternalTexture2D(simul::crossplatform::RenderPlatform renderPlatform, void t, void srv, int w, int l, simul::crossplatform::PixelFormat f, bool make_rt, bool setDepthStencil, bool need_srv, int numOfSamples)
Initialize this object as a wrapper around a native, platform-specific texture. The interpretations of t and srv are platform-dependent.
<a name="IsDepthStencil"></a>
### bool IsDepthStencil()
Get whether texture is a depth stencil
<a name="IsUnfenceable"></a>
### bool IsUnfenceable()
Is the texture "unfenceable": if so, it need never be checked for fences, either because it is constant,
or because we don't care if it's not been updated.
<a name="MoveToFastRAM"></a>
### void MoveToFastRAM()
Asynchronously move this texture to fast RAM.
Some hardware has "fast RAM" that we can prefetch textures into.
<a name="MoveToSlowRAM"></a>
### void MoveToSlowRAM()
Asynchronously move this texture to slow RAM.
<a name="NumFaces"></a>
### int NumFaces()
The number of "faces": either equal to the array size, or in the case of a cubemap, six times that number.
<a name="RestoreExternalTextureState"></a>
### void RestoreExternalTextureState(simul::crossplatform::DeviceContext)
For API's that care about Resource State, aka Layout, restore the state internally.
<a name="SetFence"></a>
### void SetFence(simul::crossplatform::DeviceContext, unsigned long long)
Set the fence on this texture: it cannot be used until the fence has been triggered by the rendering API.
<a name="setTexels"></a>
### void setTexels(simul::crossplatform::DeviceContext deviceContext, void src, int texel_index, int num_texels)
Set the texture data from CPU memory.
<a name="SetUnfenceable"></a>
### void SetUnfenceable(bool v)
Set whether to never check for fences on this texture.
<a name="StoreExternalState"></a>
### void StoreExternalState(simul::crossplatform::ResourceState)
For API's that care about Resource State, aka Layout, tell the Simul API what state it was in to begin with.

Fields
---

**cubemap**  A Texture base class.
