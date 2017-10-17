---
title: Sky
layout: unity
weight : 5
---


The Sky in trueSKY
=======

In trueSKY, the sky is modified in two ways: through sky keyframes and the sky layer. Keyframe properties will dictate the look of the sky at a given point in time – with interpolation used to derive properties at times between keyframes – whereas layer properties will be active throughout a sequence. These properties can be modified via the sequencer and/or through Unity scripting.

Read more about how the sky is rendered in trueSKY [here](https://docs.simul.co/reference/classsimul_1_1sky_1_1BaseSkyRenderer.html).


Editing The Sky in the Sequencer
----------------


To select a sky keyframe, click it. To select all the keyframes of the sky layer, double-click on the space between them. To select and modify the properties of the whole sky layer, click on the "Sky" text at left.

<a href="https://docs.simul.co/unity/images/SkySeqExample.png"><img src="https://docs.simul.co/unity/images/SkySeqExample.png" alt="Sky"/></a> 

Read more about editing the Sky Layer or Sky Keyframes on [The Sky Sequencer Page](https://docs.simul.co/reference/man_8_sequencer.html).



Editing The Sky Via Scripting: The Sky Layer
---------------


To Get/Set sky layer properties, use **trueSKY.GetSkyFloat**, **trueSKY.GetSkyInt**, **trueSKY.SetSkyFloat** and **trueSKY.SetSkyInt**. For more information on how to use these functions, see [Scripting](https://docs.simul.co/unity/Scripting.html). The tables below show the various sky layer properties (named as they appear in the sequencer), along with the matching name string to use for scripting. **Note**: Parameters that are Bools in the Sequencer are treated as Ints in scripting, where 0 = false and 1 = true.


**Floating-point**

Sequencer Property | Name Variable | Definition
-------------------|---------------|---------    
Brightness Power | "BrightnessPower" | Adjusts light levels to compensate for variations via power function (e.g 0.5 = square root dependence, 1.0 = no adjustment). Between 0.01 and 1.0.
Max Altitude | "MaxAltitudeKm" | 	Max altitude that will be used for fade and sky colour calculations, in km. Between 2.0 and 100.0.
Distance Range | "MaxDistanceKm"| Maximum distance for fade. Between 5.0 and 2000.0
Overcast Effect | "OvercastEffectStrength"| How strongly cloud layer blocks light. Between 0.0 and 1.0.
Ozone  | "OzoneStrength" | Amount of ozone. Between 0.0 and 0.2.
Emissivity | "Emissivity"| Blackbody emissivity of atmosphere. Between 0.0 and 1.0.
Diameter (Sun) | "SunRadiusArcMinutes"| Size of sun's radius in arcminutes (Note: Sequencer uses diameter in degrees, which is = to radius in arcminutes * 2.f / 60.f). Between 0.0 and 3600.0.
Brightness Limit | "SunBrightnessLimit"| Brightness limit of the sunlight. Between 1.0 and 10000000.0 (1e+07).
Latitude   | "LatitudeRadians"  | Between -1.57 (-90 degrees) and 1.57 (90 degrees)
Longitude  | "LongitudeRadians"  |  Between -3.14159 (-180 degrees) and -3.14159 (180 degrees)
Timezone+- | "TimezoneHours"| Between -12.0 and 12.0.
Albedo | "MoonAlbedo"  | Between 0.0 and 1.0.
Diameter (Moon) | "MoonRadiusArcMinutes" | Size of moon's radius in arcminutes (Note: Sequencer uses diameter in degrees, which is = to radius in arcminutes * 2.f / 60.f). Between 0.0 and 3600.0.
Max Magnitude | "MaxStarMagnitude" | Between 0.0 and 9.0.
Brightness (Stars) | "StarBrightness" | Between 1.0 and 10000.0.
Background  | "BackgroundBrightness" | Brightness multiplier for background texture. Between 0.000001 and 0.001.

     

**Integer**

Sequencer Property| Name Variable | Definition
------------------|---------------|------------ 
Altitudes | "NumAltitudes"| Number of altitudes in atmpsheric table textures. Betwen 1 and 8.
Elevations | "NumElevations"| Number of elevations / height of table. Powers of 2 between 4 and 256.
Distances | "NumDistances" | Number of distances / width of table. Powers of 2 between 4 and 128.
Start Date | "StartDayNumber" | For calculating start position of sun/moon. Where 01/01/2000 = 0 , -1 = 31/12/1999, 01/01/2016 = 5844 etc (in the format: DD:MM:YYYY).


**Example:** To set the sky layer Star Brightness to 10000:

	private trueSKY tS;  
 
	void Start () 
	{
		tS = trueSKY.GetTrueSky(); 
		tS.SetSkyFloat("StarBrightness", 10000.0F);  
	} 


Editing The Sky Via Scripting: Sky Keyframes
---------------

To Get/Set sky keyframe properties, use **trueSKY.GetKeyframeValue** and **trueSKY.SetKeyframeValue**, ensuring the pass the keyframe's Uid as an argument. For information on what functions to use to get keyframe Uids, along with information about other helpful functions, see [Scripting](https://docs.simul.co/unity/Scripting.html). The tables below show the various sky keyframe properties (named as they appear in the sequencer), along with the matching name string to use for scripting. **Note**: Parameters that are Bools in the Sequencer are treated as Ints in scripting, where 0 = false and 1 = true.
 
**A Note about Haze/Fog/Mist**: A keyframe’s haze value determines how much Mie-scattered haze (i.e. mist or fog) is present. Haze is considered to have a density that falls-off exponentially with altitude, so the Haze scale height property determines the scaling height for this exponential. Fog and mist are both effectively low-level clouds. Fog is defined as having visibility less than 1km, it is called mist when visibility is between 1 and 2 km.


**Floating-point**

Sequencer Property|Name Variable|Definition
------------------|--------------|----------
Time | "daytime" | The trueSKY time at which the keyframe starts. Betwee 0.0 and 1.0 (for the first day, second day would be 1.0 to 2.0 and so on).
Sea Level Deg. C | "SeaLevelTemperatureK" | For infrared rendering. Between -273.0 and 1000.0.
Haze / Fog | "Haze" | Amount of haze/mist. Alters visibility. Between 0.00001 and 1000.0.
Haze Base, km | "HazeBaseKm" | Base altitude above which haze decreases in density. Between -2.0 and 20.0. 
Haze Scale, km | " HazeScaleKm" | Vertical scale over which haze reduces with altitude. Between 0.1 and 10.0.
Eccentricity | "HazeEccentricity" | Anisotropy of Mie scattering. Between 0.0 and 1.0.
Mie Coefficients | "MieRed", "MieGreen", "MieBlue" | Mie scattering coefficients, xyz = RGB.
Sun Elevation | " SunElevation" | How high the sun is, in radians. Between -1.57 (-90 degrees) and 1.57 (90 degrees).
Sun Azimuth | "SunAzimuth" | Horizontal angle of sun , in radians. Between -3.14159 (-180 degrees) and -3.14159 (180 degrees).
Moon Elevation | "MoonElevation" | How high the moon is, in radians. Between -1.57 (-90 degrees) and 1.57 (90 degrees).
Moon Azimuth | "MoonAzimuth" | Horizontal angle of moon, in radians. Between -3.14159 (-180 degrees) and -3.14159 (180 degrees).

 

**Integer**

Sequencer Property| Name Variable | Definition
------------------|---------------|------------ 
Store as Colours | "StoreAsColours" | If true, keyframe stored as colour table, rather than generating colours from properties. Bool.
Altitudes | "numColourAltitudes" | Number of altitudes for custom table texture. Between 1 and 8.
Elevations | "numColourElevations" | Number of elevations for custom table texture. Between 1 and 15.
Distances | "numColourDistances" | Number of distances for custom table texture. Between 1 and 15.
Automie | "AutoMie" | Whether to recalculate Mie coefficients based on the haze at this keyframe. Bool.
Automatic Sun Position | "AutomaticSunPosition" | Whether to calculate sun position from date and time. Bool.
Automatic Moon Position | "AutomaticMoonPosition" | Whether to calculate moon position from date and time. Bool.

 
**Example**: To get the last keyframe in a sequence, and then set its haze value to 12:

	private trueSKY tS;   

	void Start () 
	{
		tS = trueSKY.GetTrueSky();  
		int numk = tS.GetNumSkyKeyframes (); 
		uint uid = tS.GetSkyKeyframeByIndex(numk - 1); 
		tS.SetKeyframeValue (uid, "Haze", 12.0F); 
	}



Further Information
--------------
 
* [The Sequencer](https://docs.simul.co/reference/man_8_sequencer.html)  
* [Scripting in trueSKY for Unity](https://docs.simul.co/unity/Scripting.html)
* [Sky Rendering in trueSKY](https://docs.simul.co/reference/classsimul_1_1sky_1_1BaseSkyRenderer.html)
* [Watch a video tutorial](https://www.youtube.com/watch?v=Eljf5CjZ4vc)


Next: <a href="/unity/Storms">Storms</a>

