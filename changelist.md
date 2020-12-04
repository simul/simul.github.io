---
title: Change Log
layout: reference
weight: 120
---


Version 4.3
---
Wed 02 Dec : Fix to struct issue C# to C++  
Wed 02 Dec : Further fixes and additions to docs - Notably Precipitation additions, and moving some information from index pages to relevant locations.  
Tue 01 Dec : Minor fixes and rearrangement for docs  
Fri 20 Nov : Removed Toolchain  
Tue 17 Nov : Added DeleteKeyframeByUID  
Tue 17 Nov : Fix resource leak.  
Tue 17 Nov : Fix D3D11 warnings.  
Tue 17 Nov : int to size_t  
Mon 16 Nov : No need for struct size check more than once.  
Fri 13 Nov : Small fix  
Fri 13 Nov : UnityMemoryInterface compile fix.  
Fri 13 Nov : Update UnityMemoryInterface to use size_t.  
Fri 13 Nov : Memory tracking uses size_t which is 64-bit, not int which is 32-bit and overflows.  
Wed 11 Nov : Fix WindowUpdater recompile.  
Tue 10 Nov : Fix release.properties  
Tue 10 Nov : Dx11 Warning Fix, removal of force full init  
Mon 09 Nov : DX11 fixes  
Fri 06 Nov : Fix some D3D11-related problems.  
Fri 06 Nov : Small Fixes  
Wed 04 Nov : Build fixes for Platform change.  
Mon 02 Nov : Fix tex-\>IsValid() crash.  
Wed 28 Oct : Removed done_mips.  
Tue 27 Oct : Remove unused var.  
Tue 27 Oct : Initial pass for optimisation for Aurora.  
Tue 27 Oct : Check for null aurora.  
Tue 27 Oct : Remove unsupported call.  
Mon 26 Oct : CloudRenderer::RenderPrecipitationVolumeTexture() better checks and early outs.  
Mon 26 Oct : Platform ptr.  
Mon 26 Oct : Platform ptr.  
Mon 26 Oct : SkySequencer uses RenderDocLoader; switch to toggle is in CMake: SIMUL_SKYSEQUENCER_LOAD_RENDERDOC_DLL.  
Fri 23 Oct : Fix for GPU sky brightness in OpenGL. Change to terrain shader face culling.  
Fri 23 Oct : Doc update to link to VS Redist  
Thu 22 Oct : Performance improvements to Variable Grid render.  
Thu 22 Oct : Check global position for Aurora::PreRenderUpdate().  
Wed 21 Oct : Build fixes; also enable D3D11 to be disabled in CMake.  
Fri 16 Oct : DeviceContext now split into two classes, base DeviceContext and derived GraphicsDeviceContext. The latter will be used for most rendering, while the base class can be used in asynchronous compute.  
Fri 16 Oct : Re-enabling copy code  
Fri 16 Oct : Delay init of SkySequencer renderers.  
Thu 15 Oct : Docs - Update time progression page to reflect unity changes  
Thu 15 Oct : Additional profiling  
Thu 15 Oct : Updated Aurorae Docs.  
Wed 14 Oct : Show Auroral Oval is default on in SkySequencer.  
Wed 14 Oct : Added Capitals to ref headers and moved a heading into a class to make this cleaner in performance page  
Tue 13 Oct : Add fractal octaves to cell noise. Improve blending.  
Tue 13 Oct : Added PrecipitationBaseKm to define lower bound of PrecipitationLayers. WIP forced Z nearest filtering.  
Tue 13 Oct : Cell noise  
Mon 12 Oct : Shader tests.  
Mon 12 Oct : Add CELLNOISE cloud class.  
Sat 10 Oct : Block-update improvements.  
Fri 09 Oct : Check version number for ExternalDynamicValues and ExternalRenderValues. Match structures with 4.2a.  
Fri 09 Oct : Option to disable a layer in Sequencer. Max Density Fix. Removal of High Detail proportion  
Fri 09 Oct : cloud window update sync'd to layers.  
Fri 09 Oct : Transitioning to synchronized layer-volume update.  
Thu 08 Oct : Additional stored data.  
Thu 08 Oct : Extract layer data at initialization of cloud update.  
Thu 08 Oct : Add cloud_update.sfx shader, multi-texture blend for main cloud volume.  
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
Tue 29 Sep : Spherical rendering  
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

<hr>
