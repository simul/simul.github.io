---
title: Tutorials
layout: reference
weight: 10
---






Tutorial
====================

Overview
-----------------
Precipitation is controlled by cloud keyframes under the Weather Effects section in the Properties window of the selected cloud keyframe. Precipitation is bounded in trueSKY, and there are two main categories: cloud window and regional. This is controlled by the 'Regional' checkbox. A cloud window bounding means that the precipitation will fall across the scene. The  regional bounding limits the range and position of the precipitation; these are called precipitation that is regions. A Cloud Map Texture, which are explained later, also act to bound the precipitation by defining the shape of the cloud (see section on Cloud Map Texture). 

Precipitation regions are associated with their keyframe and their parameters, such as Radius, Strength and Rain - Snow, along with their position on the globe are interpolated over time. Precipitation regions can be position through the Cloud Window.

<div class="video-wrapper">
<div class="video-container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/pmyUjm__UkI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
</div>

Cloud Window
-----------------
After selecting a cloud keyframe from the timeline you wish to modify, you see a light blue box with a light blue shaded circle appear. This represents the static cloud keyframe - precipitation region pair; there will be one of these 'static' pairs per selected cloud keyframe from the timeline.

To move a precipitation region, click on the cloud window to select the window focus. Then use Shift + Left Click to drag the precipitation region. Remember that the precipitation region's position is relative to the position of its cloud keyframe, such that moving the cloud keyframe (with Left Click) will also cause the precipitation region move. The size of precipitation regions is modified by the Radius parameter in the Properties page, and these size changes are reflected in the Cloud Window. 

To learn more about the Cloud Window, please view this [tutorial](/tutorials/sequencer/tutorials#cloud-window).

![](/images/precipitation/CloudWindowPrecipitationRegions.png)


Cloud Map Texture
-----------------
A cloud map texture can be added to a cloud layer via its Properties window. This acts as a mask for both the cloud and precipitation generation. In terms of precipitation, this mask restricts the area in which precipitation can fall. This mask works in conjunction with the precipitation region to refine further shape of the precipitation volumes.

![](/images/precipitation/RainOverlayWithCloudMasks.png)


