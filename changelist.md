---
title: Change Log
layout: reference
weight: 120
---


Version 4.3
---
Tue 11 Aug : Moons page - added classes - bold fix - unity link back to legacy  
Tue 11 Aug : Cleaned up and fixed moons page formatting = moons index added - attempted fix for buoyancy index redirect 404  
Mon 10 Aug : Added Multi-Moon Explanation Page - Sky page rewording  
Mon 10 Aug : Removed Slack link from index page and added legacy note to previous moon setup tutorial.  
Mon 10 Aug : Full path for SIMUL_SOURCE_BUILD check.  
Sat 08 Aug : Remove version.properties - this duplicates release.properties.  
Sat 08 Aug : Update release.properties  
Wed 05 Aug : Added SetShowConstellationControls() to SkyEditWidget. Default is to disable constellation in plug-in.  
Wed 05 Aug : UE4 HighlightConstellation UI. HighlightConstellation is now static within BaseSkyRenderer (SkyKeyframer version is commented out). PluginTrueSkyRenderer::Get() checks CloudRenderingOptions enums to set CloudLayer wind direction from UE4.  
Sun 02 Aug : Fix debug dll deploy. Remove unwanted Sample GDK reference.  
Sun 02 Aug : Fix non-compiling shader function due to mismatched parens.  
Thu 30 Jul : Fix for find constellation and points stars. Re-enabled RenderOverlays().  
Wed 29 Jul : The rain's velocity is directed by the CloudLayer's wind parameters.  
Wed 29 Jul : Small Fix  
Wed 29 Jul : Removed Standalone UI from Engine + removing moon functionality  
Fri 24 Jul : Doc Sidebar Update  
Fri 24 Jul : Update to IG Licence Agreement  
Fri 24 Jul : Docs - Added tutorial videos to relevant Categories - Buoyancy page added - Attempted fixes to Indie licences directing to incorrect page and 404 errors. Attempted fix to IG licencing being a 404, Updated links within FAQ  
Thu 23 Jul : Docs - Adding image and updating TimeProgression on UE4 Page  
Thu 23 Jul : Fix to no Moon Texture by default - adding function to get a specific moon by ID  
Wed 22 Jul : Try to initialize SIMUL_SOURCE_BUILD depending on whether source is present.  
Thu 16 Jul : Updated Aurora::RecompileShaders and Aurora::RestoreDeviceObjects  
Wed 15 Jul : Adjust BrightnessPower value.  
Wed 15 Jul : Added edited MilkyWay texture, adjusted default BrightnessPower to 0.05.  
Mon 13 Jul : SkyKeyframer::GetSiderealTimeDegrees() now uses interpolatedKeyframe.time. Fix for Sky Background doing full reverse rotation before midnight.  
Sun 12 Jul : Xbox header fix.  
Sun 12 Jul : Remove WIN64=1 for Linux  
Sun 12 Jul : DX12_JSON_FILE  
Sun 12 Jul : Fix Spectrum json location.  
Sun 12 Jul : Fix compile error.  
Sat 11 Jul : Fix some warnings.  
Sat 11 Jul : Remove unwanted files.  
Sat 11 Jul : Spectrum PLATFORM_TXT.  
Sat 11 Jul : Cross-platform API build fixes.  
Fri 10 Jul : Fixes to bugs exposed by next-gen platform work.  
Wed 08 Jul : Update Doc  
Tue 07 Jul : Storm fix  
Thu 02 Jul : Mie Value from blueprint fix  
Thu 02 Jul : Updating ExternalRenderValues + removed unnecessary CopyToDesigner Function  
Tue 30 Jun : Shader Recompile Fix  
Fri 26 Jun : Fix warnings.  
Fri 26 Jun : Nsis installer fixes for Dx12.  
Thu 25 Jun : Fix merge issue  
Thu 25 Jun : Fix to layer names  
Thu 25 Jun : Layers have names, added wip Cloud Class  
Wed 24 Jun : Removed line that doesn't compile.  
Wed 24 Jun : Build fixes.  
Wed 24 Jun : Small fix for DX11 water being incorrectly drawn and add the ability to draw only water  
Fri 19 Jun : added getCloudLayerUIDbyIndex  
Wed 17 Jun : Fix to Horizon and Zenith  
Wed 17 Jun : Doc Update  
Mon 15 Jun : Default for SIMUL_QT_DIR .  
Fri 12 Jun : fix to GetDependencies.bat  
Fri 12 Jun : Update to extracting Zip File  
Fri 12 Jun : Minor update to Aurora.cpp Checksum issue.  
Wed 10 Jun : Fix nsi build.  
Wed 10 Jun : Fix to Linux Build  
Wed 10 Jun : Fix Linux build  
Mon 08 Jun : Added 4.2a Changes  
Mon 08 Jun : Updated ReadMe  
Mon 08 Jun : Add Cmake QT_dir Variable to CopyToTargetDir.py  
Mon 08 Jun : Update To GetDependencies.bat and default .json  
Sat 06 Jun : Merge 4.3  
Fri 05 Jun : Update to Support_Vulkan Option  
Thu 04 Jun : Fix to batch  
Thu 04 Jun : Build.bat file fix.  
Thu 04 Jun : Build.bat file fix.  
Thu 04 Jun : Fix win_flex path.  
Thu 04 Jun : Added 4.1a - compatible cloud class.  
Thu 04 Jun : Allowing Simul_Support_API options to function  
Wed 03 Jun : Amended NSI/Setup.nsi for win_flex_bison  
Thu 28 May : Godrays improvements.  
Thu 28 May : Remove unneeded project files. Improve build batches.  
Wed 27 May : Rename to cloud_constants.sl  
Tue 26 May : New method functional.  
Thu 21 May : Added WindowUpdater.  
Wed 20 May : Fix shaky rain.  
Wed 20 May : Fix NaN's in rain.  
Tue 19 May : test.sfx compile fixed.  
Tue 19 May : Fix rayleigh edit in sky panel.  
Fri 15 May : Cloud shader work-in-progress.  
Wed 13 May : Minor changes to VulkanSample/Main.cpp. Copying glfw includes and libs.  
Tue 12 May : Commit Platform ptr.  
Tue 12 May : Added .sl files to Setup.nsi along with some default values and destination simul_log.md file.  
Tue 12 May : Fix for empty #define in Applications/SkySequencer/main.cpp  
Tue 12 May : Cloud rendering optimizations.  
Mon 11 May : Remove std::clamp (C++17). Fix Xbox build.  
Sun 10 May : Deploy d3d11/12 sfxo's to subdirectories for engines.  
Wed 06 May : Removing reference to CloudWindow in sky::Aurora. RenderAurora() takes the cloudWindow's origin quaternion.  
Tue 05 May : PS4 compile fix.  
Tue 05 May : PS4 compile fix.  
Mon 04 May : D3d11 Sfx working, though still using fxc for individual shader compilation.  
Mon 04 May : Remove circular dependency on cloud project from sky in aurora code.  
Mon 27 Apr : Add latest VC redist exe.  
Sun 26 Apr : Tools\bin optional in Setup.  
Sun 26 Apr : Add test sample scripts.  
Sat 25 Apr : Remove extraneous include.  
Sat 25 Apr : Don't include GFX.hlsl  
Sat 25 Apr : Use ThisPlatform/Direct3D12.h.  
Sat 25 Apr : Use ThisPlatform/Direct3D12.h.  

<hr>
