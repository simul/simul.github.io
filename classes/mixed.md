---
title: Mixed Resolution Compositing
layout: reference
weight: 0
---
=======<br>Previous: <a href="shaders">Shaders</a>

TrueSKY's cloud rendering is usually performed at below the full resolution of the screen. This is because, as a raytracing system, its
efficiency is highly dependent on the number of pixels drawn. To draw at 1/4 the full resolution, for example means rendering 1/16th the
number of pixels, with significant time savings.

However, clouds and Simul's other volumetric effects can be blended seamlessly with the full-resolution scene, even taking into account MSAA
anti-aliasing. To do this, trueSKY uses a mixed-resolution compositor.



