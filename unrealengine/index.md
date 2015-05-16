---
title: Home
layout: unreal
---
Getting started
---
* Register your username at [https://simul.co/register](https://simul.co/register)
* You'll find your licence at [simul.co/account](https://simul.co/account).
* After evaluating, to get a full licence head to [simul.co/truesky-ue4](https://simul.co/truesky-ue4).

How to build it
---
* Enter your GitHub username at [https://simul.co/wp-admin/profile.php](http://simul.co/wp-admin/profile.php). This needs to be the same username connected to your Unreal Engine account at [www.unrealengine.com/settings](https://www.unrealengine.com/settings)
* Get the trueSKY UE4 fork from [GitHub](https://github.com/simul/UnrealEngine).
If you are using a different UE4 codebase, pull changes from the Simul fork, and merge.

* As described in the UE4 readme (in the root UnrealEngine directory), Run Setup.bat and GenerateProjectFiles.bat from UE4. This will generate projects and the solution file (UE4.sln)

* Use UE4.sln (UE4.vcxproj).
The UE4 project contains the "TrueSkyPlugin" folder in Engine/UE4/Plugins.The plugin is in the “[UE4]\Engine\Plugins\TrueSkyPlugin” directory in your UE4 installation.
The trueSKY binaries are in “[UE4]\Engine\Binaries\ThirdParty\Simul”. 
There are two trueSKY modules in the UE4 project – TrueSkyPlugin, and TrueSkyEditorPlugin.


* Build the UE4 project in the "Development Editor" configuration.



How to run it
---
* Run UE4, either standalone or with the debugger.
The TrueSkyPlugin loads "TrueSkyUI_MD.dll" and "UE4PluginRenderInterface_MT.dll" from [UE4]\Engine\Plugins\TrueSkyPlugin\Binaries\Win64.
TrueSkyUI_MD.dll further loads the Qt libraries. For that, the PATH environment-variable is extended temporarily by the plugin to include "Engine/Binary/ThirdParty/Simul/Win64"
* When the UE4 editor is running, go to Windows->Plugin and type "trueSKY" into the search box to find the plugin, and check its "enabled" box, to enable the TrueSky plugin.

  <a href="http://simul.co/wp-content/uploads/2014/07/UE4_ShowPlugins.png"><img src="http://simul.co/wp-content/uploads/2014/07/UE4_ShowPlugins-96x300.png" /></a>

  <a href="http://docs.simul.co/unrealengine/images/EnableTrueSKY.png"><img src="http://docs.simul.co/unrealengine/images/EnableTrueSKY.png" /></a>

Restart the editor! The plugin adds the "TrueSky" section into the "Window" menu.

* Press "Window->Add Sequence to Scene" -- this adds a TrueSkySequenceActor to the current level.

 <a href="http://simul.co/wp-content/uploads/2014/07/UE4_AddSequence.png"><img src="http://simul.co/wp-content/uploads/2014/07/UE4_AddSequence-81x300.png"/></a> 

This actor provides a reference to a sequence asset which is rendered. Choose the actor (from "Scene Outliner" window). In the "Details" window, set the reference to a TrueSky Sequence asset (read below how to create one) in the "Active Sequence" property.

* It may be that the default UE4 sky obscures the trueSKY image. Remove the Atmospheric Fog and Sky Sphere objects from your scene.

* To create a new TrueSkySeqence asset, go to the "Content Browser" window. Press "New Asset" button (or do a right mouse click inside the window) to open an asset selection window. Choose "Miscellaneous / TrueSky Sequence Asset". A new asset will be created. Now you can rename/save/delete it.

<a href="http://simul.co/wp-content/uploads/2014/07/UE4_CreateAsset.png"><img src="http://simul.co/wp-content/uploads/2014/07/UE4_CreateAsset-233x300.png"/></a> 

 In the Scene Outliner, select your trueSKY sequence actor , and in the Details panel, set its Active Sequence to be the newly created asset: 
 
<a href="http://simul.co/wp-content/uploads/2014/07/Clipboard-Image-8.png"><img src="http://simul.co/wp-content/uploads/2014/07/Clipboard-Image-8-150x150.png"/></a> 

* To edit the TrueSkySequence asset just double-click on it:

<a class=" id=" title="" href="http://simul.co/wp-content/uploads/2014/07/Editor.png"><img src="http://simul.co/wp-content/uploads/2014/07/Editor-150x150.png" /></a>

* Enter your licence key in the Sequencer Window. This enables the window's editing functions.

* You can see changes to the properties (e.g. "preview") only if the edited asset is also assigned to the level's TrueSkySequenceActor! The trueSky plugin renderer uses only the asset which is referenced from that actor. If you are editing some other asset (which is not assigned to the TrueSky actor of the current level) then you won't see any visualization of it.

* Your changes in TrueSky properties are saved to the asset when you close the editing window. If the plugin has been compiled with autosaving on (#define ENABLE_AUTO_SAVING), it saves changes automatically every X seconds (currently X=4).

* If the TrueSkySequence asset has been changed, it can be saved to the disc by right-clicking on it and choosing "Save". You are also prompted about any unsaved assets when closing Unreal Editor.

* You can edit any number of TrueSkySequence assets at once. However, only that which is also set to the current level's TrueSkySequenceActor is visible in editor's rendering window.

* A TrueSkySequenceActor can be added to the level only through "Window->Add Sequence to Scene" menu command. This prevents more than one such actor being present on the level.

* To add clouds, double-click the TrueSKY Sequence Asset and right-click on the timeline to add cloud keyframes.

===================================

	Engine\Source\Runtime\Renderer\Private\DeferredShadingRenderer.cpp
	Engine\Source\Runtime\Renderer\Public\RendererInterface.h
	Engine\Source\Runtime\Renderer\Private\RendererPrivate.h
	Engine\Source\Runtime\Renderer\Private\SceneRendering.cpp

	Engine\Source\Runtime\XboxOne\XboxOneD3D11RHI\Private\D3D11Device.cpp

	Engine\Source\Programs\AutomationTool\PS4\PS4Platform.Automation.cs
	Engine\Source\Programs\AutomationTool\Win\WinPlatform.Automation.cs
	Engine\Source\Programs\AutomationTool\XboxOne\XboxOnePlatform.Automation.cs

Next: <a href="/unrealengine/Blueprint">Blueprint</a>