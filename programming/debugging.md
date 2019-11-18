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

<sup>This image shows an example of a default celestical display and an example where the Sun's position has been altered </sup>

Profiling
-------------------
Use profiling to aid performance measuring. This is a good way to determine what aspects of trueSKY are the most performmance heavy.

![](/images/Profiling.png)


Atmospheric Tables 
------------------------

![](/images/AtmosphericTables.png)


Cube Maps
--------------------------
Helpful to see what your clouds are doing. Will cycle through the different Mips.

![](/images/CubeMaps.png)


Water Texture
----------------------



Flow Rays
-------------

Lighting        
--------------------


Composition
-----------------------

![](/images/composition.png)


Rain Overlay
------------------------
![](/images/Precipitation/RainOverlay.png)


3D cloud Textures
------------------------------
![](/images/cloudtextures.png)

