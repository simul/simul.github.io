---
title: Tutorial
layout: unreal
weight : 7
---

If you haven't already, please see here [Getting Started](http://docs.simul.co/unrealengine/) for information on how to install, build and run the plugin in Unreal Engine 4. 

Whether you have installed trueSKY via the Git Repo or via the binary installer, start by creating and opening a new project. When you first open the scene you will probably see the default Sky and Fog folder in the World Outliner. If so, then it is important to remove the contents of this folder (this may require deleting them individually and not just deleting the folder itself), as the default Fog and Sky sphere can cause issues with trueSKY. 

<a href="http://docs.simul.co/unrealengine/images/DeleteSkyFog.png"><img src="http://docs.simul.co/unrealengine/images/DeleteSkyFog.png" alt="Blueprint"/></a> 

After doing this you should see the default atmospherics disappear, leaving a black sky. Now we can insert a trueSKY Sequence Actor. To do so, click Window -> Add Sequence to Scene. Find the TrueSkySequenceActor in the World Outliner, and in the Details Panel, click on Active Sequence. If there are no existing trueSKY sequences to load, we can create a new one by clicking the Create New Asset option. Name this whatever you wish and find a location in which to save it. Once done, it will be automatically assigned to the TrueSkySequenceActor. You can change the sequence currently in use at any time by clicking on the Active Sequence option. 

The sky in your scene should now appear blue, but will lack clouds or anything interesting. To liven up the scene, find your newly created sequence asset in the Content Browser and double click it. This will load the trueSKY Sequencer. If you haven't already, input your license key into the sequencer to allow full access. [Read more about the Sequencer here](http://docs.simul.co/reference/man_8_sequencer.html). For now however we will just add some basic clouds to the scene. To do this, right click in the 3D Clouds section of the timeline and click "New cloud keyframe". You can also add a 2D Cloud keyframe if you wish. 

<a href="http://docs.simul.co/unrealengine/images/AddCloudKF.png"><img src="http://docs.simul.co/unrealengine/images/AddCloudKF.png" alt="Blueprint"/></a>

Select the keyframe and try experimenting with the values. You can also use the Presets on the left hand side of the sequencer to select predefined arrangements. Be sure to set the Wind Speed value to something greater than 0, if you wish to see the clouds move (once time is being progressed). To further enhance the scene, you can also add a keyframe for 2D clouds, by right clicking on the 2D Clouds area and creating a keyframe in the same manner as before. [Read more about both kinds of clouds here]. In this example I have set the Wind Speed to 1, raised the cloudbase to 5.0 and increased cloudiness by to 0.6. I have also added a 2D cloud keyframe with default settings. 

<a href="http://docs.simul.co/unrealengine/images/Scene1.png"><img src="http://docs.simul.co/unrealengine/images/Scene1.png" alt="Blueprint"/></a>

Though we can now see some clouds, you will notice that they aren't moving, even if the Wind Speed has been increased above 0. To get some movement in the scene we can use the Blueprint system to drive trueSKY. To do this we will want to progress the trueSKY time. Open up the level blueprint and create an Event Tick event. Next create a float variable to store the current time, then connect the Event Tick event to a Setter for this variable. For framerate independence, we should use Delta Time to progress the trueSKY time. To do this, create a Getter for the Time variable and then a "Float + Float" function and a "Float / Float" function. Connect the Delta Seconds pin from the Event Tick event to the divide function, then connect the output from this to the addition function. Next connect the Time Getter to the other input pin of the addition function, and then connect the ouput pin of the addition function to the Time Setter. Lastly find the trueSKY Set Time function and connect the Time Setter to this, and pass the Time variable output pin to the Set Time function's float input pin. 

<a href="http://docs.simul.co/unrealengine/images/SettingTime.png"><img src="http://docs.simul.co/unrealengine/images/SettingTime.png" alt="Blueprint"/></a>

If you press Play/Simulate now you will see the the clouds move and the day turn to night very quickly. This is because we are not scaling the raw Delta Time input just yet, so every real time second is progressing trueSKY by one whole day. It is unlikely that you would want the days to move so quickly, so try replacing the second argument in the division function that is receiving the Delta Time input, with a more suitable value. For example, a value of 60 will equate one trueSKY day to 60 seconds, a value of 3600 would equal an hour and a value of 86400 (60 x 60 x 24) would simulate a real day. In this example I am using 600, so a full day will pass in ten minutes. You may find that you need to change the Wind Speed variable to suit the rate at which you are changing time. Additionally, if you want the scene to start at a specific time, try changing the default value of the Time float variable (where 0.0 is the start of the first day, 0.5 is noon on the first day and 1.0 is the start of the second day). 

Now that time is moving and the clouds are behaving properly, the next element of trueSKY to configure is the lighting. In trueSKY you can drive both the Sun and the Moon using the Blueprint system. By default your scene should already have a directional light present, but we will need two (one for the moon and one for the sun) so add another into the scene and rename them accordingly. Additionally, ensure that their Mobility (Details Panel -> Transform) is set to Movable. Open up the level blueprint and create references to these two directional lights. Create trueSKYSun and trueSKYMoon macros (right click -> TrueSky), connect them together and then ensure the Set Time node (assuming this was the last node in use) connects to the first of these two macros. Now connect the respective references to the input pins on the macros. You can also apply a multiplier to each to scale the brightness (in this example I have left the sun at 1.0 but doubled the moon's brightness).

<a href="http://docs.simul.co/unrealengine/images/SunAndMoon.png"><img src="http://docs.simul.co/unrealengine/images/SunAndMoon.png" alt="Blueprint"/></a>

An alternative, more compact way to set the time and drive the sun and moon is via the TrueSkyLighting Macro, as shown below. Feel free to use either method.  

<a href="http://docs.simul.co/unrealengine/images/AlternateTrueSkyLighting.png"><img src="http://docs.simul.co/unrealengine/images/AlternateTrueSkyLighting.png" alt="Blueprint"/></a> 

By default the Unreal Engine will place a Skylight in the scene. To get the most out of this it is advisable to navigate to the TrueSkySequence Actor and set the Skylight Cubemap RT. It's also worth rembering to set the Render Textures for Loss, Inscatter and Cloud Visibility (these won't be much use here, but are important when rendering transparent materials alongside trueSKY). Unfortunately the default Skylight isn't ideal and if you find that your scene isn't lighting accurately (for example, if it is too bright at night), try removing the default Skylight and dragging a True Sky Light (Modes -> All Classes) into the scene. This needs no configuration but there are two things to be aware of. Firstly, do not manually capture the cubemap when using this Skylight, as it will automatically capture. And secondly, remove the Skylight Cubemap RT from the TrueSkySequenceActor if it has been set (this is only for the default Skylight).

<a href="http://docs.simul.co/unrealengine/images/RTConfigure.png"><img src="http://docs.simul.co/unrealengine/images/RTConfigure.png" alt="Blueprint"/></a> 

With that your scene is now fully configured and functioning. Of course this is a very basic scene, so to learn more and get the most out of trueSKY for Unreal, please see the further information section below.

Further Information
--------------
 
* [The Sequencer](http://docs.simul.co/reference/man_8_sequencer.html) 
* [Driving trueSKY via Blueprint](http://docs.simul.co/unrealengine/Blueprint.html) 
* [Watch a video tutorial](https://www.youtube.com/watch?v=hE6qFzJgED4&feature=youtu.be&t=11m1s) 


Next: <a href="/unrealengine/Blueprint">Blueprint</a>