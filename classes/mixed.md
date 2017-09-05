---
title: Mixed Resolution Compositing
layout: reference
weight: 0
---
Mixed Resolution Compositing
=======
Previous: <a href="shaders">Shaders</a>

TrueSKY's cloud rendering is usually performed at below the full resolution of the screen. This is because, as a raytracing system, its
efficiency is highly dependent on the number of pixels drawn. To draw at 1/4 the full resolution, for example means rendering 1/16th the
number of pixels, with significant time savings.

However, clouds and Simul's other volumetric effects can be blended seamlessly with the full-resolution scene, even taking into account MSAA
anti-aliasing. To do this, trueSKY uses a mixed-resolution compositor.



*Mixed-resolution compositing in trueSKY*


The downscaling is set as a property of the weather renderer:

~~~~~~~~~~~~~~~{.c}
        weatherRenderer->SetDownscale(4);
~~~~~~~~~~~~~~~

The depth values passed to the weather renderer in your depth texture are processed to obtain the needed information for the compositing. This processing uses the projection matrix passed in in your DeviceContext object. The most efficient projection is usually the depth-reversed style, for which the far plane is at z=0.

<h2>Using trueSKY's compositor for other things</h2>
trueSKY's mixed-resolution compositor can be useful for blending other effects, like particle systems, into the scene.
To do this, you can adapt RenderMixedResolution, or the function it calls, RenderLowResolutionElements. You will need to fill in two rendertargets: one for the far depth, one for the near.

For the far pass, use the x-component of the lowResDepthTexture as depth. For the near pass, use the y-component, but discard fragments whenever the z-component is zero (z represents edges).

<hr>
Next: <a href="../sequencer">The Sky Sequencer</a>
