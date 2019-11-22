---
title: Water
layout: reference
weight: 90
---





trueWATER
====================
**Water is only available in trueSKY 4.2**

Realtime, Volumetric Water is one of the latest features to be brought to trueSKY, bringing the high quality we produce in the sky to the ground. Just like the Sky, we have an array of customisation for the water.

For a quick setup - check out this [short video](https://www.youtube.com/watch?v=uwZZTEqaUbo){:target="_blank"}


These setting are on the trueSKYActor.

{:.object}
Variable                                                                                |       Definition                                                                                                              |       Value
--------------                                                                  |--------------                                                                                                         |--------------
Render Water                                                                    |If the water should be rendered.                                                                       |Bool
Water Resolution                                                                |Resolution of the Water.                                                                                       |Half or Full
Enable Reflection                                                               |Enable or Disable Reflections.                                                                         |Bool           
Reflection Resolution                                                   |Resolution of the Water.                                                                                       |Half or Full



These settings are available on the the trueSKY Water Object

{:.object}
Variable                                                                                |       Definition                                                                                                              |       Value
--------------                                                                  |--------------                                                                                                         |--------------
Render                                                                                  |If the water should be rendered.                                                                       |Bool
Boundless Ocean                                                                 |Render a full Ocean. Use this for large scale scenes.                          |Bool
Enable Wave Grid                                                                |Enable to use Buoyancy and wave physics.                                                       |Bool
Beaufort Scale                                                                  |Easy to use scale to determine the type of wave you require            |0.0 to 12
Wind Direction                                                                  |Direction of the wind                                                                                          |0 to 1
Wind Dependency                                                                 |How dependant the wave direction is on the wind.                                       |0 to 1
Use Colour Presets                                                              |Should colour presets be used.                                                                         |Bool
Colour Presets                                                                  |Select a colour preset to quickly change the colour of your water.     |Preset Selection
Scattering                                                                              |Amount of light scattering. Vec3                                                                       |0 to 1
Absorption                                                                              |Amount of light absorption. Vec3                                                                       |0 to 1 
Profile Buffer Resolution                                               |Buffer resolution. Increase this if you water appears to "shimmer"     |512 to 4096


We also have Advanced Water options, to allow for further customization. Enabling this will disable Beaufort scale.
{:.object}

Variable                                                                                |       Definition                                                                                                              |       Value
--------------                                                                  |--------------                                                                                                         |-------------
Advanced Water Options                                                  |If Advanced water options should be used                                                       |Bool
Wind Speed                                                                              |Speed of the wind. This will affect the size of the waves.             |0 to 40
Wave Amplitude                                                                  |Amplitude of the waves                                                                                         |0.01 to 2.0
Max Wavelength                                                                  |Minimum Wavelength of waves.                                                                           |1.01 to 100
Min Wavelength                                                                  |Maximum Wavelength of waves.                                                                           |0.1 to 1
Enable Foam                                                                             |If foam should be rendered on the waves                                                        |Bool
Foam Strength                                                                   |Strength of the foam effect.                                                                           |0 to 0.5


Shore Effects can be used to reduce the waves splashing unevenly over the water's edge.

{:.object}
Variable                                                                                |       Definition                                                                                                              |       Value
--------------                                                                  |--------------                                                                                                         |--------------
Shore Effects                                                                   |If shore effects should be enabled or not                                                      |Bool
Shore Depth Scene Capture                                               |The Depth Scene Capture camera that should be used                                     |SceneCapture2D
Shore Depth Width                                                               |Width of the Shore depth effect                                                                        |1000.0 to 10000.0
Shore Depth Extent                                                              |Depth of the Shore Depth Effects                                                                       |1000.0 to 10000.0


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
