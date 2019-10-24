---
title: Debugging
layout: reference
weight: 30
---





Debugging
=========

<div class="ue4-specific">
To show the trueSKY debugging overlays, assign the Render Target Texture TrueSkyOverlayRT (under TrueSkyPlugin/Overlay content) to the Overlay RT slot in the trueSKY Sequence Actor. The RT texture is then used with the PostProcessVolume: under Rendering Features, add a Post Process Material, and set it to the TrueSkyOverlay material reference.

![](/Images/unreal/postprocessmaterial.png)


![](/Images/unreal/overlayrt.png)


The overlays can then be set in Windows->Overlays and then select the overlays you want to show.

![](/Images/unreal/DebugWindows.png)




</div>

Celestial Display
---------------------
Shows the current position and path of the Sun and Moon. The circles indicate the positions between the current and next keyframe.

![](/Images/CelestialDisplay.png)

<sup>This image shows an example of a default celestical display and an example where the Sun's position has been altered </sup>

Profiling
-------------------
Use profiling to aid performance measuring. This is a good way to determine what aspects of trueSKY are the most performmance heavy.

![](/Images/Profiling.png)


Atmospheric Tables 
------------------------

![](/Images/AtmosphericTables.png)


Cube Maps
--------------------------
+ Cross section

![](/Images/CubeMaps.png)


Water Texture
----------------------



Flow Rays
-------------

Lighting        
--------------------


Composition
-----------------------

![](/Images/composition.png)

Rain Overlay
------------------------

![](/Images/rainOverlay.png)

3D cloud Textures
------------------------------

![](/Images/cloudtextures.png)



2D Cloud Textures
---------------------------
Depreciated? or works with 4.1a?


