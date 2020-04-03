---
title: Tutorials
layout: reference
weight: 10
---




Clouds
===========
Clouds in trueSKY are easy to create, hard to master. For a quick solution, use one of our presets!

<div class="video-wrapper">
<div class="video-container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/pkt3eqa9YB8" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
</div>




Cloud Movement
--------------------
Use the keyframes to set specific positions for the clouds at set times. Then watch as your clouds will move between. For fast clouds make a shorter gap, or reduce the time between. 

<div class="video-wrapper">
<div class="video-container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/XQ-BDpAR-sY" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
</div>


Using a Map Texture
---------------------

When creating or finding a map texture ensure that the map is black and white. You can gain a slight gradient on your clouds using greys to blend between values.

Ensure you are saving your map texture files into the correct location.

<div class="ue4-specific">
For Unreal:
Unreal Build folder -> Engine -> Plugins -> TrueSkyPlugin -> Resources -> Media -> Insert .png
</div>

<div class="unity-specific">
For Unity:
Unity -> Locate your unity project folder -> Insert .png
</div>

Within the sequencer, select your cloud layer and open the file browser under the "map texture" heading.

Locate the correct file path as shown above, and select your .png map file.

Once the map is applied, alter a value within the sequencer to update your scene and edit settings as through the keyframes were a 
regular cloudkeyframe (all regular functionality still apllies)

Be aware of artifacting if your map texture has very thin parts. A good solution is to reduce the Cloud Height, along with adding some more Diffusivity.

<div class="video-wrapper">
<div class="video-container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/ffMJyoNKWZc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
</div>

For more tutorials, head to [our YouTube Page](https://www.youtube.com/user/simulsoftware), where we upload tutorials and showcases of trueSKY
