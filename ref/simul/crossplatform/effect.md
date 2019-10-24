---
title: Effect
layout: reference
weight: 0
---
class Effect
===

| Include: | Sky/BaseAtmosphericsRenderer.h |



Functions
---

| void | [Apply](#Apply)(simul::crossplatform::DeviceContext deviceContext, char tech_name, char pass) |
| void | [Apply](#Apply)(simul::crossplatform::DeviceContext deviceContext, char tech_name, int pass) |
| void | [Apply](#Apply)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::EffectTechnique effectTechnique, int pass) |
| void | [Apply](#Apply)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::EffectTechnique effectTechnique, char pass) |
| void | [EnsureEffect](#EnsureEffect)(simul::crossplatform::RenderPlatform r, char filename_utf8) |
| simul::crossplatform::SamplerStateAssignmentMap  & | [GetSamplers](#GetSamplers)() |
| void | [Reapply](#Reapply)(simul::crossplatform::DeviceContext deviceContext) |
| void | [SetConstantBuffer](#SetConstantBuffer)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ConstantBufferBase s) |
| void | [SetSamplerState](#SetSamplerState)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ShaderResource name, simul::crossplatform::SamplerState s) |
| void | [SetTexture](#SetTexture)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ShaderResource name, simul::crossplatform::Texture tex, int array_idx, int mip) |
| void | [SetTexture](#SetTexture)(simul::crossplatform::DeviceContext deviceContext, char name, simul::crossplatform::Texture tex, int array_idx, int mip) |
| void | [SetUnorderedAccessView](#SetUnorderedAccessView)(simul::crossplatform::DeviceContext deviceContext, char name, simul::crossplatform::Texture tex, int index, int mip) |
| void | [SetUnorderedAccessView](#SetUnorderedAccessView)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ShaderResource name, simul::crossplatform::Texture tex, int index, int mip) |
| void | [Unapply](#Unapply)(simul::crossplatform::DeviceContext deviceContext) |
| void | [UnbindTextures](#UnbindTextures)(simul::crossplatform::DeviceContext deviceContext) |


Functions
---
<a name="Apply"></a>
### void Apply(simul::crossplatform::DeviceContext deviceContext, char tech_name, char pass)
Activate the shader. Unapply must be called after rendering is done.
<a name="Apply"></a>
### void Apply(simul::crossplatform::DeviceContext deviceContext, char tech_name, int pass)
Activate the shader. Unapply must be called after rendering is done.
<a name="Apply"></a>
### void Apply(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::EffectTechnique effectTechnique, int pass)
Activate the shader. Unapply must be called after rendering is done.
<a name="Apply"></a>
### void Apply(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::EffectTechnique effectTechnique, char pass)
Activate the shader. Unapply must be called after rendering is done.
<a name="EnsureEffect"></a>
### void EnsureEffect(simul::crossplatform::RenderPlatform r, char filename_utf8)
Ensure it's built and up-to-date.
<a name="GetSamplers"></a>
### simul::crossplatform::SamplerStateAssignmentMap  & GetSamplers()
Map of sampler states used by this effect
<a name="Reapply"></a>
### void Reapply(simul::crossplatform::DeviceContext deviceContext)
Call Reapply between Apply and Unapply to apply the effect of modified constant buffers etc.
<a name="SetConstantBuffer"></a>
### void SetConstantBuffer(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ConstantBufferBase s)
Set a constant buffer for this effect.
<a name="SetSamplerState"></a>
### void SetSamplerState(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ShaderResource name, simul::crossplatform::SamplerState s)
Set the texture for this effect.
<a name="SetTexture"></a>
### void SetTexture(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ShaderResource name, simul::crossplatform::Texture tex, int array_idx, int mip)
Set the texture for this effect. If mip is specified, the specific mipmap will be used, otherwise it's the full texture with all its mipmaps.
<a name="SetTexture"></a>
### void SetTexture(simul::crossplatform::DeviceContext deviceContext, char name, simul::crossplatform::Texture tex, int array_idx, int mip)
Set the texture for this effect. If mip is specified, the specific mipmap will be used, otherwise it's the full texture with all its mipmaps.
<a name="SetUnorderedAccessView"></a>
### void SetUnorderedAccessView(simul::crossplatform::DeviceContext deviceContext, char name, simul::crossplatform::Texture tex, int index, int mip)
Set the texture for read-write access by compute shaders in this effect.
<a name="SetUnorderedAccessView"></a>
### void SetUnorderedAccessView(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ShaderResource name, simul::crossplatform::Texture tex, int index, int mip)
Set the texture for read-write access by compute shaders in this effect.
<a name="Unapply"></a>
### void Unapply(simul::crossplatform::DeviceContext deviceContext)
Deactivate the shader.
<a name="UnbindTextures"></a>
### void UnbindTextures(simul::crossplatform::DeviceContext deviceContext)
Zero-out the textures that are set for this shader. Call before apply.

Fields
---

**renderPlatform**  The cross-platform base class for shader effects.
