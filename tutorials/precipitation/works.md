---
title: How it works
layout: reference
weight: 30
---






How it works
====================

Multi-Layer Precipitation and Precipitation Volume
-----------------
With trueSKY 4.2's introduction of multiple cloud layer, the rain generation system has now changed to allow multiple layers of precipitation to interact with each other. The old Rain Map has been replaced with a Precipitation Volume texture defining the precipitation at any altitude and position. The 2D precipitation regions drawn as vertically aligned cylinders in the the precipitation volume, ranging from the ground to the base of the cloud layer. It encodes the Strength and Rain - Snow values along with a pre-calculated precipitation/cloud density value. When two precipitation region intersect or overlap each other the intersecting volume regions mix together. No other set up is required to use multi-layered precipitation, however as this is a recent improvement to trueSKY, we advise using the Rain Texture Overlay (found from the Menu bar under View/Onscreen displays/Show Rain Textures) for debugging your scene.

![](/images/Precipitation/RainOverlay.png)
![](/images/Precipitation/PrecipitationVolumeDiagram.png)

