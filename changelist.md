---
title: Change Log
layout: reference
weight: 120
---


Version 4.3
---
Fri 16 Oct : Re-enabling copy code  
Thu 15 Oct : Docs - Update time progression page to reflect unity changes  
Thu 15 Oct : Updated Aurorae Docs.  
Wed 14 Oct : Show Auroral Oval is default on in SkySequencer.  
Wed 14 Oct : Added Capitals to ref headers and moved a heading into a class to make this cleaner in performance page  
Tue 13 Oct : Added PrecipitationBaseKm to define lower bound of PrecipitationLayers. WIP forced Z nearest filtering.  
Fri 09 Oct : Check version number for ExternalDynamicValues and ExternalRenderValues. Match structures with 4.2a.  
Fri 09 Oct : Option to disable a layer in Sequencer. Max Density Fix. Removal of High Detail proportion  
Wed 07 Oct : Platform ptr.  
Wed 07 Oct : Platform ptr.  
Wed 07 Oct : General fix for warning for casting. Aurora UI change to match engines, docs updated. Shaders/Vulkan/CMakeLists.txt changed to use Platform/Vulkan/Sfx/Vulkan.json. Commit Platform ptr.  
Wed 07 Oct : enum fixes for Topology.  
Wed 07 Oct : Update Vulkan json  
Mon 05 Oct : Update to ExternalDynamicValues.  
Mon 05 Oct : Small fixes for unity  
Mon 05 Oct : Fix to Cloud type class in Sequencer  
Mon 05 Oct : Update to full init  
Mon 05 Oct : Update to ExternalStruct to include WindowGrid and LightingMode. Fix to Sequencer. Disabled Random Seed  
Fri 02 Oct : Added Save/Load functions to Aurora.  
Fri 02 Oct : Fix layout in UnityPluginInterface.h and commit Platform ptr.  
Fri 02 Oct : SetShowAuroraeControls() added to disable in Engine. Aurora values added ExternalRenderValues. Aurora is now solely in SkyKeyframer  
Wed 30 Sep : Fixing minor issues and adding missing image on blueprint page  
Wed 30 Sep : Updating FAQ as Niagara information was incorrect  
Wed 30 Sep : Update to blueprint pages - adding in Create / delete of keyframe and layers - as well as new map texture location and nodes  
Wed 23 Sep : Updating Docs - 4.3 specific features  
Wed 23 Sep : Rename Override Wind  
Tue 22 Sep : Keep licence header visible  
Tue 22 Sep : Block lighting corrections, improvements.  
Mon 21 Sep : Update position of celestial background.  
Mon 21 Sep : Fix CloudRenderer::RenderCrossSections() debug overlays viewports.  
Mon 21 Sep : Minor space/tab format changes to WindowUpdater.cpp/.h  
Mon 21 Sep : Minor space/tab format changes to WindowUpdater.cpp/.h  
Mon 21 Sep : Minor corrections.  
Fri 18 Sep : Cloud block fill in direction away from light. Automatic number of mips in cloud texture so that block size is maximized. Remove old unused code and classes.  
Thu 17 Sep : Fix block update issue.  
Thu 17 Sep : Platform ptr.  
Thu 17 Sep : Removing Old Keyframe Values  
Wed 16 Sep : Update to the Aurorae documentation.  
Wed 16 Sep : Actually fixed image extensions  
Wed 16 Sep : Fixed image extensions  
Wed 16 Sep : Fix to Uninstaller + GLFW files for Static Builds  
Tue 15 Sep : Update to water object tutorial  
Tue 15 Sep : .nsi fixes  
Mon 14 Sep : Commit Platform ptr.  
Mon 14 Sep : BoundedWaterObject initialiser list order fixed.  
Fri 11 Sep : Updated documentation for water  
Fri 11 Sep : Vulkan needs the precipitationLayerInfos StructuredBuffer to be applied on the init pass.  
Fri 11 Sep : Keyframe Positioning via Lat/Lon/Heading input  
Fri 11 Sep : Minor UI update.  
Wed 09 Sep : Aurorae Documentation typo fixed.  
Wed 09 Sep : Minor correction to rainbow compositing to cubemap.  
Wed 09 Sep : Fix for aurorae variables.md  
Wed 09 Sep : Platform ptr.  
Wed 09 Sep : Minor change to clouds.sfx  
Wed 09 Sep : Unifying changes from 4.2a: PrecipitationGridDivisors, updated precipitation rendering with PrecipitationLayerInfo, Debug Overlays for Rain and Queries and initial change for Unity D3D12.  
Wed 09 Sep : Added Aurorae documentation and corrected others. Changed Aurora FAC controls. Minor improvements to Aurora checksum, class initialisation etc.  
Wed 09 Sep : Removal of automatic Sun + Moon Position from Sky Keyframes. Removed Star variables out of Sky Layer settings. (Both moving engine side)  
Tue 08 Sep : Added support for water objects to accept meshes for their shape, rather than using only the given generated surface  
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

<hr>
