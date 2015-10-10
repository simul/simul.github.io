---
title: Building the Source
layout: manual
---
If you have a git source code distribution of trueSKY, you can build it by running Setup.bat from within the Simul directory.

Engine Plugins
---
There are two plugin projects that can be incorporated in game engines such as Unity or Unreal Engine.  These are currently located in Simul/Plugins/UE4, but can be used in any game engine with the appropriate wrapper code. The rendering project is  Simul/Plugins/UE4/PluginRenderInterface/UE4Plugin.vcxproj: this builds TrueSkyPluginRender_MT.dll, which is a statically-linked DLL, using the static runtimes (on Windows, other platforms use the standard runtimes).

The project Simul/Plugins/UE4/TrueSkyUI/TrueSkyUI build TrueSkyUI_MD.dll, which is a dynamically-linked DLL requiring the Simul core DLL's, and several Qt DLL's (these can be downloaded from the Simul website).

To deploy the compiled libraries to an engine distribution, we use the Python 3 script CopyToTargetDir.py, whch is a member of the plugin rendering project, as a custom build step. The destinations to deploy to are determined by a file called truesky_setup.json in your user home directory (C:/Users/${USERNAME}).

<hr>
Next: \ref 09-Changelist.md