---
title: LensFlare
layout: reference
weight: 0
---
class LensFlare
===

| Include: | Platform/CrossPlatform/LensFlare.h |

A helpful class to calculate lens flares.


Functions
---

| float  const * | [GetArtifactPosition](#GetArtifactPosition)(int i) |
| float | [GetArtifactSize](#GetArtifactSize)(int i) |
| int | [GetNumArtifacts](#GetNumArtifacts)() |
| int | [GetNumArtifactTypes](#GetNumArtifactTypes)() |
| void | [UpdateCamera](#UpdateCamera)(float cam_dir, float dir_to_light) |

A helpful class to calculate lens flares.
  


Functions
---

### <a name="GetArtifactPosition"/>float  const * GetArtifactPosition(int i)
Get the direction to the flare.
Get the direction to the flare.

### <a name="GetArtifactSize"/>float GetArtifactSize(int i)
Get the size of the flare.
Get the size of the flare.

### <a name="GetNumArtifacts"/>int GetNumArtifacts()
Get the number of flare artifacts.
Get the number of flare artifacts.

### <a name="GetNumArtifactTypes"/>int GetNumArtifactTypes()
Returns the number of artifact types (halo, ring, flare, etc.) - this will be the number of textures needed.
Returns the number of artifact types (halo, ring, flare, etc.) - this will be the number of textures needed.

### <a name="UpdateCamera"/>void UpdateCamera(float cam_dir, float dir_to_light)
Set the camera and light directions. Do this once per frame to update the flare positions.
Set the camera and light directions. Do this once per frame to update the flare positions.
