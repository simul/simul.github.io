---
title: Change Log
layout: reference
weight: 120
---


Version HEAD
---
Sat 18 Jan : Fix Clang compiler error from member initialization order.  
Fri 17 Jan : Temporarily removed rainbow docs to allow for update  
Fri 17 Jan : Doc updates  
Fri 17 Jan : Fix for Rainbows and Amortization  
Fri 17 Jan : Fix for install script.  
Fri 17 Jan : Fix imported targets in CMakeLists to be global, so correct lib names are used for Debug sample-only builds.  
Fri 17 Jan : Minor fixes and optimisations  
Thu 16 Jan : Vulkan link fix.  
Thu 16 Jan : Linux build fixes.  
Thu 16 Jan : Alternate Vulkan lib link directory for Linux.  
Thu 16 Jan : Amortization re-enabled.  
Thu 16 Jan : Fix Cmake error.  
Thu 16 Jan : Cloud amortization re-enabled.  
Thu 16 Jan : Rain effect not superspeed.  
Thu 16 Jan : Addded simul_refract_reflect.sl  
Thu 16 Jan : CMake allows SIMUL_BUILD_SHADERS to be false, so shaders are not built.  
Thu 16 Jan : Force Cmake to not exclude shader projects from build. Why would it do this?  
Thu 16 Jan : Added Documentation for Rainbows. Other minor fixes.  
Wed 15 Jan : Added missing image  
Wed 15 Jan : Doc Updates  
Wed 15 Jan : Rainbows now use a moisture value found in the nearFarTexture. Moisture values is saved into RaytracePixelOutput::nearFarDepth.w  
Wed 15 Jan : Documentation Updates  
Wed 15 Jan : CMake functional for samples. Include SkySequencer in main SDK installer.  
Tue 14 Jan : Fix for OpenGL, Add half4 support to SFX for OpenGL only.  
Mon 13 Jan : Fix for DX12 and Vulkan. OpenGL is WIP.  
Mon 13 Jan : Using the view position, instead of just height. simul::vulkan::DeviceManagerInternal store the VkPhysicalDeviceFeatures, queried from the gpu. vkCreateDevice queries against the stored VkPhysicalDeviceFeatures for compatibility. simul::vulkan::Texture::IsValid() check for a valid object handle as well.  
Fri 10 Jan : Added UI, Lunar Rainbows and General Fixes  
Thu 09 Jan : Removed duplicate BackgroundLatLongSphere() from sky.sfx  
Wed 08 Jan : Added DrawMultipleCrossSections() to SphereRenderer for better viewing of the cloudDensity texture in the CloudWindow. Added high resolution MilkyWay background texture. Re-worked SiderealSky to improve sidereal accuracy.  
Wed 08 Jan : Small fix for water geometry  
Tue 07 Jan : Fix for EditorRenderCloudWindow() not drawing cloud map textures. Initial fix for reversed sidereal sky background.  
Mon 06 Jan : Output Simul path to log.  
Mon 06 Jan : Shaderbin path fix.  
Mon 06 Jan : Additional shader bin paths for deployed version.  
Mon 06 Jan : Fix for deprecated std::getenv() in Effect::EnsureEffect(), changes to _dupenv_s() if defined(_CRT_SECURE_NO_WARNINGS). Fix for GPU profiling and RenderPlatform begin and end frame boolean check. Reset Position of Region defaults to zero offset from cloud keyframe orientation. Updated CloudKeyframe::GetPrecipitationCentre(), which defaults to returning the absolute position. Fix CloudWindowEditor::origin is constructor. Updated Precipitation Documentation.  
Mon 06 Jan : Write shaderbin paths to log.  
Mon 06 Jan : SkySequencer should work without Qt environment settings.  
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
Wed 11 Dec : Added sun occlusion lookup, when drawing rainbows. Experimentation supernumerary rainbows added.  
Tue 10 Dec : Added ability for water to run off game time instead of real time, other small changes  
Tue 10 Dec : Updated rainbow blending and performance.  
Mon 09 Dec : Fix for Vulkan validation error relating to VkQueryPool.  
Fri 06 Dec : Initial commit for Vulkan profiling.  
Fri 06 Dec : Updated DX12 SetIndexBuffer to correctly override the crossplatform version, made sure that textures texture arrays will always be set as such for vulkan  
Fri 06 Dec : Added Profiling for OpenGL. Platform/OpenGL/Profiler.h/.cpp is used.  
Thu 05 Dec : Initial fix to getting cloud layer variables  
Thu 05 Dec : Vulkan: Added Dummy2DMS texture, and modify FinishLoading() as vkCmdCopyBufferToImage() need its dstImage to have a sample count equal to VK_SAMPLE_COUNT_1_BIT.  
Thu 05 Dec : Sfx adds multisample texture info .sfxo files.  
Wed 04 Dec : Update to Snow pixel shader to make snowflakes more visible at smaller sizes.  
Wed 04 Dec : Fix build path in py script.  
Wed 04 Dec : Refining CS_DrawRainbow()  
Tue 03 Dec : Fix for Qt 2017(5.9.8) file copy. Qt5CLucene.dll and qnativewifibearer.dll are not part of Qt5.9.8  
Tue 03 Dec : Added CS_DrawRainbow  
Mon 02 Dec : Added QT_VER to release.properties  
Fri 29 Nov : Crash on deleting cloud layer with volumes present  
Fri 29 Nov : Fix ssleay/libeay usage by Qt: Must force Path Environment.  
Fri 29 Nov : Updated XboxOne submodule.  
Fri 29 Nov : Updated XboxOne submodule.  
Fri 29 Nov : Fix cloud.sfx precipitationVolumeRW texture type.  
Fri 29 Nov : Added define SFX_D3D12  
Fri 29 Nov : Initial commit for a rainbow_lookup texture.  
Fri 29 Nov : Fix DX11 Precipitation Volume. Fix for PrecipitationRenderer to use the Precipitation Volume texture.  
Thu 28 Nov : Fix for GetPrecipitationCentre().  
Thu 28 Nov : Vulkan layout/resourcestate fixes.  
Wed 27 Nov : Disabled Visibility  
Wed 27 Nov : UI Updates + set time to selected keyframe  
Wed 27 Nov : Externally-set ResourceStates for D3D12.  
Wed 27 Nov : Externally-set ResourceStates for D3D12.  
Tue 26 Nov : QT dir fix.  
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

<hr>
