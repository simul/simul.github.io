---
title: Debugging
layout: reference
weight: 30
---





Debugging
=========
Our goal is to have as much data publicly available to see as possible. If something is not working, you should know what isn't and why.

<div class="ue4-specific">
To show the trueSKY debugging overlays, assign the Render Target Texture TrueSkyOverlayRT (under TrueSkyPlugin/Overlay content) to the Overlay RT slot in the trueSKY Sequence Actor. The RT texture is then used with the PostProcessVolume: under Rendering Features, add a Post Process Material, and set it to the TrueSkyOverlay material reference.

![](/images/unreal/postprocessmaterial.png)


![](/images/unreal/overlayrt.png)


The overlays can then be set in Windows->Overlays and then select the overlays you want to show.

![](/images/unreal/DebugWindows.png)



</div>

Celestial Display
---------------------
Shows the current position and path of the Sun and Moon. The circles indicate the positions between the current and next keyframe.

![](/images/CelestialDisplay.png)

<sup>This image shows an example of a default celestial display and an example where the Sun's position has been altered </sup>

Profiling
-------------------
Use profiling to aid performance measuring. This is a good way to determine what aspects of trueSKY are the most performance heavy.

![](/images/Profiling.png)


Atmospheric Tables 
------------------------
Detailed numbers on lighting values as well as colours. Issues with lighting can be looked at here.
![](/images/AtmosphericTables.png)


Cube Maps
--------------------------
Helpful to see what your clouds are doing. Will cycle through the different Mips.

![](/images/CubeMaps.png)


Water Texture
----------------------
Here you can view the water Texture to see any issues that may be caused due to overlapping terrain or unusual behaviour.

Flow Rays
-------------

Lighting        
--------------------


Composition
-----------------------
Here is an overview of many of the systems use, helpful for depth tests and general debugging.
![](/images/composition.png)


Rain Overlay
------------------------
Here is an overlay of the rain map texture. If the precipitation volume is blank, then the rain does not know where to fall. Rain will only fall under clouds, unless specifically asked not to.
![](/images/precipitation/RainOverlay.png)


3D cloud Textures
------------------------------
3D clouds textures including the shadow map texture. Helpful to see how much your Worley setting are affecting the clouds, as well as how large the Shadow Map is.
![](/images/cloudtextures.png)

