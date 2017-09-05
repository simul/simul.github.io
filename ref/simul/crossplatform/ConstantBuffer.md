---
title: ConstantBuffer
layout: reference
weight: 0
---
classtemplate ConstantBuffer
===

| Include: | Platform/CrossPlatform/Effect.h |


[simul::crossplatform::ConstantBufferBase](ConstantBufferBase)
[]()

Functions
---

| size_t | [GetSize](#GetSize)() |
| void * | [GetAddr](#GetAddr)() |
| int | [GetIndex](#GetIndex)() |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [Unbind](#Unbind)(simul::crossplatform::DeviceContext deviceContext) |


Base Classes
---
[simul::crossplatform::ConstantBufferBase](ConstantBufferBase)
[]()

Functions
---

### <a name="GetSize"/>size_t GetSize()
For Effect's use only, do not call.
For Effect's use only, do not call.

### <a name="GetAddr"/>void * GetAddr()
For Effect's use only, do not call.
For Effect's use only, do not call.

### <a name="GetIndex"/>int GetIndex()
Get the binding index in shaders.
Get the binding index in shaders.

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Free the allocated buffer.
Free the allocated buffer.

### <a name="Unbind"/>void Unbind(simul::crossplatform::DeviceContext deviceContext)
Unbind from the effect.
Unbind from the effect.
