---
title: WaterParticleSimulator
layout: reference
weight: 0
---
class WaterParticleSimulator
===

| Include: | Terrain/WaterParticleSimulator.h |

Class for containing a set of particle generators. Currently a work in progress.
  


Functions
---

| bool | [AddWaterParticleGenerator](#AddWaterParticleGenerator)(simul::terrain::particleGeneratorValues newGenerator, simul::terrain::particleGeneratorType newGeneratorType, simul::crossplatform::Texture customPlaneTexture) |
| void | [InvalidateDeviceObjects](#InvalidateDeviceObjects)() |
| void | [RecompileShaders](#RecompileShaders)() |
| void | [RemoveWaterParticleGenerator](#RemoveWaterParticleGenerator)(int ID) |
| void | [RestoreDeviceObjects](#RestoreDeviceObjects)(simul::crossplatform::RenderPlatform renderPlatform) |
| void | [UpdateWaterParticleGeneratorValues](#UpdateWaterParticleGeneratorValues)(simul::terrain::particleGeneratorValues generator, simul::terrain::particleGeneratorType generatorType, simul::crossplatform::Texture customPlaneTexture) |

Class for containing a set of particle generators. Currently a work in progress.
  


Functions
---
<a name="AddWaterParticleGenerator"></a>
### bool AddWaterParticleGenerator(simul::terrain::particleGeneratorValues newGenerator, simul::terrain::particleGeneratorType newGeneratorType, simul::crossplatform::Texture customPlaneTexture)
Create a particle generator
<a name="InvalidateDeviceObjects"></a>
### void InvalidateDeviceObjects()
Platform-dependent function called when uninitializing the wavelets simulator.
<a name="RecompileShaders"></a>
### void RecompileShaders()
Platform-dependent function to reload the shaders - only use this for debug purposes.
<a name="RemoveWaterParticleGenerator"></a>
### void RemoveWaterParticleGenerator(int ID)
Remove a particle generator
<a name="RestoreDeviceObjects"></a>
### void RestoreDeviceObjects(simul::crossplatform::RenderPlatform renderPlatform)
Platform-dependent function called when initializing the wavelets simulator.
<a name="UpdateWaterParticleGeneratorValues"></a>
### void UpdateWaterParticleGeneratorValues(simul::terrain::particleGeneratorValues generator, simul::terrain::particleGeneratorType generatorType, simul::crossplatform::Texture customPlaneTexture)
Update the values of a specific water particle generator
