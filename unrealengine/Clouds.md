---
title: Clouds
layout: unreal
weight : 4
---

Clouds in trueSKY
========

In trueSKY, clouds are split into two layers: 3D clouds and 2D clouds. They have similar properties, with the exception of those pertaining to precipitation, which are strictly for 3D clouds. These properties can be modified via the sequencer and via Blueprint visual scripting.

Each layer has its own properties and its own keyframes. Layer properties will affect the entire sequence. Keyframe properties will only affect the keyframe in question, unless there is only one keyframe present, in which case this will be used continously. Otherwise the clouds will use interpolation to move between specified properties at adjacent keyframes. 

Read more about how clouds are rendered in trueSKY [here](https://docs.simul.co/reference/classsimul_1_1clouds_1_1BaseCloudRenderer.html).


Editing Clouds in the Sequencer
-------------------------------

To select a cloud keyframe, click it. To select all the keyframes of a cloud layer, double-click on the space between them or box select them. To select and modify the properties of a whole cloud layer, click on the "Clouds" text at left.

<a href="https://docs.simul.co/unrealengine/images/CloudSeqExample.png"><img src="https://docs.simul.co/unrealengine/images/CloudSeqExample.png" alt="Cloud"/></a> 

Read more about editing the Cloud Layer or Cloud Keyframes on [The Sky Sequencer Page](https://docs.simul.co/reference/man_8_sequencer.html).


Editing Clouds in Blueprint: The Cloud Layer
-------------------------

To Get and Set 3D cloud layer properties, use the provided SetInt, GetInt, SetFloat and GetFloat functions. For more on how to use these, along with information about other helpful blueprint functions see [Blueprint](http://docs.simul.co/unrealengine/Blueprint.html). 

The tables below show the various cloud layer properties (named as they appear in the sequencer), The entries in the "Name" column are what should be used as the "Name" string parameter in any Blueprint calls to GetKeyframeFloat, GetKeyframeInt, SetKeyframeFloat and SetKeyframeInt. The Name strings should be prefixed with "clouds:" or "2dclouds:", depending on the layer in use. The following (precipitation) properties are exclusive to the 3D cloud layer: Max Particles, Threshold, Radius, Rain Speed and Raindrop Size. **Note**: Parameters that are Bools in the Sequencer are treated as Ints in scripting, where 0 = false and 1 = true.


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
Override Wind| "overrideWind"| Whether to apply realtime wind motion (as opposed to simulation time). Bool.
Render Mode|"renderMode"| How renderer should raytrace clouds. Standard = 0, Simplified = 1.
Max Particles|"maxPrecipitationParticles"| The max number of rain particles to render. Between 0 and 1000000
Default Slices|"defaultNumSlices"| Number of slices in main view. Between 80 and 255.
Shadow Texture Size|"shadowTextureSize"| Size of cloud shadow texture. Powers of 2 between 16 and 256.
Grid Width|"gridWidth"| Width of grid (determines cloud detail). Powers of 2 between 16 and 512.
Grid height|"gridHeight"| Height of grid (determines cloud detail). Powers of 2 between 1 and 64.
Noise Resolution|"noiseResolution"| 3D Perlin noise resolution, for cloud generation. Powers of 2 between 4 and 64.
Frequency|"edgeNoiseFrequency"| Frequency of edge noise. Powers of 2 between 1 and 16.
Resolution|"edgeNoiseResolution"| Resolution of edge noise texture. Powers of 2 between 4 and 64.


Editing Clouds in Blueprint: Cloud Keyframes
-------------------------

To get a cloud keyframe's properties, you will first need its Unique ID (Uid) to identify it. Uids can be retrieved using a variety of provided Blueprint functions. These functions have a Layer Int parameter, which should be set to 1 for 3D Clouds or 2 for 2D Clouds. The functions are as follows:

* **GetCloudKeyframebyIndex:** Returns a cloud keyframe's Uid, given a cloud layer and an index (this is zero-indexed; the first cloud keyframe in a sequence is 0, the second is 1 and so on).

* **GetPreviousCloudKeyframeBeforeTime:** Given a cloud layer and a time, returns the Uid of the last cloud keyframe before said time.

* **GetNextCloudKeyframeAfterTime:** Given a cloud layer and a time, returns the Uid of the next cloud keyframe after said time.

* **GetNextModifiableCloudKeyframe:** Given a cloud layer, returns the Uid of the next cloud keyframe that can be modified without requiring any recalculation (this will be the next cloud keyframe + 1).

* **GetInterpolatedCloudKeyframe:** Returns the current interpolated cloud keyframe's Uid (Note: this cannot be used to set any values; it is read-only).


Once you have a cloud keyframe's Uid, you can Get and Set its properties. These functions have a "Name" parameter, which must be set to the matching string for the property required (see the table below). The functions are as follows:

* **GetKeyFrameFloat:** Given a keyframe Uid and a name string, returns the float value matching the name.

* **GetKeyframeInt:** Given a keyframe Uid and a name string, returns the integer value matching the name.

* **SetKeyframeFloat:** Given a keyframe Uid, a name string and a float value, will set the matching property for the Name to the specified float value.

* **SetKeyframeInt:** Given a keyframe Uid, a name string and an integer value, will set the matching property for the Name to the specified integer value.

<a href="https://docs.simul.co/unrealengine/images/CloudBPGetSet.png"><img src="https://docs.simul.co/unrealengine/images/CloudBPGetSet.png" alt="Blueprint"/></a>


The tables below show the various cloud keyframe properties, for floating point and integer values respectively. The entries in the "Name" column are what should be used as the "Name" string parameter in any Blueprint calls to GetKeyframeFloat, GetKeyframeInt, SetKeyframeFloat and SetKeyframeInt. 


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
			



Further Information
--------------
 
* [The Sequencer](https://docs.simul.co/reference/man_8_sequencer.html)  
* [Driving trueSKY via Blueprint](https://docs.simul.co/unrealengine/Blueprint.html)
* [Cloud Rendering in trueSKY](https://docs.simul.co/reference/classsimul_1_1clouds_1_1BaseCloudRenderer.html)
* [Watch a video tutorial](https://www.youtube.com/watch?v=hE6qFzJgED4) 




Next: <a href="/unrealengine/Sky">Sky</a>