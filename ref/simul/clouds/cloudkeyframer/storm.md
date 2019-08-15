---
title: Storm
layout: reference
weight: 0
---
struct Storm
===

| Include: | Clouds/CloudKeyframer.h |

A structure representing a thunderstorm. See CloudKeyframer::AddStorm.
  


Functions
---

| void | [AddStrike](#AddStrike)(float cloudbase_km, float game_time, float real_time) |
| float | [GetDefaultFloat](#GetDefaultFloat)(char name) |
| int | [GetDefaultInt](#GetDefaultInt)(char name) |
| float | [GetFloat](#GetFloat)(char name) |
| int | [GetInt](#GetInt)(char name) |
| simul::clouds::LightningProperties | [GetLightningProperties](#GetLightningProperties)(float game_time, float real_time, float base_km) |
| simul::clouds::Strike | [GetStrike](#GetStrike)(int i) |
| int | [GetTotalNumStrikes](#GetTotalNumStrikes)() |
| bool | [HasFloat](#HasFloat)(char name) |
| bool | [HasInt](#HasInt)(char name) |
| void | [SetFloat](#SetFloat)(char name, float val) |
| void | [SetInt](#SetInt)(char name, int val) |
| int | [SpawnStrike](#SpawnStrike)(float time, vec3 startpos, vec3 endpos, float magnitude, vec3 colour, bool sh, float dur, float leader_dur) |
| void | [Update](#Update)(float game_time, float real_time) |

A structure representing a thunderstorm. See CloudKeyframer::AddStorm.
  


Functions
---
<a name="AddStrike"></a>
### void AddStrike(float cloudbase_km, float game_time, float real_time)
Add the next random strike.
<a name="GetDefaultFloat"></a>
### float GetDefaultFloat(char name)
Returns the default for the named property - see HasFloat().
<a name="GetDefaultInt"></a>
### int GetDefaultInt(char name)
Returns the default for the named property - see HasInt().
<a name="GetFloat"></a>
### float GetFloat(char name)
Returns the named property - see HasFloat().
<a name="GetInt"></a>
### int GetInt(char name)
Returns the named property - see HasInt().
<a name="GetLightningProperties"></a>
### simul::clouds::LightningProperties GetLightningProperties(float game_time, float real_time, float base_km)
Get the properties of the currently active lightning strike
<a name="GetStrike"></a>
### simul::clouds::Strike GetStrike(int i)
Return the currently active strike, or return a default strike
<a name="GetTotalNumStrikes"></a>
### int GetTotalNumStrikes()
Get the approximate number of strikes that are generated over a day with the current settings
<a name="HasFloat"></a>
### bool HasFloat(char name)
Returns true if the keyframe has the named property.
<a name="HasInt"></a>
### bool HasInt(char name)
Returns true if the keyframe type has the named integer property.
<a name="SetFloat"></a>
### void SetFloat(char name, float val)
Set the named property - see HasFloat().
<a name="SetInt"></a>
### void SetInt(char name, int val)
Set the named property - see HasFloat().
<a name="SpawnStrike"></a>
### int SpawnStrike(float time, vec3 startpos, vec3 endpos, float magnitude, vec3 colour, bool sh, float dur, float leader_dur)
Spawn a strike at a certain time with the given properties
<a name="Update"></a>
### void Update(float game_time, float real_time)
Once per frame update to discard old strikes.

Fields
---

**radiusKm**  < Centre of the lightning storm.

**start_time**  < Radius of the lightning storm.

**end_time**  < Time the storm commences.

**realTime**  < Time the storm ends.

**sheet**  < If true, frequency and duration of strikes are in real time, not simulation time.

**strikeFrequencyPerSecond**  < What proportion of the strikes are sheet lightning as opposed to ground strikes.

**strikeDurationSeconds**  < In simulated seconds - not necessarily realtime

**strikeThicknessMetres**  < How long, in simulated seconds - not realtime - each strike should last.

**roughness**  < Thickness of the main trunk.

**motion**  < How rough/smooth to make the branches.

**seed**  < How much to move/animate during a strike.

**numLevels**  < Pseudo-random seed.

**numBranches**  < Number of levels of branching.

**branchAngleDegrees**  < Mean number of branches to generate from each parent.

**colour**  < Mean angle of branching.

**maxRadiance**  < Colour of the strikes.

**minPixelWidth**  < Maximum radiance of the strikes.

**unique_id**  < Minimum pixel-size for strike rendering.

**last_strike_uid**  < A non-persistent unique identifier.

**strikes**  We can store a stack of non-random strikes. These take precedence over pseudo-randomly generated strikes.
