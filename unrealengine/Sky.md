---
title: Sky
layout: unreal
weight : 5
---

The Sky in trueSKY
========

In trueSKY, the sky is modified in two ways: through sky keyframes and the sky layer. Keyframe properties will dictate the look of the sky at a given point in time -- with interpolation used to derive properties at times between keyframes -- whereas layer properties will be active throughout a sequence. Both can be modified via the sequencer or through the Blueprint system.

Read more about how the sky is rendered in trueSKY [here](https://docs.simul.co/reference/classsimul_1_1sky_1_1BaseSkyRenderer.html).


Editing The Sky in the Sequencer
-------------------------

To select a sky keyframe, click it. To select all the keyframes of the sky layer, double-click on the space between them or box select them. To select and modify the properties of whole sky layer, click on the "Sky" text at left.

<a href="https://docs.simul.co/unrealengine/images/SkySeqExample.png"><img src="https://docs.simul.co/unrealengine/images/SkySeqExample.png" alt="Sky"/></a> 

Read more about editing the Sky Layer or Sky Keyframes on [The Sky Sequencer Page](https://docs.simul.co/sequencer.html).


Editing The Sky in Blueprint: The Sky Layer
-------------------------

To Get and Set sky layer properties, use the provided SetInt, GetInt, SetFloat and GetFloat functions. For more on how to use these, along with information about other helpful blueprint functions see [Blueprint](https://docs.simul.co/unrealengine/Blueprint.html). 

The tables below show the various sky layer properties (named as they appear in the sequencer), The entries in the "Name" column are what should be used as the "Name" string parameter in any Blueprint calls to GetKeyframeFloat, GetKeyframeInt, SetKeyframeFloat and SetKeyframeInt. The Name strings should be prefixed with "sky:". **Note**: Parameters that are Bools in the Sequencer are treated as Ints in scripting, where 0 = false and 1 = true.


**Floating-point**

Sequencer Property | Name Variable | Definition
-------------------|---------------|---------    
Brightness Power | "BrightnessPower"| Adjusts light levels to compensate for variations via power function (e.g 0.5 = square root dependence, 1.0 = no adjustment). Between 0.01 and 1.0.
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



Editing The Sky in Blueprint: Sky Keyframes
--------------------------

To get a sky keyframe’s properties, you will first need its Unique ID (Uid) to identify it. Uids can be retrieved using a variety of provided Blueprint functions. The functions are as follows:

* **GetSkyKeyframebyIndex:** Returns a sky keyframe’s Uid, given an index (this is zero-indexed; the first sky keyframe in a sequence is 0, the second is 1 and so on).

* **GetPreviousSkyKeyframeBeforeTime:** Given a time, returns the Uid of the last sky keyframe before said time.

* **GetNextSkyKeyframeAfterTime:** Given a time, returns the Uid of the next sky keyframe after said time.

* **GetNextModifiableSkyKeyframe:** Returns the Uid of the next sky keyframe that can be modified without requiring any recalculation (this will be the next sky keyframe + 1).

* **GetInterpolatedSkyKeyframe:** Returns the current interpolated sky keyframe’s Uid (Note: this cannot be used to set any values; it is read-only).


Once you have a sky keyframe’s Uid, you can Get and Set its properties. These functions have a "Name" parameter, which must be set to the matching string for the property required (see the table below). The functions are as follows:

* **GetKeyFrameFloat:** Given a keyframe Uid and a name string, returns the float value matching the name.

* **GetKeyframeInt:** Given a keyframe Uid and a name string, returns the integer value matching the name.

* **SetKeyframeFloat:** Given a keyframe Uid, a name string and a float value, will set the matching property for the Name to the specified float value.

* **SetKeyframeInt:** Given a keyframe Uid, a name string and an integer value, will set the matching property for the Name to the specified integer value.

<a href="https://docs.simul.co/unrealengine/images/SkyBPGetSet.png"><img src="https://docs.simul.co/unrealengine/images/SkyBPGetSet.png" alt="Blueprint"/></a>


The tables below show the various sky keyframe properties, for floating point and integer values respectively. The entries in the "Name" column are what should be used as the "Name" string parameter in any Blueprint calls to GetKeyframeFloat, GetKeyframeInt, SetKeyframeFloat and SetKeyframeInt.

**A Note about Haze/Fog/Mist:** A keyframe's haze value determines how much Mie-scattered haze (i.e. mist or fog) is present. Haze is considered to have a density that falls-off exponentially with altitude, so the Haze scale height property determines the scaling height for this exponential. Fog and mist are both effectively low-level clouds. Fog is defined as having visibility less than 1 km, it is called mist when visibility is between 1 and 2 km.


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



Further Information
--------------
 
* [The Sequencer](https://docs.simul.co/sequencer.html)  
* [Driving trueSKY via Blueprint](https://docs.simul.co/unrealengine/Blueprint.html)
* [Sky Rendering in trueSKY](https://docs.simul.co/reference/classsimul_1_1sky_1_1BaseSkyRenderer.html)
* [Watch a video tutorial](https://www.youtube.com/watch?v=hE6qFzJgED4) 



			
Next: <a href="/unrealengine/Blueprint">Blueprint</a>