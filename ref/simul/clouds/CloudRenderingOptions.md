---
title: CloudRenderingOptions
layout: reference
weight: 0
---
struct CloudRenderingOptions
===

| Include: | Clouds/CloudRenderingOptions.h |

This controls the rendering of clouds.<br>



This controls the rendering of clouds.

  


Fields
---

**CloudShadowStrength**  < Resolution to draw full-detail cloud buffers

**RenderGridZKm**  < Minimum grid width for raytracing.

**RaytraceMode**  < Minimum grid height for raytracing.

**DefaultNumSlices**  < Hint for the renderer on how to raytrace these clouds.

**MediumDetailProportion**  < For cloud volume update rate.

**DirectLight**  < For medium cloud volume update rate.

**IndirectLight**  < The amount of direct light to be used for rendering.

**AmbientLight**  < The amount of indirect or secondary light to be used for rendering.

**Extinction**  < The amount of ambient light to be used for rendering.

**MieAsymmetry**  < The amount of light scattered per metre - larger values produce darker clouds, default 0.05.
