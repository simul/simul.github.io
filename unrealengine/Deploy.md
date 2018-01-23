---
title: Deployment
layout: unreal
weight : 7
---

trueSKY Deployment
========

**Running Cooked Games**

The trueSKY DLL's are  located in [UE4]/Engine/Binaries/ThirdParty/Simul. When you package, cook, or launch a build, UE4 does not yet provide the capability to automatically deploy files to a build. Therefore on the Simul branch of UE4, this code has been inserted into [UE4]/Engine/Source/Programs/AutomationTool/Win/WinPlatform.Automation.cs (see line 43):

###### For 4.18 and above use:
	/// BEGIN trueSKY Additional code
	SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Binaries/ThirdParty/Simul", SC.PlatformDir), "TrueSkyPluginRender_MT.dll", StageFilesSearch.TopDirectoryOnly);        
	if (!SC.StageTargetConfigurations.Contains(UnrealTargetConfiguration.Shipping))
    	SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Binaries/ThirdParty/Simul", SC.PlatformDir), "TrueSkyPluginRender_MT.pdb", StageFilesSearch.TopDirectoryOnly);
	SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/Resources"), "*.*", StageFilesSearch.TopDirectoryOnly);
	SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/Content"), "*.*", StageFilesSearch.TopDirectoryOnly);
	SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/shaderbin", SC.PlatformDir), "*.fxo", StageFilesSearch.TopDirectoryOnly);
	/// END trueSKY Additional code
	
###### For other versions:
	/// BEGIN trueSKY Additional code
	SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Binaries/ThirdParty/Simul", SC.PlatformDir), "TrueSkyPluginRender_MT.dll", true, null, null,false);
	SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/Resources"), "*.*", true, null, null, false);
	SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/Content"), "*.*", true, null, null, false);
	SC.StageFiles(StagedFileType.NonUFS, DirectoryReference.Combine(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/shaderbin", SC.PlatformDir), "*.fxo", true, null, null, false);
	/// END trueSKY Additional code

To rebuild the tools, build the UE4 solution in the "Development" configuration. This will recreate the executables located in the [UE4]\Engine\Binaries\DotNET directory.

If you're using the binary distribution of UE with the trueSKY plugin binary installer, you won't have this file: you'll need to copy the resources manually. After packaging, find the "Engine" directory in your game, and copy:

* (UE)/Engine/Binaries/ThirdParty/Simul to (GAME)/Engine/Binaries/ThirdParty/Simul
* (UE)/Engine/Plugins/TrueSkyPlugin/Resources to (GAME)/Engine/Plugins/TrueSkyPlugin/Resources
* (UE)/Engine/Plugins/TrueSkyPlugin/Content to (GAME)/Engine/Plugins/TrueSkyPlugin/Content
* (UE)/Engine/Plugins/TrueSkyPlugin/shaderbin to (GAME)/Engine/Plugins/TrueSkyPlugin/shaderbin

Now you are ready to run your game with trueSKY.

**Console Deployment**

As the console automation files are not in the Git repository, it is not possible to distribute the necessary changes. So you must modify by hand the console Platform.Automation.cs files, in the function GetFilesToDeployOrStage(), add:

	/// BEGIN trueSKY Additional code
	SC.StageFiles(StagedFileType.NonUFS, CombinePaths(SC.LocalRoot, "Engine/Binaries/ThirdParty/Simul", SC.PlatformDir), "*.*", true, null, null, false);
	SC.StageFiles(StagedFileType.NonUFS, CombinePaths(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/Resources"), "*.*", true, null, null, false);
	SC.StageFiles(StagedFileType.NonUFS, CombinePaths(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/Content"), "*.*", true, null, null, false);
	SC.StageFiles(StagedFileType.NonUFS, CombinePaths(SC.LocalRoot, "Engine/Plugins/TrueSkyPlugin/shaderbin", SC.PlatformDir), "*.*", true, null, null, false);
	/// END trueSKY Additional code

		
Next: <a href="/unrealengine/Troubleshooting">Troubleshooting</a>