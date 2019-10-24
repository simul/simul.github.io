---
title: Sky
layout: reference
weight: 30
---





Sky
====================

In trueSKY, the sky is modified in two ways: through sky keyframes and the sky layer. Keyframe properties will dictate the look of the sky at a given point in time - with interpolation used to derive properties at times between keyframes -- whereas layer properties will be active throughout a sequence. Both can be modified via the sequencer or through the Blueprint system.


Sky
======

{:.keyframe}
Variable                                                                                |       Definition                                                                                                                                                                                                                                              |       Value
--------------                                                                  |--------------                                                                                                                                                                                                                                         |--------------
Sea Level Deg. C                                                                |For infra-red rendering.                                                                                                                                                                                                                       |-273.0 to 1000
Zenith                                                                                  |Colour of the Zenith (Sky above you). Make sure to enable Store as Colours to be able to adjust.                                                                       |RGB 
Horizon                                                                                 |Colour of the horizon (Sky around you). Make sure to enable Store as Colours to be able to adjust.                                                                     |RGB 


{:.layer}
Variable                                                                                |       Definition                                                                                                                                                                                                                                              |       Value
--------------                                                                  |--------------                                                                                                                                                                                                                                         |--------------
Loop                                                                                    |If the sky should loop the first day. The loop can be seen on the timeline, indicated by a yellow bracket above the Sky Layer.         |Bool

{:.object}
Variable                                                                                |       Definition                                                                                                                                                                                                                                              |       Value
--------------                                                                  |--------------                                                                                                                                                                                                                                         |--------------
Sky Multiplier                                                                  |Multiplier to scale the brightness of the Sky.                                                                                                                                                                         |1 to 100                               




Atmosphere
=============

{:.layer}
Variable                                                                                |       Definition                                                                                                                                                                                                                                              |       Value
--------------                                                                  |--------------                                                                                                                                                                                                                                         |--------------
Planet Radius                                                                   |Radius of the planet in meters.                                                                                                                                                                                                        |100 to 100000
Atmosphere Thickness                                                    |Thickness of the Atmosphere in Km.                                                                                                                                                                                             |10 to 1000
Ozone                                                                                   |Ozone level of the atmosphere.                                                                                                                                                                                                         |0 to 0.2
Emissivity                                                                              |Emissivity of the Atmosphere.                                                                                                                                                                                                          |0 to 1
Rayleigh Coefficient                                                    |Rayleigh scattering coefficients at standard sea level density, xyz = RGB. Can be calculated based on wavelength with Auto Button.     |0 to 10000

{:.object}
Variable                                                                                |       Definition                                                                                                                                                                                                                                              |       Value
--------------                                                                  |--------------                                                                                                                                                                                                                                         |--------------
Atmospherics Amortization                                               |How to spread the cost of rendering atmospherics over frames. Similar to Cloud Amortization                                                                            |1 to 8

Sun
=======

{:.keyframe}
Variable                                                                                |       Definition                                                                                      |       Value
--------------                                                                  |--------------                                                                                 |--------------
Automatic Sun Position                                                  |Whether to calculate sun position from date and time.  |Bool.


{:.layer}
Variable                                                                                |       Definition                                                                                                                                                                                                                                              |       Value
--------------                                                                  |--------------                                                                                                                                                                                                                                         |--------------
Light Wavelength (R,G,B)                                                |Wavelength of the light from the sun.                                                                                                                                                                                          |0 to 1000
Irradiance                                                                              |Irradiance of the Sun, in Watts/m2/nm. XYZ=RGB.                                                                                                                                                                        |0 to 50
Diameter                                                                                |Size of sun’s radius in degrees                                                                                                                                                                                                      |0.0 to 3600.0
Link Keyframe time and daytime                                  |See [Link Keyframe Time](#linktime)                                                                                                                                                                                            |Bool
Time Zone                                                                               |Time Zone based on Greenwich Mean Time (GMT).                                                                                                                                                                          |Between -12.0 and 12.0
Start Date                                                                              |For calculating start position of sun/moon. Where 01/01/2000 = 0 , -1 = 31/12/1999, 01/01/2016 = 5844(format DD:MM:YYYY).                      |-100000 to 100000

{:.object}
Variable                                                                                |       Definition                                                                                                                                                                                                                                              |       Value
--------------                                                                  |--------------                                                                                                                                                                                                                                         |--------------
Sun Multiplier                                                                  |Multiplier to scale the brightness of sunlight in the scene.                                                                                                                                           |From 1 to 10
Max Sun Radiance                                                                |Maximum Sun radiance produced.                                                                                                                                                                                                         |0 to 1000000.0
Adjust Sun Radiance                                                             |If enabled, adjusting the Sun radiance will cause the sun to automatically scale to keep spectral irradiance the same.                         |Bool

Moon
=======
The moon has a customisable texture, so you can use it to make some interesting effects!

{:.keyframe}
Variable                                                                                |       Definition                                                                                                                                                                                                                                              |       Value
--------------                                                                  |--------------                                                                                                                                                                                                                                         |--------------
Automatic Moon Position                                                 |Whether to calculate moon position from date and time.                                                                                                                                                         |Bool

{:.layer}
Variable                                                                                |       Definition                                                                                                                                                                                                                                              |       Value
--------------                                                                  |--------------                                                                                                                                                                                                                                         |--------------
Albedo                                                                                  |The proportion of the incident light that is reflected by a surface.                                                                                                                           |0.0 to 1.0     
Diameter                                                                                |Size of moon's radius in degrees                                                                                                                                                                                                       |0.0 to 3600.0
Colour                                                                                  |Colour of the moon. Uses a colour wheel, can also input HTML Colour Code.                                                                                                                      |RGB                                            


{:.object}
Variable                                                                                |       Definition                                                                                                                                                                                                                                              |       Value
--------------                                                                  |--------------                                                                                                                                                                                                                                         |--------------
Moon texture                                                                    |Texture to use for the moon. trueSKY has a moon texture by default                                                                                                                             |.png
Moon Multiplier                                                                 |Brightness multiplier for the moon                                                                                                                                                                                             |0.0 to 10.0


Stars
========

{:.layer}
Variable                                                                                |       Definition                                                                                                                                                                                                                                              |       Value
--------------                                                                  |--------------                                                                                                                                                                                                                                         |-------------¬
Max Magnitude                                                                   |Maximum Magnitude of stars.                                                                                                                                                                                                            |0.0 to 9.0
Brightness                                                                              |Star Brightness.                                                                                                                                                                                                                                       |1.0 to 10000.0
Minimum Pixel Size                                                              |Minimum size of each star.                                                                                                                                                                                                             |1.0 to 10000.0
Background                                                                              |Brightness multiplier for background texture.                                                                                                                                                                          |0.000001 to 0.001
Find Constellation                                                              |*Out for Repairs*                                                                                                                                                                                                                                      |*Out for Repairs*      

{:.object}
Variable                                                                                |       Definition                                                                                                                                                                                                                                              |       Value
--------------                                                                  |--------------                                                                                                                                                                                                                                         |--------------
Cosmic Background Texture                                               |Texture to appear for the night sky. Default is an image of the Milky way                                                                                                                      |.png
Minimum Star Pixel Size                                                 |Minimum pixel size of stars in the sky. If set to 0 they are drawn as point, otherwise as quads. Does not affect the Sun.                      |0 to 


Fog
=============

A keyframe's haze value determines how much Mie-scattered haze (i.e. mist or fog) is present. Haze is considered to have a density that falls-off exponentially with altitude, so the HazeScaleHeightKm property determines the scaling height for this exponential. TheHazeBaseHeightKm is also used. Below this height, full haze is applied.

{:.keyframe}
Variable                                                                                |       Definition                                                                                                                                                                                                                                              |Value
--------------                                                                  |--------------                                                                                                                                                                                                                                         |--------------
Visibility                                                                              |Visibility controls haze/fog, represents visibility at sea level.                                                                                                                                      |0.1 to 10000
Haze/fog                                                                                |Amount of haze/mist.                                                                                                                                                                                                                           |0.00001 to 1000.0.
Haze Base                                                                               |Base altitude above which haze decreases in density.                                                                                                                                                           |-2.0 to 20.0.
Haze Scale                                                                              |Vertical scale over which haze reduces with altitude.                                                                                                                                                          |0.1 to 10.0.
Eccentricity                                                                    |Anisotropy of Mie scattering.                                                                                                                                                                                                          |0.0 to 1.0.
Ground Fog                                                                              |Strength of ground fog.                                                                                                                                                                                                                        |0.0 to 10.0.
Fog Ceiling                                                                             |Fog Ceiling in Km.                                                                                                                                                                                                                                     |0 to 10.
Mie Coefficients                                                                |Mie scattering coefficients. XYZ = RGB                                                                                                                                                                                         |0 to 50






{:#linktime}
Link keyframe time and daytime
---------------
The SkyKeyframer has two modes of operation. By switching <a href="../ref/simul/sky/skykeyframer/setlinkkeyframetimeanddaytime.html">LinkKeyframeTimeAndDaytime</a>on or off,
you can choose whether the keyframes have a daytime value which is independent of time, or whether these two numbers are the same.

If they are linked, <a href="../ref/simul/sky/basekeyframe/time.html">time</a>and <a href="../ref/simul/sky/skykeyframe/daytime.html">daytime </a>
will be the same number, where 0 represents the first midnight of the sequence, 1.0 represents 24 hours after this, and so on.




Linked Time and Daytime
-----------------------


![](/Images/SkyKeyframerLinked.png)


Here we enable this link by calling SetLinkKeyframeTimeAndDaytime, then verify that daytime and time are now the same:

simul::sky::SkyKeyframer *sk=environment->skyKeyframer;
sk->SetLinkKeyframeTimeAndDaytime(true);
for(int i=0;i<sk->GetNumKeyframes();i++)
{
simul::sky::SkyKeyframe *k=(simul::sky::SkyKeyframe *)sk->GetKeyframe(i);
assert(k->daytime==k->time);
}


Unlinked Time and Daytime
-------------------------

If they are not linked, then while daytime is defined as above, the keyframe's <a href="../ref/simul/sky/basekeyframe/time.html">time</a>
value is arbitrary - it could represent the real time in seconds, or some other scale. Furthermore, while the keyframes
will be sorted so that they are in ascending order of <a href="../ref/simul/sky/basekeyframe/time.html">time</a>,
daytime will have no such restriction. You could have a midday keyframe, followed by sunset, followed by midday again.
Here, we set all the keyframes to be at daytime=0.25 (6am):

simul::sky::SkyKeyframer *sk=environment->skyKeyframer.Get();
sk->SetLinkKeyframeTimeAndDaytime(false);
for(int i=0;i<sk->GetNumKeyframes();i++)
{
simul::sky::SkyKeyframe *k=(simul::sky::SkyKeyframe *)sk->GetKeyframe(i);
k->daytime=0.25f;
}

You could also disable <a href="../ref/simul/sky/skykeyframe/automaticsunposition.html">automaticSunPosition</a>, in which case daytime will have no effect
on sun position.

The unlinked time mode is particularly suitable to situations where you will use the Simul API to change conditions on the fly.
At any given time, two keyframes are being used for rendering, and the next one along will be partially updated. So the properties
of the fourth keyframe can be changed without having any need for recalculations.

simul::sky::SkyKeyframe *k=environment->skyKeyframer->GetNextModifiableKeyframe();
k->haze=20.f;

This works just as well with linked as with unlinked times.




