---
title: Precipitation
layout: reference
weight: 50
---






Precipitation
====================
Precipitation can be attached to any cloud keyframe and it will produce precipitation based on cloud position and thickness (if desired).

* [**Tutorial**](tutorials.html)                                                                - Learn how to create a rain and snow in your scene.

* [**Variables**](variables.html)                                                       - Details of all the different variables for precipitation. 

* [**How it works**](works.html)                                                        - Learn more about how we create precipitation in trueSKY!


<hr>

No Precipitation?
-----------------
Check you are editing the correct keyframe on the currently active sequence. In order see your edits as you procede, ensure the time is correctly set in the timeline and that the simulation is running.

Ensure there are enough cloud above the viewer to produce precipitation. If there's no clouds, no precipitation can occur.

{:.ue4-specific}
Double check you have trueSKY Translucent as a [Post Process.](/faq.html#postprocess) 


<div class="ue4-specific">

Precipitation under cover?
--------------------------

* To prevent precipitation from falling in covered areas, create a SceneCapture2D actor and give it a texture target that contains only a red channel; e.g. RainDepthRT from the trueSKY content. Make the Capture Source "SceneDepth in R". You don't need to enable "Capture Every Frame" unless you expect the geometry to change.

![](/images/unreal/scenecapture2dProperties.png)


* Rotate the SceneCapture2D actor to face downwards.

* On the trueSKY Sequence Actor, assign the SceneCapture2D actor to the Rain Mask SceneCapture property. Now precipitation will only appear where there is no cover above the SceneCapture actor.

![](/images/unreal/precipitationProperties.png)


</div>
