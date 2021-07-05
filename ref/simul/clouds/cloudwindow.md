---
title: CloudWindow
layout: reference
weight: 0
---
struct CloudWindow
===

| Include: | Clouds/CloudKeyframer.h |



Functions
---

| void | [CheckForOriginChange](#CheckForOriginChange)(simul::crossplatform::Quaterniond new_origin, simul::clouds::CloudRenderingOptions opts) |
| double | [GetOriginHeadingDegrees](#GetOriginHeadingDegrees)() |
| double | [GetOriginLatitudeDegrees](#GetOriginLatitudeDegrees)() |
| void | [GetOriginLatitudeLongitudeHeading](#GetOriginLatitudeLongitudeHeading)(double lat_deg, double lon_deg, double head_deg) |
| double | [GetOriginLongitudeDegrees](#GetOriginLongitudeDegrees)() |
| void | [InitWindowCentre](#InitWindowCentre)(double lat_degrees, double long_degrees, double x_heading_degrees) |
| void | [MoveCloudWindow](#MoveCloudWindow)(int x, int y) |
| simul::clouds::CloudWindow  const & | [operator=](#operator=)(simul::clouds::CloudWindow) |
| void | [Reset](#Reset)() |
| float | [UpdateWindowCentre](#UpdateWindowCentre)(float lat_degrees, float long_degrees) |


Functions
---
<a name="CheckForOriginChange"></a>
### void CheckForOriginChange(simul::crossplatform::Quaterniond new_origin, simul::clouds::CloudRenderingOptions opts)
Check if the cloud window origin has changed, and update values if it has.
<a name="GetOriginHeadingDegrees"></a>
### double GetOriginHeadingDegrees()
< Get the longitude referred to by the origin quaternion.
<a name="GetOriginLatitudeDegrees"></a>
### double GetOriginLatitudeDegrees()
< Get the latitude/longitude referred to by the specified quaternion.
<a name="GetOriginLatitudeLongitudeHeading"></a>
### void GetOriginLatitudeLongitudeHeading(double lat_deg, double lon_deg, double head_deg)
< Get the latitude/longitude referred to by the specified position value.
<a name="GetOriginLongitudeDegrees"></a>
### double GetOriginLongitudeDegrees()
< Get the latitude referred to by the origin quaternion.
<a name="InitWindowCentre"></a>
### void InitWindowCentre(double lat_degrees, double long_degrees, double x_heading_degrees)
Initialize the window.
<a name="MoveCloudWindow"></a>
### void MoveCloudWindow(int x, int y)
Translate the cloud window by the given x and y
<a name="operator="></a>
### simul::clouds::CloudWindow  const & operator=(simul::clouds::CloudWindow)
assignment operator only copies properties, not state.
<a name="Reset"></a>
### void Reset()
Reset offsets
<a name="UpdateWindowCentre"></a>
### float UpdateWindowCentre(float lat_degrees, float long_degrees)
Returns updated x heading in degrees.
