---
title: Storms
layout: unity
weight : 3
---

Storms in trueSKY
======================

Storm keyframes are added to the 3D cloud layer, to create structures representing thunderstorms. Just like with cloud keyframes, you can get and set their properties via scripting as well as in the sequencer.


Editing Storms in the Sequencer
-----------------------

To create a storm in the sequencer, simply right click on the 3D cloud layer and select "Add storm". Clicking on the keyframe will show a selection of storm properties that can be changed. To set the storm's start time, end time and duration, simply drag out its edges horizontally to encompass what part of the timeline is required.

<a href="http://docs.simul.co/unity/images/StormSequencer.png"><img src="http://docs.simul.co/unity/images/StormSequencer.png" alt="Storms"/></a> 


Editing Clouds via Scripting
-----------------------

As with cloud and sky keyframes, to get/set properties of a storm keyframe, you will first need to get its uid. To do this, use GetStormUidByIndex(int index) or GetStormUidAtTime(float time). Once you have the storm keyframe's uid, you can get and set its float and int properties using GetStormFloat(uint uid, string name), SetStormFloat(uint uid, string name, float value), GetStormInt(uint uid, string name) and SetStormInt(uint uid, string name, int value). For information on these functions, see [Scripting](http://docs.simul.co/unity/Scripting.html). The tables below show the storm properties (named as they appear in the sequencer), along with the matching name string to use for scripting. **Note:** Parameters that are Bools in the Sequencer are treated as Ints in scripting, where 0 = false and 1 = true.
		 

**Floating-point**

Sequencer Property | Name Variable | Definition
-------------------|---------------|------------
Radiance |"maxRadiance"|   Maximum radiance of the strikes.
Branch Angle |"branchAngleDegrees" | Mean angle of branching, in degrees.
Roughness |"roughness" | How rough/smooth to make the lightning branches.
Strike Duration	(s)| "StrikeDurationSeconds" | The time each strike should last, in (simulated) seconds.
Strike Frequency (/s)| "strikeFrequencyPerSecond" | How many strikes per (simulated) second.
Thickness |"StrikeThicknessMetres" | Thickness of the lightning trunk, in metres (or in cm via sequencer).
Min Pixel Width |"minPixelWidth"| Minimum pixel size for rendering the lightning strikes.
Motion | "motion" | How much to move/animate during a strike.
Radius |"radius_km" | Radius of the lightning storm, in km.
Start Time |"start_time"| The time at which the storm commences. 
End Time|"end_time"   | The time at which the storm ends.


**Integer**

Sequencer Property | Name Variable | Definition
-------------------|---------------|-----------
Real-time |"realTime"| Bool. Sets frequency/duration of strikes to real time. If false, then simulation time.  
Levels |"numLevels"| Number of levels of branching.
Branches |"numBranches"| Mean number of branches to generate from each parent.
Random Seed |"randomSeed"| Pseudo-random seed.


Further Information
--------------
 
* [The Sequencer](http://docs.simul.co/reference/man_8_sequencer.html)  
* [Scripting in trueSKY for Unity](http://docs.simul.co/unity/Scripting.html) 
* [The Storm Struct](http://docs.simul.co/reference/structsimul_1_1clouds_1_1CloudKeyframer_1_1Storm.html)


Next: <a href="/unity/index">Home</a>