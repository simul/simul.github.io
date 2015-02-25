---
title: Home
layout: unreal
---
Deployment
---

**Running Cooked Games**

The trueSKY DLL's are  located in [UE4]/Engine/Binaries/ThirdParty/Simul. This makes them more accessible for standalone builds. When you deploy a build, these DLL's will no longer be accessible, and UE4 does not yet provide us with the capability to automatically deploy files to a build (e.g. in Game Launcher). Therefore this code has been inserted into [UE4]/Engine/Source/Programs/AutomationTool/Win/WinPlatform.Automation.cs (see line 43):
	
	/// BEGIN trueSKY Additional code
	StageExecutable("dll",SC,CommandUtils.CombinePaths(SC.LocalRoot,"Engine/Binaries/ThirdParty/Simul",SC.PlatformDir),"*.",true,null,null,true);		SC.StageFiles(StagedFileType.NonUFS,CombinePaths(SC.LocalRoot,"Engine/Binaries/ThirdParty/Simul/shaderbin"),"*.fxo",true,null,null,true);
	/// END trueSKY Additional code

To rebuild the tools, build the UE4 solution in the "Development" configuration. This will recreate the executables located in the [UE4]\Engine\Binaries\DotNET directory.

Now you are ready to run your game with trueSKY.