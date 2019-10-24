---
title: FastCloudNode
layout: reference
weight: 0
---
class FastCloudNode
===

| Include: | Clouds/FastCloudNode.h |

Create an instance of FastCloudNode to generate cloud data for rendering.
This class can use a custom memory allocator, because it is derived from
a ResourceUser<> of simul::base::MemoryInterface. To use this feature
call SetResource( simul::base::MemoryInterface *) with a pointer to a
an instance of a class derived from MemoryInterface.
  

[simul::clouds::CellularCloudNode](cellularcloudnode.html)

Functions
---

| void | [AddHumidityCallback](#AddHumidityCallback)(simul::clouds::HumidityCallbackInterface hc) |
| void | [ClearHumidityCallbacks](#ClearHumidityCallbacks)() |
| void | [RemoveHumidityCallback](#RemoveHumidityCallback)(simul::clouds::HumidityCallbackInterface hc) |
| std::istream  & | [StateStreamIn](#StateStreamIn)(std::istream is) |
| std::ostream  & | [StateStreamOut](#StateStreamOut)(std::ostream os) |
| std::istream  & | [StreamIn](#StreamIn)(std::istream is) |
| std::ostream  & | [StreamOut](#StreamOut)(std::ostream os) |

Create an instance of FastCloudNode to generate cloud data for rendering.
This class can use a custom memory allocator, because it is derived from
a ResourceUser<> of simul::base::MemoryInterface. To use this feature
call SetResource( simul::base::MemoryInterface *) with a pointer to a
an instance of a class derived from MemoryInterface.
  


Base Classes
---
[simul::clouds::CellularCloudNode](cellularcloudnode.html)

Functions
---
<a name="AddHumidityCallback"></a>
### void AddHumidityCallback(simul::clouds::HumidityCallbackInterface hc)
Assign a callback object to control humidity (cloud density) within the cloud volume.
<a name="ClearHumidityCallbacks"></a>
### void ClearHumidityCallbacks()
Remove all humidity callbacks.
<a name="RemoveHumidityCallback"></a>
### void RemoveHumidityCallback(simul::clouds::HumidityCallbackInterface hc)
Remove the stated callback object from the list.
<a name="StateStreamIn"></a>
### std::istream  & StateStreamIn(std::istream is)
Stream/load from the std::isteam is.
<a name="StateStreamOut"></a>
### std::ostream  & StateStreamOut(std::ostream os)
Stream/save to the std::osteam os.
<a name="StreamIn"></a>
### std::istream  & StreamIn(std::istream is)
Stream/load from the std::isteam is.
<a name="StreamOut"></a>
### std::ostream  & StreamOut(std::ostream os)
Stream/save to the std::osteam os.
