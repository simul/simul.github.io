---
title: Change Log
layout: reference
weight: 120
---


Version 4.4
---
Thu 29 Jul : WIP CloudRaytraceLighting update.  
Thu 29 Jul : WIP added RT cloud UI and overlays. cloud_raytrace.sfx used constant buffer for TraceRays parameters. CloudRaytraceLighting.h updated with ShaderBindingTable and new methods.  
Tue 20 Jul : RenderingPlugin.cpp InitDefaultTargets() will note continuously log warning.  
Mon 19 Jul : CloudThresholdDistanceKm is now in Has/Get/SetFloat().  
Wed 14 Jul : PluginTrueSkyRenderer::SetTexture() checks for valid texture. Platform updated too. SIMUL_CERR changed to SIMUL_CERR_ONCE in UnityD3D12Context.  
Fri 09 Jul : Update to CreateRTV().  
Fri 09 Jul : Better checks in UnityD3D12Context::CreateRTV().  
Fri 09 Jul : Minor fixes for Jarvis build.  
Thu 08 Jul : Updated cloud_edit.sfx for better rendering of elements 'on the sphere'.  
Tue 06 Jul : Velocity trails.  
Sun 04 Jul : Global weather: advection is now functional.  
Sun 04 Jul : Added Docs folder for Sphinx documentation.  
Sun 04 Jul : Added WGS84 support. WGS84 coordinate system now applies internally in CloudWindow. X=Meridian, Y=90 deg East, Z=North Pole as before.  
Sun 04 Jul : Added GlobalWeather system, experimental.  
Tue 29 Jun : RenderTarget checks for PS4.  
Thu 24 Jun : Fix delayload settings. DELAYIMP_INSECURE_WRITABLE_HOOKS to test dll loading.  
Mon 21 Jun : GetCustomD3D11RTV() does typeless to typed convert of image format. Minor update to OpenGLSample for RenderDoc support. Better checks on textures for DX11 and DX12.  
Tue 15 Jun : Minor correction.  
Mon 14 Jun : TrueSkyPluginRender moved Vulkan out into separate functions. UnityViewStruct::colourTextureArrayIndex added and updated IUnityGraphicsVulkan.h. UnityD3D12Context better handled of reloading the context. GetCustomD3D11RTV() for Unity HDRP skylights.  
Mon 14 Jun : Added WinPixGpuCapturer support to SkySequencer.  
Wed 02 Jun : Minor change to clouds_experimental.sl  
Tue 01 Jun : Updated clouds_experimental.sl noiseval calculation and step count for performance. cloud_update.sfx illumation texture updated values.  
Tue 01 Jun : Updated clouds_experimental.sl removed upsampling_offset, changed opacity calculation and added cosine value to ColourStep2().  
Tue 01 Jun : Updated clouds_experimental.sl and clouds_raytrace.sl  
Tue 01 Jun : Add CloudDepthTemporalAlpha to UI and default to 0.5. Add Cycle overlay view id to Main UI.  
Wed 26 May : Updated to support WinGDK.  
Tue 25 May : Updated conditional statement in UnityRenderEventD3D12(). Better viewport assignment in UnityRenderFrame().  
Mon 24 May : offset fix  
Mon 24 May : Update worleyTexcoordOffset to worleyOffsetKm. Removed noise3DTexcoordScale2, noise3DTexcoordOffset2 and EdgeNoiseWavelength2Km from shaders. Update noise input from cloud_lighting.sfx and updated cloud_experimental.sla and others.  
Fri 21 May : Fixing dead link  
Fri 21 May : Further changes  
Fri 21 May : link fix  
Fri 21 May : Amending doc errors  
Fri 21 May : Link update for SDK  
Fri 21 May : Adding Skysequence specific page, fixed dead link within timeline page  
Fri 07 May : Adding WaterMask documentation page as not previously created. this includes image and update to waters index  
Fri 07 May : Commodore support merges from 4.3  
Thu 06 May : Add SkySequencer icon to TrueSkyUI/MainWindow.  
Thu 06 May : Change Directory for UE from XboxSeriesX to XSX  
Tue 04 May : PlanetRadius Functional  
Thu 29 Apr : Updated Unity D3D12 for greater stability. assimp-vc142-mt is copied by CopyToTargetDir.py, as SimulCrossPlatform_MD has a link depenedencies to it if using PLATFORM_USE_ASSIMP. GetSimulVersion() updated for 4.4.  
Tue 27 Apr : Fix for trueSKY build for XboxOneGDK. Platform ptr.  
Mon 26 Apr : Minor change to make output clearer.  
Tue 20 Apr : Updated Unity PlatformName and directories for Spectrum.  
Mon 19 Apr : Removed Octaves  
Fri 16 Apr : Doc Version support corrections and minor changes  
Wed 14 Apr : Docs update  
Tue 13 Apr : fixes for docs  
Tue 06 Apr : Water: newBuoyancyObject-\>outputsBuffer was incorrectly initialized without CPU read access. As was BoundedWaterObject::waterProbeOutputsBuffer.  
Thu 01 Apr : Fix water rendering in Vulkan. Fix numerous resource leaks in water renderer and related classes. Enable water in Sky Sequencer.  
Thu 01 Apr : RenderFrameStruct::colourTarget is assigned an RTV in D3D12. Nullptr check in InitDefaultTargets().  
Thu 01 Apr : Indent error fix for CopyToTargetDir.py  
Wed 31 Mar : Updated Unity Target Directories for Spectrum.  
Wed 31 Mar : Updated hard-coded link library for Spectrum.  
Tue 23 Mar : UI updates, unfinished design  
Mon 22 Mar : Added class CloudRaytraceLighting. Moved AABB Generation variables and functions to CloudRaytraceLighting. Clean up warnings.  
Sun 21 Mar : Fix memory tracking overflows.  
Fri 19 Mar : Updated RenderAABBWireframe() to account of central texel. Better generation of non-uniform grid boxes.  
Thu 18 Mar : RenderAABBWireframe() improved, draws in all quadrants.  
Wed 17 Mar : Fix for CloudRenderer::LoadVDB() and EvaluateSH()  
Wed 17 Mar : Platform ptr.  
Wed 17 Mar : Added ShowCloudAABB debug overlay  
Wed 17 Mar : RenderAABBWireframe() added.  
Wed 17 Mar : Update cloud_raytrace shaders. Platform ptr.  
Tue 16 Mar : Build fixes  
Mon 15 Mar : Changes to looping, precipitation colouring for keyframes  
Mon 15 Mar : Initial tests/changes to Timeline  
Fri 12 Mar : Uncommented out RenderPostTranslucent  
Thu 11 Mar : Update CopyToTargetDir.py to use PlatformType enum, cleared up functions and output.  
Wed 10 Mar : Updated imported water functions to stop using bool returns  
Tue 09 Mar : Limit Zoom in CloudWindow  
Mon 08 Mar : Added Acceleration Structure build based on AABB. CS_CloudDensityAABB() generation via compute shader. Added cloud_raytrace.sfx inital commit. Platform ptr.  
Fri 05 Mar : Delete old .properties files, moved deleteOldFtp.py  
Wed 17 Feb : Fix for black clouds when initialising trueSKY without a CloudKeyframer.  
Fri 12 Feb : Removed some references to latitude and longitude to prevent the values from being set incorrectly  
Fri 12 Feb : composite.sl uses absolute value for the distance to avoid nan/inf.  
Wed 10 Feb : on_actionShowCloudQueries_toggled() and Referenced amended. Added SDF generation for CloudDensity volume texture.  
Wed 03 Feb : CloudRenderer::PreRenderUpdate() checks OverrideWind in CloudLayer::CloudKeyframer* before calling CloudWindow::Update() with a new speed.  
Tue 02 Feb : CloudRenderer::SetCloudConstants() convert wind direction from RAD to DEG.  
Fri 15 Jan : Initialization order fix. Debug option for PrecipitationRaduisMeters  
Fri 15 Jan : CLoud update reset if source changes.  
Thu 14 Jan : Fixed noise offset behaviour due to wind in Variable Grid cloud rendering.  
Wed 13 Jan : Take Cmake var for vulkan sdk dir.  
Tue 12 Jan : More output from Build.bat  
Tue 12 Jan : .  
Tue 12 Jan : Platform ptr.  
Tue 12 Jan : Platform ptr.  
Tue 12 Jan : Updated version number to 4.4.  
Mon 11 Jan : Update ReadMe.md  
Mon 11 Jan : Don't use deprecated fns - this is an error on some platforms.  
Mon 11 Jan : Remove references to effects11_MT.  
Mon 11 Jan : Platform ptr  
Mon 11 Jan : Add realTimeWind option to CLoudRenderingOptions.  
Mon 11 Jan : Sample for D3D12 call FlushImmediateCommandList() at end of OnCreateDevice(). Cleaned up BaseTerrainRenderer.cpp.  
Sun 10 Jan : Platform ptr  
Sun 10 Jan : Vulkan sample fix  
Sun 10 Jan : Updated Platform now requires mip count in ensuretexture2dSizeAndFormat.  
Sat 09 Jan : Correct Vulkan version  
Sat 09 Jan : Added Setup.py. This will replace Build.bat etc.  
Fri 08 Jan : Fix to build.bat, Update to release.properties to include Vulkan SDK version  

<hr>
