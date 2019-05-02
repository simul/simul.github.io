---
title: Change List
layout: reference
weight: 120
---



Version HEAD
---
Wed 01 May : Minor fixes for sequencer stability  
Wed 01 May : SL/simul_clouds.sl GetRainAtOffsetKm() now flips the y-texture coordinate in OpenGL. Precipitation Region are now working in OpenGL.  
Tue 30 Apr : Precipitation Region Update: CloudWindow has blue interpolated and cyan static circles representing precipitation regions. Inside of CloudWindow, the cyan static circles can be positioned by left mouse button + shift. "Lock To Cloud" changed to "Affected by winds". Override Winds lock the precipitation region to the centre of the cloudkeyframe. Minor update to Debug Overlays for Rain Textures and Cloud Cross-sections.  
Tue 30 Apr : Update to cloud.sfx MapToWindow(), which correctly sets the height of the clouds when using a masking texture.  
Wed 24 Apr : Updated OpenGL/Effect.cpp/.h and OpenGL/RenderPlatform.cpp to have Sync objects around dispatch compute calls that uses a rewrite structured buffer.  
Tue 23 Apr : Changes to .sq files. The opening and closing curly brackets {} are now saved to the file. This allows .sq file to be a converted to .asset files in Unity.  
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
Wed 06 Feb : Performance update for the cloud light texture processing  
Wed 06 Feb : InitFromExternalTexture2D() now takes in a MSAA parameter (Changed in crossplatform and all renders). OpenGLSample.cpp has been updated to show this feature. RainDepthTextureMS is now set inside of PrecipitationRenderer.cpp. Minor updates to FramebufferGL and TextureHandles in OpenGL/Effect.cpp and OpenGL/Texture.cpp.  
Tue 05 Feb : Fix OpenGL Shutdown  
Tue 05 Feb : DeviceManager IsActive fn.  
Tue 05 Feb : TrueSkyRenderer used 8 MIPS and OpenGL correctly displays them. Minor update to rain.sfx, LightProbeConstants are padded to conform to std140. OpenGL/Texture.cpp LoadFromFile() cycles through all texture paths.  
Mon 04 Feb : Debug: Forcing 8 MIPS for cube maps.  
Mon 04 Feb : CopyToTargetDir.py fixes.  
Mon 04 Feb : CopyToTargetDir.py fixes.  
Mon 04 Feb : static default_size for skylight.  
Fri 01 Feb : Cmake build fixes for static projects.  
Tue 29 Jan : Fix for Skylights not rendering atmospheric effects  
Tue 29 Jan : Fix rain.sfx build  
Mon 28 Jan : PS4 ptr.  
Mon 28 Jan : Rain etc to separate translucent buffer optionally.  
Sun 27 Jan : Update Setup.nsi  
Sun 27 Jan : Update SkySequencer.nsi  
Thu 24 Jan : Updated rain.sfx so that rain in Vulkan works correctly. CloudRenderer.cpp RenderPointSource(), checks the arraySize, before setting textures for a cube map. Minor clean up of Vulkan/RenderPlatform.cpp Resolve(), though they are still issue in resolving the msaa framebuffer.  
Wed 23 Jan : Minor update to rain.sfx, where mapped_rain will have a minimum value of 0.25. This has fixed the issues with mapped_rain value in the VS; rain_dist and solid_dist values in the PS on OpenGL!  
Wed 23 Jan : Updated light_probes.sfx and OpenGL/GLSL/shader_platform.sl due a shader compile issue. OpenGL/Effect.cpp changed so that the shaderResource.slot can update the binding index, use for the Lightning vertices SSBOs. Updated rain.sfx to include "..._msaa" passes and for the vertex shader to resolve the MS texture. OpenGL has issues with mapped_rain value in the VS; rain_dist and solid_dist values in the PS!  
Fri 18 Jan : .  
Thu 17 Jan : Updated .sl files, so that UBO and SSBO in OpenGL are correctly laid out. Vulkan's GetBuffer() function changed back to return a vec3* pointer due instability. For RenderDoc, if !GLAD_GL_ARB_bindless_texture, then it will attempt to load the functions from the driver.  
Thu 17 Jan : Minor update to cloud shadows  
Wed 16 Jan : General fixes to rain, cloud shadows, atmospherics and others, reduced detail of water objects for performance  
Tue 15 Jan : BaseSkyRenderer and CloudRenderer, when using OpenGL or Vulkan only, cased return value of GetBuffer() from a vec3* to a vec4*. OpenGL/Vulkan need this as a vec4* for glsl std140/std430 the SSBO. BaseWeatherRenderer has had temporary fix removed.  
Mon 14 Jan : Add 2017 Effects11_2017.vcxproj project. Update installers. Tidy up old functions.  
Mon 14 Jan : Updated DX11, DX12 and OpenGL MSAA FBO. Adjusted Lightning Renderer and LineQueryResult in simul_cloud_constants.sl  
Mon 14 Jan : Add units.h from https://github.com/nholthaus/units for physical units.  
Mon 07 Jan : Add different VS launcher scripts. Help updates.  
Sun 30 Dec : Cmake build fixes.  
Sun 30 Dec : Add Cmake files.  
Sat 29 Dec : Samples build  
Sat 29 Dec : Solution dependencies.  
Fri 28 Dec : Remove refs to deleted files  
Thu 27 Dec : Only include \<filesystem\> on Windows.  
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

<hr>
