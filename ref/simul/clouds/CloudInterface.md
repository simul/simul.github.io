---
title: CloudInterface
layout: reference
weight: 0
---
class CloudInterface
===

| Include: | Clouds/CloudInterface.h |

The virtual interface for controlling and reading cloud data.
  


Functions
---

| float | [GetCloudDensity](#GetCloudDensity)(float cloud_base_z, float width, float height, simul::math::Vector3 X, float time, float cloudiness, float extinction, float diffusivity) |
| simul::math::NoiseInterface * | [GetNoiseInterface](#GetNoiseInterface)() |
| float | [GetOpticalPathLength](#GetOpticalPathLength)(float cloud_base_z, float w, float h, simul::math::Vector3 X, simul::math::Vector3 dir, float time, float cloudiness, float extinction, float diffusivity) |

The virtual interface for controlling and reading cloud data.
  


Functions
---

### <a name="GetCloudDensity"/>float GetCloudDensity(float cloud_base_z, float width, float height, simul::math::Vector3 X, float time, float cloudiness, float extinction, float diffusivity)
Get the normalized cloud density at real-world position X.

### <a name="GetNoiseInterface"/>simul::math::NoiseInterface * GetNoiseInterface()
Get the noise object.

### <a name="GetOpticalPathLength"/>float GetOpticalPathLength(float cloud_base_z, float w, float h, simul::math::Vector3 X, simul::math::Vector3 dir, float time, float cloudiness, float extinction, float diffusivity)
