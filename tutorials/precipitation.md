---
title: Precipitation
layout: reference
weight: 50
---






Precipitation
====================
Precipitation can be attached to any 3D cloud keyframe and will produce rain based on cloud position and thickness (if desired).

{:.ue4-specific}
For transparent effects to work in Unreal, trueSKYtransluscent needs to be added as a post process material. This should be done automatically. Learn about this [here.](/faq.html#postprocess) 

{:.keyframe}
Variable                                                                                        |       Definition                                                                                                                                                                                                      |       Value
--------------                                                                          |--------------                                                                                                                                                                                                 |--------------
Regional                                                                                        |Whether rain/snow falls only in specified region, or globally.                                                                                                 |Bool.
Wind affects position                                                           |If the wind should affect the regional area.                                                                                                                                   | Bool.
Radius (km)                                                                                     |Radius of precipitation region.                                                                                                                                                                |Between 0.1 and 1000
Edge                                                                                            |How strong the cutoff is at the edge of the precipitation region.                                                                                              |0.0 to 1.0
Rain - Snow                                                                                     |How the Precipitation will act. 0 = rain, 1 = snow, values in between will share characteristics.                              |0.0 to 1.0 
Strength                                                                                        |Amount of rain/snow.                                                                                                                                                                                   |0.0 to 1.0
Rain Streaks                                                                            |Visual strength of rain streak effect.                                                                                                                                                 |0.0 to 1.0
Wind Effect                                                                             |How much precipitation is affected by wind.                                                                                                                                    |0.0 to 1.0

{:.object}
Variable                                                                                        |       Definition                                                                                                                                                                                                      |       Value
--------------                                                                          |--------------                                                                                                                                                                                                 |--------------
Max Precipitation Particles                                                     |The maximum number of rain particles to render.                                                                                                                                |0 to 1000000
Precipitation Radius Meters                                                     |Size of particle zone.  Higher values allow you to render precipitation at greater distances                                   |0.0 to 100.0
Rain Fall Speed MS                                                                      |Speed at which raindrops will fall.                                                                                                                                                    |0.0 to 120.0
Rain Drop Size mm                                                                       |Size of each individual Raindrop.                                                                                                                                                              |0.001 to 100.0
Snow Fall Speed MS                                                                      |Speed at which Snow Flakes will fall.                                                                                                                                                  |0.0 to 10
Snow Flake Size mm                                                                      |Size of each individual Snow Flake.  Recommended to increase for testing purposes.                                                             |0.0 to 1
Precipitation Wind effect                                                       |How much precipitation is affected by wind.                                                                                                                                    |0.0 to 1.0
Precipitation Waver                                                                     |How much precipitation wavers.  Waver is how much the rain or snow will sway while falling                                     |0.0 to 10
Precipitation Waver Timescale                                           |Intervals between waver. In seconds between                                                                                                                                    |1 to 10
Precipitation Threshold Km                                                      |Thickness of cloud needed for rainfall. No threshold when set to 0.                                                                                    |0.0 to 10.0
Rain Cubemap                                                                            |Cubemap to be used to light the Rain                                                                                                                                                   |Cubemap
Velocity Streaks                                                                        |If the raindrop shape is altered by their velocity.                                                                                                                    |Bool
Simulation Time                                                                         |If time progression should be taken into account for rain fall.                                                                                                |Bool
Rain Near Threshold                                                                     |Draw no rain closer than this distance.                                                                                                                                                |0.01 t0 0.5
Rain Mask Scene Capture 2D                                                      |2D Screen capture to limit rain below surfaces. Lean more about this [here](#rain-indoors).                                    |Scene Capture 2D
Rain Mask Width                                                                         |Width of the Rain Mask                                                                                                                                                                                 |100 to 50000
Rain Mask Depth Extent                                                          |Height of the Rain Mask                                                                                                                                                                                |100 to 100000
Translucent RT                                                                          |The render texture used to render Precipitation effects.                                                                                                               |Render Texture


<hr>

Current Issue
=================
There is currently an issue with multiple layers and precipitation. If you want precipitation with multiple layers, please just use the most recently created layer.


No Rain?
========

{:.ue4-specific}
Double check you have trueSKY Translucent as a [Post Process.](/faq.html#postprocess) 

Try starting the game

Make sure there are enough clouds to produce rain

Check you are editing the correct keyframe (At the right time and on the current sequence)

Rain Indoors
======================

To prevent rain from falling in covered areas, create a SceneCapture2D actor, and give it a texture target that's contains only a red channel (e.g. RainDepthRT from the trueSKY content). Make the Capture Source "SceneDepth in R". You don't need to enable "Capture Every Frame" unless you expect the geometry to change.

![](/images/unreal/scenecapture2dProperties.png)


Rotate the Scene Capture 2D to face Downwards.

On the trueSKY Sequence Actor, assign the Scene Capture 2D actor to the Rain Mask SceneCapture property. Now, rain will only appear where there is no cover above the Scene Capture actor.

![](/images/unreal/PrecipitationProperties.png)

