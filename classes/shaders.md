---
title: Shaders
layout: reference
weight: 0
---
=======<br>Previous: [classes::env::cloud_keyframer](/ref/classes/env/cloud_keyframer)


trueSKY uses *effects* for rendering. An effect is a collection of shaders - vertex shaders, pixel shaders and so on, along with information on
how to combine them, how to set render state when they are used, and what inputs they take.

Platform-specific derived classes of <a href="../ref/simul/crossplatform/effect">Effect</a>are created with [simul::crossplatform::RenderPlatform::CreateEffect](/ref/simul/crossplatform/renderplatform/createeffect)
,
usually with an extensionless filename passed to the function.

The RenderPlatform first looks for a platform-specific shader source file by appending its platform shader file extension - .fx effect files for DirectX,
.glfx files for GLSL etc. If this is not found, the cross-platform .sfx extension is appended.


