---
title: Noise3D
layout: reference
weight: 0
---
class Noise3D
===

| Include: | Math/Noise3D.h |

A 3D Perlin noise class.
  

[simul::math::NoiseInterface](noiseinterface.html)

Functions
---

| void | [Setup](#Setup)(unsigned int freq, int RandomSeed, int octaves, float persistence) |

A 3D Perlin noise class.
  


Base Classes
---
[simul::math::NoiseInterface](noiseinterface.html)

Functions
---
<a name="Setup"></a>
### void Setup(unsigned int freq, int RandomSeed, int octaves, float persistence)
Define the grid of pseudo-random numbers to be used in the PerlinNoise3D function. The parameter freq is the
frequency, or grid-size.
RandomSeed is a reproducible seed for the pseudo-random number generation.
Octaves is the number of octaves of noise super-imposed.
Persistence is the relative scaling of subsequent octaves - higher persistence leads to a more noisy function.
