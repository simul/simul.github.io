---
title: Tutorial
layout: unreal
weight : 7
---

Tutorial
========

Initial Configuration
-------------------------

If you haven't already, please see [Getting Started](https://docs.simul.co/unrealengine/) for information on how to install, build and run the plugin in Unreal Engine 4. 

Whether you have installed trueSKY via the Git Repo or via the binary installer, start by creating and opening a new project. When you first open the scene you will probably see the default Sky and Fog folder in the World Outliner. If so, then it is important to remove the contents of this folder (this may require deleting them individually and not just deleting the folder itself), as the default Fog and Sky sphere can cause issues with trueSKY. 

<a href="https://docs.simul.co/unrealengine/images/DeleteSkyFog.png"><img src="https://docs.simul.co/unrealengine/images/DeleteSkyFog.png" alt="Blueprint"/></a> 

After doing this, you should see the default atmospherics disappear, leaving a black sky. Now we can insert a trueSKY Sequence Actor. To do so, click Window -> Add Sequence to Scene. Find the TrueSkySequenceActor in the World Outliner, and in the Details Panel, click on Active Sequence. If there are no existing trueSKY sequences to load, we can create a new one by clicking the Create New Asset option. Name this whatever you wish and find a location in which to save it. Once done, it will be automatically assigned to the TrueSkySequenceActor. You can change the sequence currently in use at any time by clicking on the Active Sequence option. 


Adding Clouds
-------------------------

The sky in your scene should now appear blue, but will lack clouds or anything interesting. To liven up the scene, find your newly created sequence asset in the Content Browser and double click it. This will load the trueSKY Sequencer. If you haven't already, input your license key into the sequencer to allow full access. [Read more about the Sequencer here](https://docs.simul.co/reference/man_8_sequencer.html). For now however we will just add some basic clouds to the scene. To do this, right click in the 3D Clouds section of the timeline and click "New cloud keyframe".  

<a href="https://docs.simul.co/unrealengine/images/AddCloudKF.png"><img src="https://docs.simul.co/unrealengine/images/AddCloudKF.png" alt="Blueprint"/></a>

Select the keyframe and try experimenting with the values. You can also use the Presets on the left hand side of the sequencer to select predefined arrangements. Be sure to set the Wind Speed value to something greater than 0, if you wish to see the clouds move (once time is being progressed). To further enhance the scene, you can also add a keyframe for 2D clouds, by right clicking on the 2D Clouds area and creating a keyframe in the same manner as before. [Read more about both kinds of clouds here](https://docs.simul.co/unrealengine/Clouds.html). In this example I have set the Wind Speed to 1, raised the cloudbase to 5.0 and increased cloudiness by to 0.6. I have also added a 2D cloud keyframe with default settings. 

<a href="https://docs.simul.co/unrealengine/images/Scene1.png"><img src="https://docs.simul.co/unrealengine/images/Scene1.png" alt="Blueprint"/></a>


Progressing Time
-------------------------

Though we can now see clouds, you will notice that they aren't moving, even if the Wind Speed has been increased above 0. To get some movement in the scene we can use the Blueprint system to drive trueSKY. To do this we will want to progress the trueSKY time. Open up the level blueprint and create an Event Tick event. Next create a float variable to store the current time, then connect the Event Tick event to a Setter for this variable. For framerate independence, we should use Delta Time to progress the trueSKY time. To do this, create a Getter for the Time variable and then a "Float + Float" function and a "Float / Float" function. Connect the Delta Seconds pin from the Event Tick event to the divide function, then connect the output from this to the addition function. Next connect the Time Getter to the other input pin of the addition function, and then connect the ouput pin of the addition function to the Time Setter. Lastly find the trueSKY Set Time function and connect the Time Setter to this, and pass the Time variable output pin to the Set Time function's float input pin. 

<a href="https://docs.simul.co/unrealengine/images/SettingTime.png"><img src="https://docs.simul.co/unrealengine/images/SettingTime.png" alt="Blueprint"/></a>

If you press Play/Simulate now you will see the clouds move and the day turn to night very quickly. This is because we are not scaling the raw Delta Time input just yet, so every real time second is progressing trueSKY by one whole day. It is unlikely that you would want the days to move so quickly, so try replacing the second argument in the division function that is receiving the Delta Time input, with a more suitable value. For example, a value of 60 will equate one trueSKY day to 60 seconds, a value of 3600 would equal an hour and a value of 86400 (60 x 60 x 24) would simulate a real day. In this example I am using 600, so a full day will pass in ten minutes. You may find that you need to change the Wind Speed variable to suit the rate at which you are changing time. Additionally, if you want the scene to start at a specific time, try changing the default value of the Time float variable (where 0.0 is the start of the first day, 0.5 is noon on the first day and 1.0 is the start of the second day). 


Implementing Lighting
-------------------------

Now that time is moving and the clouds are behaving properly, the next element of trueSKY to configure is the lighting. By default your scene should already have a directional light present. Ensure that its Mobility (Details Panel -> Transform) is set to Movable. Open up the TrueSkySequenceActor and assign the directional light under the Lighting group. You can also apply a multiplier to each to scale the brightness of sunlight and moonlight.

<a href="https://docs.simul.co/unrealengine/images/DirectionalLight.png"><img src="https://docs.simul.co/unrealengine/images/DirectionalLight.png" alt="DirectionalLight"/></a>

Ambient Light with TrueSkyLight
-------------------------------

The default Unreal Engine Skylight is not dynamic. To get the most out of trueSKY it is advisable to replace this with a TrueSkyLight (Modes -> All Classes). Do not manually capture the cubemap when using this Skylight: it works automatically.
You can adjust the update frequency (default 4 means every four frames the TrueSkyLight is updated), and the Diffuse and Specular brightness - it's recommended not to change these dynamically, but choose in advance the values that work best. The Blend property controls how smoothly (and thus, slowly) the light changes over time.

It's also worth rembering to set the Render Textures for Loss, Inscatter and Cloud Visibility (these are important when rendering transparent materials alongside trueSKY). 

<a href="https://docs.simul.co/unrealengine/images/RTConfigure.png"><img src="https://docs.simul.co/unrealengine/images/RTConfigure.png" alt="Blueprint"/></a> 

With that your scene is now fully configured and should be showing moving clouds and correct lighting. Of course this is a very basic scene, so to learn more and get the most out of trueSKY for Unreal, please see the further information section below.

Cloud Shadows
-------------
To enable cloud shadows, connect the render texture "CloudShadowRT" to the "Cloud Shadow" slot of the trueSKY Sequence Actor.
Assign the material function M_LightFunction to the "Light Function Material" slot of your Directional Light. To increase the range of the shadows, adjust the Directional Light's Dynamic Shadow Distance, under Cascaded Shadow Maps.

Rain Masking
------------
To prevent rain from falling in covered areas, create a SceneCapture2D actor, and give it a texture target that's contains only a red channel (e.g. RainDepthRT from the trueSKY content). Make the Capture Source "SceneDepth in R". You don't need to enable "Capture Every Frame" unless you expect the geometry to change.
<a href="https://docs.simul.co/unrealengine/images/SceneCapture2DProperties.png"><img src="https://docs.simul.co/unrealengine/images/SceneCapture2DProperties.png" alt="Blueprint"/></a> 

Rotate the Scene Capture 2D to face upwards.

<a href="https://docs.simul.co/unrealengine/images/RainMaskView.png"><img src="https://docs.simul.co/unrealengine/images/RainMaskView.png" alt="Blueprint"/></a> 

On the trueSKY Sequence Actor, assign the Scene Capture 2D actor to the Rain Mask SceneCapture property. Now, rain will only appear where there is no cover above the Scene Capture actor.

<a href="https://docs.simul.co/unrealengine/images/PrecipitationProperties.png"><img src="https://docs.simul.co/unrealengine/images/PrecipitationProperties.png" alt="Blueprint"/></a> 

Skyboxes
--------
You can use trueSKY to create stationary skyboxes, to produce procedural weather states with no impact on GPU or CPU usage. To do this, add a trueSKY Sequence Actor as normal, and set its Visible flag to **false**. Add a TrueSkyLight also. In the TrueSky content folder, find the Blueprint Class, SM_SkySphere, and add an instance to the scene. This adds a background skybox using the BackgroundCube Mesh and the material StaticSky_M.

<a href="https://docs.simul.co/unrealengine/images/SM_SkySphere_Construction.png"><img src="https://docs.simul.co/unrealengine/images/SM_SkySphere_Construction.png" alt="SM_SkySphere_Construction.png"/></a>

The material uses a lookup into the cubemap as the Emissive colour.

<a href="https://docs.simul.co/unrealengine/images/StaticSky_Material.png"><img src="https://docs.simul.co/unrealengine/images/StaticSky_Material.png" alt="StaticSky_Material.png"/></a> 

And to update the skybox, call the trueSKY Blueprint function Render to Cubemap, shown here updating StaticSkyboxRT when Tab is pressed.

<a href="https://docs.simul.co/unrealengine/images/RenderToCubemap.png"><img src="https://docs.simul.co/unrealengine/images/RenderToCubemap.png" alt="RenderToCubemap.png"/></a>

The TrueSkyLightComponent input would be the component from your TrueSkyLight Actor in the scene. The resulting skybox will be sampled from the same position as the TrueSkyLight ambient lighting, which will also be resampled, along with all other standard TrueSKY updates, when Render To Cubemap is called.

Further Information
--------------
 
* [The Sequencer](https://docs.simul.co/sequencer.html) 
* [Driving trueSKY via Blueprint](https://docs.simul.co/unrealengine/Blueprint.html)  
* [trueSKY Developer Manual](https://docs.simul.co/ref.html)


Next: <a href="/unrealengine/Clouds">Clouds</a>