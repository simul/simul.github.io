---
title: Storms
layout: reference
weight: 60
---






Storms
====================

Storms can be a useful tool when creating atmospheric environments, when you want lighting to illuminate your scene.

Storm keyframes are added to the cloud layer, to create structures representing thunderstorms. Just like with cloud keyframes, you can get and set their properties via scripting or blueprints as well as in the sequencer. Don't forget, to produce a storm, you need clouds!


{:.keyframe}
Variable                                                                                |       Definition                                                                                                                                                      |       Value
--------------                                                                  |--------------                                                                                                                                                 |--------------
Real time                                                                               | Sets frequency/duration of strikes to real time. If false, then simulation time.              |Bool
Motion                                                                                  | How much to move/animate during a strike.                                                                                             |0 to 10
Strike Duration                                                                 | The time each strike should last, in (simulated) seconds.                                                             |0.1 to 1000
Strike Frequency                                                                | How many strikes per (simulated) second.                                                                                              |0.1 to 10
Branch Angle                                                                    | Mean angle of branching, in degrees from 0 - 90.                                                                              |0 to 90
Random seed                                                                             | Pseudo-random seed.                                                                                                                                   |0 to 1000
Levels                                                                                  | Number of levels of branching.                                                                                                                |1 to 5
Branches                                                                                | Mean number of branches to generate from each parent.                                                                 |1 to 12
Vertical to Sheet                                                               | How much of the lighting should stay within the clouds.                                                               |0 to 1
Roughness                                                                               | How rough/smooth to make the lightning branches.                                                                              |0 to 1
Storm Radius                                                                    | Radius of the lightning storm, in km.                                                                                                 |1 to 100
Thickness                                                                               | Thickness of the lightning trunk, in metres (or in cm via sequencer).                                 |1 to 100
Min Pixel Width                                                                 | Minimum pixel size for rendering the lightning strikes.                                                               |0 to 8
Radiance                                                                                | Maximum radiance of the strikes.                                                                                                              |0.1 to 10000




Editing Storms in the Sequencer
-----------------------

To create a storm in the sequencer, simply right click on the 3D cloud layer and select "Add storm". Clicking on the keyframe will show a selection of storm properties that can be changed. To set the storm's start time, end time and duration, simply drag out its edges horizontally to encompass what part of the timeline is required. Make sure there are enough clouds to produce lightning while the storm is active.

![](/images/unity/stormsequencer.png)


You cannot drag the storm keyframe to move it, you must move it by extending and shrinking the keyframe. This is because, unlike keyframes which effect lasts until the next keyframe, Storms must have a set, determined size.



<div class="unity-specific">

Editing Storms through Scripting
-----------------------

As with cloud and sky keyframes, to get/set properties of a storm keyframe, you will first need to get its uid. To do this, use GetStormUidByIndex(int index) or GetStormUidAtTime(float time). Once you have the storm keyframe's uid, you can get and set its float and int properties using GetStormFloat(uint uid, string name), SetStormFloat(uint uid, string name, float value), GetStormInt(uint uid, string name) and SetStormInt(uint uid, string name, int value). For information on these functions, see [Scripting](/unity/scripting.html). The tables below show the storm properties (named as they appear in the sequencer), along with the matching name string to use for scripting. **Note:** Parameters that are Bools in the Sequencer are treated as Ints in scripting, where 0 = false and 1 = true.


</div>

<div class="ue4-specific">

Editing Storm through Blueprints
------------------------

Coming Soon


</div>
