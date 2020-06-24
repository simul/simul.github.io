---
title: WaterWaveletsSimulator
layout: reference
weight: 0
---
class WaterWaveletsSimulator
===

| Include: | Terrain/WaterWaveletsSimulator.h |



Functions
---

| void | [GenerateContourMap](#GenerateContourMap)(simul::crossplatform::DeviceContext deviceContext, simul::terrain::shoreTexture shoreDepth, float oceanHeight) |
| void | [GenerateSurfaceFlow](#GenerateSurfaceFlow)(simul::crossplatform::DeviceContext deviceContext, simul::terrain::WaveGrid surfaceFlowGrid) |
| simul::terrain::surfaceFlowRayBuffer * | [getBaseFlowRayBuffer](#getBaseFlowRayBuffer)() |
| simul::crossplatform::Texture * | [getContourMap](#getContourMap)() |
| simul::terrain::surfaceFlowRayBuffer * | [getSubFlowRayBuffer](#getSubFlowRayBuffer)() |
| void | [InitialiseWaveGrid](#InitialiseWaveGrid)(simul::terrain::WaveGrid newWaveGrid, uint2 dimension, int theta, int k) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [PrecomputeProfileBuffers](#PrecomputeProfileBuffers)(simul::crossplatform::DeviceContext deviceContext, simul::terrain::WaveGrid targetWaveGrid, float time, simul::terrain::localWaterValues waterValues) |
| void | [PrecomputeWaveSpeeds](#PrecomputeWaveSpeeds)(simul::crossplatform::DeviceContext deviceContext) |
| void | [ResetAmplitudeGrid](#ResetAmplitudeGrid)(simul::crossplatform::DeviceContext deviceContext) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform renderPlatform) |
| void | [SetShader](#SetShader)(simul::crossplatform::Effect e) |
| void | [SetTargetWaveGrid](#SetTargetWaveGrid)(simul::terrain::WaveGrid targetWaveGrid, simul::terrain::localWaterValues waterValues) |
| void | [UpdateAmplitudeGrid](#UpdateAmplitudeGrid)(simul::crossplatform::DeviceContext deviceContext, float real_time_seconds, vec4 waterProbePositions, vec4 waterProbeVelocities, vec3 center, vec2 camPos) |


Functions
---
<a name="GenerateContourMap"></a>
### void GenerateContourMap(simul::crossplatform::DeviceContext deviceContext, simul::terrain::shoreTexture shoreDepth, float oceanHeight)
Generate a contour map that stores the normal of the shore surface
<a name="GenerateSurfaceFlow"></a>
### void GenerateSurfaceFlow(simul::crossplatform::DeviceContext deviceContext, simul::terrain::WaveGrid surfaceFlowGrid)
Calculate the path of the flow rays
<a name="getBaseFlowRayBuffer"></a>
### simul::terrain::surfaceFlowRayBuffer * getBaseFlowRayBuffer()
Get a pointer to the base flow ray buffer
<a name="getContourMap"></a>
### simul::crossplatform::Texture * getContourMap()
Get a pointer to the contour map
<a name="getSubFlowRayBuffer"></a>
### simul::terrain::surfaceFlowRayBuffer * getSubFlowRayBuffer()
Get a pointer to the sub flow ray buffer
<a name="InitialiseWaveGrid"></a>
### void InitialiseWaveGrid(simul::terrain::WaveGrid newWaveGrid, uint2 dimension, int theta, int k)
Initialise a given wave grid
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the wavelets simulator.
<a name="PrecomputeProfileBuffers"></a>
### void PrecomputeProfileBuffers(simul::crossplatform::DeviceContext deviceContext, simul::terrain::WaveGrid targetWaveGrid, float time, simul::terrain::localWaterValues waterValues)
Precompute the profile buffers of a given wave grid
<a name="PrecomputeWaveSpeeds"></a>
### void PrecomputeWaveSpeeds(simul::crossplatform::DeviceContext deviceContext)
Precompute the wave speeds of the target wave grid
<a name="ResetAmplitudeGrid"></a>
### void ResetAmplitudeGrid(simul::crossplatform::DeviceContext deviceContext)
Clear the wave amplitude grid of the target wave grid
<a name="RestoreDeviceObjects"></a>
### void RestoreDeviceObjects(simul::crossplatform::RenderPlatform renderPlatform)
Platform-dependent function called when initializing the wavelets simulator.
<a name="SetShader"></a>
### void SetShader(simul::crossplatform::Effect e)
Set the precompiled shader used by the wavelets simulator - debug only
<a name="SetTargetWaveGrid"></a>
### void SetTargetWaveGrid(simul::terrain::WaveGrid targetWaveGrid, simul::terrain::localWaterValues waterValues)
Set the target wave grid the simulator will be working on.
<a name="UpdateAmplitudeGrid"></a>
### void UpdateAmplitudeGrid(simul::crossplatform::DeviceContext deviceContext, float real_time_seconds, vec4 waterProbePositions, vec4 waterProbeVelocities, vec3 center, vec2 camPos)
Update the wave amplitude grid of the target wave grid
