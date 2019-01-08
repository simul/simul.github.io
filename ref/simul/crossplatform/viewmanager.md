---
title: ViewManager
layout: reference
weight: 0
---
class ViewManager
===

| Include: | Platform/CrossPlatform/View.h |

A class to store a set of View objects, one per view id.
  


Functions
---

|  | [ViewManager](#ViewManager)() |
| simul::crossplatform::View * | [AddView](#AddView)(int) |
| void | [CleanUp](#CleanUp)(int current_framenumber, int max_age) |
| void | [Clear](#Clear)() |
| simul::crossplatform::View * | [GetView](#GetView)(int view_id) |
| simul::crossplatform::ViewManager::ViewMap  const & | [GetViews](#GetViews)() |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [RemoveView](#RemoveView)(int view_id) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform renderPlatform) |

A class to store a set of View objects, one per view id.
  


Functions
---

### <a name="ViewManager"/> ViewManager()
Default constructor.

### <a name="AddView"/>simul::crossplatform::View * AddView(int)
Adds a view.
An int view_id.

### <a name="CleanUp"/>void CleanUp(int current_framenumber, int max_age)
Delete old views

### <a name="Clear"/>void Clear()
Clears this object to its blank/initial state.

### <a name="GetView"/>simul::crossplatform::View * GetView(int view_id)
Gets a view.
null if it fails, else the view.

### <a name="GetViews"/>simul::crossplatform::ViewManager::ViewMap  const & GetViews()
Gets the views.

### <a name="InvalidateDeviceObjects"/>void InvalidateDeviceObjects()
Invalidate device objects.

### <a name="RemoveView"/>void RemoveView(int view_id)
Removes the view.

### <a name="RestoreDeviceObjects"/>void RestoreDeviceObjects(simul::crossplatform::RenderPlatform renderPlatform)
Restore the device objects.

Fields
---

**renderPlatform**  The render platform.

**last_created_view_id**  Identifier for the last created view.
