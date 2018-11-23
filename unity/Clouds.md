---
title: Clouds
layout: unity
weight : 4
---

Clouds in trueSKY
========

In trueSKY, clouds are split into two layers: 3D clouds and 2D clouds. They have similar properties, with the exception of precipitation, which is strictly for 3D clouds. These properties can be modified via the sequencer and/or through Unity scripting.

Each layer has its own properties and its own keyframes. Layer properties will affect the entire sequence. Keyframe properties will only affect the keyframe in question, unless there is only one keyframe present, in which case this will be used continously. Otherwise the clouds will use interpolation to move between specified properties at adjacent keyframes.

Read more about how clouds are rendered in trueSKY [here](/ref/simul/clouds/basecloudrenderer).


Editing Clouds in the Sequencer
----------------

To select a cloud keyframe, click it. To select all the keyframes of a cloud layer, double-click on the space between them. To select and modify the properties of a whole cloud layer, click on the “Clouds” text at left.

<a href="https://docs.simul.co/unity/images/CloudSeqExample.png"><img src="https://docs.simul.co/unity/images/CloudSeqExample.png" alt="Clouds"/></a> 

Read more about editing the Cloud Layer or Cloud Keyframes on [The Sky Sequencer Page](https://docs.simul.co/sequencer.html).



Editing Clouds Via Scripting: The Cloud Layer
---------------
 
To Get and Set 3D cloud layer properties, use **trueSKY.GetCloudFloat**, **trueSKY.GetCloudInt**, **trueSKY.SetCloudFloat** and **trueSKY.SetCloudInt**. For 2D cloud layer properties, use **trueSKY.Get2DCloudFloat**, **trueSKY.Get2DCloudInt**, **trueSKY.Set2DCloudFloat** and **trueSKY.Set2DCloudInt**. For more on how to use these functions, along with information about other helpful functions (such as cloud queries) see [Scripting](https://docs.simul.co/unity/scripting.html). 

The tables below show the various cloud layer properties (named as they appear in the sequencer), along with the matching name string to use for scripting. The following (precipitation) properties are exclusive to the 3D cloud layer: Max Particles, Threshold, Radius, Rain Speed and Raindrop Size. **Note**: Parameters that are Bools in the Sequencer are treated as Ints in scripting, where 0 = false and 1 = true.


**Floating-point**

Sequencer Property | Name Variable | Definition
-------------------|---------------|---------
Threshold |"precipitationThresholdKm"| Thickness of cloud needed for rainfall. Between 0.0 and 10.0.
Radius | "precipitationRadiusMetres"| Size of particle zone. Between 0.0 and 100.0.
Rain Speed| "rainFallSpeedMS"| Between 0.0 and 120.0.
Raindrop Size|"rainDropSizeMm"| Between 0.001 and 100.0.
Shadow|"cloudShadowStrength" | Amount of shadow. Between 0.0 and 1.0.
Shadow Range|"cloudShadowRange"| Range of cloud shadow texture, in km. Between 0.5 and 200.0.
Max cloud dist|"maxCloudDistanceKm"| Distance of furthest cloud layer. Between 100.0 and 500.0.
Noise Period | "noisePeriod" | Fractal noise period, in days. Between 0.001 and 1000.0.
Persistence |"edgeNoisePersistence"| Persistence for edge noise texture. Between 0.0 and 1.0.


**Integer**

Sequencer Property| Name Variable | Definition
------------------|---------------|------------
Enabled|"Visible"|Whether or not GPU should calculate clouds. Bool.
Wrap Horizontally|"wrap"| Whether to wrap clouds horizontally. Bool.
Override Wind| "overrideWind"| Whether to override keyframe wind speed. Bool.
Render Mode|"renderMode"| How renderer should raytrace clouds. Standard = 0, Simplified = 1.
Max Particles|"maxPrecipitationParticles"| The max number of rain particles to render. Between 0 and 1000000
Default Slices|"defaultNumSlices"| Number of slices in main view. Between 80 and 255.
Shadow Texture Size|"shadowTextureSize"| Size of cloud shadow texture. Powers of 2 between 16 and 256.
Grid Width|"gridWidth"| Width of grid (determines cloud detail). Powers of 2 between 16 and 512.
Grid height|"gridHeight"| Height of grid (determines cloud detail). Powers of 2 between 1 and 64.
Noise Resolution|"noiseResolution"| 3D Perlin noise resolution, for cloud generation. Powers of 2 between 4 and 64.
Frequency|"edgeNoiseFrequency"| Frequency of edge noise. Powers of 2 between 1 and 16.
Resolution|"edgeNoiseResolution"| Resolution of edge noise texture. Powers of 2 between 4 and 64.

   
**Example:** To increment the 3D cloud layer Rain Fall Speed by 5:

	private trueSKY tS;  
 
	void Start () 
	{
		tS = trueSKY.GetTrueSky();
		tS.SetCloudFloat("rainFallSpeedMS", tS.GetCloudFloat("rainFallSpeedMS") + 5.0F);
	} 



Editing Clouds Via Scripting: Cloud Keyframes
---------------  

Keyframe properties for clouds generally fall into four categories:
 
* **Generation**: These properties are used as per-keyframe values to generate the cloud textures. These textures are then interpolated for rendering. The following are generation properties: *Cloudiness*, *Distribution Base*, *Distribution Transition*, *Upper Density*, *Octaves*, *Persistence*, *Extinction* and *Diffusivity*. The shape of the clouds can be controlled using the distribution base, distribution transition and upper density.
* **Interpolated**: When rendering, these properties are used as per-frame, interpolated values, and can be used to determine the geometry of the clouds. The following are interpolated properties: *Wind Speed*, *Wind Direction*, *Cloud Base*, *Cloud Height* and *Offset* (X and Y). 
* **Visual**: These properties fine tune the appearance of trueSKY. The following are visual properties: *Local Density*, *Direct light*, *Indirect light*, *Ambient light*, *Light Asymmetry*, *Fractal Amplitude*, *Fractal Wavelength*, *Sharpness*, *Churn* and *Base noise factor*.
* **Effect**: These properties are used to inform different parts of the rendering system, and generate various environmental and weather effects. The following are effect properties: *Precipitation*, *Rain - Snow*, *precipitationWindEffect*, *precipitationWaver*, *Godray strength*, *rainEffectStrength*, *Rain Radius* and *Rain Centre* (X and Y).


To Get/Set cloud keyframe properties, use **trueSKY.GetKeyframeValue** and **trueSKY.SetKeyframeValue**, ensuring the pass the keyframe's Uid as an argument. For information on what functions to use to get keyframe Uids, along with information about other helpful functions, see [Scripting](https://docs.simul.co/unity/scripting.html). The tables below show the various cloud keyframe properties (named as they appear in the sequencer), along with the matching name string to use for scripting. **Note**: Parameters that are Bools in the Sequencer are treated as Ints in scripting, where 0 = false and 1 = true.


**Floating-point**

Sequencer Property|Name Variable|Definition
------------------|-------------|-------
Cloudiness| "cloudiness"| How much cloud in the cloud layer. Between 0.0 and 1.0.
Cloudbase|"cloudBase"| Base altitude of cloud layer. Between -1.0 and 20.0.
Layer Height|"cloudHeight"| Height of cloud layer, in km. Between 0.1 and 25.0.
Volume Width | cloudWidthKm", "cloudWidthMetres"| Width of cloud layer, in km or Metres (depending on name string). Between 20.0 km and 200.0 km.
Wind Speed |"windSpeed"| Wind speed in m/s. Between 0.0 and 1000.0.
Wind Heading|windHeadingDegrees"| Horizontal cloud movement direction, in degrees. Between 0 and 360.0.
Base Layer |"distributionBaseLayer"| Start of transition from cloudbase to upper cloud. Between 0.0 and 1.0.
Transition|"distributionTransition"| Transition from cloudbase to upper cloud. Between 0.0 and 1.0.
Upper Density|"upperDensity"| Proportion of cloud density retained in upper layer, above transition. Between 0.0 and 1.0.
Persistence|"persistence"| Fractal persistence for generating clouds. Between 0.0 and 1.0.
Worley Noise|"WorleyNoise"| How much Worley noise to apply. Between 0.0 and 1.0.
Worley Scale|"WorleyScale"| Scale of Worley noise. Between 0.0 and 12.0 (locked to Int if clouds wrapped).
Diffusivity| "diffusivity"| How much cloud edges should be diffused. Between 0.0 and 1.0.
Direct Light| "directLight"| Amount of direct light. Between 0.0 and 4.0.
Asymmetry|"lightAsymmetry" | Anisotropic distribution of direct lighting, or eccentricity. Between 0.0 and 1.0.
Indirect Light|"indirectLight"| Amount of indirect light. Between 0.0 and 4.0.
Ambient Light|"ambientLight"| Amount of ambient light. Between 0.0 and 4.0.
Extinction| "extinction"| Amount of light scattered per metre (larger values = darker clouds). Between 0.0001 and 10.0.
Godrays|"godrayStrength"| Strength of godray effect. Between 0.0 and 1.0.
Scale| "fractalWavelength"| Wavelength of fractal edge effect. Between 1.0 and 1000.0.
Amplitude | "fractalAmplitude"| Strength of fractal edge effect. Between 0.01 and 100.0.
Worley Scale | "EdgeWorleyScale" |  Wavelength of fractal Worley noise. Between 0.1 and 10000.0.
Worley Ampltitude |"EdgeWorleyNoise"| Strength of fractal Worley noise. Between 0.0 and 1.0.
Sharpness| "edgeSharpness"| Sharpness applied at boundary. Between 0.0 and 1.0.
Base Factor| "baseNoiseFactor"| Proportion of noise applied at cloudbase. Between 0.0 and 1.0.
Churn |"churn"| Strength of cloud edge churning effect (larger values = more turbulent clouds). Between 0.001 and 1000.0.
Radius (km)|"rainRadiusKm"| Radius of precipitation region. Between 0.1 and 1000.0.
Strength|"precipitation"  | Amount of rain/snow. Between 0.0 and 1.0.
Rain Streaks|"rainEffectStrength"| Visual strength of rain streak effect. Between 0.0 and 1.0.
Rain - Snow|"rainToSnow"| Between 0.0 and 1.0 (0 = rain, 1 = snow, values in between are rounded).
Wind Effect|"precipitationWindEffect"| How much precipitation is affected by wind. Between 0.0 and 1.0.
Waver|"precipitationWaver"| How much precipitation wavers. Between 0.0 and 1.0.
Offset (Map)|"offsetx", "offsety"| Offset of keyframe due to accumulation of wind motion.
Precipitation Centre (Map)| "rainCentreXKm""rainCentreYKm"| Centre of precipitation region.

  
 
**Integer**

Sequencer Property|Name Variable|Definition
------------------|-------------|---------
Octaves| "octaves"| Number of noise octaves to generate clouds. Between 1 and 5.
Regional| "regionalPrecipitation" | Whether rain/snow falls only in specified region, or globally. Bool.
Lock to Cloud| "lockRainToClouds" | Whether to make precipitation region move with wind motion. Bool


**Example**: To get the cloudiness value of the current, interpolated 3D cloud keyframe:

	private trueSKY tS;   

	void Start () 
	{
		tS = trueSKY.GetTrueSky();
		uint uid = tS.GetInterpolatedCloudKeyframe (1);
		tS.GetKeyframeValue (uid, "cloudiness"); 
	}




Further Information
--------------
 
* [The Sequencer](https://docs.simul.co/sequencer.html)  
* [Scripting in trueSKY for Unity](https://docs.simul.co/unity/scripting.html)
* [Cloud Rendering in trueSKY](/ref/simul/clouds/basecloudrenderer)
* [Watch a video tutorial](https://www.youtube.com/watch?v=Eljf5CjZ4vc)



Next: <a href="/unity/Sky">Sky</a>