---
title: Effect
layout: reference
weight: 0
---
class Effect
===

| Include: | Clouds/BaseLightningRenderer.h |

The cross-platform base class for shader effects.
  


Functions
---

| void | [Apply](#Apply)(simul::crossplatform::DeviceContext deviceContext, char tech_name, char pass) |
| void | [Apply](#Apply)(simul::crossplatform::DeviceContext deviceContext, char tech_name, int pass) |
| void | [Apply](#Apply)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::EffectTechnique effectTechnique, int pass) |
| void | [Apply](#Apply)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::EffectTechnique effectTechnique, char pass) |
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

The cross-platform base class for shader effects.
  


Functions
---

### <a name="Apply"/>void Apply(simul::crossplatform::DeviceContext deviceContext, char tech_name, char pass)
Activate the shader. Unapply must be called after rendering is done.

### <a name="Apply"/>void Apply(simul::crossplatform::DeviceContext deviceContext, char tech_name, int pass)
Activate the shader. Unapply must be called after rendering is done.

### <a name="Apply"/>void Apply(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::EffectTechnique effectTechnique, int pass)
Activate the shader. Unapply must be called after rendering is done.

### <a name="Apply"/>void Apply(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::EffectTechnique effectTechnique, char pass)
Activate the shader. Unapply must be called after rendering is done.

### <a name="GetSamplers"/>simul::crossplatform::SamplerStateAssignmentMap  & GetSamplers()
Map of sampler states used by this effect

### <a name="Reapply"/>void Reapply(simul::crossplatform::DeviceContext deviceContext)
Call Reapply between Apply and Unapply to apply the effect of modified constant buffers etc.

### <a name="SetConstantBuffer"/>void SetConstantBuffer(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ConstantBufferBase s)
Set a constant buffer for this effect.

### <a name="SetSamplerState"/>void SetSamplerState(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ShaderResource name, simul::crossplatform::SamplerState s)
Set the texture for this effect.

### <a name="SetTexture"/>void SetTexture(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ShaderResource name, simul::crossplatform::Texture tex, int array_idx, int mip)
Set the texture for this effect. If mip is specified, the specific mipmap will be used, otherwise it's the full texture with all its mipmaps.

### <a name="SetTexture"/>void SetTexture(simul::crossplatform::DeviceContext deviceContext, char name, simul::crossplatform::Texture tex, int array_idx, int mip)
Set the texture for this effect. If mip is specified, the specific mipmap will be used, otherwise it's the full texture with all its mipmaps.

### <a name="SetUnorderedAccessView"/>void SetUnorderedAccessView(simul::crossplatform::DeviceContext deviceContext, char name, simul::crossplatform::Texture tex, int index, int mip)
Set the texture for read-write access by compute shaders in this effect.

### <a name="SetUnorderedAccessView"/>void SetUnorderedAccessView(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::ShaderResource name, simul::crossplatform::Texture tex, int index, int mip)
Set the texture for read-write access by compute shaders in this effect.

### <a name="Unapply"/>void Unapply(simul::crossplatform::DeviceContext deviceContext)
Deactivate the shader.

### <a name="UnbindTextures"/>void UnbindTextures(simul::crossplatform::DeviceContext deviceContext)
Zero-out the textures that are set for this shader. Call before apply.
