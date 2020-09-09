---
title: Change Log
layout: reference
weight: 120
---


Version 4.3
---
Wed 09 Sep : Fix for aurorae variables.md  
Wed 09 Sep : Platform ptr.  
Wed 09 Sep : Minor change to clouds.sfx  
Wed 09 Sep : Unifying changes from 4.2a: PrecipitationGridDivisors, updated precipitation rendering with PrecipitationLayerInfo, Debug Overlays for Rain and Queries and initial change for Unity D3D12.  
Wed 09 Sep : Added Aurorae documentation and corrected others. Changed Aurora FAC controls. Minor improvements to Aurora checksum, class initialisation etc.  
Wed 09 Sep : Removal of automatic Sun + Moon Position from Sky Keyframes. Removed Star variables out of Sky Layer settings. (Both moving engine side)  
Mon 31 Aug : Full init of cloud texture.  
Wed 26 Aug : Xbox build fix.  
Wed 26 Aug : Allow for Global Wind Movement - Layer Creation via blueprints  
Tue 25 Aug : Added extra skylight control variables for unity (Temporary)  
Tue 25 Aug : Fix uninitialized var.  
Tue 25 Aug : using SWAP_NOEXCEPT  
Tue 25 Aug : SWAP_NOEXCEPT macro.  
Tue 25 Aug : No need for explicit vec3d_to_vec3, implicit conversion in the template now.  
Fri 21 Aug : Creating and deleting keyframes at runtime - Sun Position set in engine, Refactor of CloudWindowEditor  
Thu 20 Aug : Fix for compile errors and some warnings.  
Thu 20 Aug : Added extra reflections controls, fixed water surface being flipped  
Thu 20 Aug : Remove console build folders.  
Thu 20 Aug : Fix non-compiling shader.  
Wed 19 Aug : Fixing bad merges.  
Wed 19 Aug : Remove unwanted build files that shouldn't be in the repo. Also: hack disabled.  
Wed 19 Aug : Remove unwanted file.  
Wed 19 Aug : Remove unwanted file.  
Wed 19 Aug : Remove unwanted files.  
Wed 19 Aug : tvector3 fixes.  
Wed 19 Aug : Improvements to OpenGL GPU brightness calculations and debug info. No Platform ptr commit compared with 4.2a!  
Fri 14 Aug : Docs - Added water probe documentation page - altered / standardised fullstops on multiple pages  
Tue 11 Aug : Docs - Added multi-moon variables to variables page. Moons page - minor typo fix  
Tue 11 Aug : Moons page - added classes - bold fix - unity link back to legacy  
Tue 11 Aug : Cleaned up and fixed moons page formatting = moons index added - attempted fix for buoyancy index redirect 404  
Mon 10 Aug : Added Multi-Moon Explanation Page - Sky page rewording  
Mon 10 Aug : Removed Slack link from index page and added legacy note to previous moon setup tutorial.  
Mon 10 Aug : Full path for SIMUL_SOURCE_BUILD check.  
Sun 09 Aug : Uninitialized Variable Fix  
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
Sat 18 Jul : nightly commit  
Thu 16 Jul : Updated Aurora::RecompileShaders and Aurora::RestoreDeviceObjects  
Wed 15 Jul : Adjust BrightnessPower value.  
Wed 15 Jul : Added edited MilkyWay texture, adjusted default BrightnessPower to 0.05.  
Mon 13 Jul : SkyKeyframer::GetSiderealTimeDegrees() now uses interpolatedKeyframe.time. Fix for Sky Background doing full reverse rotation before midnight.  
Sun 12 Jul : Xbox header fix.  
Sun 12 Jul : Remove WIN64=1 for Linux  
Sun 12 Jul : DX12_JSON_FILE  
Sun 12 Jul : Fix Spectrum json location.  
Sun 12 Jul : Fix Spectrum json location.  
Sun 12 Jul : Fix compile error.  
Sat 11 Jul : Fix some warnings.  
Sat 11 Jul : Merges from 4.3 for platform support.  
Sat 11 Jul : Remove unwanted files.  
Sat 11 Jul : Spectrum PLATFORM_TXT.  
Sat 11 Jul : Cross-platform API build fixes.  
Fri 10 Jul : Commodore platform support.  
Fri 10 Jul : Fixes to bugs exposed by next-gen platform work.  
Thu 09 Jul : SkyKeyframer::GetSiderealTimeDegrees() now uses interpolatedKeyframe.time. Fix for Sky Background doing full reverse rotation before midnight.  
Wed 08 Jul : Update Doc  
Wed 08 Jul : ExternalRenderValues Struct Improvement  
Tue 07 Jul : Fix to Struct mis-match  
Tue 07 Jul : Storm fix  
Tue 07 Jul : Re-enabling Sky. Storm Fix.  
Thu 02 Jul : Mie Value from blueprint fix  
Thu 02 Jul : Mie value from blueprint fix  
Thu 02 Jul : Updating ExternalRenderValues + removed unnecessary CopyToDesigner Function  
Thu 02 Jul : Updating ExternalRenderValues Struct  
Tue 30 Jun : Rayleigh coef + Manual Colour Fix  
Tue 30 Jun : Shader Recompile Fix  
Mon 29 Jun : Added GetCloudLayerUIDByIndex Blueprint  
Mon 29 Jun : If statement fix  
Mon 29 Jun : Fix for flipped water surface in DX11  
Fri 26 Jun : Fix warnings.  
Fri 26 Jun : Nsis installer fixes for Dx12.  
Fri 26 Jun : Nsis installer fixes for Dx12.  
Thu 25 Jun : Fix merge issue  
Thu 25 Jun : Fix to layer names  
Thu 25 Jun : Layers have names, added wip Cloud Class  
Wed 24 Jun : Removed line that doesn't compile.  
Wed 24 Jun : Moved D3d12 json file.  
Wed 24 Jun : Build fixes.  
Wed 24 Jun : Small fix for DX11 water being incorrectly drawn and add the ability to draw only water  
Fri 19 Jun : added getCloudLayerUIDbyIndex  
Wed 17 Jun : Fix to Horizon and Zenith  
Wed 17 Jun : Doc Update  
Mon 15 Jun : Default for SIMUL_QT_DIR .  
Mon 15 Jun : Default for SIMUL_QT_DIR .  
Fri 12 Jun : Update to GetDependencies.bat  
Fri 12 Jun : fix to GetDependencies.bat  

<hr>
