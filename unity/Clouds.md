---
title: Clouds
layout: unity
weight : 4
---

Cloud Layers and Cloud Keyframes
========

To select a cloud keyframe, click it. To select all the keyframes of a cloud layer, double-click on the space between them. To select and modify the properties of a whole cloud layer, click on the "Clouds" text at left.

To find out if there is cloud at a given 3D position, use **trueSKY.GetCloudAtPosition**; for rain, use **trueSKY.GetPrecipitationAtPosition**.

3D Cloud properties can be set using ***trueSKY.SetCloudFloat*** and ***trueSKY.SetCloudFloat***. These are the properties that can be set:

**CloudWidth:**("CloudWidth","CloudWidthKm" or "CloudWidthMetres") Width of the clouds in km or metres (will default to km). 

**NoisePeriod:** Period in days of the fractal noise function.

**EdgeNoisePersistence:** Fractal persistence to use when generating the noise texture.

**CloudShadowRange:** Range of the cloud shadow texture in km.

For example:

	trueSky.SetCloudFloat("NoisePeriod", 2.0F);

Integer properties are set using ***trueSKY.SetCloudInt*** and ***trueSKY.SetCloudInt***. These are the properties that can be set:


**GridWidth:** Grid width - use powers of 2.

**GridHeight:** Grid height - use powers of 2.

**Use3DNoise:** Whether to use 3D noise textures for the edge effect.

**Wrap:** Whether to wrap clouds horizontally.

**NoiseResolution:** Size of the noise function - powers of 2.

**OverrideWind:** Whether to set wind speed and direction directly, or use the keyframe values.

**EdgeNoiseOctaves:** Number of fractal octaves for the edge noise effect.

**EdgeNoiseFrequency:** Frequency (power of 2) of the edge noise effect.
 
**EdgeNoiseTextureSize:** Texture size (power of 2) of the edge noise effect.
 
**ExplicitOffsets:** Whether to use explicit cloud offset positions ("offsetx", "offsety" in cloud keyframes).
 
**ShadowTextureSize:** Size of the cloud shadow texture.

**DefaultNumSlices:** Default number of volume cloud samples for rendering - typically 80-200.

**Visible:** Show or hide the clouds.

**Generation Properties**
--------
These are the editable properties - in brackets are given the properties as you would specify them when scripting with GetKeyframeValue and SetKeyframeValue.
Some cloud keyframe properties are used as per-keyframe values to generated the 3D or 2D cloud textures. These textures are then interpolated for rendering.

**Cloudiness:** ("cloudiness") How cloudy it will be at this keyframe.

**Distribution base:** ("distributionBaseLayer") Proportion of the volume vertically that forms the base of the clouds.

**Distribution transition:** ("distributionTransition") Proportion that transitions from the cloudbase to the upper layer.

**Upper density:** ("upperDensity") Density of the upper layer as a proportion of the base density.

**Octaves:** ("octaves" - int) How many fractal octaves to use.

**Persistence:** ("persistence") Fractal persistence.

**Extinction:** ("extinction") How much light is lost per metre through the clouds.

**Diffusivity:** ("diffusivity") How diffuse are the cloud edges.

The cloud shape can be controlled using the keyframe properties **distribution base**, **distribution transition** and **upper density**.

**Interpolated Properties**
---------------
Some are used as interpolated values per-frame when rendering, either to determine the geometry of the clouds:

**Wind_speed:** ("windSpeed") How fast, in m/s.

**Wind direction:** ("WindHeadingDegrees") Direction in compass degrees.

**Cloud base:** ("cloudBaseKm") Height of the cloudbase in km above sea level.

**Cloud height:** ("cloudHeightKm") Height of the clouds in km.

**Offset:**("offsetxKm","offsetyKm") If absolute positioning (see cloud layer property "ExplicitOffsets") is enabled, the offset in km.


**Visual Properties**
---------------

**localDensity:** ("localDensity") 2D clouds only - the thickness of the local cloud distribution.

**Direct light:** ("DirectLight") How much direct sunlight (moonlight) affects the clouds.

**Indirect light:** ("IndirectLight") How much indirectly scattered light is shown.

**Ambient light:** ("AmbientLight") How strongly the clouds reflect ambient light.

**Light asymmetry:** ("Asymmetry") How asymmetric is the direct light scattering.

**Fractal amplitude:** ("FractalAmplitude") Amplitude of the fractal edge effect.

**Fractal wavelength:** ("FractalWavelength") Wavelength of the fractal edge effect.

**Sharpness:** ("Sharpness") Sharpness of cloud edges.

**Churn:** ("Churn") How much cloud turbulence is shown.

**Base noise factor:** ("BaseFactor") How much the edge effect is shown at cloudbase.

**Effect Properties**
---------------

Other properties are used to inform different parts of the rendering system:

**Precipitation**: ("Precipitation") Strength of rain or snow.

**Rain to snow**: ("RainToSnow") Between zero (rain) and one (snow).

**precipitationWindEffect**:

**precipitationWaver**:

**Godray strength**: ("GodrayStrength") Brightness of crepuscular rays.

**rainEffectStrength**: ("")

**rain Centre:** ("RainCentreXKm","RainCentreYKm") Centre of the rain area, if rain is regional for this keyframe.

**rain Radius:** ("RainRadiusKm") Radius of the rain area, if rain is regional for this keyframe.
