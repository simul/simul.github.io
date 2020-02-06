---
title: Change Log
layout: reference
weight: 120
---


Version HEAD
---
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
Thu 16 Jan : Force Cmake to not exclude shader projects from build. Why would it do this?  
Thu 16 Jan : Added Documentation for Rainbows. Other minor fixes.  
Wed 15 Jan : Added missing image  
Wed 15 Jan : Doc Updates  
Wed 15 Jan : Rainbows now use a moisture value found in the nearFarTexture. Moisture values is saved into RaytracePixelOutput::nearFarDepth.w  
Wed 15 Jan : Documentation Updates  
Wed 15 Jan : CMake functional for samples. Include SkySequencer in main SDK installer.  
Tue 14 Jan : Update water changes from base 4.2  
Tue 14 Jan : Fix for OpenGL, Add half4 support to SFX for OpenGL only.  
Mon 13 Jan : Fix for DX12 and Vulkan. OpenGL is WIP.  
Mon 13 Jan : Using the view position, instead of just height. simul::vulkan::DeviceManagerInternal store the VkPhysicalDeviceFeatures, queried from the gpu. vkCreateDevice queries against the stored VkPhysicalDeviceFeatures for compatibility. simul::vulkan::Texture::IsValid() check for a valid object handle as well.  
Sat 11 Jan : Remove xmlParser, stampver, and ATLServer from External.  
Sat 11 Jan : Remove Oculus, freeglut, glew from Externals.  
Sat 11 Jan : FindFileInPathStack finds NEWEST file, not first.  
Sat 11 Jan : Remove nasty boost.  
Fri 10 Jan : Added UI, Lunar Rainbows and General Fixes  
Fri 10 Jan : Add SimulPS4.props  
Fri 10 Jan : Remove unwanted .props reference.  
Thu 09 Jan : Build.bat fixes  
Thu 09 Jan : Batch file fixes  
Thu 09 Jan : Removed duplicate BackgroundLatLongSphere() from sky.sfx  

<hr>
