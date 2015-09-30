---
title: Sky
layout: unity
---


Sky and Atmospherics
=======

To select a sky keyframe, click on it in the timeline; to select the overall sky properties, click "Sky" on the left of the timeline.

Sky properties can be set using ***trueSKY.SetSkyFloat*** and ***trueSKY.GetSkyFloat***. These are the properties that can be set:

**LatitudeRadians:** Latitude, in radians.

**LongitudeRadians:** Latitude, in radians.
	
**MaxStarMagnitude:** Maximum magnitude of star to be visible from the Bright Star Catalogue of 9110 stars. Star magnitude is between 0 (brightest) and 9 (dimmest).
	
**StarBrightness:** A multiplier for star brightness.
	
**BackgroundBrightness:** A multiplier for the brightness of the cosmic background texture.
	
**MaxDistanceKm:** Largest distance to use for generating atmospherics tables.
	
**MaxAltitudeKm:** Largest altitude to use for generating atmospherics tables.
	
**OvercastEffectStrength:** From 0 to 1, the amount that atmospheric inscatter is dimmed when the clouds are overcast.
	
**TimezoneHours:** A floating-point value - positive values are GMT+ (Eastern Hemisphere), negative are GMT- (Western).
	
**SunRadiusArcMinutes:** Size of the sun to render.
	
**MoonRadiusArcMinutes:** Size of the moon to render.

For example:

	trueSky.SetSkyFloat("StarBrightness", 10000.0F);

There are also integer properties - use ***trueSKY.SetSkyInt*** and ***trueSKY.GetSkyInt***:


**StartDayNumber:** Day number (Epoch 2000)

**NumAltitudes:**  Number of altitudes in atmospheric table textures.

**NumElevations:** Number of elevations in atmospheric table textures. 

**NumDistances:** Number of distances in atmospheric table textures.


Properties of a Sky Keyframe
-------------------------

These are the editable properties - in brackets are given the properties as you would specify them when scripting with GetKeyframeValue and SetKeyframeValue.

Get the last keyframe in the sequence:

	int numk=trueSky.GetNumSkyKeyframes()
	uint uid=GetSkyKeyframeByIndex(numk-1);

Add a keyframe at midday:

	uint uid=InsertSkyKeyframe(0.5F);

Get or set the haze:

	SetKeyframeValue(uid,"Haze",12.0F)
	float h=GetKeyframeValue(uid,"Haze");

Destroy a keyframe:

	DeleteKeyframe(uid);


**Time:** ("time") The time of this keyframe on the timeline.

**Daytime:** ("daytime") The time this keyframe represents, in a floating-point number of days from the starting midnight of the sequence. If the sky layer's "Link Keyframe Time and Daytime" value is true, this is the same as the keyframe's time value. Otherwise, it can be modified freely.

**Mie:** ("MieRed","MieGreen","MieBlue") The Mie scattering coefficients (x=red,y=green,z=blue).

**Auto Mie:** ("AutoMie") The Mie scattering coefficients will be calculated based on wavelength and haze if this is set - overrides Mie.

**Haze:** ("Haze") The amount of haze, mist or fog.

**Haze Base:** ("HazeBaseKm") The base altitude, above which haze starts to decrease in density.

**Haze Scale :** ("HazeScaleKm") The vertical scale over which haze reduces with altitude.

**Eccentricity:** ("Eccentricity") The anisotropy of Mie scattering.

A keyframe's haze value determines how much Mie-scattered haze (i.e. mist or fog) is present. Haze is considered to have a density that falls-off exponentially with altitude, so the Haze scale height property determines the scaling height for this exponential.

Fog and mist are both effectively low-level clouds. Fog is defined as having visibility less than 1km, it is called mist when visibility is between 1 and 2 km.



