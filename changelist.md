---
title: Change List
layout: reference
weight: 120
---



Version 4.2
---
Mon 07 Jan : Add different VS launcher scripts. Help updates.

Sun 30 Dec : Cmake build fixes.

Sun 30 Dec : Add Cmake files.

Sat 29 Dec : Samples build

Sat 29 Dec : Solution dependencies.

Fri 28 Dec : Remove refs to deleted files\
Thu 27 Dec : Only include <filesystem> on Windows.
Thu 20 Dec : Sfx builds in CMake.
Wed 19 Dec : Remove depth attachments from VulkanSample/Main.cpp, fixes validation warnings.
Wed 19 Dec : Return on QRenderWidget.cpp to avoid recursive paint.
Wed 19 Dec : Fixed the OpenGL view re-opening issue in SkySequencer. Added new function to DeviceManager.cpp - Deactivate(), which nullifies the GL context before closing the view.
Tue 18 Dec : Updated DX12 CloudRenderer.cpp RenderCloudWindow() will return void if cloud_texture or light_texture AsD3D11SRV is nullptr.
Tue 18 Dec : Updated DX12: mSubResourceStates.  Crossplatform: Light Probe links to effect for UBO. OpenGL: Rebuild the FBO as a cubemap. Vulkan sample expanded the vulkan triangle code and shaders.
Tue 18 Dec : Add Sample CMakeLists.txt, init default colour format in Vulkan sample.
Tue 18 Dec : SetDefaultColourFormat call from DisplaySurface.
Mon 17 Dec : Fix build of Qt widgets project.
Mon 17 Dec : Fix build of Qt widgets project.
Fri 14 Dec : Add Simul.cmake
Fri 14 Dec : Add cmake files, fix Xbox v141 build.
Thu 13 Dec : Removed Resources.cpp from SkySequencer Project
Wed 12 Dec : Updates to make CMake work better.
Wed 12 Dec : Add VulkanSample shaders.
Tue 11 Dec : Updated DX11&12 Antialiasing, InitSRVTables in DX12.Texture.cpp and GetFloat issue in Keyframer.cpp - AJR
Tue 11 Dec : Xbox build fix.
Mon 10 Dec : mmxrand.cpp build fix.
Mon 10 Dec : Update PS4 pointer
Mon 10 Dec : PS4 ptr.
Mon 10 Dec : Removed cloudsamplerstate due to redundancy and problems with DX12, other small fixes
Mon 10 Dec : Fix for rain and rain depth masking
Mon 10 Dec : No Vulkan for Xbox.
Mon 10 Dec : Some warnings fixed. PS4 ptr.
Wed 05 Dec : Proper fix for GL texture-delete-related crash. We needed to track resident texture handles and make them unresident when deleting the texture.
Wed 05 Dec : CleanSlack.py added
Wed 05 Dec : OpenGL: when any texture is deleted, we call ClearResidentTextures to re-initialize that list.
Tue 04 Dec : Fix addendum
Tue 04 Dec : Fix for 'Halo' effect on water in the UE editor
Thu 29 Nov : Xbox build fix: no Vulkan headers.
Thu 29 Nov : Build fixes for PS4 and GL Sample.
Tue 27 Nov : Build fixes
Tue 27 Nov : Vulkan build fixes for latest VS2017 compiler.
Tue 27 Nov : Add casts to vulkan functions
Tue 27 Nov : Vulkan files
Mon 26 Nov : Add PixelFormat.cpp
Mon 26 Nov : Build fixes
Mon 26 Nov : To enable Vulkan support, InitFromExternalTexture2D now has specifiers for texture size and format, because that might not be something that can be gleaned from the native object.
Mon 19 Nov : Added extra checksum variables to force light tables recalculation, other minor changes
Thu 15 Nov : Vulkan fully functional.
Wed 14 Nov : Water cleanup, complete disabling of old FFT system.
Tue 13 Nov : Implement Water Wave Grid, small fixes
Mon 05 Nov : For Vulkan, Topology is now part of the sfx shader definition.
Fri 02 Nov : Added VulkanSample.
Wed 31 Oct : Reverted change to water probe functions
Wed 31 Oct : Fixed missing header
Wed 31 Oct : Fix to Cloud Window crash
Mon 29 Oct : Minor fix for Render Cloud Window
Sat 27 Oct : All shaders compile for Vulkan except water.sfx.
Thu 25 Oct : Godrays fix, warning suppression
Wed 24 Oct : Vulkan effect compiling.
Wed 24 Oct : deleteOldFtp updates.
Tue 23 Oct : PS4 ptr.
Tue 23 Oct : GetNextModifiableKeyframe for cloud layers fixed.
Tue 23 Oct : Fix for Xbox build
Tue 23 Oct : Terrain export
Mon 22 Oct : Xbox build fix.
Sun 21 Oct : Xbox ptr to fix GFXRS defn.
Mon 15 Oct : Sequencer platform-specific shaderbin folders.
Mon 15 Oct : Vulkan implementation proceeding.
Mon 15 Oct : DX12 texture load fixed.
Mon 15 Oct : DX12 build fix
Sat 13 Oct : OpenGL tidyups and build fix.
Fri 12 Oct : PS4 ptr.
Fri 12 Oct : Sfx preamble from json is always added, even to compute shaders. If present, computePreamble is added after this.
Fri 12 Oct : Add template Vulkan lib.
Fri 12 Oct : PS4 build fix.
Fri 12 Oct : Minor GL fixes. CommandLineParams ignores exe filename.
Thu 11 Oct : Fixed GL context-sharing. Fixed GL texture UBO conflict when different shaders use different textures in same pass. GL functional in Sequencer.
Thu 11 Oct : Added enum support for water, various other small fixes
Tue 09 Oct : OpenGL work-in-progress
Tue 09 Oct : Enabled CloudShadowRange to affect the area that the shadows are renderer to. Small water fixes
Mon 08 Oct : Revert test code that impacted framerate.
Tue 02 Oct : GL, at least in the current NVidia implementation, seems unable to write to a re-used texture id that it has generated after that id was previously freed. Therefore we force the issue by making the tex id's go up sequentially, not standard GL behaviour.
Thu 20 Sep : Updated Water to use the basic Water Wavelets method. Also includes warning cleanups and other small bugfixes
Fri 14 Sep : Disable DX12 in Sequencer by default. Cmake for OpenGL.
Fri 07 Sep : Build fixes wrt CMake.
Fri 07 Sep : Linux build mods.
Fri 07 Sep : Linux build mods.
Wed 05 Sep : Fix gl sample build.
Tue 04 Sep : Fixed macro build error on PS4.
Tue 04 Sep : OpenGL build fixes; CloudDepthTemporalAlpha in rendering options and mixed_resolution.sfx
Mon 03 Sep : Fixed getSunlightFactor, other small fixes
Tue 21 Aug : .
Wed 01 Aug : Small fix to water overlay rendering
Wed 25 Jul : Fix commandlist problems in DisplaySurface::EndFrame which broke texture init.
Tue 24 Jul : Init order fixes.
Thu 19 Jul : Water fix
Thu 19 Jul : Various warning messages removal and cleanup
Wed 18 Jul : Remove superfluous SV_Target from water shaders that return structs.
Tue 17 Jul : Call EndFrame on WindowManagers
Tue 17 Jul : Sun is treated as having finite size in calculating light and colour at sunrise/sunset.
Mon 16 Jul : Variant is now base::Variant, don't use Variant32.

<hr>
