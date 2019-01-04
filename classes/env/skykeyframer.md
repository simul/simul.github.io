---
title: The Sky Keyframer
layout: reference
weight: 0
---
=================<br>Previous: Unresolved reference environment

Updating
--------
An instance of simul::sky::SkyKeyframer SkyKeyframeris stored in simul::clouds::Environment. As a keyframer, this class
stores a list of keyframes; this list can be modified at runtime, or loaded from a sequence (see Unresolved reference man_6_sequencer).

The keyframes each have a time value, and the keyframer tracks a current time through these frames, interpolating properties as it does so.

The SkyKeyframer has two modes of operation. By switching simul::sky::SkyKeyframer::SetLinkKeyframeTimeAndDaytime LinkKeyframeTimeAndDaytimeon or off,
you can choose whether the keyframes have a daytime value which is independent of time, or whether these two numbers are the same.

You don't need to update the keyframer specifically, so long as you're calling simul::clouds::Environment::Update environment->Update().

Linked Time and Daytime
-----------------------

If they are linked, simul::sky::BaseKeyframe::time timeand simul::sky::SkyKeyframe::daytime daytime 
will be the same number, where 0 represents the first midnight of the sequence, 1.0 represents 24 hours after this, and so on.

![](/Images/SkyKeyframerLinked.png)
""

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

If they are not linked, then while daytime is defined as above, the keyframe's simul::sky::BaseKeyframe::time time
value is arbitrary - it could represent the real time in seconds, or some other scale. Furthermore, while the keyframes
will be sorted so that they are in ascending order of simul::sky::BaseKeyframe::time time,
daytime will have no such restriction. You could have a midday keyframe, followed by sunset, followed by midday again.
Here, we set all the keyframes to be at daytime=0.25 (6am):

simul::sky::SkyKeyframer *sk=environment->skyKeyframer.Get();
sk->SetLinkKeyframeTimeAndDaytime(false);
for(int i=0;i<sk->GetNumKeyframes();i++)
{
simul::sky::SkyKeyframe *k=(simul::sky::SkyKeyframe *)sk->GetKeyframe(i);
k->daytime=0.25f;
}

You could also disable simul::sky::SkyKeyframe::automaticSunPosition automaticSunPosition, in which case daytime will have no effect
on sun position.

The unlinked time mode is particularly suitable to situations where you will use the Simul API to change conditions on the fly.
At any given time, two keyframes are being used for rendering, and the next one along will be partially updated. So the properties
of the fourth keyframe can be changed without having any need for recalculations.

simul::sky::SkyKeyframe *k=environment->skyKeyframer->GetNextModifiableKeyframe();
k->haze=20.f;

This works just as well with linked as with unlinked times.


Properties of a Sky Keyframe
-------------------------

For a complete list of a sky keyframe's properties, see simul::sky::SkyKeyframe SkyKeyframe.

<table>
<tr><td>float daytime</td><td>The time this keyframe represents, in a floating-point number of days from the starting midnight of the sequence. If simul::sky::SkyKeyframer::SetLinkKeyframeTimeAndDaytime is true, this is the same as the keyframe's time value.</td>
</tr>
<tr><td>float4 Mie</td><td>The Mie scattering coefficients (x=red,y=green,z=blue).</td></tr>
<tr><td>bool AutoMie</td><td>The Mie scattering coefficients will be calculated based on wavelength and haze if this is set - overrides Mie.</td></tr>
<tr><td>float Haze</td><td>The amount of haze, mist or fog.</td></tr>
<tr><td>float HazeBaseKm</td><td>The base altitude, above which haze starts to decrease in density.</td></tr>
<tr><td>float HazeScaleKm</td><td>The vertical scale over which haze reduces with altitude.</td></tr>
<tr><td>float HazeEccentricity</td><td>The anisotropy of Mie scattering.</td></tr>
<tr><td>float SunAzimuth</td><td>Horizontal angle to the sun. This will be overridden if sun position is automatic.</td></tr>
<tr><td>float SunElevation</td><td>Angle of the sun above the horizon. This will be overridden if sun position is automatic.</td></tr>
<tr><td>float MoonElevation</td><td>Angle of the moon above the horizon. This will be overridden if moon position is automatic.</td></tr>
<tr><td>float MoonAzimuth</td><td>Horizontal angle to the moon. This will be overridden if moon position is automatic.</td></tr>
</table>

These are public properties of the structure. You can set any property of any keyframe at any time.
But setting properties of active keyframes causes recalculation, which will interrupt the program for a short time,
so it is recommended not to do this frequently outside of tools and testing.

To ensure that no recalculation takes place, the function simul::sky::SkyKeyframer::GetNextModifiableKeyframe GetNextModifiableKeyframe()
can be used to get a pointer to the keyframe after those currently being interpolated or used for table-generation.
You can change its properties freely.

A keyframe's haze value determines how much Mie-scattered haze (i.e. mist or fog) is present. Haze is considered to have a density that falls-off
exponentially with altitude, so the HazeScaleHeightKm property determines the scaling height for this exponential. The
HazeBaseHeightKm is also used. Below this height, full haze is applied.

Fog and mist are both effectively low-level clouds. Fog is defined as having visibility less than 1km, it is called mist when visibility
is between 1 and 2 km.

As time passes and the sun and moon move, you can use simul::sky::BaseSkyInterface::GetDirectionToSun GetDirectionToSunand simul::sky::BaseSkyInterface::GetDirectionToMoonto find their positions.

<hr size="1">
Next: Unresolved reference cloud_keyframer
