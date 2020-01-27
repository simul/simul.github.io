---
title: Ways to progress time
layout: reference
weight: 70
---





<div class="ue4-specific">

Via Blueprints
==============

The easiest way to progress time in Unreal is through blueprints. Within the trueSKY content folder there is a blueprint macro called "trueSKYDemo". If this is placed into your scene, time will progress. Below will walk through how it was made, and how to customise your own time altering blueprint.


Open up the level blueprint and create an Event Tick event. Next create a float variable to store the current time, then connect the Event Tick event to a Setter for this variable. For frame rate independence, we should use Delta Time to progress the trueSKY time. To do this, create a Getter for the Time variable and then a "Float + Float" function and a "Float / Float" function. Connect the Delta Seconds pin from the Event Tick event to the divide function, then connect the output from this to the addition function. Next connect the Time Getter to the other input pin of the addition function, and then connect the output pin of the addition function to the Time Setter. Lastly find the trueSKY Set Time function and connect the Time Setter to this, and pass the Time variable output pin to the Set Time function's float input pin. 

![](/images/unreal/settingtime.png)



If you press Play/Simulate now you will see the clouds move and the day turn to night very quickly. This is because we are not scaling the raw Delta Time input just yet, so every real time second is progressing trueSKY by one whole day. It is unlikely that you would want the days to move so quickly, so try replacing the second argument in the division function that is receiving the Delta Time input, with a more suitable value. For example, a value of 60 will equate one trueSKY day to 60 seconds, a value of 3600 would equal an hour and a value of 86400 (60 x 60 x 24) would simulate a real day. In this example I am using 600, so a full day will pass in ten minutes. You may find that you need to change the Wind Speed variable to suit the rate at which you are changing time. Additionally, if you want the scene to start at a specific time, try changing the default value of the Time float variable (where 0.0 is the start of the first day, 0.5 is noon on the first day and 1.0 is the start of the second day).

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



