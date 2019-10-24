---
title: Water
layout: reference
weight: 90
---





Water
====================

Realtime, Volumetric Water is one of the latest features to be brought to trueSKY, bringing the high quality we produce in the sky to the ground. Just like the Sky, we have an array of customisation for the water.

For quick setup - check out this [short video](https://www.youtube.com/watch?v=uwZZTEqaUbo){:target="_blank"}

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


Shore Effects
-----------------

![](/images/unreal/shoreeffects.png)


To use the Shore effects, add a 2D Scene depth camera into your project, with only Scene depth in R enabled.

![](/images/unreal/scenedepthR.png)


Next, create a RenderTexture, setting it to capture only the Red channel

![](/images/unreal/RenderTargetFormat.png)


Now, attach the RenderTexture to the 2DSceneCapture, and attach the Camera to the correct water instance.

You can now place the camera above where you want to apply the effect (pointing downwards), and adjust the Shore Depth Width and Extents to your liking.
