---
title: Moons
layout: reference
weight: 40
---





Moons
====
<div class="ue4-specific">

Multiple Moon support (4.2a)
----------------------------------------

With the 4.2a update we have added an extensive additional moon controls, as well as adding the ability to support multiple moons.



Setting up a Moon
----------------------------------------

Upon initialization your scene will include a Moon. This oon will have the settings to reflect Earth's moon. As such is a good reference point for many projects, as well as a good starting point when attempting to achieve realistic results for satellites around a planet.


The controls for the new moon system are now found on the trueSKYSequenceActor (within unreal), under the "Moons" subheading, You can create and delete moons via the "array elements" setting.

By default you will have a moon array element created within the sequence actor. As mentioned above, this will by default be simulating Earth's moon, and as such the settings are accurate to those of our own moon.

At the bottom of the page we have a image of the orbital model we are using, which may be useful to reference in order to understand how some of these settings function. All of our settings can be edited via blueprints by getting a reference of the array of moons stored in the trueSkySequenceActor.



Each of the settings functions as follows:
----------------------------------------


<b> Use Presets -</b> This check box allows you to use one of the preset moon templates we have made. Checking this will cause all your currently setting to be overridden by the preset, so ensure to take care before pressing it.

<b> Moon Preset -</b> This drop down only becomes available for use when the above "use presets" setting is checked, and changes all of the settings within the moon array element to a series of preassigned values. Helpful to revert settings back to default.

<b> Name -</b> This allows for assigning a name for each moon within the scene. Names are important to help you differentiate between moons. This is also used within some of the trueSKY functionality, and as such users should ensure not to name moons the same thing as this may cause conflicts and undesired results. We have blueprints to get a moon by name.

<b> Texture - </b> This allows for assigning of a 2d texture to represent the moon it is assigned to. It follows the same setup as the legacy iteration of moon texture implementation. This means that the texture will show accurate moon phases Dependant on the date and positioning in relation to the sun.

<b> Colour - </b> The colour will affect not only the texture of the moon, but the light that is reflected off of it. A blend of colours of all the moons currently above the horizon will be applied to the directional light. 

<b> Longitude of Ascending Node - </b> This determines the points in which the moon crosses the plane of the equator (due to the moon having a tilted orbit around the earth). Put in slightly simpler terms, this determines the "x" axis is located for the tilted orbit, from the equator. This is referenced in the diagram below for a more visual representation.

<b> Longitude of Ascending Node Rate - </b> The amount the ascending node increases each day (the angle is different at different times of the year, and how much it changes per day will be determined via this setting)

<b> Inclination - </b> This controls the tilt angle of the orbit. 0 will represent the moon rotating directly around the Earth's equator, adding values to this will alter the angle of the orbital plane.

<b> Argument of Pericentre - </b> This is the closest point of that the moon is to the Earth's surface. The moons orbit is naturally an ellipses and not a perfect circle. So changing this changes the location in which the two planetary bodies are at their closest.

<b> Argument of Pericentre Rate - </b> This refers to how much the argument of the pericentre changes per day.

<b> Mean Distance - </b> The mean (average) distance the moon is from the center of the moon.

<b> Eccentricity - </b> This controls how elliptical the orbit of the moon will be around the earth. 0 will allow for a perfectly circular orbit, 0.5 will be a slight oval. 

<b> Mean Anomaly - </b> Controls the position that the moon will be around its orbit at midnight of each day.

<b> Mean Anomaly Rate - </b> This controls how much the mean anomaly changes each day, ie. how far around the orbit the moon will start from each day compared to the day before.

<b> Radius Arc Minutes - </b> Controls the apparent size of the moon when visualized from the surface of the earth. By default this is correct for the earth and its moon, increasing it can add more visibility as well as more dramatic results.



![](/images/MoonOrbitExplanation.png)

<sup>Image found from " https://en.wikipedia.org/wiki/Orbital_elements "</sup>




In addition these settings are all tied to the moons lighting and how it will affect the scene, so ensure to be careful when editing settings as these are using a physically correct model. So making the moon extremely large will in return cause the lighting from said moon to be a lot brighter compared to a realistically sized moon.


</div>

<div class="unity-specific">

The multi-moon system present within unreal engine is still in the process of being ported through to the unity engine. As such the legacy version of moon controls are still avalible and can be found [here](tutorials)

</div>
