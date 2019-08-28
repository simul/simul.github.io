---
title: Change List
layout: reference
weight: 120
---


Version HEAD
---
Tue 27 Aug : API fixes for rendering with vertex/index buffers.  
Tue 27 Aug : const correctness in DX11 buffer classes.  
Tue 27 Aug : Fix for GLSL/GLSL.json  
Mon 26 Aug : Add const where possible with Index and Vertex buffers.  
Fri 23 Aug : Fix deployment folders for shaderbin. API check for SFX-built shader effects: don't load Vulkan effects for DX12.  
Fri 23 Aug : Small changes to the water  
Fri 23 Aug : Fixes to Dx12 build and rearranging pixelformats.  
Thu 22 Aug : SimulQtWidgets and SequencerQtWidgets deployed via CMake to QTDIR/plugins/designer after build.  
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
Mon 15 Jul : Updated CMakeList directories for faster Cmake initial generation  
Sun 14 Jul : Fix htmlproofer call - needs correct working dir. Fix name of ref.md target. Fix Help files in Simul.sln  
Fri 12 Jul : Slight fix to reference .md  
Fri 12 Jul : Updated docs sidebar order, fixed index issue to allow index on home page  
Fri 12 Jul : Added DirectXTex and effects11 to CMake, updated docs in Help folder and start of editing comments for the docs  
Wed 10 Jul : Add Simul.markdoc  
Tue 09 Jul : Fix for Errno_Check  
Thu 04 Jul : Fully-working on Linux  
Wed 03 Jul : Added Effects11 and DirectxTex to CMake.  
Wed 03 Jul : Improved deployment py script.  
Fri 28 Jun : Fix for Windows build. Amended ERRNO_CHECK and DebugBreak().  
Fri 28 Jun : ERRNO_CHECK fixed.  
Fri 28 Jun : Linux build fixes: Vulkan Sample and plugin now building.  
Tue 18 Jun : Linux build fixes  
Tue 18 Jun : Cmake version build fixes.  
Mon 17 Jun : Minor update to the snow pixel shader.  
Fri 14 Jun : Minor fix to stop values that would break the water renderer from being passed to it  
Fri 14 Jun : Initial commit for Water reflections  
Thu 13 Jun : Fix Qt plugin search for Unity only.  
Thu 13 Jun : GeneratedFiles includes for SequencerQtWidgets in TrueSkyUI_x64_v140.vcxproj  
Thu 13 Jun : Add GenerateFiles include dir.  
Thu 13 Jun : Improve cloud window UI.  
Thu 13 Jun : Fix long pause at UI startup due to Qt search path.  
Fri 31 May : OpenGL and D3d12 error fixes.  
Fri 31 May : Fix water shutdown crash.  
Fri 31 May : Deployment py fixes.  
Thu 30 May : Add RenderDelegate.h  
Thu 30 May : Add RenderDelegate.h  
Thu 30 May : Don't invalidate pixelShaders from Effect: RenderPlatform is responsible for this.  
Thu 30 May : Fix for buoyancy objects not sampling the surface at the correct location. Also contains a couple of minor fixes, and a temporary fix for DX12 not seeing the profile buffer offset and direction arrays  
Thu 30 May : Fix for OpenGL SFX compilation. New SfxConfig parameter: identicalIOBlocks.  
Wed 29 May : Update Unity plugin api to new structs.  
Wed 29 May : water.sfx compiles for Vulkan.  
Wed 29 May : Update ExternalTexture definition and add full ExternalTexture structs to RenderFrameStruct, more robust for different API's.  
Tue 28 May : Add sfxb shader bins.  
Tue 28 May : Fix broken effect shader load.  
Tue 28 May : Wrap up shader binaries in sfxb for Vulkan and D3D12.  
Tue 28 May : Shader binaries lumped together in sfxb file - if -w is used in sfx.exe.  
Mon 27 May : PS4 API update and build fix.  
Mon 27 May : Delayed destruction for effects to prevent destroying in-use API objects when recompiling. Update skylight struct.  
Fri 24 May : Updated LightningRenderer.cpp to use MSAA. Updated CloudRenderer.cpp RenderRainMapTexture() and RenderCloudShadowTexture() Refined Debug Overlays due to new mono spaced font. Fix OpenGL cloud shadows. Fix rain map lookups in SFX/rain.sfx OverrideWind added back.  
Thu 23 May : Updated Rain shader using Reflection and Refraction. CloudRenderer.cpp split function into RenderCloudShadowTexture() and RenderRainMapTexture(). Precipitation Regions dimension are drawn onto the rain map. VolumeQueryResult::rain_to_snow is updated from rain map. simul_clouds.sl split function GetRainAtOffsetKm() GetRainToSnowAtOffsetKm(). quaternion.sl quat_from_axis_angle_radians() and quat_from_axis_angle_degrees().  
Mon 20 May : QT fix  
Mon 20 May : CloudKeyframeEditWidget fix  
Mon 20 May : Fix for Simple DX11 and DX12 renderer examples  
Mon 20 May : VR fix for water, other small fixes  
Fri 17 May : Fix Vulkan shader build.  
Fri 17 May : OverrideWind now works to allow precise positioning of 3D cloud layers. Click and drag in Cloud Window editor. Global wind is now a cosmetic flow, doesn't affect cloud positions.  
Fri 17 May : New 16x11 monospaced font texture. D3D11 loads textures as texture instead of as SRV.  
Wed 15 May : Pass framenumber to DisplaySurface to get consistent framenumbers for multiple windows.  
Mon 13 May : Minor fix to CloudWindow UI layout and colours. Minor fix for SetCloudConstants() and FillInQueries(). SetPrecipitationCentre() removed.  
Mon 13 May : Fix sequencer standalone crash.  
Mon 13 May : Fix shader build path for non-Cmake builds.  
Sun 12 May : Fix Xbox refs to deleted shaders.  
Sun 12 May : Project fix for DirectX12Sample_x64_v140.vcxproj  
Sat 11 May : Dx12 sample build  
Fri 10 May : Fix stringFormat error in Sfx. Prevent at least some of the spurious console output from Flex in preprocessor.lpp.  
Fri 10 May : Fix cloud mip generation. CMake build improvements.  
Thu 09 May : Minor updates to simul_clouds.sl GetRainAtOffsetKm(). The rain map is not re-drawn to reflect the precipitation region.  
Wed 08 May : New Colour Scheme for Cloud Window to improve clarity. Fix for incorrect Precipitation Region position in edge cases. Clouds/BaseGpuCloudGenerator.h SetPrecipitationCentre() removed.  
Wed 08 May : New Colour Scheme for Cloud Window is improve clarity. Fix for incorrect Precipitation Region position in edge cases. Clouds/BaseGpuCloudGenerator.h SetPrecipitationCentre() removed.  
Fri 03 May : Fix for Rain and Rain Streaks appearing at altitudes.  

<hr>
