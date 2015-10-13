---
title: Clouds
layout: unreal
---

Cloud Layers and Cloud Keyframes
========

Editing clouds in the Sequencer
-------------------------------
To select a cloud keyframe, click it. To select all the keyframes of a cloud layer, double-click on the space between them. To select and modify the properties of a whole cloud layer, click on the "Clouds" text at left.

Modifying clouds in Blueprint
-----------------------------

Cloud Keyframe Properties
-------------------------
**Floating-point**

Name						|			function
----------------------------|------------------------------------------------------------
cloudiness					| density of the cloud layer at this time.
distributionBaseLayer		| Start of the transition from the cloud base to the upper cloud (0 to 1)
distributionTransition		| transition from the cloud base to the upper cloud (0 to 1)
upperDensity				| proportion of cloud density retained in the upper layer, above the distribution_transition.
localDensity				| local, small-scale density of clouds for 2D cloud layer.
windSpeed					| wind speed in m/s
windDirection				| wind direction
persistence					| fractal persistence for generating the clouds, default 0.45.
cloudBase					| base altitude of this cloud layer.
cloudHeight					| height of the cloud layer, above its base altitude.
cloudWidth					| width of the cloud layer in km, or the repeat-length.
directLight					| amount of direct light to be used for rendering.
lightAsymmetry			| amount of indirect or secondary light to be used for rendering.
indirectLight			| amount of ambient light to be used for rendering.
ambientLight			| anisotropic distribution of direct lighting, or eccentricity.
fractalWavelength		| strength of the fractal edge effect, default 1.8.
fractalAmplitude		| wavelength of the fractal edge effect longer wavelengths produce smoother clouds, default 140.
edgeSharpness			| sharpness to be applied in rendering a the boundary.
churn				| strength of the cloud edge churning effect larger values for more turbulent clouds.
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
				| 
rainEffectStrength		| The visual strength of the rain-streak effect when rendered.


**Integer**
	

Name				|			function
----------------------------|----------------------------------------------------------
	octaves			|The number of noise octaves used to generate the clouds; default is 3.
	regionalPrecipitation	|If 1, rain/snow only occurs within the specified region. If 0, it occurs everywhere for the keyframe.
	lockRainToClouds	|If 1, the region moves with the cloud wind motion, and centreKm represents an offset from this motion.
			


Next: <a href="/unrealengine/Sky">Sky</a>