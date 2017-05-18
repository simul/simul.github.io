---
title: Source Code
layout: unreal
weight : 3
---

# Working with trueSKY from GitHub
* Enter your GitHub username at [https://simul.co/wp-admin/profile.php](http://simul.co/wp-admin/profile.php). This needs to be the same username connected to your Unreal Engine account at [www.unrealengine.com/settings](https://www.unrealengine.com/settings)

* Get the trueSKY UE4 fork from [GitHub](https://github.com/simul/UnrealEngine).
	* If you are using a different UE4 codebase, pull changes from the Simul fork, and merge.

* As described in the UE4 readme (in the root UnrealEngine directory):
	* Run `Setup.bat` to download all complementary UE4 dependencies.
	* Run `GenerateProjectFiles.bat` from the UE4 root directory; this will generate projects and the solution file (`UE4.sln`).

* The trueSKY binary libraries are *not* kept in the repository. This is because multiple trueSKY versions can work with the same Unreal version.
	* So run the batch file `Engine/Plugins/TrueSkyPlugin/GetBinaries.bat`, passing the required trueSKY version as a parameter, such as: `GetBinaries.bat 4.1`
	* This will auto-extract (upon your permission) trueSKY binaries (DLLs/LIBs) into: `[UE4]\Engine\Binaries\ThirdParty\Simul`
		* Binaries are then put into their platform-respective paths.
	* `GetBinaries.bat` will *also* download and extract the necessary trueSKY shader files (FXOs) into your TrueSkyPlugin directory under the `shaderbin` subfolder (these are also separated based on platform).

* Use UE4.sln (UE4.vcxproj).
	* The UE4 project contains the "TrueSkyPlugin" folder in Engine/UE4/Plugins (whether you installed via the installer or downloaded the source from GitHub).
		* There are two trueSKY modules in the UE4 project – **TrueSkyPlugin** and **TrueSkyEditorPlugin**. TrueSkyEditorPlugin is only built alongside an editor build of UE4.

* Build the UE4 project in the "Development Editor" configuration.

# Full Integration with Unreal Engine 4 Source Code
The following files in the UE source have been modified in the Simul fork of the UE4 repository. If you are merging trueSKY into a custom fork, you must ensure that the trueSKY modifications are carried over. In general, a good way to go about merging these changes is by using [Beyond Compare](https://www.scootersoftware.com) or [Perforce Merge](https://www.perforce.com/product/components/perforce-visual-merge-and-diff-tools) to easily do a diff across repos or, even simpler, between separate folders on your local machine.

## Core Engine Files:
* `Engine\Source\Runtime\Renderer\Private\DeferredShadingRenderer.cpp`
* `Engine\Source\Runtime\Renderer\Public\RendererInterface.h`
* `Engine\Source\Runtime\Renderer\Private\RendererPrivate.h`
* `Engine\Source\Runtime\Renderer\Private\SceneRendering.cpp`
* `Engine\Source\Runtime\Renderer\Private\RendererScene.cpp`

## Deployment File (Windows)
* `Engine\Source\Programs\AutomationTool\Win\WinPlatform.Automation.cs`

## Deployment Files (XBox One)
* `Engine\Source\Programs\UnrealBuildTool\XboxOne\XboxOneDeploy.cs`
* `Engine\Source\Programs\AutomationTool\XboxOne\XboxOnePlatform.Automation.cs`

## Deployment Files (Playstation 4
* `Engine\Source\Programs\AutomationTool\PS4\PS4Platform.Automation.cs`
* `Engine\Source\Programs\UnrealBuildTool\PS4\UEDeployPS4.cs`