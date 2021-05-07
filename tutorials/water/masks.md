---
title: Water Masks
layout: reference
weight: 95
---





Water Masks
====================

Water masks are applied across any water object within your scene (both bounded and boundless). 


How to set up water masks
----------------------


<div class="ue4-specific">

Select the object you wish to have the water mask attached to.

Within the objects component section, click on the "add component" drop down search for trueSKYWaterMask.

![](/images/unreal/watermaskaddcomponent.png)


Selecting the TrueSKY Water Mask component from the objects stack will show the settings available.



Variables:
----------------------

{:.object}
Variable                                                                                |       Definition                                                                                                                                                                                              |       Value
--------------                                                                  |--------------                                                                                                                                                                                         |--------------
Active                                                                                  |Turns the masking on or off                                                                                                                                                            |Bool
Total Mask                                                                              |Determines if the masking will be just for the surface of the water or for masking in all directions.          |Bool
Object type                                                                             |Decides if you wish for a cube shaped mask, a plane or a custom shaped mask mesh                                                       |Dropdown               
Custom mesh                                                                             |Place to input your static mesh to be used with custom mask                                                                                            |Mesh File
Box Extent                                                                              |Adjusts the size of the mask area dependent on the bounding boxes size                                                                         |Vector 3


</div>

<div class="unity-specific">

Documentation coming soon

</div>
