---
title: Buoyancy
layout: reference
weight: 50
---






Buoyancy
====================

To add buoyancy to objects within UE4 you will be required to make the object a physics object, attach a buoyancy component, and then attach buoyancy probes to the buoyancy component. The size of these probes determines how much buoyancy they supply, and weight of the mesh can be altered within the root object itself, within the physics tab.


When settings up buoyancy probes, you should have enough water probes positioned in such a way that they roughly cover the volume that the ships take up. Keep a close eye on the center of mass, as well as the overall mass of the object.

For Example, this ship has 4 probes:


![](/images/buoyancy.png)



To be affected correctly by the waves, make sure to tick Enable Wave Grid on the Water Object.

For a more in depth example this youtube video covers basic buoyancy setups, along with more advanced set up for larger and more complex objects as well as good practices to ensure your objects are stable when used with trueWater. 

<div class="video-wrapper">
<div class="video-container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/xBkgS5WMU64" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
</div>
