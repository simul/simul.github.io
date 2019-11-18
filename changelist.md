---
title: Change List
layout: reference
weight: 120
---


Version HEAD
---
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
Fri 25 Oct : Doc fix  
Fri 25 Oct : Fix QT DLLs not being deployed.  
Fri 25 Oct : Apply patch from Game Studio.  
Fri 25 Oct : Support for altitude-dependent sunlight.  
Fri 25 Oct : Fix Simul QTWidgets deployment.  
Thu 24 Oct : Each cloud layer builds its own rain map. Updated clouds.sfx, GetRainAtOffsetKm() and GetRainToSnowAtOffsetKm() for volume queries to use the texture array. For this commit, rain.sfx simply flattens the array for its look up - to be amended.  
Thu 24 Oct : Small doc fix  
Thu 24 Oct : UI improvements to timeline.  
Thu 24 Oct : Image Fixing Docs  
Thu 24 Oct : Image Fix for Docs  
Thu 24 Oct : Doc Updates  
Thu 24 Oct : Doc Updates  
Thu 24 Oct : Added cloud masks to Cloud Layer Precipitation shader. DrawTexture() now supports Texture2DArrays  
Thu 24 Oct : Doc Update  
Tue 22 Oct : Undo works again in Sky Sequencer.  
Tue 22 Oct : Fix sky keyframe sequence being set to invalid values on undo.  
Sat 19 Oct : Add missing shaders in installers.  
Fri 18 Oct : Fix Crash with sequencer  
Fri 18 Oct : Initial fix for Rain Map and Multi Cloud Layer issue.  
Thu 17 Oct : Fix Xbox error by reverting to original. However, whatever this change was put in to fix will presumably still be broken.  

<hr>
