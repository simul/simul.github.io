---
title: Source Code
layout: reference
weight: 20
---




Working with trueSKY from GitHub
==============================

1: Access to Repository
----------------
1. Make sure you have created a Simul account. If not, head over [here](https://simul.co/register/) to register. 

2. On your account page, under the [Engines Tab](https://simul.co/account/engines/), there is an Unreal Engine Section. It asks for your GitHub Username. Input your GitHub Username and select Request Access. **This needs to be the same username connected to your Unreal Engine account at [unrealengine.com/account/connected](https://www.unrealengine.com/account/connected)**

3. You should now have access to our Unreal Repo at [github.com/simul/UnrealEngine](https://github.com/simul/UnrealEngine).

4. Fork our Unreal Repository. If you are not sure how to do this, GitHub has helpful information [here](https://help.github.com/en/articles/fork-a-repo). Alternatively, if you are using a different UE4 codebase, pull changes from the Simul fork, and merge.

2: Setup
----------
1. Follow the UE4 ReadME (in the root UnrealEngine directory), making sure you:
* Run `Setup.bat` to download all complementary UE4 dependencies.
* Run `GenerateProjectFiles.bat` from the UE4 root directory; this will generate projects and the solution file (`UE4.sln`).

2. The trueSKY binary libraries are *not* kept in the repository. This is because multiple trueSKY versions can work with the same Unreal version. So, to get the binary libraries, you can either:
* Run the batch file located in `Engine/Plugins/TrueSkyPlugin/GetBinaries.bat`, passing in the required trueSKY version as a parameter, for example as: `GetBinaries.bat 4.2`.
* Or, go to [our downloads page](https://simul.co/downloads) and get the appropriate TrueSkyUE4Binaries installer. Make sure to choose the correct Unreal Engine install directory.

3. In both cases this will auto-extract (upon your permission) trueSKY binaries (DLLs/LIBs) into `[UE4]/Engine/Binaries/ThirdParty/Simul`. Binaries are then put into their platform-respective paths, while the trueSKY shader files will go into your TrueSkyPlugin directory under the `shaderbin` subfolder (these are also separated based on platform).

3. Use UE4.sln to open the project in Visual Studio.The UE4 project contains the "TrueSkyPlugin" folder in Engine/UE4/Plugins (whether you installed via the installer or downloaded the source from GitHub). There are two trueSKY modules in the UE4 project – **TrueSkyPlugin** and **TrueSkyEditorPlugin**. TrueSkyEditorPlugin is only built alongside an editor build of UE4.

4. Build the UE4 project in the "Development Editor" configuration. Once this has compiled trueSKY will be present in your UE4 build.

You can learn how to add trueSKY to the level [here](tutorial#addtruesky).



Full Integration with Custom Unreal Source Code
-------------------------------------

The following files in the UE source have been modified in the Simul fork of the UE4 repository. If you are merging trueSKY into a custom fork, you must ensure that the trueSKY modifications are carried over. In general, a good way to go about merging these changes is by using [Beyond Compare](https://www.scootersoftware.com) or [Perforce Merge](https://www.perforce.com/product/components/perforce-visual-merge-and-diff-tools) to easily do a diff across repos or, even simpler, between separate folders on your local machine.

## Core Engine Files:
* `Engine/Source/Runtime/Renderer/Private/DeferredShadingRenderer.cpp`
* `Engine/Source/Runtime/Renderer/Public/RendererInterface.h or Engine/Source/Runtime/RenderCore/Public/RendererInterface.h`
* `Engine/Source/Runtime/Renderer/Private/RendererModule.h`
* `Engine/Source/Runtime/Renderer/Private/SceneRendering.cpp`
* `Engine/Source/Runtime/Renderer/Private/RendererScene.cpp`
* `Engine/Source/Runtime/Renderer/Private/TranslucentRendering.cpp`

## Deployment File (Windows)
* `Engine/Source/Programs/AutomationTool/Win/WinPlatform.Automation.cs`

## Deployment Files (XBox One)
* `Engine/Source/Programs/UnrealBuildTool/XboxOne/XboxOneDeploy.cs`
* `Engine/Source/Programs/AutomationTool/XboxOne/XboxOnePlatform.Automation.cs`

## Deployment Files (Playstation 4)
* `Engine/Source/Programs/AutomationTool/PS4/PS4Platform.Automation.cs`
* `Engine/Source/Programs/UnrealBuildTool/PS4/UEDeployPS4.cs`


