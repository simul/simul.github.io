---
title: Buffer
layout: reference
weight: 0
---
class Buffer
===

| Include: | Clouds/Base2DCloudRenderer.h |



Functions
---

| void | [EnsureIndexBuffer](#EnsureIndexBuffer)(simul::crossplatform::RenderPlatform renderPlatform, int num_indices, int index_size_bytes, void data) |
| void | [EnsureVertexBuffer](#EnsureVertexBuffer)(simul::crossplatform::RenderPlatform renderPlatform, int num_vertices, simul::crossplatform::Layout layout, void data, bool cpu_access, bool streamout_target) |
| void * | [Map](#Map)(simul::crossplatform::DeviceContext deviceContext) |
| void | [Unmap](#Unmap)(simul::crossplatform::DeviceContext deviceContext) |


Functions
---

### <a name="EnsureIndexBuffer"/>void EnsureIndexBuffer(simul::crossplatform::RenderPlatform renderPlatform, int num_indices, int index_size_bytes, void data)
Set up as an index buffer.

### <a name="EnsureVertexBuffer"/>void EnsureVertexBuffer(simul::crossplatform::RenderPlatform renderPlatform, int num_vertices, simul::crossplatform::Layout layout, void data, bool cpu_access, bool streamout_target)
Set up as a vertex buffer. You must pass a pointer to an already-created Layout, and don't destroy the layout until after destroying the vertex buffer.

### <a name="Map"/>void * Map(simul::crossplatform::DeviceContext deviceContext)
Get a pointer to the data for updating. Must call Unmap after any changes.

### <a name="Unmap"/>void Unmap(simul::crossplatform::DeviceContext deviceContext)
Return the modified data to the device object.
