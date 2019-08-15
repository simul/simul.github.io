---
title: Query
layout: reference
weight: 0
---
struct Query
===

| Include: | Platform/CrossPlatform/Effect.h |



Functions
---

| bool | [GetData](#GetData)(simul::crossplatform::DeviceContext deviceContext, void data, size_t sz) |


Functions
---
<a name="GetData"></a>
### bool GetData(simul::crossplatform::DeviceContext deviceContext, void data, size_t sz)
Get query data. Returns true if successful, or false otherwise.
Blocking queries will return false until they succeed.

Variables
---
