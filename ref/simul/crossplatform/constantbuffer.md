---
title: ConstantBuffer
layout: reference
weight: 0
---
classtemplate ConstantBuffer
===

| Include: | Platform/CrossPlatform/Effect.h |


[simul::crossplatform::ConstantBufferBase](constantbufferbase.html)
[](/ref/.html)

Functions
---

| size_t | [GetSize](#GetSize)() |
| void * | [GetAddr](#GetAddr)() |
| int | [GetIndex](#GetIndex)() |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform p) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [Unbind](#Unbind)(simul::crossplatform::DeviceContext deviceContext) |


Base Classes
---
[simul::crossplatform::ConstantBufferBase](constantbufferbase.html)
[](/ref/.html)

Functions
---
<a name="GetSize"></a>
### size_t GetSize()
For Effect's use only, do not call.
<a name="GetAddr"></a>
### void * GetAddr()
For Effect's use only, do not call.
<a name="GetIndex"></a>
### int GetIndex()
Get the binding index in shaders.
<a name="RestoreDeviceObjects"></a>
### void RestoreDeviceObjects(simul::crossplatform::RenderPlatform p)
Create the buffer object.
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Free the allocated buffer.
<a name="Unbind"></a>
### void Unbind(simul::crossplatform::DeviceContext deviceContext)
Unbind from the effect.
