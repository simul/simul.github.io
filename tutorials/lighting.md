---
title: Lighting
layout: reference
weight: 40
---






Lighting
====================

trueSKY takes control of a direction light in your scene, and will also take control of a directional light. trueSKY can perform all of its calculations with just one directional light, so we recommend only having one in the scene.


{:.layer}
Variable                                                                        |       Definition                                                                                                                                                                                                                                                      |       Value
--------------                                                          |--------------                                                                                                                                                                                                                                                 |--------------
Brightness Power                                                        |Adjusts light levels to compensate for variations via power function (e.g 0.5 = square root dependence, 1.0 = no adjustment).                  |0.01 to 1.0 
Altitude                                                                        |Higher Altitude, less atmosphere. Will allow more light to pass through.                                                                                                                               |1 to 8
Max Altitude                                                            |Max altitude that will be used for fade and sky colour calculations, in km.                                                                                                                    |2.0 and 100.0
Elevations                                                                      |Number of elevations / height of table. |Powers of 2 between 4 and 256.
Distances                                                                       |Number of distances / width of table.| Powers of 2 between 4 and 128.
Distance Range                                                          |Maximum distance for fade.  |5.0 and 2000.0.


{:.object}
Variable                                                                        |       Definition                                                                                                                                                                                                                                                      |       Value
--------------                                                          |--------------                                                                                                                                                                                                                                                 |--------------
Light source                                                            |Which directional light source trueSKY should control                                                                                                                                                                  |Directional Light
Drive Light Direction                                           |If trueSKY should alter the angle of the Directional Light based on the movement of the Sun and Moon.                                                                  |Bool
Light Units                                                             |Radiometric or Photometric Light Units. Use Radiometric unless you understand Unreal's Exposure settings.[Light Units](#light-units)   |Radiometric or Photometric
Brightness                                                                      |A Brightness Multiplier applied to the Sun, Moon and Sky.                                                                                                                                                              |0.1 to 10.0
Gamma                                                                           |Gamma adjustment value.                                                                                                                                                                                                                                |0.0 to 10.0                                    
Direct Light                                                            |Amount of direct light.                                                                                                                                                                                                                                |0.0 to 4.0
Indirect Light                                                          |Amount of indirect light.                                                                                                                                                                                                                              |0.0 to 4.0
Ambient Light                                                           |Amount of ambient light.                                                                                                                                                                                                                               |0.0 to 4.0
Extinction                                                                      |Amount of light scattered per metre (larger values = darker clouds).                                                                                                                                   |0.0001 to 10.0
Mie Asymmetry                                                           |Anisotropic distribution of direct lighting, or eccentricity.                                                                                                                                                  |0.0 to 1.0



<hr>

trueSKY Light
==================
This applies a constant ambient light over the whole scene. Check out [Unreal's SkyLight](https://docs.unrealengine.com/en-US/Engine/Rendering/LightingAndShadows/LightTypes/SkyLight/index.html) for information on most of the variables. This will just cover the variables unique to trueSKY, as we have created our own skylight.

{:.object}
Variable                                                                        |       Definition                                                                                                                                                                                              |       Value
--------------                                                          |--------------                                                                                                                                                                                         |--------------
Update Frequency                                                        |How often the trueSKYLight will update, in frames. 1 means every frame, two mean every other frame etc.        |1 to 100
Blend                                                                           |How much to blend new updates with previous values.                                                                                                            |0 to 1
Amortization                                                            |How much to Amortize rendering.                                                                                                                                                        |1 to 8
All Faces                                                                       |Whether to fill all cube maps faces on every update.                                                                                                           |Bool
All Mips                                                                        |Whether to fill all mipmaps on every update.                                                                                                                           |Bool
Diffuse Multiplier                                                      |A multiplier for the diffuse illumination from the skylight.                                                                                           |0.0 to 20.0
Specular Multiplier                                                     |A multiplier for the specular reflections from the skylight.                                                                                           |0.0 to 20.0
Gamma Correction                                                        |A gamma adjustment to apply.                                                                                                                                                           |0.0 to 20.0


<hr>





Lighting Information
===================


Point Lights
-------------

Point lights can be used to illuminate the clouds. Because of the relative scale of clouds compared to the scene, the intensity of the light must be very large in order to have a visible effect.

![](/images/unreal/pointlight.png)



<div class="ue4-specific">

This can be done with the SetPointLight Blueprint node.

![](/images/unreal/setpointlight.png)


If you do not have a PointLight actor, you can use SetPointLightSource to individually apply the position, colour and intensity of a light to the clouds.

![](/images/unreal/setpointlightsource.png)


</div>



<div class="unity-specific">
To do so, access the trueSKY object and call:

public void SetPointLight(int id, Vector3 pos, float min_radius, float max_radius, Vector3 irradiance)

This function will map point lights to the given id, so it can be called to both create a point light and to change the values of an existing point light.

</div>


<div class="ue4-specific">

The sky at sunrise can be less than one quarter as bright as at noon. Moonlight is hundreds of times dimmer than sunlight. Starlight is much dimmer still. The human eye adjusts to a very wide range of light conditions, but for rendering we usually apply a brightness, or exposure level, to make dark scenes visible and bright scenes clear.

The Brightness Power value for a sky sequence adjusts the light levels to compensate for this large variation by introducing a power function.

If the Power is 1.0, there is no adjustment. If it is 0.5, it will be a square-root dependence, e.g. a light 4 times dimmer than daylight would appear only half as dim, and so on.


<hr>


Physical Units (trueSKY 4.1 onward)
-----------------------------------

trueSKY is a physically-based renderer, which means that the light and colour values generated correspond to true physical properties. The pixel colours rendered to a view are spectral radiance values. However, to keep the numbers from getting too high or low, a global adjustment is applied. This is because numerical accuracy would be lost, particularly for very dark night-time scenes, if we kept the same scale at all times. The Sky property "Brightness Power" controls this adjustment - if equal to one, there is no adjustment. Values smaller than one reduce the range of outputs - brightening dark skies and dimming very bright skies. To obtain the current value of the multiplier, use the Blueprint function "GetReferenceSpectralRadiance". Then you can use the calculation:

spectral radiance (watts/square metre/steradian/nm) = pixel value * reference spectral radiance

You can use this value to calibrate the other lights in your scene. Say you have a point light representing an electric bulb. The brightness of this light would in reality be constant. But because trueSKY adjusts the physical value of a pixel as time passes, you must compensate for this by scaling the intensity of the bulb by the inverse of the reference radiance.

![](/images/unreal/ReferenceSpectralRadiance.png )
Using the spectral radiance value to modulate the intensity of lights in the scene.")

So the light appears to get brighter as day turns to night. You can get the same effect using Unreal's Eye Adaptation (Auto Exposure). But because this is a post-process effect, it cannot cope with very dark scenes - you may see banding in the sky colours due to the low numerical accuracy of very small numbers.

![](/images/unreal/DayLightRadiance.png)

<sup> Spectral radiance example: Day </sup>

![](/images/unreal/SunsetLightRadiance.png)

<sup> Spectral radiance example: Sunset </sup>

![](/images/unreal/NightLightRadiance.png)

<sup> Spectral radiance example: Night </sup>

<hr>

Light Units
-----------

If you would like to use Lux for your light units, so direct light is over 100k, you will need to switch to Photometric Units. This is done under the Lighting Section on the trueSKYActor, in the additional drop down tab. This will make your scene unbearably bright unless you know how to adjust Unreal's Exposure settings. When using Lux, make sure to set the Brightness Power to 1 to remove the Adjustment, and be aware of the size of your Irradiance Values. This is a work in progress.


</div>

<hr>

Transparency
-------------

<div class="ue4-specific">
In a material that uses transparency, insert the trueSKYTransparencyModifier function between the inputs and the final output node:

![](/images/unreal/Transparency.png)

<sup>Using the trueSKYTransparencyModifier material function to modulate the material output values </sup>

</div>

<div class="unity-specific">
Coming Soon
</div>

