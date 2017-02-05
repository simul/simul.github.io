---
title: Unreal
layout: unreal
weight : 1
---
Getting started
---
* Register your username at [https://simul.co/register](https://simul.co/register)
* You'll find your licence at [simul.co/account](https://simul.co/account).
* After evaluating, to get an indie licence, you can buy or subscribe at [simul.co/account](https://simul.co/account). For all other licences, write to [contact@simul.co](mailto:contact@simul.co).

Installing the Plugin
---
For binary installations of Unreal Engine, binary trueSKY plugin installers are available from [https://simul.co/download](https://simul.co/truesky/download). For other versions, or if you have a version of Unreal Engine built from source, you will need to build the plugin.

**Important**
The stock binary version of Unreal does not deploy trueSKY files when packaging a project. You will see a black sky unless you deploy these files. See [Deployment](/unrealengine/Deploy) for instructions.

How to build it
---
* Enter your GitHub username at [https://simul.co/wp-admin/profile.php](http://simul.co/wp-admin/profile.php). This needs to be the same username connected to your Unreal Engine account at [www.unrealengine.com/settings](https://www.unrealengine.com/settings)

* Get the trueSKY UE4 fork from [GitHub](https://github.com/simul/UnrealEngine).
If you are using a different UE4 codebase, pull changes from the Simul fork, and merge.

* As described in the UE4 readme (in the root UnrealEngine directory), run Setup.bat and GenerateProjectFiles.bat from UE4. This will generate projects and the solution file (UE4.sln).

* The trueSKY binary libraries are *not* kept in the repository. This is because multiple trueSKY versions can work with the same Unreal version. So run the batch file Engine/Plugins/TrueSkyPlugin/GetBinaries.bat, passing the required trueSKY version as a parameter, e.g.

	GetBinaries.bat 4.1

* Use UE4.sln (UE4.vcxproj).
The UE4 project contains the "TrueSkyPlugin" folder in Engine/UE4/Plugins. The plugin is in the “[UE4]\Engine\Plugins\TrueSkyPlugin” directory in your UE4 installation.
The trueSKY binaries are in “[UE4]\Engine\Binaries\ThirdParty\Simul”. 
There are two trueSKY modules in the UE4 project – TrueSkyPlugin and TrueSkyEditorPlugin.

* Build the UE4 project in the "Development Editor" configuration.


How to run it
---
* Run UE4, either standalone or with the debugger.
The TrueSkyPlugin loads "TrueSkyUI_MD.dll" and "UE4PluginRenderInterface_MT.dll" from [UE4]\Engine\Plugins\TrueSkyPlugin\Binaries\Win64.

When you run the UE4 editor, the trueSKY plugin should be enabled by default. If not, go to Edit->Plugin and type "trueSKY" into the search box to find the plugin, and check its "enabled" box, to enable the trueSKY plugin.

  <a href="http://simul.co/wp-content/uploads/2014/07/UE4_ShowPlugins.png"><img src="http://simul.co/wp-content/uploads/2014/07/UE4_ShowPlugins-96x300.png" /></a>

  <a href="http://docs.simul.co/unrealengine/images/EnableTrueSKY.png"><img src="http://docs.simul.co/unrealengine/images/EnableTrueSKY.png" /></a>

After this, restart the editor.

Adding trueSKY to your level
---
* Press "Window->Add Sequence to Scene" -- this adds a TrueSkySequenceActor to the current level.

 <a href="http://simul.co/wp-content/uploads/2014/07/UE4_AddSequence.png"><img src="http://simul.co/wp-content/uploads/2014/07/UE4_AddSequence-81x300.png"/></a> 

This actor provides a reference to a sequence asset which is rendered. Choose the actor (from "World Outliner" window). In the "Details" window, set the reference to a TrueSky Sequence asset (see below for information on how to create one) in the "Active Sequence" property.

* To create a new TrueSkySequence asset, go to the "Content Browser" window. Press "New Asset" button (or do a right mouse click inside the window) to open an asset selection window. Choose "Miscellaneous / trueSKY Sequence Asset". A new asset will be created. Now you can rename/save/delete it.

<a href="http://simul.co/wp-content/uploads/2014/07/UE4_CreateAsset.png"><img src="http://simul.co/wp-content/uploads/2014/07/UE4_CreateAsset-233x300.png"/></a> 

 In the World Outliner, select your trueSKY sequence actor, and in the Details panel, set its Active Sequence to be the newly created asset: 
 
<a href="http://simul.co/wp-content/uploads/2014/07/Clipboard-Image-8.png"><img src="http://simul.co/wp-content/uploads/2014/07/Clipboard-Image-8-150x150.png"/></a> 

* To edit the TrueSkySequence asset just double-click on it:

<a class=" id=" title="" href="http://simul.co/wp-content/uploads/2014/07/Editor.png"><img src="http://simul.co/wp-content/uploads/2014/07/Editor-150x150.png" /></a>

* Enter your licence key in the Sequencer Window. This enables the window's editing functions.

* You can see changes to the properties (e.g. "preview") only if the edited asset is also assigned to the level's TrueSkySequenceActor! The trueSky plugin renderer uses only the asset which is referenced from that actor. If you are editing some other asset (which is not assigned to the TrueSky actor of the current level) then you won't see any visualization of it.

* If the TrueSkySequence asset has been changed, it can be saved to the disc by right-clicking on it and choosing "Save".

* You can edit any number of TrueSkySequence assets at once. However, only that which is also assigned to the active TrueSkySequenceActor is visible in editor's rendering window.

* To add clouds, double-click the trueSKY Sequence Asset and right-click on the timeline to add cloud keyframes.

* It may be that the default UE4 sky obscures the trueSKY image. Remove the Atmospheric Fog and Sky Sphere objects from your scene.

* For optimal performance, you can replace the default Skylight with the custom True Sky Light (found in Modes -> All Classes). Simply drag it into the scene to use. 

Multiple Sequence Actors and Transitions
---
You can have any number of trueSKY Sequence Actors in your level, all with different Sequence Assets assigned. In the Editor, check the Actor's property "Active in Editor" to see its weather state in the 3D view. In-game, the active Actor is determined by bounds. By default, a Sequence Actor is unbounded – it is always active. You can create bounding by adding a Box Collision component to the Actor.

<a href="http://docs.simul.co/unrealengine/images/AddBounds.png"><img src="http://docs.simul.co/unrealengine/images/AddBounds.png" alt="Add Bounds"/></a>

When this is done, the Actor will have limited bounds, and only affect the weather when the player is within the bounding box. You should have at most one unbounded trueSKY Sequence Actor in your level: this will apply when the player is not in the bounds of any other Sequence Actor.

To allow a smooth transition between weather states, you should adjust the Mode property of the Sky and Cloud Layers in all the Sequence Assets to allow a gradual transition between the different weather states. If you're using real-time transition (this is simplest), you can adjust the Interval in seconds (default 10.0) to determine how quickly the change takes place. Otherwise, use the Interval in days.

<a href="http://docs.simul.co/unrealengine/images/GradualMode.png"><img src="http://docs.simul.co/unrealengine/images/GradualMode.png" alt="Gradual Mode"/></a>

Profiling
---------
Use the Blueprint function GetProfilingText to get GPU and CPU timing numbers for trueSKY as a tree.

Modified Files in the Unreal Engine
--------
The following files in the UE source have been modified in the Simul branch.

	Engine\Source\Runtime\Renderer\Private\DeferredShadingRenderer.cpp
	Engine\Source\Runtime\Renderer\Public\RendererInterface.h
	Engine\Source\Runtime\Renderer\Private\RendererPrivate.h
	Engine\Source\Runtime\Renderer\Private\SceneRendering.cpp
	Engine\Source\Runtime\Renderer\Private\RendererScene.cpp

	Engine\Source\Programs\AutomationTool\Win\WinPlatform.Automation.cs

	Engine\Source\Programs\AutomationTool\PS4\PS4Platform.Automation.cs
	Engine\Source\Programs\AutomationTool\XboxOne\XboxOnePlatform.Automation.cs
	
	Engine\Source\Programs\UnrealBuildTool\PS4\UEDeployPS4.cs
	Engine\Source\Programs\UnrealBuildTool\XboxOne\XboxOneDeploy.cs


Further Information
---------

* [trueSKY Tutorial: Unreal Engine 4](http://docs.simul.co/unrealengine/Tutorial.html)
* [The Sequencer](http://docs.simul.co/reference/man_8_sequencer.html)
* [Driving trueSKY via Blueprint](http://docs.simul.co/unrealengine/Blueprint.html)
* [The trueSKY Renderer](http://docs.simul.co/reference/man_4_rendering.html)



Next: <a href="/unrealengine/Tutorial">Tutorial</a>