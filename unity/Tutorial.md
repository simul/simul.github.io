---
title: Tutorial
layout: unity
weight : 6
---
 
Tutorial
========

Initial Configuration
-------------------------

If you haven't already, please see [Getting Started](https://docs.simul.co/unity/) for information on how to install the plugin in Unity.

Either create a new project or open the provided sample project at: \Simul\Plugins\Unity\Project5. The easiest way to setup trueSKY is using the provided setup wizard. This can be found by clicking GameObject->Initialise trueSKY in Scene. Simply follow the steps to create and assign a trueSKY sequence asset, the TrueSkyCamera script, the trueSKY GameObject, the SimulSun script, the trueSKY Cubemap Probe and remove the default fog and skybox (recommended).

If your scene is appearing upside down, then navigate to the camera and the TrueSkyCamera script component, and change the Flipped View value. This will need to be true for Forward rendering and false for Deferred rendering. You should also assign the Inscatter, Loss and Cloud Visibility Render Textures (in the TrueSkyCamera component). You may also wish to attach the SimulMouseLook script to an object in the scene, so you can right click and drag on the Game window to move the camera.

<a href="https://docs.simul.co/unity/images/RenderTexturesAssigned.png"><img src="https://docs.simul.co/unity/images/RenderTexturesAssigned.png" alt="Tutorial"/></a> 

**Note:** Most settings in trueSKY can be manipulated using both the Sequencer and Unity scripting. This tutorial will uses a mixture of both to illustrate. You can [read more about the Sequencer here](https://docs.simul.co/sequencer.html) and [read more about scripting here](https://docs.simul.co/unity/Scripting.html).


Adding Clouds
-------------------------

Find your newly created sequence asset, or create a new one (right click->Create->trueSKY Sequence) and open it, to view the Sequencer. To add some basic clouds to the scene, right click in the 3D Clouds section of the timeline and click "New cloud keyframe".

<a href="https://docs.simul.co/unity/images/SequencerClouds.png"><img src="https://docs.simul.co/unity/images/SequencerClouds.png" alt="Tutorial"/></a>  

Select the keyframe and try experimenting with the values. You can also use the Presets on the left hand side of the sequencer to select predefined arrangements. Be sure to set the Wind Speed value to something greater than 0, if you wish to see the clouds move (once time is being progressed). To further enhance the scene, you can also add a keyframe for 2D clouds, by right clicking on the 2D Clouds area and creating a keyframe in the same manner as before. [Read more about both kinds of clouds here](https://docs.simul.co/unity/Clouds.html). In this example I have set the Wind Speed to 1, raised the cloudbase to 5.0 and increased cloudiness to 0.6. I have also added a 2D cloud keyframe with default settings. 

<a href="https://docs.simul.co/unity/images/CloudsScene.png"><img src="https://docs.simul.co/unity/images/CloudsScene.png" alt="Tutorial"/></a>  


Progressing Time
-------------------------

Time in trueSKY is measured such that 0.0 is midnight on the first day, 0.5 is noon on the first day, 1.0 is midnight on the second day and so on. To get movement in the scene we need to increment the trueSKY time. Navigate to the trueSKY object and you will see a field called "Speed". This will affect the rate at which time changes in trueSKY. By default this is set to 10, which will increment the time by .0001 each second. Setting this to 1000 for example will increment the time by .01 each second, and setting it to 100000 will make a trueSKY day pass every second. It is also possible to write your own scripts to change the time in trueSKY. This is done via by altering the trueSKY.Time value and you can approach this however you wish. However to achieve framerate-independence, it is advisable to make use of Time.deltaTime. 

To do so, first set the Speed variable in the trueSKY object to 0, so it doesn't affect the time. Create and attach a new script to the trueSKY object, and open it. The trueSKY time is changed via the trueSKY.Time value. You can approach this however you wish, but making use of deltaTime is recommended. This will return the time in seconds since the last frame, so multiplying whatever rate of time increase you specify by this allows the time in trueSKY to be updated smoothly. In this example I have created a public "timeToAdd" float, which is set in the editor to 0.01666 (1 / 60), making one trueSKY day equivalent to one real-time minute.

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

If you press play now you will see the clouds move, along with the sun, moon and the stars (depending on the time of day). 


Lighting
-------------------------
 
Assuming the trueSKY setup wizard was used, you should have the SimulSun script attached to a directional light. You can change the multiplier variable on this script to increase/decrease the sun's radiance. You can alter the brightness of the moon (and thus the brightness of the scene at night) via the Brightness Power value in the sky layer. This can be accessed in the sequencer by clicking on the "Sky" text on the left of the timeline. You can [read more about Brightness Power here](https://docs.simul.co/sequencer.html). You can also increase or decrease the brightness of the stars in the sky layer.

<a href="https://docs.simul.co/unity/images/BrightnessPower.png"><img src="https://docs.simul.co/unity/images/BrightnessPower.png" alt="Tutorial"/></a>  

Additionally it is possible to create point lights using trueSKY. To do so, access the trueSKY object and call:

		public void SetPointLight(int id, Vector3 pos, float min_radius, float max_radius, Vector3 irradiance)

This function will map point lights to the given id, so it can be called to both create a point light and to change the values of an existing point light.


With that your scene is now fully configured and functioning. Of course this is a very basic scene, so to learn more and get the most out of trueSKY for Unity, please see the further information section below.


Further Information
--------------
 
* [The Sequencer](https://docs.simul.co/sequencer.html)  
* [Scripting in trueSKY for Unity](https://docs.simul.co/unity/Scripting.html)
* [trueSKY Developer Manual](https://docs.simul.co/reference/)
* [Watch a video tutorial](https://www.youtube.com/watch?v=Eljf5CjZ4vc)


Next: <a href="/unity/Clouds">Clouds</a>
 