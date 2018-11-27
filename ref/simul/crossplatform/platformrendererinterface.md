---
title: PlatformRendererInterface
layout: reference
weight: 0
---
class PlatformRendererInterface
===

| Include: | Platform/CrossPlatform/GraphicsDeviceInterface.h |

This represents an interface that faces the raw API.
The implementing class should keep a list of integer view id's
  


Functions
---

| int | [AddView](#AddView)() |
| void | [RemoveView](#RemoveView)(int) |
| void | [Render](#Render)(int view_id, void pContext, void renderTexture, int w, int h) |
| void | [ResizeView](#ResizeView)(int view_id, int w, int h) |

This represents an interface that faces the raw API.
The implementing class should keep a list of integer view id's
  


Functions
---

### <a name="AddView"/>int AddView()
Add a view. This tells the renderer to create any internal stuff it needs to handle a viewport, so that it is ready when Render() is called. It returns an identifier for that view.

### <a name="RemoveView"/>void RemoveView(int)
Remove the view. This might not have an immediate effect internally, but is a courtesy to the interface.

### <a name="Render"/>void Render(int view_id, void pContext, void renderTexture, int w, int h)
Render the specified view. It's up to the renderer to decide what that means. The renderTexture is required because many API's don't allow querying of the current state.
It will be assumed for simplicity that the viewport should be restored to the entire size of the renderTexture.

### <a name="ResizeView"/>void ResizeView(int view_id, int w, int h)
For a view that has already been created, this ensures that it has the requested size and format.
