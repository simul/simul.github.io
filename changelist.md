---
title: Change Log
layout: reference
weight: 120
---


Version HEAD
---
Tue 18 Feb : Amended build fix for Linux.  
Tue 18 Feb : Revert TrueSkyLogo.psd as current version doesn't load.  
Tue 18 Feb : Include math.h for Linux.  
Tue 18 Feb : NSI/SkySequencer.nsi path fix.  
Tue 18 Feb : NOMINMAX for Xbox.  
Tue 18 Feb : Fix PS4 compile error.  
Tue 18 Feb : PS4 build  
Mon 17 Feb : Add Storm.h and cpp  
Mon 17 Feb : Updating default values.  
Mon 17 Feb : Move brightness multiplier calculation to GPU for more accuracy.  
Mon 17 Feb : Option for StaticRenderOverlays2 in Unity.cpp.  
Fri 14 Feb : Fix for D3D12 Rain streaks flicking.  
Thu 13 Feb : Sequencer nsi fixes.  
Tue 11 Feb : Remove SimulGeometry dependencies.  
Tue 11 Feb : Optional reading of Lat/Long. Removed window grid UI.  
Mon 10 Feb : Fix installers.  
Mon 10 Feb : Renamce toolchain.ORBIS.cmake to toolchain-ORBIS.cmake  
Mon 10 Feb : Math is now in Platform.  
Mon 10 Feb : GetInterpolatedCloudKeyframeUniqueId() returns the UID for the Cloud Keyframer based on the layer index. New function Environment::GetCloudKeyframerUIDByLayerIndex();  
Thu 06 Feb : Removal of Duplicate Images  
Thu 06 Feb : Switch cldoc to simul/markdoc submodule remote.  
Thu 06 Feb : Added cloud volume calculations to MixInCirrus shader.  
Thu 06 Feb : Fix for copied keyframes not being accessible.  
Tue 04 Feb : Minor fixes to build script.  
Tue 04 Feb : Fix shader build conflict for CMake. Remove win_flex_bison, this is in Platform/ now.  
Tue 04 Feb : Move albedo and colour into Moon structs.  
Tue 04 Feb : CMake for PS4. Return from EditorRenderCloudWindow instead of calling EnsureLayersAreInitialized if checksum fails.  
Mon 03 Feb : Fix for Rainbows appearing front of scene geometry  
Mon 03 Feb : Build.bat quotation mark fixes.  
Mon 03 Feb : Platform ptr.  
Mon 03 Feb : Remove submodules moved to Platform. Sfx has moved to Platform.  
Mon 03 Feb : Clang CMake fixes. Updates win_flex_bison to newer version, should no longer write "register" which is outdated.  
Mon 03 Feb : Clang CMake fixes. Updates win_flex_bison to newer version, should no longer write "register" which is outdated.  
Sat 01 Feb : Fix compile error.  
Sat 01 Feb : Help compile with Clang on Windows.  
Wed 29 Jan : Documentation Update  
Tue 28 Jan : Linux compile fixes.  
Tue 28 Jan : Fix PS4 compiler errors.  
Tue 28 Jan : Doc Fixes  
Tue 28 Jan : Fix compile errors in Orientation.cpp  
Tue 28 Jan : .  
Tue 28 Jan : Fix for VS_SnowParticles  
Tue 28 Jan : Minor fix for images in rainbow documentation  
Tue 28 Jan : Minor update to Rainbow docs  
Tue 28 Jan : Move AzimuthElevationToDirection into cpp.  
Mon 27 Jan : Temp fix for rainbow images + Layout Fix  
Mon 27 Jan : Doc Update  
Mon 27 Jan : Fix for disappearing rain particles when simulation is paused. Vulkan validation fix: Changed cubeTexture from TextureCube to TextureCubeArray.  
Mon 27 Jan : Merged in multiple moon support.  
Mon 27 Jan : Fix for rain particles spinning, when simulation is paused.  
Sat 25 Jan : GetExportLightningStrikes signature changed.  
Sat 25 Jan : Extra safety checks.  
Sat 25 Jan : Save/load Quaternions.  
Sat 25 Jan : Sample builds fixed  
Fri 24 Jan : Build fixes  
Fri 24 Jan : Merge 4.2 Sfx fix  
Fri 24 Jan : Fixes to lightning.  
Fri 24 Jan : Lightning rendering and quality fixes.  
Fri 24 Jan : Improve python deploy script.  
Fri 24 Jan : Improve file handling for shaders. Storms now use Quaternion for centre. Remove NoiseOctaves from CellularCloudGrid.  
Fri 24 Jan : Extra safety checks.  
Thu 23 Jan : Shader paths  
Thu 23 Jan : Fix GL Sample.  
Wed 22 Jan : Build fix for VSVER.  
Wed 22 Jan : Reset errorlevel at start of InitProperties.bat  
Wed 22 Jan : .  
Wed 22 Jan : Tweaks in batch files.  
Wed 22 Jan : Tweaks in batch files.  
Wed 22 Jan : Platform ptr.  
Wed 22 Jan : Fixes to PS4 build.  
Wed 22 Jan : Performance improvements to water, some other fixes  
Wed 22 Jan : Performance improvements to water, some other fixes  
Wed 22 Jan : Platform ptr  
Tue 21 Jan : trueSKY Shaders moved from Platform/Crossplatform/ to Shaders/  
Tue 21 Jan : Added Shaders CMakeLists.txt. Shaders are now built from here instead of from Platform subprojects.  
Mon 20 Jan : Match 4.2 Setup.nsi  
Mon 20 Jan : Fix for CS_DrawRainbow() use of GetDimensions().  
Mon 20 Jan : Fix for Rainbow documentation : How it works  
Mon 20 Jan : Recommit Rainbow Documentation.  
Mon 20 Jan : Fix for rendering preciptation_volume, when Strength is 0, but RainToSnow is greater than 0.  
Mon 20 Jan : Fix images for rainbow documentation.  
Sat 18 Jan : Fix Clang compiler error from member initialization order.  
Fri 17 Jan : Temporarily removed rainbow docs to allow for update  
Fri 17 Jan : Doc updates  
Fri 17 Jan : Fix for Rainbows and Amortization  
Fri 17 Jan : Fix for install script.  
Fri 17 Jan : Fix imported targets in CMakeLists to be global, so correct lib names are used for Debug sample-only builds.  
Fri 17 Jan : Minor fixes and optimisations  
Thu 16 Jan : Vulkan link fix.  
Thu 16 Jan : Fix Cmake Linux build.  
Thu 16 Jan : Linux build fixes.  
Thu 16 Jan : Alternate Vulkan lib link directory for Linux.  
Thu 16 Jan : Amortization re-enabled.  
Thu 16 Jan : Fix Cmake error.  
Thu 16 Jan : Cloud amortization re-enabled.  
Thu 16 Jan : Rain effect not superspeed.  
Thu 16 Jan : Addded simul_refract_reflect.sl  
Thu 16 Jan : CMake supports SIMUL_BUILD_SHADERS, set to false to disable shader build proejcts.  
Thu 16 Jan : CMake allows SIMUL_BUILD_SHADERS to be false, so shaders are not built.  
Thu 16 Jan : Force Cmake to actually build shader projects...  

<hr>
