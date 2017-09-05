---
title: RenderPlatform
layout: reference
weight: 0
---
class RenderPlatform
===

| Include: | Sky/BaseGpuSkyGenerator.h |

RenderPlatform is an interface that allows Simul's rendering functions to be developed<br>        in a cross-platform manner. By abstracting the common functionality of the different graphics API's<br>        into an interface, we can write render code that need not know which API is being used. It is possible<br>        to create platform-specific objects like /link CreateTexture textures/endlink, /link CreateEffect effects/endlink<br>        and /link CreateBuffer buffers/endlink<br>


Functions
---

| void | [ActivateRenderTargets](#ActivateRenderTargets)(simul::crossplatform::DeviceContext deviceContext, int num, simul::crossplatform::Texture targs, simul::crossplatform::Texture depth) |
| void | [BeginEvent](#BeginEvent)(simul::crossplatform::DeviceContext deviceContext, char name) |
| void | [Clear](#Clear)(simul::crossplatform::DeviceContext deviceContext, vec4 colour_rgba) |
| void | [ClearTexture](#ClearTexture)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture texture, vec4 colour) |
| simul::crossplatform::Buffer * | [CreateBuffer](#CreateBuffer)() |
| simul::crossplatform::Effect * | [CreateEffect](#CreateEffect)(char filename_utf8) |
| simul::crossplatform::Effect * | [CreateEffect](#CreateEffect)() |
| simul::crossplatform::Effect * | [CreateEffect](#CreateEffect)(char filename_utf8, std::map<std::basic_string<char, std::char_traits<char>, std::allocator<char> >, std::basic_string<char, std::char_traits<char>, std::allocator<char> >, std::less<std::basic_string<char, std::char_traits<char>, std::allocator<char> > >, std::allocator<std::pair<const std::basic_string<char, std::char_traits<char>, std::allocator<char> >, std::basic_string<char, std::char_traits<char>, std::allocator<char> > > > > defines) |
| simul::crossplatform::BaseFramebuffer * | [CreateFramebuffer](#CreateFramebuffer)(char) |
| simul::crossplatform::Layout * | [CreateLayout](#CreateLayout)(int num_elements, simul::crossplatform::LayoutDesc layoutDesc) |
| simul::crossplatform::Light * | [CreateLight](#CreateLight)() |
| simul::crossplatform::Material * | [CreateMaterial](#CreateMaterial)() |
| simul::crossplatform::Mesh * | [CreateMesh](#CreateMesh)() |
| simul::crossplatform::PlatformConstantBuffer * | [CreatePlatformConstantBuffer](#CreatePlatformConstantBuffer)() |
| simul::crossplatform::PlatformStructuredBuffer * | [CreatePlatformStructuredBuffer](#CreatePlatformStructuredBuffer)() |
| simul::crossplatform::Query * | [CreateQuery](#CreateQuery)(simul::crossplatform::QueryType q) |
| simul::crossplatform::RenderState * | [CreateRenderState](#CreateRenderState)(simul::crossplatform::RenderStateDesc desc) |
| simul::crossplatform::SamplerState * | [CreateSamplerState](#CreateSamplerState)(simul::crossplatform::SamplerStateDesc) |
| simul::crossplatform::Texture * | [CreateTexture](#CreateTexture)(char lFileNameUtf8) |
| void | [DispatchCompute](#DispatchCompute)(simul::crossplatform::DeviceContext deviceContext, int w, int l, int d) |
| void | [Draw](#Draw)(simul::crossplatform::DeviceContext deviceContext, int num_verts, int start_vert) |
| void | [DrawCircle](#DrawCircle)(simul::crossplatform::DeviceContext deviceContext, float dir, float rads, float colr, bool fill) |
| void | [DrawCircle](#DrawCircle)(simul::crossplatform::DeviceContext deviceContext, float pos, float dir, float radius, float colr, bool fill) |
| void | [DrawCubemap](#DrawCubemap)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture cubemap, float offsetx, float offsety, float size, float exposure, float gamma, float displayLod) |
| void | [DrawIndexed](#DrawIndexed)(simul::crossplatform::DeviceContext deviceContext, int num_indices, int start_index, int base_vertex) |
| void | [EndEvent](#EndEvent)(simul::crossplatform::DeviceContext deviceContext) |
| void | [EnsureEffectIsBuilt](#EnsureEffectIsBuilt)(char filename_utf8, std::vector<simul::crossplatform::EffectDefineOptions, std::allocator<simul::crossplatform::EffectDefineOptions> > options) |
| simul::crossplatform::Shader * | [EnsureShader](#EnsureShader)(char filenameUtf8, simul::crossplatform::ShaderType t) |
| simul::crossplatform::ContextState * | [GetContextState](#GetContextState)(simul::crossplatform::DeviceContext deviceContext) |
| simul::crossplatform::DeviceContext  & | [GetImmediateContext](#GetImmediateContext)() |
| char  const * | [GetName](#GetName)() |
| simul::crossplatform::SamplerState * | [GetOrCreateSamplerStateByName](#GetOrCreateSamplerStateByName)(char name_utf8, simul::crossplatform::SamplerStateDesc desc) |
| char  const * | [GetShaderBinaryPath](#GetShaderBinaryPath)() |
| simul::crossplatform::ShaderBuildMode | [GetShaderBuildMode](#GetShaderBuildMode)() |
| std::vector<std::basic_string<char, std::char_traits<char>, std::allocator<char> >, std::allocator<std::basic_string<char, std::char_traits<char>, std::allocator<char> > > > | [GetShaderPathsUtf8](#GetShaderPathsUtf8)() |
| simul::crossplatform::Viewport | [GetViewport](#GetViewport)(simul::crossplatform::DeviceContext deviceContext, int index) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [PopRenderTargets](#PopRenderTargets)(simul::crossplatform::DeviceContext deviceContext) |
| void | [PopShaderPath](#PopShaderPath)() |
| void | [PopTexturePath](#PopTexturePath)() |
| void | [PushRenderTargets](#PushRenderTargets)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::TargetsAndViewport tv) |
| void | [PushShaderPath](#PushShaderPath)(char path_utf8) |
| void | [PushTexturePath](#PushTexturePath)(char pathUtf8) |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [Resolve](#Resolve)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture destination, simul::crossplatform::Texture source) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(void) |
| void | [RestoreRenderState](#RestoreRenderState)(simul::crossplatform::DeviceContext deviceContext) |
| void | [SaveTexture](#SaveTexture)(simul::crossplatform::Texture texture, char lFileNameUtf8) |
| void | [SetIndexBuffer](#SetIndexBuffer)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Buffer buffer) |
| void | [SetLayout](#SetLayout)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Layout l) |
| void | [SetRenderState](#SetRenderState)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::RenderState s) |
| void | [SetShaderBinaryPath](#SetShaderBinaryPath)(char path_utf8) |
| void | [SetShaderBuildMode](#SetShaderBuildMode)(simul::crossplatform::ShaderBuildMode s) |
| void | [SetShaderPathsUtf8](#SetShaderPathsUtf8)(std::vector<std::basic_string<char, std::char_traits<char>, std::allocator<char> >, std::allocator<std::basic_string<char, std::char_traits<char>, std::allocator<char> > > > pathsUtf8) |
| void | [SetStandardRenderState](#SetStandardRenderState)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::StandardRenderState s) |
| void | [SetStreamOutTarget](#SetStreamOutTarget)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Buffer buffer, int start_index) |
| void | [SetTopology](#SetTopology)(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Topology t) |
| void | [SetVertexBuffers](#SetVertexBuffers)(simul::crossplatform::DeviceContext deviceContext, int slot, int num_buffers, simul::crossplatform::Buffer buffers, simul::crossplatform::Layout layout, int vertexSteps) |
| void | [StoreRenderState](#StoreRenderState)(simul::crossplatform::DeviceContext deviceContext) |
| void | [SynchronizeCacheAndState](#SynchronizeCacheAndState)(simul::crossplatform::DeviceContext) |
| vec4 | [TexelQuery](#TexelQuery)(simul::crossplatform::DeviceContext deviceContext, int query_id, uint2 pos, simul::crossplatform::Texture texture) |
| bool | [ApplyContextState](#ApplyContextState)(simul::crossplatform::DeviceContext, bool) |

Be sure to make the following calls at the appropriate places:
        RestoreDeviceObjects(), InvalidateDeviceObjects(), RecompileShaders()

  


Functions
---

### <a name="ActivateRenderTargets"/>void ActivateRenderTargets(simul::crossplatform::DeviceContext deviceContext, int num, simul::crossplatform::Texture targs, simul::crossplatform::Texture depth)
Make the specified rendertargets and optional depth target active.
Make the specified rendertargets and optional depth target active.

### <a name="BeginEvent"/>void BeginEvent(simul::crossplatform::DeviceContext deviceContext, char name)
For platforms that support named events, e.g. PIX in DirectX. Use BeginEvent(), EndEvent() as pairs.
For platforms that support named events, e.g. PIX in DirectX. Use BeginEvent(), EndEvent() as pairs.

### <a name="Clear"/>void Clear(simul::crossplatform::DeviceContext deviceContext, vec4 colour_rgba)
Clear the current render target (i.e. the screen). In most API's this is simply a case of drawing a full-screen quad in the specified rgba colour.
Clear the current render target (i.e. the screen). In most API's this is simply a case of drawing a full-screen quad in the specified rgba colour.

### <a name="ClearTexture"/>void ClearTexture(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture texture, vec4 colour)
Clear the contents of the given texture to the specified colour
Clear the contents of the given texture to the specified colour

### <a name="CreateBuffer"/>simul::crossplatform::Buffer * CreateBuffer()
Create a platform-specific buffer instance - e.g. vertex buffers, index buffers etc.
Create a platform-specific buffer instance - e.g. vertex buffers, index buffers etc.

### <a name="CreateEffect"/>simul::crossplatform::Effect * CreateEffect(char filename_utf8)
Create a platform-specific effect instance.
Create a platform-specific effect instance.

### <a name="CreateEffect"/>simul::crossplatform::Effect * CreateEffect()
Create a platform-specific effect instance.
Create a platform-specific effect instance.

### <a name="CreateEffect"/>simul::crossplatform::Effect * CreateEffect(char filename_utf8, std::map<std::basic_string<char, std::char_traits<char>, std::allocator<char> >, std::basic_string<char, std::char_traits<char>, std::allocator<char> >, std::less<std::basic_string<char, std::char_traits<char>, std::allocator<char> > >, std::allocator<std::pair<const std::basic_string<char, std::char_traits<char>, std::allocator<char> >, std::basic_string<char, std::char_traits<char>, std::allocator<char> > > > > defines)
Create a platform-specific effect instance.
Create a platform-specific effect instance.

### <a name="CreateFramebuffer"/>simul::crossplatform::BaseFramebuffer * CreateFramebuffer(char)
Create a platform-specific framebuffer instance - i.e. an optional colour and an optional depth rendertarget. Optionally takes a name string.
Create a platform-specific framebuffer instance - i.e. an optional colour and an optional depth rendertarget. Optionally takes a name string.

### <a name="CreateLayout"/>simul::crossplatform::Layout * CreateLayout(int num_elements, simul::crossplatform::LayoutDesc layoutDesc)
Create a platform-specific layout instance based on the given layout description **layoutDesc** and buffer **buffer**.
Create a platform-specific layout instance based on the given layout description **layoutDesc** and buffer **buffer**.

### <a name="CreateLight"/>simul::crossplatform::Light * CreateLight()
Create a platform-specific light instance.
Create a platform-specific light instance.

### <a name="CreateMaterial"/>simul::crossplatform::Material * CreateMaterial()
Create a platform-specific material instance.
Create a platform-specific material instance.

### <a name="CreateMesh"/>simul::crossplatform::Mesh * CreateMesh()
Create a platform-specific mesh instance.
Create a platform-specific mesh instance.

### <a name="CreatePlatformConstantBuffer"/>simul::crossplatform::PlatformConstantBuffer * CreatePlatformConstantBuffer()
Create a platform-specific constant buffer instance. This is not usually used directly, instead, create a
simul::crossplatform::ConstantBuffer, and pass this RenderPlatform's pointer to it in RestoreDeviceObjects().
Create a platform-specific constant buffer instance. This is not usually used directly, instead, create a
simul::crossplatform::ConstantBuffer, and pass this RenderPlatform's pointer to it in RestoreDeviceObjects().

### <a name="CreatePlatformStructuredBuffer"/>simul::crossplatform::PlatformStructuredBuffer * CreatePlatformStructuredBuffer()
Create a platform-specific structured buffer instance. This is not usually used directly, instead, create a
simul::crossplatform::StructuredBuffer, and pass this RenderPlatform's pointer to it in RestoreDeviceObjects().
Create a platform-specific structured buffer instance. This is not usually used directly, instead, create a
simul::crossplatform::StructuredBuffer, and pass this RenderPlatform's pointer to it in RestoreDeviceObjects().

### <a name="CreateQuery"/>simul::crossplatform::Query * CreateQuery(simul::crossplatform::QueryType q)
Create an API-specific query object, e.g. for occlusion or timing tests.
Create an API-specific query object, e.g. for occlusion or timing tests.

### <a name="CreateRenderState"/>simul::crossplatform::RenderState * CreateRenderState(simul::crossplatform::RenderStateDesc desc)
Create a platform-specific RenderState object - e.g. a Blend state, Depth state, etc.
Create a platform-specific RenderState object - e.g. a Blend state, Depth state, etc.

### <a name="CreateSamplerState"/>simul::crossplatform::SamplerState * CreateSamplerState(simul::crossplatform::SamplerStateDesc)
Create a platform-specific sampler state instance.
Create a platform-specific sampler state instance.

### <a name="CreateTexture"/>simul::crossplatform::Texture * CreateTexture(char lFileNameUtf8)
Create a platform-specific texture instance.
Create a platform-specific texture instance.

### <a name="DispatchCompute"/>void DispatchCompute(simul::crossplatform::DeviceContext deviceContext, int w, int l, int d)
Execute the currently applied compute shader.
Execute the currently applied compute shader.

### <a name="Draw"/>void Draw(simul::crossplatform::DeviceContext deviceContext, int num_verts, int start_vert)
Draw the specified number of vertices.
Draw the specified number of vertices.

### <a name="DrawCircle"/>void DrawCircle(simul::crossplatform::DeviceContext deviceContext, float dir, float rads, float colr, bool fill)
Draw a circle facing the viewer at the specified direction and angular size.
Draw a circle facing the viewer at the specified direction and angular size.

### <a name="DrawCircle"/>void DrawCircle(simul::crossplatform::DeviceContext deviceContext, float pos, float dir, float radius, float colr, bool fill)
Draw a circle in 3D space at pos
Draw a circle in 3D space at pos

### <a name="DrawCubemap"/>void DrawCubemap(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture cubemap, float offsetx, float offsety, float size, float exposure, float gamma, float displayLod)
Draw a cubemap as a sphere at the specified screen position and size.
Draw a cubemap as a sphere at the specified screen position and size.

### <a name="DrawIndexed"/>void DrawIndexed(simul::crossplatform::DeviceContext deviceContext, int num_indices, int start_index, int base_vertex)
Draw the specified number of vertices using the bound index arrays.
Draw the specified number of vertices using the bound index arrays.

### <a name="EndEvent"/>void EndEvent(simul::crossplatform::DeviceContext deviceContext)
For platforms that support named events, e.g. PIX in DirectX. Use BeginEvent(), EndEvent() as pairs.
For platforms that support named events, e.g. PIX in DirectX. Use BeginEvent(), EndEvent() as pairs.

### <a name="EnsureEffectIsBuilt"/>void EnsureEffectIsBuilt(char filename_utf8, std::vector<simul::crossplatform::EffectDefineOptions, std::allocator<simul::crossplatform::EffectDefineOptions> > options)
This function is called to ensure that the named shader is compiled with all the possible combinations of \#define's given in **options**.
This function is called to ensure that the named shader is compiled with all the possible combinations of \#define's given in **options**.

### <a name="EnsureShader"/>simul::crossplatform::Shader * EnsureShader(char filenameUtf8, simul::crossplatform::ShaderType t)
Get or create an API-specific shader object.
Get or create an API-specific shader object.

### <a name="GetContextState"/>simul::crossplatform::ContextState * GetContextState(simul::crossplatform::DeviceContext deviceContext)
Get the current state to be applied to the given context at the next draw or dispatch.
Get the current state to be applied to the given context at the next draw or dispatch.

### <a name="GetImmediateContext"/>simul::crossplatform::DeviceContext  & GetImmediateContext()
Gets an object containing immediate-context API-specific values.
Gets an object containing immediate-context API-specific values.

### <a name="GetName"/>char  const * GetName()
Returns the name of the render platform - DirectX 11, OpenGL, etc.
Returns the name of the render platform - DirectX 11, OpenGL, etc.

### <a name="GetOrCreateSamplerStateByName"/>simul::crossplatform::SamplerState * GetOrCreateSamplerStateByName(char name_utf8, simul::crossplatform::SamplerStateDesc desc)
Look for a sampler state of the stated name, and create one if it does not exist. The resulting state will be owned by the RenderPlatform, so do not destroy it.
This is for states that will be shared by multiple shaders. There will be a warning if a description is passed that conflicts with the current definition,
as the Effects system assumes that SamplerState names are unique.
Look for a sampler state of the stated name, and create one if it does not exist. The resulting state will be owned by the RenderPlatform, so do not destroy it.
This is for states that will be shared by multiple shaders. There will be a warning if a description is passed that conflicts with the current definition,
as the Effects system assumes that SamplerState names are unique.

### <a name="GetShaderBinaryPath"/>char  const * GetShaderBinaryPath()
Returns the path where generated shader binaries should be saved, and where stored shader binaries should be loaded from.
Returns the path where generated shader binaries should be saved, and where stored shader binaries should be loaded from.

### <a name="GetShaderBuildMode"/>simul::crossplatform::ShaderBuildMode GetShaderBuildMode()
When shaders should be built, or loaded if available.
When shaders should be built, or loaded if available.

### <a name="GetShaderPathsUtf8"/>std::vector<std::basic_string<char, std::char_traits<char>, std::allocator<char> >, std::allocator<std::basic_string<char, std::char_traits<char>, std::allocator<char> > > > GetShaderPathsUtf8()
Returns the stack of shader source paths.
Returns the stack of shader source paths.

### <a name="GetViewport"/>simul::crossplatform::Viewport GetViewport(simul::crossplatform::DeviceContext deviceContext, int index)
Get the viewport at the given index.
Get the viewport at the given index.

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Call this once, when the 3d graphics device object is being shut down.
Call this once, when the 3d graphics device object is being shut down.

### <a name="PopRenderTargets"/>void PopRenderTargets(simul::crossplatform::DeviceContext deviceContext)
Restore rendertargets and viewports from the top of the stack.
Restore rendertargets and viewports from the top of the stack.

### <a name="PopShaderPath"/>void PopShaderPath()
Remove a path from the top of the shader source path stack.
Remove a path from the top of the shader source path stack.

### <a name="PopTexturePath"/>void PopTexturePath()
Remove a path from the top of the texture path stack.
Remove a path from the top of the texture path stack.

### <a name="PushRenderTargets"/>void PushRenderTargets(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::TargetsAndViewport tv)
Store the current rendertargets and viewports at the top of the stack
Store the current rendertargets and viewports at the top of the stack

### <a name="PushShaderPath"/>void PushShaderPath(char path_utf8)
Push the given file path onto the shader path stack.
Push the given file path onto the shader path stack.

### <a name="PushTexturePath"/>void PushTexturePath(char pathUtf8)
Push the given file path onto the texture path stack.
Push the given file path onto the texture path stack.

### <a name="RecompileShaders"/>void RecompileShaders()
Optional - call this to recompile the standard shaders.
Optional - call this to recompile the standard shaders.

### <a name="Resolve"/>void Resolve(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Texture destination, simul::crossplatform::Texture source)
Resolve a MSAA texture to a normal texture.
Resolve a MSAA texture to a normal texture.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(void)
Call this once, when the 3D graphics device has been initialized, and pass the API-specific device pointer/identifier.
Call this once, when the 3D graphics device has been initialized, and pass the API-specific device pointer/identifier.

### <a name="RestoreRenderState"/>void RestoreRenderState(simul::crossplatform::DeviceContext deviceContext)
Called to restore the render state previously stored with StoreRenderState. There must be exactly one call of RestoreRenderState
for each StoreRenderState call, and they are not expected to be nested.
Called to restore the render state previously stored with StoreRenderState. There must be exactly one call of RestoreRenderState
for each StoreRenderState call, and they are not expected to be nested.

### <a name="SaveTexture"/>void SaveTexture(simul::crossplatform::Texture texture, char lFileNameUtf8)
Save a texture to disk.
Save a texture to disk.

### <a name="SetIndexBuffer"/>void SetIndexBuffer(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Buffer buffer)
Activate the specified index buffer in preparation for rendering.
Activate the specified index buffer in preparation for rendering.

### <a name="SetLayout"/>void SetLayout(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Layout l)
Set the layout for following draw calls - format of the vertex buffer.
Set the layout for following draw calls - format of the vertex buffer.

### <a name="SetRenderState"/>void SetRenderState(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::RenderState s)
Apply the RenderState to the device context - e.g. blend state, depth masking etc.
Apply the RenderState to the device context - e.g. blend state, depth masking etc.

### <a name="SetShaderBinaryPath"/>void SetShaderBinaryPath(char path_utf8)
Set the path where generated shader binaries should be saved, and where stored shader binaries should be loaded from.
Set the path where generated shader binaries should be saved, and where stored shader binaries should be loaded from.

### <a name="SetShaderBuildMode"/>void SetShaderBuildMode(simul::crossplatform::ShaderBuildMode s)
When shaders should be built, or loaded if available.
When shaders should be built, or loaded if available.

### <a name="SetShaderPathsUtf8"/>void SetShaderPathsUtf8(std::vector<std::basic_string<char, std::char_traits<char>, std::allocator<char> >, std::allocator<std::basic_string<char, std::char_traits<char>, std::allocator<char> > > > pathsUtf8)
Replace the entire stack of shader source paths.
Replace the entire stack of shader source paths.

### <a name="SetStandardRenderState"/>void SetStandardRenderState(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::StandardRenderState s)
Apply a standard renderstate - e.g. opaque blending
Apply a standard renderstate - e.g. opaque blending

### <a name="SetStreamOutTarget"/>void SetStreamOutTarget(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Buffer buffer, int start_index)
Graphics hardware can write to vertex buffers using vertex and geometry shaders; use this function to set the target buffer.
Graphics hardware can write to vertex buffers using vertex and geometry shaders; use this function to set the target buffer.

### <a name="SetTopology"/>void SetTopology(simul::crossplatform::DeviceContext deviceContext, simul::crossplatform::Topology t)
Set the topology for following draw calls, e.g. TRIANGLELIST etc.
Set the topology for following draw calls, e.g. TRIANGLELIST etc.

### <a name="SetVertexBuffers"/>void SetVertexBuffers(simul::crossplatform::DeviceContext deviceContext, int slot, int num_buffers, simul::crossplatform::Buffer buffers, simul::crossplatform::Layout layout, int vertexSteps)
Activate the specifided vertex buffers in preparation for rendering.
Activate the specifided vertex buffers in preparation for rendering.

### <a name="StoreRenderState"/>void StoreRenderState(simul::crossplatform::DeviceContext deviceContext)
Called to store the render state - blending, depth check, etc. - for later retrieval with RestoreRenderState.
Some platforms may not support this.
Called to store the render state - blending, depth check, etc. - for later retrieval with RestoreRenderState.
Some platforms may not support this.

### <a name="SynchronizeCacheAndState"/>void SynchronizeCacheAndState(simul::crossplatform::DeviceContext)
Implementations of RenderPlatform will cache the API state in order to reduce driver overhead.
But we can't always be sure that external render code hasn't modified the API state. So by calling SynchronizeCacheAndState()
the API state is forced to the cached state. This can be called at the start of Renderplatform's rendering per-frame.
Implementations of RenderPlatform will cache the API state in order to reduce driver overhead.
But we can't always be sure that external render code hasn't modified the API state. So by calling SynchronizeCacheAndState()
the API state is forced to the cached state. This can be called at the start of Renderplatform's rendering per-frame.

### <a name="TexelQuery"/>vec4 TexelQuery(simul::crossplatform::DeviceContext deviceContext, int query_id, uint2 pos, simul::crossplatform::Texture texture)
Query for the texture value at the specified position in the texture. On most API's, the query will have a few frames' latency.
Query for the texture value at the specified position in the texture. On most API's, the query will have a few frames' latency.

### <a name="ApplyContextState"/>bool ApplyContextState(simul::crossplatform::DeviceContext, bool)
This is called by draw functions to do any lazy updating prior to the actual API draw/dispatch call.
This is called by draw functions to do any lazy updating prior to the actual API draw/dispatch call.

Fields
---

**mirrorY** This was introduced because Unity's deferred renderer flips the image vertically sometime after we render. This was introduced because Unity's deferred renderer flips the image vertically sometime after we render.

**mirrorY2** This was introduced because Unity's deferred renderer flips the image vertically sometime after we render. This was introduced because Unity's deferred renderer flips the image vertically sometime after we render.

**mirrorYText** This was introduced because Unity's deferred renderer flips the image vertically sometime after we render. This was introduced because Unity's deferred renderer flips the image vertically sometime after we render.
