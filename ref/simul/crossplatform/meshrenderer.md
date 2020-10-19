---
title: MeshRenderer
layout: reference
weight: 0
---
class MeshRenderer
===

| Include: | Platform/CrossPlatform/MeshRenderer.h |



Functions
---

| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [Render](#Render)(simul::crossplatform::GraphicsDeviceContext deviceContext, simul::crossplatform::Mesh mesh, mat4 model, simul::crossplatform::Texture diffuseCubemap, simul::crossplatform::Texture specularCubemap) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform r) |


Functions
---
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
To be called when the rendering device is no longer valid.
<a name="Render"></a>
### void Render(simul::crossplatform::GraphicsDeviceContext deviceContext, simul::crossplatform::Mesh mesh, mat4 model, simul::crossplatform::Texture diffuseCubemap, simul::crossplatform::Texture specularCubemap)
Render the lens flares based on the given direction to the light, and its colour.
<a name="RestoreDeviceObjects"></a>
### void RestoreDeviceObjects(simul::crossplatform::RenderPlatform r)
To be called when a rendering device has been initialized.
