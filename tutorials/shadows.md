---
title: Shadows
layout: reference
weight: 80
---






Shadows 
============
Shadows are a vital part of making an environment feel 'alive', and trueSKY supports realtime shadows on all clouds, based on the position of the sun/moon.

<hr>

![](/Images/shadows.png)


<hr>

{:.ue4-specific}
In unreal, shadows should automatically be set up. If not, make sure that the CloudShadowRT is connected to trueSKYObject under shadows, and your directional light is using trueSKY's M_lightFunction.



Cloud Shadows
-----------------

{:.object}
Variable                                                                        |       Definition                                                                                                                                                                              |       Value
--------------                                                          |--------------                                                                                                                                                                         |--------------
Shadow Range                                                            |Range of cloud shadow texture, in km.                                                                                                                          |0.5 to 200.0.
Shadow Texture Size                                                     |Size of cloud shadow texture.                                                                                                                                          |Powers of 2 between 32 and 2048.
Shadow Strength                                                         |Amount of shadow produced. Large values can produce obvious edges if the resolution is too low.        |0.0 to 1.0
Cloud Shadow RT                                                         |Render texture that is used to draw cloud shadow texture at runtime                                                            |Render Texture


God Rayss
-------------

{:.object}
Variable                                                                        |       Definition                                              |       Value
--------------                                                          |--------------                                         |--------------
Crepuscular Ray (God-Rays) Strength                     |Strength of god-ray effect.            | 0.0 to 1.0. 
Crepuscular Grid                                                        |Grid size for God-rays. X, Y, Z.       | 8 to 256.

