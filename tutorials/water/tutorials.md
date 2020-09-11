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

If you are planning to create a large body of water / an ocean, you can check the "Boundless Ocean" checkbox within the trueSKYWater assets properties section, which will extend the surface of the water to the horizon.
Regular bounded water objects can be scaled and rotated to fit within your scene. You can also use your own static meshes for the water surface for performance, or to fit the water within very specific bounds in your scene.
Please note that the default bounded objects are designed for quite small bodies of water, if they are made too large they may cause performnce issues.
