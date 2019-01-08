---
title: ConstantBuffer
layout: reference
weight: 0
---
classtemplate ConstantBuffer
===

| Include: | Platform/CrossPlatform/Effect.h |


[simul::crossplatform::ConstantBufferBase](constantbufferbase)
[](/ref/)

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
[simul::crossplatform::ConstantBufferBase](constantbufferbase)
[](/ref/)

Functions
---

### <a name="GetSize"/>size_t GetSize()
For Effect's use only, do not call.

### <a name="GetAddr"/>void * GetAddr()
For Effect's use only, do not call.

### <a name="GetIndex"/>int GetIndex()
Get the binding index in shaders.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform p)
Create the buffer object.

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Free the allocated buffer.

### <a name="Unbind"/>void Unbind(simul::crossplatform::DeviceContext deviceContext)
Unbind from the effect.
