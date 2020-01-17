---
title: Tutorials
layout: reference
weight: 30
---





Tutorials
============


<div class="video-wrapper">
<div class="video-container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/uwZZTEqaUbo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
<!-- /video -->
</div>
<!-- /video-wrapper --> 


Adding water your scene
-----------------
Implementing volumetric water into your scene is quick and easy thanks to trueSKY! The first thing you need to do is make sure you have initialized trueSKY in your scene, so you have a trueSKY Actor/Object in your scene. Then, enable "Render Water" on your trueSKY Object. This option decides if we should render any water at all, while each water instance has their own render option.

Next, we need to add a trueSKY water instance. 

<div class="unity-specific">
Go to Gameobject->createOther->create trueSKY water Object
</div>

<div class="ue4-specific">
Search for True Sky Water, and then drag it into your scene.
</div>

If you are planning to create a large body of water / an ocean, you can check the "Boundless Ocean" checkbox within the trueSKYWater assets propertys section. You can control all of your waters propertys and settings from within the trueSKYWaters details panel.

Shore Effects
-----------------

![](/images/unreal/shoreeffects.png)


To use the Shore effects, add a 2D Scene depth camera into your project, with only Scene depth in R enabled.

![](/images/unreal/scenedepthR.png)


Next, create a RenderTexture, setting it to capture only the Red channel

![](/images/unreal/RenderTargetFormat.png)


Now, attach the RenderTexture to the 2DSceneCapture, and attach the Camera to the correct water instance.

You can now place the camera above where you want to apply the effect (pointing downwards), and adjust the Shore Depth Width and Extents to your liking.


Buoyancy
---------------
Generally, you should have enough water probes positioned in such a way that they roughly cover the volume that the ships take up.

For Example, this ship has 4 probes:


![](/images/buoyancy.png)



To be affected correctly by the waves, make sure to tick Enable Wave Grid on the Water Object. [Click here to learn  more.](https://simul.co/real-time-rendering-news/truesky-volumetric-water-tutorials-and-tips/)
