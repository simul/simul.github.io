---
title: Water Probes
layout: reference
weight: 40
---





Water Probes
====================

Water probes are a component which can be added to objects. Their primary use is to allow for buoyancy functionality in conjunction with trueWATER - which can be found documented [here](buoyancy). However the probes have further functionality and use cases which may be useful within projects.

Attaching a probe to a object is as simple as adding a trueSKY Water Buoyancy component to your object, and then adding a trueSKY Water probe onto the buoyancy component.

Once a probe has been attached to an object it will by default be set to a "physics" probe type. This probe type allows for [buoyancy](buoyancy) to be enabled. However, there are multiple other probe types that can be used.


<b> Physics </b> This is the default probe type, and allows for buoyancy to be used. Setup for this can be found [here](buoyancy)

<b> Source </b> This probe type allows for interation with the water grid within trueWATER - essentially allowing generation of waves without requiring to add additional physics probes and thus affect the overall buoyancy of the object.

<b> Depth Test </b> These probes allow for accurately measuring the depth at which the probe is located. This can be used in blueprints by referencing the depth probe and using the node "get depth". 
