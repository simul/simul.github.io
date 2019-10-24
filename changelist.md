---
title: Change List
layout: reference
weight: 120
---


Version HEAD
---
Thu 24 Oct : Small doc fix  
Thu 24 Oct : UI improvements to timeline.  
Thu 24 Oct : Image Fixing Docs  
Thu 24 Oct : Image Fix for Docs  
Thu 24 Oct : Doc Updates  
Thu 24 Oct : Doc Updates  
Thu 24 Oct : Doc Update  
Tue 22 Oct : Undo works again in Sky Sequencer.  
Tue 22 Oct : Fix sky keyframe sequence being set to invalid values on undo.  
Sat 19 Oct : Add missing shaders in installers.  
Fri 18 Oct : Fix Crash with sequencer  
Thu 17 Oct : Fix Xbox error by reverting to original. However, whatever this change was put in to fix will presumably still be broken.  
Thu 17 Oct : Removed duplicate UpdateUI(...) definition. Fixed water crash when setting dimension with invalid ID.  
Wed 16 Oct : Attempted fix of merge errors  
Wed 16 Oct : .  
Wed 16 Oct : Reverted sfx project changes  
Wed 16 Oct : UnitySetRenderFrameValues(): Checks for nullptr in colourTexture. Added UpdateUI() and default initialiser for ExternalTexture.  
Wed 16 Oct : Added some water reflection quality parameters  
Wed 16 Oct : Cloud shadow texture size not passed via enum system.  
Tue 15 Oct : further fixes  
Tue 15 Oct : Fixing gets and sets for keyframes and layers.  
Tue 15 Oct : Sky is cleared when SetSequence is passed a sequence with no data.  
Sat 12 Oct : Fixed binary path bug.  
Fri 11 Oct : Fix SHADERBIN_SOURCE deploy  
Fri 11 Oct : Update to Unity Sky Sequencer UI.  
Fri 11 Oct : Created an UpdateUI function for Unity to call, for processing of QT events.  
Fri 11 Oct : Camera constants changes restored.  
Fri 11 Oct : Fixed shaderbin not being copied from the build directory  
Fri 11 Oct : Fix Unity Sequencer UI disappearance.  
Mon 07 Oct : Fix Sfx build for PS4.  
Fri 04 Oct : PreprocessLexer and PreprocessParser were renamed to PreprocessorLexer and PreprocessorParser a while back.  
Sun 29 Sep : Fail to blank texture if compressed format not supported.  
Thu 26 Sep : Minor fixes and cleanup  
Thu 26 Sep : Essential RenderPlatform fix for D3D12.  
Wed 25 Sep : Add interleaved option to layoutdesc.  
Tue 24 Sep : Fix D3D11 load binary shader.  
Tue 24 Sep : Shaderbinarypaths as list.  
Tue 24 Sep : Temp fix for hidden UI.  
Tue 24 Sep : Xbox Cmake fix.  
Tue 24 Sep : Small Doc Update  
Tue 24 Sep : Directxtex cmake.  
Tue 24 Sep : Revert debug.sfx  
Tue 24 Sep : Fix file loader virtual def to match UE version.  
Sat 21 Sep : Xbox /DEBUG in link options.  
Wed 18 Sep : Xbox One Cmake fixes.  
Wed 11 Sep : XboxOne ptr.  
Wed 11 Sep : Xbox Cmake fixes.  
Wed 11 Sep : Fix build on PS4.  
Tue 10 Sep : Long timeout for Sfx compiler calls.  
Tue 10 Sep : Fixed timeout behaviour launching compilers from Sfx.  
Tue 10 Sep : .  
Mon 09 Sep : Cmake tidy-up.  
Mon 09 Sep : Fix Cmake fxc command usage.  
Mon 09 Sep : Cmake now builds OpenGL shaders, which are packed as glsl into the sfxb output.  
Mon 09 Sep : Added multiple binary paths for RenderPlatforms.  
Mon 09 Sep : CMake to use SIMUL_ variables : keep them better organized.  
Wed 04 Sep : Doc Update  
Mon 02 Sep : Fix for skyTimelineWidget  
Mon 02 Sep : Minor fix for overridden functions  
Fri 30 Aug : Minor fix to copy-pasting cloud keyframes  
Wed 28 Aug : Support BC compressed textures in D3D11.  
Tue 27 Aug : API fixes for rendering with vertex/index buffers.  
Tue 27 Aug : const correctness in DX11 buffer classes.  
Tue 27 Aug : Fix for GLSL/GLSL.json  
Mon 26 Aug : Add const where possible with Index and Vertex buffers.  
Fri 23 Aug : Fix deployment folders for shaderbin. API check for SFX-built shader effects: don't load Vulkan effects for DX12.  
Fri 23 Aug : Small changes to the water  
Fri 23 Aug : Fixes to Dx12 build and rearranging pixelformats.  
Thu 22 Aug : SimulQtWidgets and SequencerQtWidgets deployed via CMake to QTDIR/plugins/designer after build.  
Wed 21 Aug : More Doc updating  
Wed 21 Aug : Added template for cloud shape list in Cloud Layer Edit widget.  
Mon 19 Aug : Small fix for water reflections  
Fri 16 Aug : Updated Docs + removed hard coded directories from .markdoc  
Thu 15 Aug : ADd DirectX11Sample to CMake.  
Thu 15 Aug : Add Build_XboxOne.bat  
Tue 13 Aug : Fix Vulkan build paths.  
Mon 12 Aug : Build fix  
Mon 12 Aug : Very temp possible fix for build issues  
Sun 11 Aug : Fix build/exe path  
Sat 10 Aug : backslash not forward in properties file.  
Sat 10 Aug : CMake tweaks.  
Fri 09 Aug : glfw3.lib even in debug, not glfw3d.lib.  
Fri 09 Aug : glfw3.lib even in debug, not glfw3d.lib.  
Fri 09 Aug : Build.bat correction.  
Thu 08 Aug : Build.bat CMake QT_DIR  
Thu 08 Aug : Fix VSVER in build.bat  
Thu 08 Aug : Build.bat working with CMake.  
Thu 08 Aug : Add EXE_PATH to WindowsEnvironment.properties  
Thu 08 Aug : CMake and Build.bat  
Wed 07 Aug : More Documentation Updating  
Tue 06 Aug : Minor fix for lightning and water reflections  
Tue 30 Jul : Remove Effects11_win8sdk dep.  
Tue 30 Jul : Update that adds water masks, other small fixes  
Fri 26 Jul : More organisation and fixed internal Linking  
Wed 24 Jul : Reorganised doc files  
Fri 19 Jul : Flipped view distance for cloudDepthTexture in lightning.sfx for best depth lookup.  
Fri 19 Jul : Beginning start of documentation editing. Organisation, baseline for files.  
Fri 19 Jul : PS4 build fix  
Wed 17 Jul : All C++ projects now build in CMake, at least on Windows. MT and MD versions of effects11 and directxtex.  
Tue 16 Jul : .  

<hr>
