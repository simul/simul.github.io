---
title: Ways to progress time
layout: reference
weight: 70
---





<div class="ue4-specific">

Via Blueprints
==============

The trueSKY plugin for Unreal Engine allows time progression to be set directly through the progression scale setting within the sequence actor. Setting this value will control the speed at which time progresses. When using the default time unit, whose setting is found within the Times advanced settings, which controls the units used to measure time and is by default set to a 24 hour system, you can set the progression scale to 1 which will allow for time to progress in real-time (such that 1 second in the engine is 1 second in real life) and setting it to 3600 will make 1 hour in-game progress for each second passing.

To calculate a specific amount of time for a full day to progress, we can just multiply the number of minutes in a 24 hour cycle by 60 (representing the number of seconds within each minute).

For example, if we are aiming for a full 24 hour period to take 5 minutes in-game, we would multiply 5 by 60 giving a value of 300, which if used as the progression scale, will cause the 24 hour period to take 5 minutes.
We can also control the time progression via blueprints. Previous versions of the trueSKY plugin supplied a "trueSKYDemo" which could be placed within the scene to allow for time progression. However with the integration of time progression directly into the sequence actor, we have removed this from the contents folders.

However, control via blueprints has not been completely removed. You can add the trueSKY sequence actor to a blueprint, drag a node from it and search for "time", which will show the "get time" and "set time" variables that are exposed for use within blueprints. This allows for time to be set or interpolated directly through blueprints. If you also have a progression scale set, this progression will continue as normal from the newly set time. 
The progression scale can also be altered at runtime via blueprints in the same manner that as time; essentially allowing full control of the time and whether it's progressing.

![](/images/Time_Exposed_Variables.png)


For example, you could use a trigger box so that the time variable is set to a specific time of day and progression is stopped, when a certain event occurs. Upon leaving that trigger box, the progression scale is returned to its default, and time of day continues from the new time seamlessly.


</div>



<div class="unity-specific">

Via Scripting
================

Unlike Unreal, if you press Play, the clouds will move without any modifications. However, they will be moving very quickly. This is because we are not scaling the raw Delta Time input just yet, so every second in real time is progressing trueSKY by one whole day. It is unlikely that you would want the days to move so quickly, so try replacing the second argument in the division function that is receiving the Delta Time input, with a more suitable value. For example, a value of 60 will equate one trueSKY day to 60 seconds, a value of 3600 would equal an hour and a value of 86400 (60 x 60 x 24) would simulate a real day. In this example I am using 600, so a full day will pass in ten minutes. If you want the scene to start at a specific time, try changing the default value of the Time float variable (where 0.0 is the start of the first day, 0.5 is noon on the first day and 1.0 is the start of the second day). 

It is also possible to write your own scripts to change the time in trueSKY. This is done via by altering the `trueSKY.Time` value and you can approach this however you wish. However to achieve frame rate independence, it is advisable to make use of `Time.deltaTime`.

To do so, first set the Speed variable in the trueSKY object to 0, so it doesn't affect the time. Create and attach a new script to the trueSKY object, and open it. The trueSKY time is changed via the trueSKY.Time value. You can approach this however you wish, but making use of deltaTime is recommended. This will return the time in seconds since the last frame, so multiplying whatever rate of time increase you specify by this allows the time in trueSKY to be updated smoothly. In this example I have created a public "timeToAdd" float, which is set in the editor to 0.01666 (1 / 60), making one trueSKY day equivalent to one real-time minute.

`
private trueSKY tS;
public float timeToAdd;
public float startTime;
void Start ()
{
tS = trueSKY.GetTrueSky ();
tS.time = startTime;
}
void Update ()
{
tS.time += timeToAdd * Time.deltaTime;
}       
`
If you press play now you will see the clouds move, along with the sun, moon and the stars (depending on the time of day).

</div>



