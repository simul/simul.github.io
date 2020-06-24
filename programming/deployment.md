---
title: Deployment
layout: reference
weight: 40
---




trueSKY Deployment
========

<div class="ue4-specific">
For Unreal
------------

My Sky is black when I Package!
---------------------------------
With the latest change to 4.25 - Niagara particle systems are enabled by default. Because of this, if you are not using our UE4 Source branch, you will not be able to package unless you disable the Niagara. We have reached out to Epic to implement our fix, but are still waiting. 

To Disable, go to Edit->Plugins and then Search Built-in for Niagara. Then disable it. 

If you are using your own UE4 Source, there are two files that need to be changed. Our pull request is at - https://github.com/EpicGames/UnrealEngine/pull/6414


**Running Cooked Games**

The trueSKY DLL's are  located in [UE4]/Engine/Binaries/ThirdParty/Simul. When you package, cook, or launch a build, UE4 does not yet provide the capability to automatically deploy files to a build. Therefore on the Simul branch of UE4, this code has been inserted into [UE4]/Engine/Source/Programs/AutomationTool/Win/WinPlatform.Automation.cs (see line 43):



* SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Binaries/ThirdParty/Simul", SC.PlatformDir), "TrueSkyPluginRender_MT.dll", StageFilesSearch.TopDirectoryOnly);        
* if (!SC.StageTargetConfigurations.Contains(UnrealTargetConfiguration.Shipping))
*       SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Binaries/ThirdParty/Simul", SC.PlatformDir), "TrueSkyPluginRender_MT.pdb", StageFilesSearch.TopDirectoryOnly);
* SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/Resources"), "*.*", StageFilesSearch.TopDirectoryOnly);
* SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/Content"), "*.*", StageFilesSearch.TopDirectoryOnly);
* SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/shaderbin", SC.PlatformDir), "*.fxo", StageFilesSearch.TopDirectoryOnly);



To rebuild the tools, build the UE4 solution in the "Development" configuration. This will recreate the executables located in the [UE4]/Engine/Binaries/DotNET directory.

If you're using the binary distribution of UE with the trueSKY plugin binary installer, you won't have this file: you'll need to copy the resources manually. After packaging, find the "Engine" directory in your game, and copy:


* (UE)/Engine/Binaries/ThirdParty/Simul to (GAME)/Engine/Binaries/ThirdParty/Simul
* (UE)/Engine/Plugins/TrueSkyPlugin/Resources to (GAME)/Engine/Plugins/TrueSkyPlugin/Resources
* (UE)/Engine/Plugins/TrueSkyPlugin/Content to (GAME)/Engine/Plugins/TrueSkyPlugin/Content
* (UE)/Engine/Plugins/TrueSkyPlugin/shaderbin to (GAME)/Engine/Plugins/TrueSkyPlugin/shaderbin

Now you are ready to run your game with trueSKY.


**Console Deployment**

As the console automation files are not in the Git repository, it is not possible to distribute the necessary changes. So you must modify by hand the console Platform.Automation.cs files, in the function GetFilesToDeployOrStage(), add:

###### 4.18 and above (XBoxOne):
~~~~~~~~~~~~~~~~~~~~~~~
/// BEGIN trueSKY Additional code
SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Binaries/ThirdParty/Simul", SC.PlatformDir), "TrueSkyPluginRender_MD.dll", StageFilesSearch.TopDirectoryOnly);
if(!SC.StageTargetConfigurations.Contains(UnrealTargetConfiguration.Shipping))
SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Binaries/ThirdParty/Simul", SC.PlatformDir), "TrueSkyPluginRender_MD.pdb", StageFilesSearch.TopDirectoryOnly);
SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/Resources"), "*.*", StageFilesSearch.AllDirectories);
SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/Content"), "*.*", StageFilesSearch.AllDirectories);
SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/shaderbin",SC.PlatformDir), "*.*", StageFilesSearch.AllDirectories);
/// END trueSKY Additional code         
~~~~~~~~~~~~~~~~~~~~~~~


###### 4.18 and above (PS4):
~~~~~~~~~~~~~~~~~~~~~~~
/// BEGIN trueSKY Additional code
SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Binaries/ThirdParty/Simul", SC.PlatformDir), "trueskypluginrender.prx", StageFilesSearch.TopDirectoryOnly);
SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/Resources"), "*.*", StageFilesSearch.AllDirectories);
SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/textures"), "*.*", StageFilesSearch.AllDirectories);
SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/Content"), "*.*", StageFilesSearch.AllDirectories);
SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/shaderbin", SC.PlatformDir), "*.*", StageFilesSearch.AllDirectories);
/// END trueSKY Additional code
~~~~~~~~~~~~~~~~~~~~~~~
</div>

<div class="unity-specific">

Unity
----------

Coming Soon
</div>
