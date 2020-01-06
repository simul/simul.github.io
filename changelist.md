---
title: Change Log
layout: reference
weight: 120
---


Version HEAD
---
Fri 03 Jan : Fix Vulkan sample on Windows.  
Fri 03 Jan : unistd include.  
Fri 03 Jan : Fix bad spacing in Sfx files.  
Fri 03 Jan : D3d12 build fixes.  
Tue 31 Dec : Linux build fixes  
Sun 29 Dec : Update Licence.md  
Thu 19 Dec : Reverting timer, adding check to see if licence is long enough to even send  
Tue 17 Dec : Fix skySequencer installer.  
Mon 16 Dec : Update GetDependencies.bat  
Mon 16 Dec : Lowering default values. Capitalizing Names on Sequencer.  
Mon 16 Dec : Increased timeout time when waiting for data  
Mon 16 Dec : Removed Override Wind, now on by default.  
Fri 13 Dec : Added some water optimisations and options  
Fri 13 Dec : Removal of Wind values from Sequencer. Doc Update. Blueprint section soon to be rewritten  
Thu 12 Dec : Update RenderingPlugin.cpp  
Thu 12 Dec : Update RenderingPlugin.cpp  
Thu 12 Dec : LightweightConstantUpdateEngine::kMaxResourceCount size check.  
Thu 12 Dec : LightweightConstantUpdateEngine::kMaxResourceCount size check.  
Thu 12 Dec : PS4 SDK 7 compile fixes.  
Wed 11 Dec : Python script uses release.properties.  
Wed 11 Dec : Commiting missing file  
Tue 10 Dec : Added ability for water to run off game time instead of real time, other small changes  
Mon 09 Dec : Fix for Vulkan validation error relating to VkQueryPool.  
Fri 06 Dec : Initial commit for Vulkan profiling.  
Fri 06 Dec : Updated DX12 SetIndexBuffer to correctly override the crossplatform version, made sure that textures texture arrays will always be set as such for vulkan  
Fri 06 Dec : Added Profiling for OpenGL. Platform/OpenGL/Profiler.h/.cpp is used.  
Thu 05 Dec : Initial fix to getting cloud layer variables  
Thu 05 Dec : Vulkan: Added Dummy2DMS texture, and modify FinishLoading() as vkCmdCopyBufferToImage() need its dstImage to have a sample count equal to VK_SAMPLE_COUNT_1_BIT.  
Thu 05 Dec : Sfx adds multisample texture info .sfxo files.  
Wed 04 Dec : Update to Snow pixel shader to make snowflakes more visible at smaller sizes.  
Wed 04 Dec : Fix build path in py script.  
Tue 03 Dec : Fix for Qt 2017(5.9.8) file copy. Qt5CLucene.dll and qnativewifibearer.dll are not part of Qt5.9.8  
Mon 02 Dec : Added QT_VER to release.properties  
Fri 29 Nov : Crash on deleting cloud layer with volumes present  
Fri 29 Nov : Fix ssleay/libeay usage by Qt: Must force Path Environment.  
Fri 29 Nov : Updated XboxOne submodule.  
Fri 29 Nov : Fix cloud.sfx precipitationVolumeRW texture type.  
Fri 29 Nov : Added define SFX_D3D12  
Fri 29 Nov : Fix DX11 Precipitation Volume. Fix for PrecipitationRenderer to use the Precipitation Volume texture.  
Thu 28 Nov : Fix for GetPrecipitationCentre().  
Thu 28 Nov : Vulkan layout/resourcestate fixes.  
Wed 27 Nov : Disabled Visibility  
Wed 27 Nov : UI Updates + set time to selected keyframe  
Wed 27 Nov : Externally-set ResourceStates for D3D12.  
Wed 27 Nov : Externally-set ResourceStates for D3D12.  
Tue 26 Nov : Fixed the default orientation for CloudWindowEditor.  
Tue 26 Nov : Fix CloudWindowEditor view lines, and rotateByOffsetPolar();  
Tue 26 Nov : Feature level 12.0 for D3D12 supported.  
Mon 25 Nov : Cloud Index initial implementation.  
Mon 25 Nov : Window Fix  
Mon 25 Nov : Fix for Precipitation Volume on OpenGL. Sfx GetSizeFunction handles return parameters assignment for ShaderResourceType::UNKNOWN with replacement token {dim_check:textureName,x,y,z,tempName}  
Mon 25 Nov : Doc fix  
Mon 25 Nov : Quaternion function reorg.  
Mon 25 Nov : Heading etc works for cloud window panel.  
Sat 23 Nov : Added DXCompiler and switched D3d12 shader compilation to use dxc.  
Sat 23 Nov : Text rendering fixes.  
Fri 22 Nov : Prevent Unity overlay crash.  
Fri 22 Nov : Fix for previous Commit  
Fri 22 Nov : UI changes for cloudWindow  
Fri 22 Nov : Added to lock guard to TrueSkyRenderer::RemoveView()  
Fri 22 Nov : Cloud Window UI changes, small doc update  
Fri 22 Nov : only if SIMUL_EDITOR is 1 reference sphereRenderer.  
Thu 21 Nov : Extra debug info for shader loads.  
Thu 21 Nov : Removal of old variables from sequencer. Added Extra Cloud section to docs.  
Thu 21 Nov : Improved cloud volume editing.  
Thu 21 Nov : Qt version revert to 5.9 as 5.12 has bugs in layout.  
Wed 20 Nov : Fix warnings for D3d12.  
Mon 18 Nov : Update Build.bat for recent CMake and Vs2017.  
Mon 18 Nov : Fix OpenGL cloud lighting issues: nVidia driver bug can't cope with 16-bit floats in computable volume.  
Mon 18 Nov : Moving images into one folder  
Mon 18 Nov : Fixed image in docs  
Mon 18 Nov : Amended file name and extension  
Mon 18 Nov : Renamed precipitation folder to lowercase  
Mon 18 Nov : Update to Help/tutorials/precipitation/3 how it works.md  
Mon 18 Nov : Doc Fixes  
Mon 18 Nov : Doc layout fix  
Mon 18 Nov : Minor update to precipitation documentation.  
Mon 18 Nov : Add files after merge: Help/tutorials/precipitation/3 how it works.md  
Mon 18 Nov : Update to precipitation documentation.  
Sun 17 Nov : Shader projects only depend on Sfx for Win/Lin.  
Sun 17 Nov : .  
Sun 17 Nov : Fix Sfx for GLSL texture size queries where texture is a parameter rather than global.  
Sat 16 Nov : CMake dependencies.  
Sat 16 Nov : Build fixes re. Qt  
Sat 16 Nov : .  
Sat 16 Nov : Fix WindowsEnvironment.properties  
Fri 15 Nov : Add release.properties  
Fri 15 Nov : Remove glfx  
Fri 15 Nov : QT_INFIX to installer.  
Fri 15 Nov : QT_INFIX supported for custom Qt builds.  
Fri 15 Nov : Fixed key frames being pasted to wrong layer when cloud layer IDs didn't correlate to row number.  
Fri 15 Nov : Changed sampler lookup in precipitation volume texture.  
Fri 15 Nov : Doc fix  
Fri 15 Nov : Slight fix to Precipitation Docs  
Fri 15 Nov : Moving to sky::uid. Updating Doc folder structure.  
Fri 15 Nov : Added view lines to CloudWindowEditor. Updated to rotateByOffsetCartesian(), rotateByOffsetPolar() and DrawArc() function and shader. MainCameraViewStruct added to CloudRenderer.  
Thu 14 Nov : Fix including wrong qt libs.  
Thu 14 Nov : Xbox build fix.  
Wed 13 Nov : Xbox build fix.  
Wed 13 Nov : Fix some Vulkan warnings.  

<hr>
