---
title: Change List
layout: reference
weight: 120
---



Version HEAD
---
Thu 13 Jun : Fix Qt plugin search for Unity only.  
Thu 13 Jun : GeneratedFiles includes for SequencerQtWidgets in TrueSkyUI_x64_v140.vcxproj  
Thu 13 Jun : Add GenerateFiles include dir.  
Thu 13 Jun : Improve cloud window UI.  
Thu 13 Jun : Fix long pause at UI startup due to Qt search path.  
Fri 31 May : OpenGL and D3d12 error fixes.  
Fri 31 May : Fix water shutdown crash.  
Fri 31 May : Deployment py fixes.  
Thu 30 May : Add RenderDelegate.h  
Thu 30 May : Add RenderDelegate.h  
Thu 30 May : Don't invalidate pixelShaders from Effect: RenderPlatform is responsible for this.  
Thu 30 May : Fix for buoyancy objects not sampling the surface at the correct location. Also contains a couple of minor fixes, and a temporary fix for DX12 not seeing the profile buffer offset and direction arrays  
Thu 30 May : Fix for OpenGL SFX compilation. New SfxConfig parameter: identicalIOBlocks.  
Wed 29 May : Update Unity plugin api to new structs.  
Wed 29 May : water.sfx compiles for Vulkan.  
Wed 29 May : Update ExternalTexture definition and add full ExternalTexture structs to RenderFrameStruct, more robust for different API's.  
Tue 28 May : Add sfxb shader bins.  
Tue 28 May : Fix broken effect shader load.  
Tue 28 May : Wrap up shader binaries in sfxb for Vulkan and D3D12.  
Tue 28 May : Shader binaries lumped together in sfxb file - if -w is used in sfx.exe.  
Mon 27 May : PS4 API update and build fix.  
Mon 27 May : Delayed destruction for effects to prevent destroying in-use API objects when recompiling. Update skylight struct.  
Fri 24 May : Updated LightningRenderer.cpp to use MSAA. Updated CloudRenderer.cpp RenderRainMapTexture() and RenderCloudShadowTexture() Refined Debug Overlays due to new mono spaced font. Fix OpenGL cloud shadows. Fix rain map lookups in SFX/rain.sfx OverrideWind added back.  
Thu 23 May : Updated Rain shader using Reflection and Refraction. CloudRenderer.cpp split function into RenderCloudShadowTexture() and RenderRainMapTexture(). Precipitation Regions dimension are drawn onto the rain map. VolumeQueryResult::rain_to_snow is updated from rain map. simul_clouds.sl split function GetRainAtOffsetKm() GetRainToSnowAtOffsetKm(). quaternion.sl quat_from_axis_angle_radians() and quat_from_axis_angle_degrees().  
Mon 20 May : QT fix  
Mon 20 May : CloudKeyframeEditWidget fix  
Mon 20 May : Fix for Simple DX11 and DX12 renderer examples  
Mon 20 May : VR fix for water, other small fixes  
Fri 17 May : Fix Vulkan shader build.  
Fri 17 May : OverrideWind now works to allow precise positioning of 3D cloud layers. Click and drag in Cloud Window editor. Global wind is now a cosmetic flow, doesn't affect cloud positions.  
Fri 17 May : New 16x11 monospaced font texture. D3D11 loads textures as texture instead of as SRV.  
Wed 15 May : Pass framenumber to DisplaySurface to get consistent framenumbers for multiple windows.  
Mon 13 May : Minor fix to CloudWindow UI layout and colours. Minor fix for SetCloudConstants() and FillInQueries(). SetPrecipitationCentre() removed.  
Mon 13 May : Fix sequencer standalone crash.  
Mon 13 May : Fix shader build path for non-Cmake builds.  
Sun 12 May : Fix Xbox refs to deleted shaders.  
Sun 12 May : Project fix for DirectX12Sample_x64_v140.vcxproj  
Sat 11 May : Dx12 sample build  
Fri 10 May : Fix stringFormat error in Sfx. Prevent at least some of the spurious console output from Flex in preprocessor.lpp.  
Fri 10 May : Fix cloud mip generation. CMake build improvements.  
Thu 09 May : Minor updates to simul_clouds.sl GetRainAtOffsetKm(). The rain map is not re-drawn to reflect the precipitation region.  
Wed 08 May : New Colour Scheme for Cloud Window to improve clarity. Fix for incorrect Precipitation Region position in edge cases. Clouds/BaseGpuCloudGenerator.h SetPrecipitationCentre() removed.  
Wed 08 May : New Colour Scheme for Cloud Window is improve clarity. Fix for incorrect Precipitation Region position in edge cases. Clouds/BaseGpuCloudGenerator.h SetPrecipitationCentre() removed.  
Fri 03 May : Fix for Rain and Rain Streaks appearing at altitudes.  
Fri 03 May : Disable part of the flow rays calculations due to current PS4 incompatibility, current progress on fixing water vr support  
Wed 01 May : Minor fixes for sequencer stability  
Wed 01 May : SL/simul_clouds.sl GetRainAtOffsetKm() now flips the y-texture coordinate in OpenGL. Precipitation Region are now working in OpenGL.  
Tue 30 Apr : Precipitation Region Update: CloudWindow has blue interpolated and cyan static circles representing precipitation regions. Inside of CloudWindow, the cyan static circles can be positioned by left mouse button + shift. "Lock To Cloud" changed to "Affected by winds". Override Winds lock the precipitation region to the centre of the cloudkeyframe. Minor update to Debug Overlays for Rain Textures and Cloud Cross-sections.  
Tue 30 Apr : Update to cloud.sfx MapToWindow(), which correctly sets the height of the clouds when using a masking texture.  
Wed 24 Apr : Updated OpenGL/Effect.cpp/.h and OpenGL/RenderPlatform.cpp to have Sync objects around dispatch compute calls that uses a rewrite structured buffer.  
Tue 23 Apr : Changes to .sq files. The opening and closing curly brackets {} are now saved to the file. This allows .sq file to be a converted to .asset files in Unity.  
Tue 23 Apr : Small CMake fixes  
Wed 17 Apr : Initial Documentation updates, added buoyancy objects, small fixes  
Fri 12 Apr : Updated Sky Sequencer UI to show Snow Speed and Snowflake Size. Fixed CloudWindowWidget to support multiple concurrent rendering API in the main view.  
Thu 11 Apr : PS4 Pointer  
Wed 10 Apr : Updated SFX compiler to fix OpenGL issue binding slot and UBO for TextureHandles. The binding slot defaults to 0, expect in the pixel/fragment shader where it is 1; this was to solve the issue of snow rendering New parameter in SfxConfig maintainSamplerDeclaration to deal with issue between GLSL and PSSL. Updated rain.sfx PS_SnowParticles_NoCubemap();  
Tue 09 Apr : Fix paths for Sequencer D3D11 shaders.  
Thu 04 Apr : Applications/SkySequencer/MainWindow.cpp CloudWindow can now use DX11, DX12 or OpenGL. Clouds/BaseGpuCloudGenerator.h SetPrecipitationCentre() added. Clouds/CloudKeyframer.cpp rotateByOffset() updated to use Quaternion solely. Clouds/CloudRenderer.cpp RenderCrossSections() lays out all textures correctly. SetCloudConstants() OverrideWind checkbox locks the PrecipitationRegion to the cloud map. RenderCloudWindow() now draws blue circle to denote the PrecipitationRegion. Platform/OpenGL/Texture.cpp LoadTextureData() can correct any errno. Sky/BaseSkyRenderer.cpp RenderCelestialDisplay() is corrected.  
Fri 29 Mar : New technique "msaa_with_lightpass" in hdr.sfx. Updated Clouds/BaseWeatherRenderer.cpp to match. Minor logic update to Effect::SetUnorderedAccessView().  
Fri 29 Mar : Added check to ensure native OpenGL textures in Effect::SetUnorderedAccessView() are valid before binding them.  
Thu 28 Mar : Update to PrecipitationRegion, which now uses a quaternion for its position, though cloudConstants.rainCentreKm is still a vec3. Update to Quaterniond.h, as definition and declaration didn't match.  
Wed 27 Mar : Fix cloud_edit.sfx compille for DX11.  
Sun 17 Mar : Add TrueSkyUI/CMakeLists.txt  
Thu 07 Mar : Added ability for plugins to get the sampled height of the cloud shadow  
Wed 06 Mar : Added commented out shader code for cloud shadow offsets  
Tue 05 Mar : disable part of the water to fix PS4 version  
Mon 04 Mar : Update to water mips, small fixes  
Thu 28 Feb : Update to VolumeQueryResult and LineQueryResult, which now uses vec4. SFX/clouds.sfx and SL/simul_cloud_constants.sl updated to match. BaseSkyRenderer.cpp GetLightingQuery() updated to use vec4.  
Thu 28 Feb : Add Switch projects.  
Wed 27 Feb : Autofill PS4 resource slots.  
Sat 23 Feb : Sfx specified registers.  
Sat 23 Feb : Sfx reverted some bad code.  
Fri 22 Feb : Amended SunElevationSlider in SequencerQtWidgets/KeyframeEditWidget.ui  
Fri 22 Feb : Undo keyFrameEditWidget Change  
Fri 22 Feb : Cloud/CloudRenderer.cpp updated function CloudRenderer::RenderQueries().  
Thu 21 Feb : ClearFencedTextures now crossplatform. Called in plugin frame init.  
Thu 21 Feb : Minor update to BaseSkyRenderer  
Thu 21 Feb : Sfx support for inline shader binaries in the .sfxo output file.  
Thu 21 Feb : Sky/BaseSkyRenderer.cpp has a new function RenderLightingQueryResultsText(). Displays the values of the current LightQueryResults to the screen. This is used in Clouds/TrueSkyRenderer.cpp TrueSkyRenderer::RenderOverlays() under the Fades output.  
Wed 20 Feb : Minor update to Sky/BaseSkyRenderer.cpp  
Wed 20 Feb : Updated BaseSkyRenderer.cpp FillInLightingQueries(), due OpenGL buffer misalignment. LightingQueryResult now has a vec4 for the position and padded. It is initialise in SFX/sky.sfx lightingQueryInputs is now a StructuredBuffer of vec4.  
Wed 20 Feb : BaseSkyRenderer::RenderBackgroundCubemap() updated to accept depthTexture as nullptr.  
Tue 19 Feb : Fix delayloads. Must use semicolon separateor in vcxproj!  
Tue 19 Feb : Vulkan cubemap issue is fixed, still issues with its spherical harmonics. The native framebuffer is passed from Platform/Vulkan/Framebuffer.cpp and used when rendering cube map faces in Platform/Vulkan/RenderPlatform.cpp.  
Mon 18 Feb : Fix for storms not deleting  
Sat 16 Feb : Call ApplyDefaultRenderTargets to ensure we are actually using the default target specified.  
Sat 16 Feb : PS4 ptr. RenderCloudShadowTexture should be called before FillInQueries. internalFrameNumber for PlatformConstantBuffer. ORBIS ActivateRenderTargets in plugin to make sure we're Actually using the default RT.  
Wed 13 Feb : Fix delayloads: commas don't work, must use semicolons!  
Wed 13 Feb : Platform/Vulkan/RenderPlatform.cpp CreateVulkanRenderpass() take in a MSAA value, default is 1. Platform/Vulkan/RenderPlatform.cpp Resolve() is currently commented out.  
Tue 12 Feb : Fix window lighting  
Mon 11 Feb : Minor Update to CopyToTargetDir.py.  
Mon 11 Feb : CopyToTargetDir.py: uiLocation default is set as 'SIMUL+"/exe/"+PLATFORM+"/"+TOOLSET+"/"+CONFIGURATION'.  
Mon 11 Feb : CopyToTargetDir.py: uiLocation default is set as 'SIMUL+"/exe/"+PLATFORM+"/"+TOOLSET+"/"+CONFIGURATION'.  
Sun 10 Feb : Improve EffectPass frame counting to prevent shaders that aren't used every frame getting confused. Add numSamples to init for Vulkan external textures.  
Sat 09 Feb : Hopeful fix to prevent from using 16 texture slots on PS4. All API's should stay under 16 for texture slots..  
Fri 08 Feb : Hopeful fix to prevent from using 16 texture slots on PS4.  
Thu 07 Feb : PS4 ptr and Cmake fixes.  
Thu 07 Feb : Slight nsi fixes.  
Thu 07 Feb : Slight nsi fixes.  
Wed 06 Feb : Fix problem with cloud fill on Vulkan. Frame number was always zero.  

<hr>
