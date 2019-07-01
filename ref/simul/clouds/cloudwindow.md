---
title: CloudWindow
layout: reference
weight: 0
---
struct CloudWindow
===

| Include: | Clouds/CloudWindow.h |



Functions
---

| void | [CheckForOriginChange](#CheckForOriginChange)(simul::crossplatform::Quaterniond new_origin, simul::clouds::CloudRenderingOptions opts) |
| double | [GetOriginHeadingDegrees](#GetOriginHeadingDegrees)() |
| void | [GetOriginLatitudeLongitudeHeading](#GetOriginLatitudeLongitudeHeading)(double lat, double lon, double head) |
| void | [InitWindowCentre](#InitWindowCentre)(float lat_degrees, float long_degrees, float x_heading_degrees) |
| void | [MoveCloudWindow](#MoveCloudWindow)(int x, int y) |
| simul::clouds::CloudWindow  const & | [operator=](#operator=)(simul::clouds::CloudWindow) |
| float | [UpdateWindowCentre](#UpdateWindowCentre)(float lat_degrees, float long_degrees) |


Functions
---

### <a name="CheckForOriginChange"/>void CheckForOriginChange(simul::crossplatform::Quaterniond new_origin, simul::clouds::CloudRenderingOptions opts)
Check if the cloud window origin has changed, and update values if it has.

### <a name="GetOriginHeadingDegrees"/>double GetOriginHeadingDegrees()
< Get the latitude/longitude referred to by the specified quaternion.

### <a name="GetOriginLatitudeLongitudeHeading"/>void GetOriginLatitudeLongitudeHeading(double lat, double lon, double head)
< Get the latitude/longitude referred to by the specified position value.

### <a name="InitWindowCentre"/>void InitWindowCentre(float lat_degrees, float long_degrees, float x_heading_degrees)
Initialize the window.

### <a name="MoveCloudWindow"/>void MoveCloudWindow(int x, int y)
Translate the cloud window by the given x and y

### <a name="operator="/>simul::clouds::CloudWindow  const & operator=(simul::clouds::CloudWindow)
assignment operator only copies properties, not state.

### <a name="UpdateWindowCentre"/>float UpdateWindowCentre(float lat_degrees, float long_degrees)
Returns updated x heading in degrees.
