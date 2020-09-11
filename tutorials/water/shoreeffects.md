---
title: Shore Effects
layout: reference
weight: 60
---




Shore Effects
====================

![](/images/unreal/shoreeffects.png)


To apply Shore effects to a boundless ocean, add a 2D Scene depth camera into your project, with only Scene depth in R enabled.

![](/images/unreal/scenedepthR.png)


Next, create a RenderTexture, setting it to capture only the Red channel

![](/images/unreal/RenderTargetFormat.png)


Now, attach the RenderTexture to the 2DSceneCapture, and attach the Camera to the correct water instance.

You can now place the camera above where you want to apply the effect (pointing downwards), and adjust the Shore Depth Width and Extents to your liking.
