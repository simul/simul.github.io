---
title: Sky
layout: unreal
weight : 5
---

The Sky in trueSKY
========

In trueSKY, the sky is modified in two ways: through sky keyframes and the sky layer. Keyframe properties will dictate the look of the sky at a given point in time -- with interpolation used to derive properties at times between keyframes -- whereas layer properties will be active throughout a sequence. Both can be modified via the sequencer or through the Blueprint system.

Read more about how the sky is rendered in trueSKY [here](http://docs.simul.co/reference/classsimul_1_1sky_1_1BaseSkyRenderer.html).


Editing The Sky in the Sequencer
-------------------------

To select a sky keyframe, click it. To select all the keyframes of the sky layer, double-click on the space between them. To select and modify the properties of whole sky layer, click on the "Sky" text at left.

<a href="http://docs.simul.co/unrealengine/images/SkySeqExample.png"><img src="http://docs.simul.co/unrealengine/images/SkySeqExample.png" alt="Sky"/></a> 

Read more about editing the Sky Layer or Sky Keyframes on [The Sky Sequencer Page](http://docs.simul.co/reference/man_8_sequencer.html).


Editing The Sky in Blueprint
-------------------------

To get a sky keyframe’s properties, you will first need its Unique ID (Uid) to identify it. This can be entered manually (each keyframe’s Uid is viewable and editable in the sequencer), but there are also Blueprint functions provided. The functions are as follows:

**GetSkyKeyframebyIndex:** Returns a sky keyframe’s Uid, given an index (this is zero-indexed; the first sky keyframe in a sequence is 0, the second is 1 and so on).

**GetPreviousSkyKeyframeBeforeTime:** Given a time, returns the Uid of the last sky keyframe before said time.

**GetNextSkyKeyframeAfterTime:** Given a time, returns the Uid of the next sky keyframe after said time.

**GetNextModifiableSkyKeyframe:** Returns the Uid of the next sky keyframe that can be modified without requiring any recalculation (this will be the next sky keyframe + 1).

**GetInterpolatedSkyKeyframe:** Returns the current interpolated sky keyframe’s Uid (Note: this cannot be used to set any values; it is read-only).


Once you have a sky keyframe’s Uid, you can Get and Set its properties. These functions have a Name parameter, which must be set to the matching string for the property required (see the table below). The functions are as follows:

**GetKeyFrameFloat:** Given a keyframe Uid and a name string, returns the float value matching the name.

**GetKeyframeInt:** Given a keyframe Uid and a name string, returns the integer value matching the name.

**SetKeyframeFloat:** Given a keyframe Uid, a name string and a float value, will set the matching property for the Name to the specified float value.

**SetKeyframeInt:** Given a keyframe Uid, a name string and an integer value, will set the matching property for the Name to the specified integer value.

<a href="http://docs.simul.co/unrealengine/images/SkyBPGetSet.png"><img src="http://docs.simul.co/unrealengine/images/SkyBPGetSet.png" alt="Blueprint"/></a>


Editable Keyframe Properties
-------------------------

The tables below show the various sky keyframe properties, for floating point and integer values respectively. The entry in the "Name" field is what should be used in the Name string parameter in any Blueprint calls to GetKeyframeFloat, GetKeyframeInt, SetKeyframeFloat and SetKeyframeInt. 

**A Note about Haze/Fog/Mist:** A keyframe's haze value determines how much Mie-scattered haze (i.e. mist or fog) is present. Haze is considered to have a density that falls-off exponentially with altitude, so the Haze scale height property determines the scaling height for this exponential. Fog and mist are both effectively low-level clouds. Fog is defined as having visibility less than 1 km, it is called mist when visibility is between 1 and 2 km.


**Floating-point**


Name						| 			Definition
-------------------------- | -------------------------------------------------------------
daytime  			| 	The float time this keyframe represents. If the sky layer's "Link Keyframe Time and Daytime" value is true, this equals the keyframe's time value. Otherwise, it can be modified freely.
haze					|  The amount of haze, mist or fog.
HazeBaseKm 		|The base altitude, above which haze starts to decrease in density.
HazeScaleKm | The vertical scale over which haze reduces with altitude.
HazeEccentricity|The anisotropy of Mie scattering.
SunElevation| How high the sun is in the sky.
MoonElevation| How high the moon is in the sky. 
SunAzimuth| The horizontal angle of the sun.
MoonAzimuth| The horizontal angle of the moon.
MieRed, MieGreen, MieBlue| The Mie scattering coefficients (x=red,y=green,z=blue). 
SeaLevelTemperatureK| Used for infrared rendering.


**Integer**
	

Name				|			Definition
----------------------------|----------------------------------------------------------
StoreAsColours| If non-zero, atmospheric table textures will be calculated using altitudes, elevations and distances, to generate custom colours.
AutoMie| If non-zero, mie scattering coefficients will be calculated based on wavelength and haze (overrides Mie). 
numColourAltitudes| Number of altitudes for use in custom atmospheric table texture.
numColourElevations| Number of elevations for use in custom atmospheric table texture. 
numColourDistances| Number of distances for use in custom atmospheric table texture.
AutomaticSunPosition| If non-zero, automatic sun positioning will be enabled.
AutomaticMoonPosition| If non-zero, automatic moon positioning will be enabled.


			
Next: <a href="/unrealengine/Deploy">Deployment</a>