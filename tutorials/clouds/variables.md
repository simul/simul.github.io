---
title: Variables
layout: reference
weight: 30
---




Variables
=============
This list of variables is grouped by how they affect the clouds, along with where they are located. Variables in the Red tables are located on the Keyframe, Green are in the Layer andBlue variables are on the trueSKYSequenceActor.

Main
============
These setting will alter setting about how and in what are the clouds are generated, as there are variables such as the ray-tracing methods used, the area which they are created within and the resolution at which they are rendered.

{:.keyframe}
Variable                                                                        |       Definition                                                                                                                                                                                                              |       Value
--------------                                                          |--------------                                                                                                                                                                                                         |--------------
Cloudiness                                                                      |How much cloud in the cloud layer.                                                                                                                                                             | 0.0 to 1.0
Cloudbase                                                                       |Base altitude of cloud layer.                                                                                                                                                                          |-1.0 to 20.0
Layer Height                                                            |Height of cloud layer, in km.                                                                                                                                                                          |-1.0 to 20.0
Volume Width                                                            |Width of cloud layer, in km                                                                                                                                                                            |-1.0 to 20.0

{:.layer}
Variable                                                                        |       Definition                                                                                                                                                                                                              |       Value
--------------                                                          |--------------                                                                                                                                                                                                         |----------
Class                                                                           |How the renderer should raytrace Clouds. If you want a layer of Whispy Clouds, set this to Cirrus                                      |Standard = 0, Cirrus = 1
Default Slices                                                          |Number of slices in main view.                                                                                                                                                                         |Between 80 and 255
Grid Width                                                                      |Width of grid                                                                                                                                                                                                          |Powers of 2 between 16 and 512
Grid height                                                             |Height of grid                                                                                                                                                                                                         |Powers of 2 between 1 and 64

{:.object}
Variable                                                                        |       Definition                                                                                                                                                                                                              |       Value
--------------                                                          |--------------                                                                                                                                                                                                         |--------------
Max Cloud Resolution                                            |Resolution of clouds, ideally in powers of 2. Recommended values of 512 or 1024                                                                        |128 to 4096 
Max Cloud distance                                                      |Distance of furthest cloud layer.                                                                                                                                                                      |100.0 to 500.0 
Render Grid X                                                           |Detail size of grid used to render clouds. Smaller grid means higher quality clouds.                                                           |0.01 to 10km
Render Grid Y                                                           |Detail size of grid used to render clouds. Smaller grid means higher quality clouds.                                                           |0.01 to 10km
Default Num Steps                                                       |Approximate number of raytrace steps.                                                                                                                                                          |40 to 300
Amortization                                                            |How rendering clouds is spread over frames. For 1, all pixels are drawn every frame, for 2, its 2x1, 3 for 3x2 etc.|1 to 8
Cloud Threshold Distance                                        |A heuristic distance to discard near depths from depth interpolation, improving accuracy of upscaling.                         |0.0 to 10.0
Depth Sampling Pixel Range                                      |The size of the sampling area, in pixels, in the full-resolution depth buffer. Used to find near/far depths.           |0.0 to 4.0
Depth Temporal Alpha                                            |The alpha for temporal blending of the solid depth buffer used for cloud rendering. 1.0 is instant.                            |0.01 to 1.0
Integration Scheme                                                      |Which method to use for grid rendering. Fixed is good for static, fluffy clouds. Not recommened for flying through |Grid or Fixed
Depth Blending                                                          |If trueSKY should blend clouds with scenery, or draw them in front/behind depending on altitude.                                       |Bool
Share Buffers for VR                                            |Share Buffer for VR.                                                                                                                                                                                           |Bool

Shape   
=============

Shape values alter the general look of the clouds, such as how transparent the cloud is. If you have unusual looking clouds or incorrect artefacts, these are the setting to investigate.

The clouds are made up of a base layer, a transition area and the upper layer. 

Clouds are thicker on the bottom, so the base layer is almost always the largest, and the transition area is where the base and upper layers meet. 

The upper density is a multiplier for the amount of clouds in the upper layer. A value of 1 will produce the same amount of clouds as the base layer. 

There are individual settings to help customise each of the different layers, allowing you to create unique but realistic clouds.

By default, the cloud volume repeats at the edges, and the volume width is controlled by the keyframe value **Cloud Width**. You can change the size of this volume freely, but to increase the size while retaining the same level of detail, you will also need to modify the size of the volumetric grid. For example, to double the size of the volume, select all the 3D cloud keyframes, and double the size of **Cloud Width**. Select the cloud layer, and increase both the **Cloud Grid Width**, and the **Generation Noise Resolution**, by a factor of two.

{:.keyframe}
Variable                                                                        |       Definition                                                                                      |       Value
--------------                                                          |--------------                                                                                 |--------------
Max Density                                                                     |Maximum allowed density.                                                               |0.0 to 1.0
Local Density                                                           |Current density of the clouds.                                                 |0.0 to 1.0 
Base layer                                                                      |Maximum density of the clouds.                                                 |0.0 to 2.0
Transition                                                                      |Transition from cloudbase to upper cloud.                              |0.0 to 1.0
Worley Noise                                                            |How much Worley noise to apply.                                                |0.0 to 1.0
Worley Scale                                                            |Scale of Worley noise.                                                                 |0.0 to 12.0 
Diffusivity                                                                     |How much cloud edges should be diffused.                               |0.0 to 1.0
Persistence                                                                     |Fractal persistence for generating clouds.                             |0.0 to 1.0
Octaves                                                                         |Number of noise octaves to generate clouds.                    |1 to 5
Upper Density                                                           |Proportion of cloud density retained in upper layer.   |0.0 to 1.0


<hr>

Wind
=========
Using Wind to create a dynamic sky and moving shadows is an effective way to make an environment feel alive. There are different ways to shift the clouds, however for clouds to move the time must be progressing. Learn how to control time [here](time.html).

Known Issues
-------------
Setting two keyframes to different wind speeds can cause a visual jump in the clouds. Currently recommend setting all keyframes on one layer to the same speed. 

Setting wind speed on the Actor will not adjust movement, only visual Churn. Currently being fixed.

{:.keyframe}
Variable                                                                        |       Definition                                                                                                                                                                                      |       Value
--------------                                                          |--------------                                                                                                                                                                                 |--------------
Wind Speed (keyframe)                                           |Wind speed in m/s.                                                                                                                                                                             |0.0 to 1000.0
Wind Heading                                                            |Horizontal cloud movement direction, in degrees.                                                                                                               |0.0 to 360.0

{:.layer}
Variable                                                                        |       Definition                                                                                                                                                                                      |Value
--------------                                                          |--------------                                                                                                                                                                                 |--------------
Override Wind                                                           |Whether to apply real-time wind motion.                                                                                                                                |Bool

{:.object}
Variable                                                                        |       Definition                                                                                                                                                                                      |       Value
--------------                                                          |--------------                                                                                                                                                                                 |--------------
Wind Speed (trueSKY Object)                                     |Wind speed in m/s. Recommended to be similar to the keyframe wind speed to avoid movement errors.              |0.0 to 1000.0 



<hr>

Noise   
===========
Noise is the best way to make sure your clouds don't look too flat or repetitive. Values in noise are very sensitive and can produce unusual results if you're not careful.


{:.keyframe}
Variable                                                                        |       Definition                                                                                                                                                                                      |       Value
--------------                                                          |--------------                                                                                                                                                                                 |--------------
Base Factor                                                                     |Proportion of noise applied at cloudbase.                                                                                                                              |0.0 to 1.0
Amplitude                                                                       |Strength of fractal edge effect.                                                                                                                                               |0.01 to 100.0
Worley Amplitude                                                        |Wavelength of fractal Worley noise.                                                                                                                                    |0.1 to 10000.0
Sharpness                                                                       |Sharpness applied at boundary.                                                                                                                                                 |0.0 to 1.0
Churn                                                                           |Strength of cloud edge churning effect (larger values = more turbulent clouds).                                                |0.001 to 1000.0

{:.layer}
Variable                                                                        |       Definition                                                                                                                                                                                      |       Value
--------------                                                          |--------------                                                                                                                                                                                 |--------------
Noise Period                                                            |Fractal noise period, in days.                                                                                                                                                 |0.001 to 1000.0
Noise Phase                                                                     |
Noise Resolution                                                        |3D Perlin noise resolution, for cloud generation.                                                                                                              |Powers of 2 between 4 and 64

{:.object}
Variable                                                                        |       Definition                                                                                                                                                                                      |       Value
--------------                                                          |--------------                                                                                                                                                                                 |--------------
Edge Noise Persistence                                          |Persistence for edge noise texture.                                                                                                                                    |0.0 to 1.0
Edge Noise Frequency                                            |Frequency of edge noise.                                                                                                                                                               |Powers of 2 between 1 and 16
Edge Noise Texture Size                                         |Size of edge noise texture.                                                                                                                                                    |Powers of 2 between 4 and 64
Edge Noise Wavelength                                           |Wavelength of the edge noise. (Great for hiding Grid Patterns)                                                                                 |0.1 to 100
Cell Noise Wavelength                                           |Wavelength of Cell Noise                                                                                                                                                               |0.1 to 100
Cell Noise Texture Size                                         |Size of cell noise texture.                                                                                                                                                    |Powers of 2 from 16 to 256
Max Fractal Amplitude                                           |Strength of edge noise effect.                                                                                                                                                 |0.1 to 10

<hr>
