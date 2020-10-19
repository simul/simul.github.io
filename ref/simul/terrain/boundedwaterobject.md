---
title: BoundedWaterObject
layout: reference
weight: 0
---
class BoundedWaterObject
===

| Include: | Terrain/BoundedWaterObject.h |



Functions
---

| simul::terrain::WaterMeshObjectValues * | [getCustomWaterMesh](#getCustomWaterMesh)() |
| vec3 | [getDimension](#getDimension)() |
| vec3 | [getLocation](#getLocation)() |
| int2 | [getQuadDensity](#getQuadDensity)() |
| float | [getRotation](#getRotation)() |
| uint | [getTotalVerticies](#getTotalVerticies)() |
| vec4 * | [getWaterProbeOutputs](#getWaterProbeOutputs)() |
| simul::crossplatform::StructuredBuffer * | [getWaterProbeOutputsBuffer](#getWaterProbeOutputsBuffer)() |
| vec4 * | [getWaterProbePositions](#getWaterProbePositions)() |
| simul::terrain::localWaterValues * | [getWaterValues](#getWaterValues)() |
| simul::terrain::WaveGrid * | [getWaveGrid](#getWaveGrid)() |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [PreRenderUpdate](#PreRenderUpdate)(simul::crossplatform::GraphicsDeviceContext deviceContext, float real_time_seconds) |
| void | [removeCustomWaterMesh](#removeCustomWaterMesh)() |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform r) |
| void | [setCustomWaterMesh](#setCustomWaterMesh)(simul::terrain::WaterMeshObjectValues newObject) |
| void | [setDimension](#setDimension)(vec3 newDimension) |
| void | [setLocation](#setLocation)(vec3 newLocation) |
| void | [setRotation](#setRotation)(float newRotation) |
| void | [setWaterGlobals](#setWaterGlobals)(simul::terrain::globalWaterValues newWaterGlobals) |
| void | [setWaterProbeOutputs](#setWaterProbeOutputs)(vec4 outputs) |
| void | [setWaterProbePosition](#setWaterProbePosition)(int ID, vec3 pos) |
| void | [setWaterWaveletsSimulator](#setWaterWaveletsSimulator)(simul::terrain::WaterWaveletsSimulator o) |
| void | [updateCustomWaterMesh](#updateCustomWaterMesh)(simul::terrain::WaterMeshObjectValues Object) |
| void | [updateLODs](#updateLODs)() |
| void | [updateQuadDensity](#updateQuadDensity)(vec3 camPos) |


Functions
---
<a name="getCustomWaterMesh"></a>
### simul::terrain::WaterMeshObjectValues * getCustomWaterMesh()
Get the current mesh object
<a name="getDimension"></a>
### vec3 getDimension()
Get the dimension of the center of the water object
<a name="getLocation"></a>
### vec3 getLocation()
Get the location of the center of the water object
<a name="getQuadDensity"></a>
### int2 getQuadDensity()
Get the dimensions of how many quads the surface of the water object is using
<a name="getRotation"></a>
### float getRotation()
Get the rotation of the center of the water object
<a name="getTotalVerticies"></a>
### uint getTotalVerticies()
Get the total verticies used to render the water object
<a name="getWaterProbeOutputs"></a>
### vec4 * getWaterProbeOutputs()
Get the Array of results from the water probes associated with this water object
<a name="getWaterProbeOutputsBuffer"></a>
### simul::crossplatform::StructuredBuffer * getWaterProbeOutputsBuffer()
Get a pointer to the probe outputs buffer
<a name="getWaterProbePositions"></a>
### vec4 * getWaterProbePositions()
Get the Array of positions of the water probes associated with this water object
<a name="getWaterValues"></a>
### simul::terrain::localWaterValues * getWaterValues()
Get a pointer the water values of this water object
<a name="getWaveGrid"></a>
### simul::terrain::WaveGrid * getWaveGrid()
Get the wave grid that the water object is using to generate its surface
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Platform-dependent function called when uinitializing the water object.
<a name="PreRenderUpdate"></a>
### void PreRenderUpdate(simul::crossplatform::GraphicsDeviceContext deviceContext, float real_time_seconds)
Once per-frame update. Do this before any rendering each frame.
<a name="removeCustomWaterMesh"></a>
### void removeCustomWaterMesh()
Remove the water mesh
<a name="RestoreDeviceObjects"></a>
### void RestoreDeviceObjects(simul::crossplatform::RenderPlatform r)
Platform-dependent function called when initializing the water object.
<a name="setCustomWaterMesh"></a>
### void setCustomWaterMesh(simul::terrain::WaterMeshObjectValues newObject)
Set a given mesh object as the shape of the water object
<a name="setDimension"></a>
### void setDimension(vec3 newDimension)
Set the dimension of the center of the water object
<a name="setLocation"></a>
### void setLocation(vec3 newLocation)
Set the location of the center of the water object
<a name="setRotation"></a>
### void setRotation(float newRotation)
Set the rotation of the center of the water object
<a name="setWaterGlobals"></a>
### void setWaterGlobals(simul::terrain::globalWaterValues newWaterGlobals)
Set the global water values
<a name="setWaterProbeOutputs"></a>
### void setWaterProbeOutputs(vec4 outputs)
Set the Array of results from the water probes associated with this water object
<a name="setWaterProbePosition"></a>
### void setWaterProbePosition(int ID, vec3 pos)
Set the Array of positions of the water probes associated with this water object
<a name="setWaterWaveletsSimulator"></a>
### void setWaterWaveletsSimulator(simul::terrain::WaterWaveletsSimulator o)
Set the water wavelets simulator that this water object will use to generate its surface
<a name="updateCustomWaterMesh"></a>
### void updateCustomWaterMesh(simul::terrain::WaterMeshObjectValues Object)
Update a given mesh object
<a name="updateLODs"></a>
### void updateLODs()
Update the LOD values depending on the size of the object
<a name="updateQuadDensity"></a>
### void updateQuadDensity(vec3 camPos)
Update the level of detail of the surface of the water object depending on how far away the camera is
