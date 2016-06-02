---
title: Clouds
layout: unreal
weight : 4
---

Clouds in trueSKY
========

In trueSKY, clouds are split into two layers: 3D clouds and 2D clouds. They have similar properties, with the exception of precipitation, which is strictly for 3D clouds. These properties can be modified via the sequencer and via Blueprint visual scripting.

Each layer has its own properties and its own keyframes. Layer properties will affect the entire sequence. Keyframe properties will only affect the keyframe in question, unless there is only one keyframe present, in which case this will be used continously. Otherwise the clouds will use interpolation to move between specified properties at adjacent keyframes. 

Read more about how clouds are rendered in trueSKY [here](http://docs.simul.co/reference/classsimul_1_1clouds_1_1BaseCloudRenderer.html).


Editing Clouds in the Sequencer
-------------------------------
To select a cloud keyframe, click it. To select all the keyframes of a cloud layer, double-click on the space between them. To select and modify the properties of a whole cloud layer, click on the "Clouds" text at left.

<a href="http://docs.simul.co/unrealengine/images/CloudSeqExample.png"><img src="http://docs.simul.co/unrealengine/images/CloudSeqExample.png" alt="Cloud"/></a> 

Read more about editing the Cloud Layer or Cloud Keyframes on [The Sky Sequencer Page](http://docs.simul.co/reference/man_8_sequencer.html).


Editing Clouds in Blueprint
-------------------------

Though the primary means of manipulating the cloud layer is via the sequencer, there are a selection of accessible Get and Set variables provided. To use them, make a reference to the TrueSkySequenceActor and drag the output pin onto an empty space. Uncheck "Context Sensitive", and navigate to Class->TrueSkySequenceActor.

<a href="http://docs.simul.co/unrealengine/images/SetGetCloudLayer.png"><img src="http://docs.simul.co/unrealengine/images/SetGetCloudLayer.png" alt="Blueprint"/></a>

To get a cloud keyframe's properties, you will first need its Unique ID (Uid) to identify it. This can be entered manually (each keyframe's Uid is viewable and editable in the sequencer), but there are also Blueprint functions provided. These functions have a Layer Int parameter, which should be set to 1 for 3D Clouds or 2 for 2D Clouds. The functions are as follows:

**GetCloudKeyframebyIndex:** Returns a cloud keyframe's Uid, given a cloud layer and an index (this is zero-indexed; the first cloud keyframe in a sequence is 0, the second is 1 and so on).

**GetPreviousCloudKeyframeBeforeTime:** Given a cloud layer and a time, returns the Uid of the last cloud keyframe before said time.

**GetNextCloudKeyframeAfterTime:** Given a cloud layer and a time, returns the Uid of the next cloud keyframe after said time.

**GetNextModifiableCloudKeyframe:** Given a cloud layer, returns the Uid of the next cloud keyframe that can be modified without requiring any recalculation (this will be the next cloud keyframe + 1).

**GetInterpolatedCloudKeyframe:** Returns the current interpolated cloud keyframe's Uid (Note: this cannot be used to set any values; it is read-only).


Once you have a cloud keyframe's Uid, you can Get and Set its properties. These functions have a Name parameter, which must be set to the matching string for the property required (see the table below). The functions are as follows:

**GetKeyFrameFloat:** Given a keyframe Uid and a name string, returns the float value matching the name.

**GetKeyframeInt:** Given a keyframe Uid and a name string, returns the integer value matching the name.

**SetKeyframeFloat:** Given a keyframe Uid, a name string and a float value, will set the matching property for the Name to the specified float value.

**SetKeyframeInt:** Given a keyframe Uid, a name string and an integer value, will set the matching property for the Name to the specified integer value.

<a href="http://docs.simul.co/unrealengine/images/CloudBPGetSet.png"><img src="http://docs.simul.co/unrealengine/images/CloudBPGetSet.png" alt="Blueprint"/></a>


Editable Keyframe Properties
-------------------------

The tables below show the various cloud keyframe properties, for floating point and integer values respectively. The entry in the "Name" field is what should be used in the Name string parameter in any Blueprint calls to GetKeyframeFloat, GetKeyframeInt, SetKeyframeFloat and SetKeyframeInt.


**Floating-point**


Name						| 			Definition
-------------------------- | -------------------------------------------------------------
cloudiness					|  Density of the cloud layer at this time.
distributionBaseLayer		|  Start of the transition from the cloud base to the upper cloud (0 to 1)
distributionTransition		|  Transition from the cloud base to the upper cloud (0 to 1)
upperDensity				|  Proportion of cloud density retained in the upper layer, above the distribution_transition.
localDensity				|  Local, small-scale density of clouds for 2D cloud layer.
windSpeed					| Wind speed in m/s
windDirection				| Wind direction
persistence					| Fractal persistence for generating the clouds, default 0.45.
cloudBase					| Base altitude of this cloud layer.
cloudHeight					| Height of the cloud layer, above its base altitude.
cloudWidth					| Width of the cloud layer in km, or the repeat-length.
directLight					| Amount of direct light to be used for rendering.
lightAsymmetry			| Amount of indirect or secondary light to be used for rendering.
indirectLight			| Amount of ambient light to be used for rendering.
ambientLight			| Anisotropic distribution of direct lighting, or eccentricity.
fractalWavelength		| Strength of the fractal edge effect, default 1.8.
fractalAmplitude		| Wavelength of the fractal edge effect longer wavelengths produce smoother clouds, default 140.
edgeSharpness			| Sharpness to be applied in rendering a the boundary.
churn				| Strength of the cloud edge churning effect larger values for more turbulent clouds.
extinction			| The amount of light scattered per metre larger values produce darker clouds, default 0.05.
precipitation			| The amount of rain/snow etc.
rainToSnow			| If zero, precipitation is interpreted as rain. If one, it is snow.
precipitationWindEffect		| How much precipitation is affected by wind, from zero to one.
precipitationWaver		| How much precipitation wavers, from zero to one.
diffusivity			| How much the edges of clouds should be diffused.
lightning			| Amount of lightning at this time.
godrayStrength			| Strength (from 0 to 1) of the godrays effect.
baseNoiseFactor			| What proportion of noise is applied at the cloudbase, between 0 and 1.0.
offsetxkm			| The x offset of this keyframe overridden by wind.
offsetykm			| The y offset of this keyframe overridden by wind.
rainCentreXKm			| The centre of the rain region.
rainCentreYKm			| The centre of the rain region.
rainRadiusKm			| The radius of the rain region.  
rainEffectStrength		| The visual strength of the rain-streak effect when rendered.


**Integer**
	

Name				|			Definition
----------------------------|----------------------------------------------------------
	octaves			|The number of noise octaves used to generate the clouds; default is 3.
	regionalPrecipitation	|If 1, rain/snow only occurs within the specified region. If 0, it occurs everywhere for the keyframe.
	lockRainToClouds	|If 1, the region moves with the cloud wind motion, and centreKm represents an offset from this motion.
			


Next: <a href="/unrealengine/Sky">Sky</a>