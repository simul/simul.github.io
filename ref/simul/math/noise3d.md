---
title: Noise3D
layout: reference
weight: 0
---
class Noise3D
===

| Include: | Math/Noise3D.h |

A 3D Perlin noise class.
  

[simul::math::NoiseInterface](noiseinterface)

Functions
---

| void | [Setup](#Setup)(unsigned int freq, int RandomSeed, int octaves, float persistence) |

A 3D Perlin noise class.
  


Base Classes
---
[simul::math::NoiseInterface](noiseinterface)

Functions
---

### <a name="Setup"/>void Setup(unsigned int freq, int RandomSeed, int octaves, float persistence)
Define the grid of pseudo-random numbers to be used in the PerlinNoise3D function. The parameter freq is the
frequency, or grid-size.

