---
title: Change List
layout: reference
weight: 120
---


Version HEAD
---
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
Wed 13 Nov : Test for Wayne  
Wed 13 Nov : Moved Unreal performance  
Wed 13 Nov : Fixed Login issues. Update Docs.  
Tue 12 Nov : New lighting: incremental cloud lighting.  
Tue 12 Nov : Execute deferred rendering for editor if set.  
Mon 11 Nov : Cloud volume improvements: UI more functional.  
Mon 11 Nov : Fix Blueprint Crash. Initial fix for registration.  
Mon 11 Nov : Changed to using a precipitation volume texture. Raytrace function updated to the volume texture. Debug has new technique trace_volume  
Mon 11 Nov : Fix PlatformStructuredBuffer errors in D3D12.  
Mon 11 Nov : FAQ update for Windows 7  
Sat 09 Nov : Cloud volumes initially functional: Some fixes to D3D12 structured buffers found.  
Fri 08 Nov : Disable add cloud volume action until feature is complete.  
Fri 08 Nov : Vulkan validation fixes. Add SphereRenderer.  
Wed 06 Nov : Doc changes  
Wed 06 Nov : Update 0 unreal index.md  
Wed 06 Nov : Create 4 Performance.md  
Wed 06 Nov : Fix bug where destroyed sequencer window still had its HWND in the toRender list.  
Wed 06 Nov : Fix broken spacing in registration box for sequencer.  
Tue 05 Nov : Quaternion slerp fix and layout.  
Tue 05 Nov : Update splash for SkySequencer.  
Tue 05 Nov : Relative quaternions for cloud volumes.  
Mon 04 Nov : Volumes working in initial form.  
Mon 04 Nov : Cloud volumes work in progress.  
Mon 04 Nov : Remove glfx  
Mon 04 Nov : Remove nodeeditor  
Mon 04 Nov : Fix missing Qt dependencies in TrueSkyUI_MD.  
Sun 03 Nov : Fix bad Cmake, was only creating GFX.cso for Xbox.  
Sun 03 Nov : Cmake build fixes, removed unwanted files.  
Sun 03 Nov : Correct header includes for CMake.  
Sun 03 Nov : Work on cloud volume selection and editing.  
Sat 02 Nov : Fix error in DirectXTexD3D11.cpp  
Sat 02 Nov : Add toolchain-Microsoft-GDK.cmake Improve cloud window editing.  
Fri 01 Nov : Fixes to make sure Xbox GDK is supported  
Fri 01 Nov : Disable SIMUL_PLUGIN_DEPLOY_ALL in Build.bat by default.  
Fri 01 Nov : Fix lightning edit widget always appearing.  
Fri 01 Nov : Add CloudKeyframe.h and cpp to PS4 project.  
Fri 01 Nov : Docs and Removal of gifs temporarily  
Fri 01 Nov : Doc fix  
Fri 01 Nov : Chaning Images to images  
Fri 01 Nov : Fix crashes from multiple sequencers open.  
Fri 01 Nov : Improved memory tracking - possible fix for D3D12 issues.  
Thu 31 Oct : Doc Fix  
Thu 31 Oct : Changed default path for dllLocation.  
Thu 31 Oct : Doc Fixes  
Thu 31 Oct : Fix some Vulkan errors that occur in cloud window editor.  
Thu 31 Oct : Removed unneeded window handle from UpdateUI().  
Thu 31 Oct : adding images  
Thu 31 Oct : Doc Fixes  
Wed 30 Oct : Fix copy and pasting of keyframes in sequencer.  
Wed 30 Oct : Odd EnsureIndexBuffer behaviour  
Wed 30 Oct : DOc Updates + UI Sorting  
Wed 30 Oct : Added combine precipitation compute shader for performance. Replaced rainMap lookup with value in RaytraceClouds functions.  
Tue 29 Oct : Added version.properties to store current variable properties, e.g. recommended SDK versions etc. Fixed platform build errors.  
Mon 28 Oct : Fix being unable to select the sky layer.  
Mon 28 Oct : Removed Add Shape from Sequencer UI  
Mon 28 Oct : Removed Min Star Size from Sequencer. Temp Disabled Get Constellation  
Mon 28 Oct : Fix right-click clearing selection.  
Mon 28 Oct : Fix stand-alone sequencer not compiling from rename.  
Fri 25 Oct : PS4-related fixes patched. QPropertyEditWidget has applyParentTooltip, should be called by derived classes after setupUI.  

<hr>
