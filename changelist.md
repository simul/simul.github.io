---
title: Change Log
layout: reference
weight: 120
---


Version HEAD
---
Mon 15 Jun : Default for SIMUL_QT_DIR .  
Fri 12 Jun : Update to GetDependencies.bat  
Wed 10 Jun : Default to NEVER_BUILD for shaders.  
Mon 08 Jun : Backport Source Setup  
Mon 08 Jun : Update ReadMe.md  
Thu 04 Jun : Fix win_flex path.  
Thu 04 Jun : GL shader fixes. QNetworkReply null check.  
Wed 03 Jun : Add ssleay and libeay dll's to installers.  
Tue 02 Jun : small variable fix  
Tue 02 Jun : Fix to shadows, initial setup for passing variables more efficiently  
Wed 20 May : Fix shaky rain.  
Wed 20 May : Fix NaN's in rain.  
Tue 19 May : Rain tweak, version number on seq panel.  
Tue 19 May : Use 0 mip to render rain with cubemap.  
Mon 18 May : Fixed aligned Sun, removed flashing sky with Sequencer DX12  
Fri 15 May : Small updates to water, backend changes to particles, fix for memory leak  
Tue 12 May : Fix D3d12 shader build.  
Mon 11 May : Improve batch build script. Deploy Win64 shaders to API subdirectories.  
Mon 11 May : Updated binary readme and batches.  
Fri 01 May : Fix zero matrix in WorldspaceToLightspaceMatrix  
Mon 27 Apr : Added Latest Redist  
Sat 25 Apr : Remove extra #include.  
Sat 25 Apr : Fix order to include Direct3D12.h  
Sat 25 Apr : Fix order to include Direct3D12.h  
Sat 25 Apr : Use ID3D12GraphicsCommandListType from ThisPlatform/Direct3D12.h  
Fri 24 Apr : Added disable #line directive to OpenGLShaders.  
Thu 23 Apr : Added shader_platform.sl to Shaders. Changed composite.sl TwoColourCompositeOutput to use SIMUL_RENDERTARGET_OUTPUT_DSB_INDEX_0 and _1.  
Thu 23 Apr : Fix for overlapping semantic in water.SFX/water_particles.sfx  
Wed 22 Apr : PLATFORM_D3D11_SFX option supported.  
Mon 20 Apr : Remove unwanted legacy vcxproj files.  
Fri 17 Apr : Do git submodule init if Platform submodule is not detected.  
Wed 08 Apr : Shader paths for internal builds.  
Thu 02 Apr : Fix for water faces being drawn backwards, small improvement for reflection setting performance  
Thu 02 Apr : Added debug output to Sequencer  
Wed 01 Apr : Fixed medium detail update region. Fixed rain render problems.  
Mon 30 Mar : Fix offset high-detail area.  
Sun 29 Mar : Fix quitafterframe behaviour in sample.  
Sun 29 Mar : Fix quitafterframe behaviour in sample.  
Sun 29 Mar : Remove DefaultFileLoader.cpp - this is now in Platform/Core.  
Fri 27 Mar : Platform ptr.  
Fri 27 Mar : CloudKeyframers have Names.  
Fri 27 Mar : Fix incorrect links in Unreal source docs page.  
Fri 27 Mar : Add Simul/Platform/Windows to Simul.markdoc so that ThisPlatform/*.h can be read.  
Wed 25 Mar : Additional cloud render mode on widget.  
Tue 24 Mar : Optional cloud rendering experimental variant  
Mon 23 Mar : DEPLOY_ALL fixed for CopyToTargetDir.py.  
Sat 21 Mar : Fix unwanted changes to CopyToTargetDir.py  
Thu 19 Mar : Add Core_MD to CopyToTargetDir.py  
Mon 16 Mar : Minor correction to structured buffer initialisation for water probes, as well as extra shader paths for the new platform module  
Mon 16 Mar : Sample changes.  
Mon 16 Mar : Fix bad merge.  
Mon 16 Mar : Fixed Vulkan sample timeout.  
Mon 16 Mar : Some fixes, potentially unstable  
Fri 13 Mar : Fix dll dependencies.  
Fri 13 Mar : Update installer to point to Platform.  
Fri 13 Mar : Re-enable disabled code.  
Fri 13 Mar : Update to licence messages  
Wed 11 Mar : Platform is now standalone, Base has been split into Simul/Base and Platform/Core. The weatherRenderer uses composite.sfx instead of hdr.sfx.  
Mon 09 Mar : Fix to storm gen + small Doc update  
Thu 05 Mar : Fix ambiguous call.  
Thu 05 Mar : Cloud generation reverting.  
Thu 05 Mar : Update clouds.sfx  
Wed 04 Mar : Small water fix  
Wed 04 Mar : Platform ptr.  
Wed 04 Mar : Moon rendering is optional. Cloud tint supported.  
Tue 03 Mar : changes to ig licence doc  
Tue 03 Mar : Added updated iula and ig-ula  
Fri 28 Feb : Improve memory tracking.  
Thu 27 Feb : Adjust time_val and checksum in CloudKeyframer::GetGpuCloudsParameters()  
Wed 26 Feb : Added NoisePhase to CloudInterface and CloudNode.  
Tue 25 Feb : Fixed water issues on PS4, some other changes for stability. Added basic water particles  
Mon 24 Feb : Changed test shader.  
Mon 24 Feb : Add TrueSkySample.cpp generic cross-api sample code.  
Mon 24 Feb : Added clouds_experimental.sl  
Mon 24 Feb : Plugin UI MainWindow compile fix.  
Mon 24 Feb : LinePrint for debug printing.  
Mon 24 Feb : CMake fixes  
Sat 22 Feb : Rename KeyframeEditWidget to SkyKeyframeEditWidget  
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

<hr>
