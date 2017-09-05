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
| bool | [HasFloat](#HasFloat)(char name) |
| bool | [HasInt](#HasInt)(char name) |
| void | [SetFloat](#SetFloat)(char name, float val) |
| void | [SetInt](#SetInt)(char name, int val) |
| void | [Update](#Update)(float game_time, float real_time) |

A structure representing a thunderstorm. See CloudKeyframer::AddStorm.
  


Functions
---

### <a name="AddStrike"/>void AddStrike(float cloudbase_km, float game_time, float real_time)
Add the next random strike.
Add the next random strike.

### <a name="GetDefaultFloat"/>float GetDefaultFloat(char name)
Returns the default for the named property - see HasFloat().
Returns the default for the named property - see HasFloat().

### <a name="GetDefaultInt"/>int GetDefaultInt(char name)
Returns the default for the named property - see HasInt().
Returns the default for the named property - see HasInt().

### <a name="GetFloat"/>float GetFloat(char name)
Returns the named property - see HasFloat().
Returns the named property - see HasFloat().

### <a name="GetInt"/>int GetInt(char name)
Returns the named property - see HasInt().
Returns the named property - see HasInt().

### <a name="HasFloat"/>bool HasFloat(char name)
Returns true if the keyframe has the named property.
Returns true if the keyframe has the named property.

### <a name="HasInt"/>bool HasInt(char name)
Returns true if the keyframe type has the named integer property.
Returns true if the keyframe type has the named integer property.

### <a name="SetFloat"/>void SetFloat(char name, float val)
Set the named property - see HasFloat().
Set the named property - see HasFloat().

### <a name="SetInt"/>void SetInt(char name, int val)
Set the named property - see HasFloat().
Set the named property - see HasFloat().

### <a name="Update"/>void Update(float game_time, float real_time)
Once per frame update to discard old strikes.
Once per frame update to discard old strikes.

Fields
---

**radiusKm** < Centre of the lightning storm. < Centre of the lightning storm.

**start_time** < Radius of the lightning storm. < Radius of the lightning storm.

**end_time** < Time the storm commences. < Time the storm commences.

**realTime** < Time the storm ends. < Time the storm ends.

**sheet** < If true, frequency and duration of strikes are in real time, not simulation time. < If true, frequency and duration of strikes are in real time, not simulation time.

**strikeFrequencyPerSecond** < What proportion of the strikes are sheet lightning as opposed to ground strikes. < What proportion of the strikes are sheet lightning as opposed to ground strikes.

**strikeDurationSeconds** < In simulated seconds - not necessarily realtime < In simulated seconds - not necessarily realtime

**strikeThicknessMetres** < How long, in simulated seconds - not realtime - each strike should last. < How long, in simulated seconds - not realtime - each strike should last.

**roughness** < Thickness of the main trunk. < Thickness of the main trunk.

**motion** < How rough/smooth to make the branches. < How rough/smooth to make the branches.

**seed** < How much to move/animate during a strike. < How much to move/animate during a strike.

**numLevels** < Pseudo-random seed. < Pseudo-random seed.

**numBranches** < Number of levels of branching. < Number of levels of branching.

**branchAngleDegrees** < Mean number of branches to generate from each parent. < Mean number of branches to generate from each parent.

**colour** < Mean angle of branching. < Mean angle of branching.

**maxRadiance** < Colour of the strikes. < Colour of the strikes.

**minPixelWidth** < Maximum radiance of the strikes. < Maximum radiance of the strikes.

**unique_id** < Minimum pixel-size for strike rendering. < Minimum pixel-size for strike rendering.

**last_strike_uid** < A non-persistent unique identifier. < A non-persistent unique identifier.

**strikes** We can store a stack of non-random strikes. These take precedence over pseudo-randomly generated strikes. We can store a stack of non-random strikes. These take precedence over pseudo-randomly generated strikes.
