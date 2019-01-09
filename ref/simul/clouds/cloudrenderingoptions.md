---
title: CloudRenderingOptions
layout: reference
weight: 0
---
struct CloudRenderingOptions
===

| Include: | Clouds/CloudWindow.h |

This controls the rendering of clouds.<br>


Functions
---

| unsigned long long | [GetEnum](#GetEnum)(char txt_utf8) |

This controls the rendering of clouds.

  


Functions
---

### <a name="GetEnum"/>unsigned long long GetEnum(char txt_utf8)
< Mie scattering eccentricity.

Fields
---

**MediumDetailProportion**  < For cloud volume update rate.

**MaximumCubemapResolution**  < For medium cloud volume update rate.

**CloudShadowStrength**  < Resolution to draw full-detail cloud buffers

**RenderGridZKm**  < Minimum grid width for raytracing.

**RaytraceMode**  < Minimum grid height for raytracing.

**DefaultNumSlices**  < Hint for the renderer on how to raytrace these clouds.

**IndirectLight**  < The amount of direct light to be used for rendering.

**AmbientLight**  < The amount of indirect or secondary light to be used for rendering.

**Extinction**  < The amount of ambient light to be used for rendering.

**MieAsymmetry**  < The amount of light scattered per metre - larger values produce darker clouds, default 0.05.
