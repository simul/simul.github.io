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

**MediumDetailProportion**  < For cloud volume update rate.

**MaximumCubemapResolution**  < For medium cloud volume update rate.

**CloudShadowStrength**  < Resolution to draw full-detail cloud buffers

**RenderGridZKm**  < Minimum grid width for raytracing.

**RaytraceMode**  < Minimum grid height for raytracing.

**lightingMode**  < Hint for the renderer on how to raytrace these clouds.

**IndirectLight**  < The amount of direct light to be used for rendering.

**AmbientLight**  < The amount of indirect or secondary light to be used for rendering.

**Extinction**  < The amount of ambient light to be used for rendering.

**MieAsymmetry**  < The amount of light scattered per metre - larger values produce darker clouds, default 0.05.

**MinimumStarPixelSize**  < Mie scattering eccentricity.

**StarBrightness**  < Smallest pixel width to use drawing stars.

**CosmicBackgroundBrightness**  < Brightness multiplier for stars.

**MaximumStarMagnitude**  < Brightness multiplier for cosmic background.

**CloudTint**  < Largest magnitude of star to draw. Larger magnitudes are dimmer.
