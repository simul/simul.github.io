---
title: RenderPlatform
layout: reference
weight: 0
---
class RenderPlatform
===

| Include: | Sky/BaseGpuSkyGenerator.h |



Functions
---

| void | [ActivateRenderTargets](#ActivateRenderTargets)(simul::crossplatform::DeviceContext deviceContext, int num, simul::crossplatform::Texture targs, simul::crossplatform::Texture depth) |
| void | [ApplyPass](#ApplyPass)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::EffectPass pass) |
| ID3D12GraphicsCommandList * | [AsD3D12CommandList](#AsD3D12CommandList)() |
| void | [BeginEvent](#BeginEvent)(simul::crossplatform::DeviceContext deviceContext, char name) |
| void | [Clear](#Clear)(simul::crossplatform::DeviceContext deviceContext, vec4 colour_rgba) |
| void | [ClearTexture](#ClearTexture)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture texture, vec4 colour) |
| void | [CopyTexture](#CopyTexture)(simul::crossplatform::DeviceContext, simul::crossplatform::Texture, simul::crossplatform::Texture) |
| simul::crossplatform::Buffer * | [CreateBuffer](#CreateBuffer)() |
| simul::crossplatform::Effect * | [CreateEffect](#CreateEffect)(char filename_utf8) |
| simul::crossplatform::Effect * | [CreateEffect](#CreateEffect)() |
| simul::crossplatform::Effect * | [CreateEffect](#CreateEffect)(char filename_utf8, std::map defines) |
| simul::crossplatform::BaseFramebuffer * | [CreateFramebuffer](#CreateFramebuffer)(char) |
| simul::crossplatform::Layout * | [CreateLayout](#CreateLayout)(int num_elements, simul::crossplatform::LayoutDesc layoutDesc, bool interleaved) |
| simul::crossplatform::Mesh * | [CreateMesh](#CreateMesh)() |
| simul::crossplatform::PlatformConstantBuffer * | [CreatePlatformConstantBuffer](#CreatePlatformConstantBuffer)() |
| simul::crossplatform::PlatformStructuredBuffer * | [CreatePlatformStructuredBuffer](#CreatePlatformStructuredBuffer)() |
| simul::crossplatform::Query * | [CreateQuery](#CreateQuery)(simul::crossplatform::QueryType q) |
| simul::crossplatform::RenderState * | [CreateRenderState](#CreateRenderState)(simul::crossplatform::RenderStateDesc desc) |
| simul::crossplatform::SamplerState * | [CreateSamplerState](#CreateSamplerState)(simul::crossplatform::SamplerStateDesc) |
| simul::crossplatform::Shader * | [CreateShader](#CreateShader)() |
| simul::crossplatform::Texture * | [CreateTexture](#CreateTexture)(char lFileNameUtf8) |
| void | [Destroy](#Destroy)(simul::crossplatform::Effect e) |
| void | [DispatchCompute](#DispatchCompute)(simul::crossplatform::DeviceContext deviceContext, int w, int l, int d) |
| void | [Draw](#Draw)(simul::crossplatform::DeviceContext deviceContext, int num_verts, int start_vert) |
| void | [DrawCircle](#DrawCircle)(simul::crossplatform::DeviceContext deviceContext, float dir, float rads, float colr, bool fill) |
| void | [DrawCircle](#DrawCircle)(simul::crossplatform::DeviceContext deviceContext, float pos, float dir, float radius, float colr, bool fill) |
| void | [DrawCubemap](#DrawCubemap)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture cubemap, float offsetx, float offsety, float size, float exposure, float gamma, float displayLod) |
| void | [DrawIndexed](#DrawIndexed)(simul::crossplatform::DeviceContext deviceContext, int num_indices, int start_index, int base_vertex) |
| void | [EndEvent](#EndEvent)(simul::crossplatform::DeviceContext) |
| void | [EnsureEffectIsBuilt](#EnsureEffectIsBuilt)(char filename_utf8, std::vector options) |
| simul::crossplatform::Shader * | [EnsureShader](#EnsureShader)(char filenameUtf8, simul::crossplatform::ShaderType t) |
| void | [GenerateMips](#GenerateMips)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture t, bool wrap, int array_idx) |
| simul::crossplatform::ContextState * | [GetContextState](#GetContextState)(simul::crossplatform::DeviceContext deviceContext) |
| simul::crossplatform::Effect * | [GetEffect](#GetEffect)(char name_utf8) |
| unsigned char | [GetIdx](#GetIdx)() |
| simul::crossplatform::DeviceContext  & | [GetImmediateContext](#GetImmediateContext)() |
| char  const * | [GetName](#GetName)() |
| simul::crossplatform::Material * | [GetOrCreateMaterial](#GetOrCreateMaterial)(char name) |
| simul::crossplatform::SamplerState * | [GetOrCreateSamplerStateByName](#GetOrCreateSamplerStateByName)(char name_utf8, simul::crossplatform::SamplerStateDesc desc) |
| std::vector | [GetShaderBinaryPathsUtf8](#GetShaderBinaryPathsUtf8)() |
| simul::crossplatform::ShaderBuildMode | [GetShaderBuildMode](#GetShaderBuildMode)() |
| std::vector | [GetShaderPathsUtf8](#GetShaderPathsUtf8)() |
| simul::crossplatform::Viewport | [GetViewport](#GetViewport)(simul::crossplatform::DeviceContext deviceContext, int index) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [LinePrint](#LinePrint)(simul::crossplatform::DeviceContext deviceContext, char text, float colr, float bkg) |
| void | [PopRenderTargets](#PopRenderTargets)(simul::crossplatform::DeviceContext deviceContext) |
| void | [PopShaderBinaryPath](#PopShaderBinaryPath)() |
| void | [PopShaderPath](#PopShaderPath)() |
| void | [PopTexturePath](#PopTexturePath)() |
| void | [PushRenderTargets](#PushRenderTargets)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::TargetsAndViewport tv) |
| void | [PushShaderBinaryPath](#PushShaderBinaryPath)(char path_utf8) |
| void | [PushShaderPath](#PushShaderPath)(char path_utf8) |
| void | [PushTexturePath](#PushTexturePath)(char pathUtf8) |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [Resolve](#Resolve)(simul::crossplatform::DeviceContext, simul::crossplatform::Texture, simul::crossplatform::Texture) |
| void | [ResourceBarrierUAV](#ResourceBarrierUAV)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture texture) |
| void | [ResourceBarrierUAV](#ResourceBarrierUAV)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::PlatformStructuredBuffer sb) |
| void | [ResourceTransition](#ResourceTransition)(simul::crossplatform::DeviceContext, simul::crossplatform::Texture, simul::crossplatform::ResourceTransition) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(void) |
| void | [RestoreRenderState](#RestoreRenderState)(simul::crossplatform::DeviceContext) |
| void | [SaveTexture](#SaveTexture)(simul::crossplatform::Texture, char) |
| void | [SetIndexBuffer](#SetIndexBuffer)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Buffer buffer) |
| void | [SetLayout](#SetLayout)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Layout l) |
| void | [SetRenderState](#SetRenderState)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::RenderState s) |
| void | [SetShaderBuildMode](#SetShaderBuildMode)(simul::crossplatform::ShaderBuildMode s) |
| void | [SetShaderPathsUtf8](#SetShaderPathsUtf8)(std::vector pathsUtf8) |
| void | [SetStandardRenderState](#SetStandardRenderState)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::StandardRenderState s) |
| void | [SetStreamOutTarget](#SetStreamOutTarget)(simul::crossplatform::DeviceContext, simul::crossplatform::Buffer, int) |
| void | [SetTopology](#SetTopology)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Topology t) |
| void | [SetVertexBuffers](#SetVertexBuffers)(simul::crossplatform::DeviceContext deviceContext, int slot, int num_buffers, simul::crossplatform::Buffer buffers, simul::crossplatform::Layout layout, int vertexSteps) |
| void | [StoreRenderState](#StoreRenderState)(simul::crossplatform::DeviceContext) |
| void | [SynchronizeCacheAndState](#SynchronizeCacheAndState)(simul::crossplatform::DeviceContext) |
| vec4 | [TexelQuery](#TexelQuery)(simul::crossplatform::DeviceContext deviceContext, int query_id, uint2 pos, simul::crossplatform::Texture texture) |
| void | [UnapplyPass](#UnapplyPass)(simul::crossplatform::DeviceContext deviceContext) |
| bool | [ApplyContextState](#ApplyContextState)(simul::crossplatform::DeviceContext, bool) |


Functions
---
<a name="ActivateRenderTargets"></a>
### void ActivateRenderTargets(simul::crossplatform::DeviceContext deviceContext, int num, simul::crossplatform::Texture targs, simul::crossplatform::Texture depth)
Make the specified rendertargets and optional depth target active.
<a name="ApplyPass"></a>
### void ApplyPass(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::EffectPass pass)
<summary>
Apply the specified effect pass for use in a draw or compute call. Must be followed by UnapplyPass() when done.
</summary>
<a name="AsD3D12CommandList"></a>
### ID3D12GraphicsCommandList * AsD3D12CommandList()
Returns the DX12 graphics command list
<a name="BeginEvent"></a>
### void BeginEvent(simul::crossplatform::DeviceContext deviceContext, char name)
For platforms that support named events, e.g. PIX in DirectX. Use BeginEvent(), EndEvent() as pairs.
<a name="Clear"></a>
### void Clear(simul::crossplatform::DeviceContext deviceContext, vec4 colour_rgba)
Clear the current render target (i.e. the screen). In most API's this is simply a case of drawing a full-screen quad in the specified rgba colour.
<a name="ClearTexture"></a>
### void ClearTexture(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture texture, vec4 colour)
Clear the contents of the given texture to the specified colour
<a name="CopyTexture"></a>
### void CopyTexture(simul::crossplatform::DeviceContext, simul::crossplatform::Texture, simul::crossplatform::Texture)
Copy a given texture to another.
<a name="CreateBuffer"></a>
### simul::crossplatform::Buffer * CreateBuffer()
Create a platform-specific buffer instance - e.g. vertex buffers, index buffers etc.
<a name="CreateEffect"></a>
### simul::crossplatform::Effect * CreateEffect(char filename_utf8)
Create a platform-specific effect instance.
<a name="CreateEffect"></a>
### simul::crossplatform::Effect * CreateEffect()
Create a platform-specific effect instance.
<a name="CreateEffect"></a>
### simul::crossplatform::Effect * CreateEffect(char filename_utf8, std::map defines)
Create a platform-specific effect instance.
<a name="CreateFramebuffer"></a>
### simul::crossplatform::BaseFramebuffer * CreateFramebuffer(char)
Create a platform-specific framebuffer instance - i.e. an optional colour and an optional depth rendertarget. Optionally takes a name string.
<a name="CreateLayout"></a>
### simul::crossplatform::Layout * CreateLayout(int num_elements, simul::crossplatform::LayoutDesc layoutDesc, bool interleaved)
Create a platform-specific layout instance based on the given layout description layoutDescand buffer buffer.
<a name="CreateMesh"></a>
### simul::crossplatform::Mesh * CreateMesh()
Create a platform-specific mesh instance.
<a name="CreatePlatformConstantBuffer"></a>
### simul::crossplatform::PlatformConstantBuffer * CreatePlatformConstantBuffer()
Create a platform-specific constant buffer instance. This is not usually used directly, instead, create a
simul::crossplatform::ConstantBuffer, and pass this RenderPlatform's pointer to it in RestoreDeviceObjects().
<a name="CreatePlatformStructuredBuffer"></a>
### simul::crossplatform::PlatformStructuredBuffer * CreatePlatformStructuredBuffer()
Create a platform-specific structured buffer instance. This is not usually used directly, instead, create a
simul::crossplatform::StructuredBuffer, and pass this RenderPlatform's pointer to it in RestoreDeviceObjects().
<a name="CreateQuery"></a>
### simul::crossplatform::Query * CreateQuery(simul::crossplatform::QueryType q)
Create an API-specific query object, e.g. for occlusion or timing tests.
<a name="CreateRenderState"></a>
### simul::crossplatform::RenderState * CreateRenderState(simul::crossplatform::RenderStateDesc desc)
Create a platform-specific RenderState object - e.g. a Blend state, Depth state, etc.
<a name="CreateSamplerState"></a>
### simul::crossplatform::SamplerState * CreateSamplerState(simul::crossplatform::SamplerStateDesc)
Create a platform-specific sampler state instance.
<a name="CreateShader"></a>
### simul::crossplatform::Shader * CreateShader()
Create a shader.
<a name="CreateTexture"></a>
### simul::crossplatform::Texture * CreateTexture(char lFileNameUtf8)
Create a platform-specific texture instance.
<a name="Destroy"></a>
### void Destroy(simul::crossplatform::Effect e)
Destroy the effect when it is safe to do so. The pointer can now be reassigned or nulled.
<a name="DispatchCompute"></a>
### void DispatchCompute(simul::crossplatform::DeviceContext deviceContext, int w, int l, int d)
Execute the currently applied compute shader.
<a name="Draw"></a>
### void Draw(simul::crossplatform::DeviceContext deviceContext, int num_verts, int start_vert)
Draw the specified number of vertices.
<a name="DrawCircle"></a>
### void DrawCircle(simul::crossplatform::DeviceContext deviceContext, float dir, float rads, float colr, bool fill)
Draw a circle facing the viewer at the specified direction and angular size.
<a name="DrawCircle"></a>
### void DrawCircle(simul::crossplatform::DeviceContext deviceContext, float pos, float dir, float radius, float colr, bool fill)
Draw a circle in 3D space at pos
<a name="DrawCubemap"></a>
### void DrawCubemap(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture cubemap, float offsetx, float offsety, float size, float exposure, float gamma, float displayLod)
Draw a cubemap as a sphere at the specified screen position and size.
<a name="DrawIndexed"></a>
### void DrawIndexed(simul::crossplatform::DeviceContext deviceContext, int num_indices, int start_index, int base_vertex)
Draw the specified number of vertices using the bound index arrays.
<a name="EndEvent"></a>
### void EndEvent(simul::crossplatform::DeviceContext)
For platforms that support named events, e.g. PIX in DirectX. Use BeginEvent(), EndEvent() as pairs.
<a name="EnsureEffectIsBuilt"></a>
### void EnsureEffectIsBuilt(char filename_utf8, std::vector options)
<a name="EnsureShader"></a>
### simul::crossplatform::Shader * EnsureShader(char filenameUtf8, simul::crossplatform::ShaderType t)
Get or create an API-specific shader object.
<a name="GenerateMips"></a>
### void GenerateMips(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture t, bool wrap, int array_idx)
Fill in mipmaps from the zero level down.
<a name="GetContextState"></a>
### simul::crossplatform::ContextState * GetContextState(simul::crossplatform::DeviceContext deviceContext)
Get the current state to be applied to the given context at the next draw or dispatch.
<a name="GetEffect"></a>
### simul::crossplatform::Effect * GetEffect(char name_utf8)
Get the effect named, or return null if it's not been created.
<a name="GetIdx"></a>
### unsigned char GetIdx()
Returns the current idx (used in ring buffers)
<a name="GetImmediateContext"></a>
### simul::crossplatform::DeviceContext  & GetImmediateContext()
Gets an object containing immediate-context API-specific values.
<a name="GetName"></a>
### char  const * GetName()
Returns the name of the render platform - DirectX 11, OpenGL, etc.
<a name="GetOrCreateMaterial"></a>
### simul::crossplatform::Material * GetOrCreateMaterial(char name)
Create a platform-specific material instance.
<a name="GetOrCreateSamplerStateByName"></a>
### simul::crossplatform::SamplerState * GetOrCreateSamplerStateByName(char name_utf8, simul::crossplatform::SamplerStateDesc desc)
Look for a sampler state of the stated name, and create one if it does not exist. The resulting state will be owned by the RenderPlatform, so do not destroy it.
This is for states that will be shared by multiple shaders. There will be a warning if a description is passed that conflicts with the current definition,
as the Effects system assumes that SamplerState names are unique.
<a name="GetShaderBinaryPathsUtf8"></a>
### std::vector GetShaderBinaryPathsUtf8()
Returns the path where generated shader binaries should be saved, and where stored shader binaries should be loaded from.
<a name="GetShaderBuildMode"></a>
### simul::crossplatform::ShaderBuildMode GetShaderBuildMode()
When shaders should be built, or loaded if available.
<a name="GetShaderPathsUtf8"></a>
### std::vector GetShaderPathsUtf8()
Returns the stack of shader source paths.
<a name="GetViewport"></a>
### simul::crossplatform::Viewport GetViewport(simul::crossplatform::DeviceContext deviceContext, int index)
Get the viewport at the given index.
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the Render Platform.
<a name="LinePrint"></a>
### void LinePrint(simul::crossplatform::DeviceContext deviceContext, char text, float colr, float bkg)
Print diagnostics, starting from the top, and going down the screen one line each time as the frame progresses, then restarting next frame.
<a name="PopRenderTargets"></a>
### void PopRenderTargets(simul::crossplatform::DeviceContext deviceContext)
Restore rendertargets and viewports from the top of the stack.
<a name="PopShaderBinaryPath"></a>
### void PopShaderBinaryPath()
Remove a path from the top of the shader source path stack.
<a name="PopShaderPath"></a>
### void PopShaderPath()
Remove a path from the top of the shader source path stack.
<a name="PopTexturePath"></a>
### void PopTexturePath()
Remove a path from the top of the texture path stack.
<a name="PushRenderTargets"></a>
### void PushRenderTargets(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::TargetsAndViewport tv)
Store the current rendertargets and viewports at the top of the stack
<a name="PushShaderBinaryPath"></a>
### void PushShaderBinaryPath(char path_utf8)
Set the path where generated shader binaries should be saved, and where stored shader binaries should be loaded from.
Push the given file path onto the shader path stack.
<a name="PushShaderPath"></a>
### void PushShaderPath(char path_utf8)
Push the given file path onto the shader path stack.
<a name="PushTexturePath"></a>
### void PushTexturePath(char pathUtf8)
Push the given file path onto the texture path stack.
<a name="RecompileShaders"></a>
### void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.
<a name="Resolve"></a>
### void Resolve(simul::crossplatform::DeviceContext, simul::crossplatform::Texture, simul::crossplatform::Texture)
Resolve an MSAA texture to a normal texture.
<a name="ResourceBarrierUAV"></a>
### void ResourceBarrierUAV(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture texture)
Ensures that all UAV read and write operation to the textures are completed.
<a name="ResourceBarrierUAV"></a>
### void ResourceBarrierUAV(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::PlatformStructuredBuffer sb)
Ensures that all UAV read and write operation to the PlatformStructuredBuffer are completed.
<a name="ResourceTransition"></a>
### void ResourceTransition(simul::crossplatform::DeviceContext, simul::crossplatform::Texture, simul::crossplatform::ResourceTransition)
Makes sure the resource is in the required state specified by transition.
<a name="RestoreDeviceObjects"></a>
### void RestoreDeviceObjects(void)
Platform-dependent function called when initializing the Render Platform.
<a name="RestoreRenderState"></a>
### void RestoreRenderState(simul::crossplatform::DeviceContext)
Called to restore the render state previously stored with StoreRenderState. There must be exactly one call of RestoreRenderState
for each StoreRenderState call, and they are not expected to be nested.
<a name="SaveTexture"></a>
### void SaveTexture(simul::crossplatform::Texture, char)
Save a texture to disk.
<a name="SetIndexBuffer"></a>
### void SetIndexBuffer(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Buffer buffer)
Activate the specified index buffer in preparation for rendering.
<a name="SetLayout"></a>
### void SetLayout(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Layout l)
Set the layout for following draw calls - format of the vertex buffer.
<a name="SetRenderState"></a>
### void SetRenderState(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::RenderState s)
Apply the RenderState to the device context - e.g. blend state, depth masking etc.
<a name="SetShaderBuildMode"></a>
### void SetShaderBuildMode(simul::crossplatform::ShaderBuildMode s)
When shaders should be built, or loaded if available.
<a name="SetShaderPathsUtf8"></a>
### void SetShaderPathsUtf8(std::vector pathsUtf8)
Replace the entire stack of shader source paths.
<a name="SetStandardRenderState"></a>
### void SetStandardRenderState(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::StandardRenderState s)
Apply a standard renderstate - e.g. opaque blending
<a name="SetStreamOutTarget"></a>
### void SetStreamOutTarget(simul::crossplatform::DeviceContext, simul::crossplatform::Buffer, int)
Graphics hardware can write to vertex buffers using vertex and geometry shaders; use this function to set the target buffer.
<a name="SetTopology"></a>
### void SetTopology(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Topology t)
Set the topology for following draw calls, e.g. TRIANGLELIST etc.
<a name="SetVertexBuffers"></a>
### void SetVertexBuffers(simul::crossplatform::DeviceContext deviceContext, int slot, int num_buffers, simul::crossplatform::Buffer buffers, simul::crossplatform::Layout layout, int vertexSteps)
Activate the specifided vertex buffers in preparation for rendering.
<a name="StoreRenderState"></a>
### void StoreRenderState(simul::crossplatform::DeviceContext)
Called to store the render state - blending, depth check, etc. - for later retrieval with RestoreRenderState.
Some platforms may not support this.
<a name="SynchronizeCacheAndState"></a>
### void SynchronizeCacheAndState(simul::crossplatform::DeviceContext)
Implementations of RenderPlatform will cache the API state in order to reduce driver overhead.
But we can't always be sure that external render code hasn't modified the API state. So by calling SynchronizeCacheAndState()
the API state is forced to the cached state. This can be called at the start of Renderplatform's rendering per-frame.
<a name="TexelQuery"></a>
### vec4 TexelQuery(simul::crossplatform::DeviceContext deviceContext, int query_id, uint2 pos, simul::crossplatform::Texture texture)
Query for the texture value at the specified position in the texture. On most API's, the query will have a few frames' latency.
<a name="UnapplyPass"></a>
### void UnapplyPass(simul::crossplatform::DeviceContext deviceContext)
<summary>
Unapply the previously applied effect pass after use in a draw or compute call.
</summary>
<a name="ApplyContextState"></a>
### bool ApplyContextState(simul::crossplatform::DeviceContext, bool)
This is called by draw functions to do any lazy updating prior to the actual API draw/dispatch call.

Fields
---

Variables
---

**mirrorY**  This was introduced because Unity's deferred renderer flips the image vertically sometime after we render.

**ApiCallLimit**  RenderPlatform is an interface that allows Simul's rendering functions to be developed
in a cross-platform manner. By abstracting the common functionality of the different graphics API's
into an interface, we can write render code that need not know which API is being used. It is possible
to create platform-specific objects like /link CreateTexture textures/endlink, /link CreateEffect effects/endlink
and /link CreateBuffer buffers/endlink

Be sure to make the following calls at the appropriate places:
RestoreDeviceObjects(), InvalidateDeviceObjects(), RecompileShaders()


**mCurIdx**  Value used to select the current heap, it will be looping around: [0,kNumIdx)

**mLastFrame**  Last frame number
