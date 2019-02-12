---
title: plugin
layout: reference
weight: 0
---
namespace plugin
===

| Include: | PlugIns/TrueSkyPluginRender/TrackingAllocator.h |



Classes and Structures
---

| struct [Query](plugin/query) |  |
| class [TrackingAllocator](plugin/trackingallocator) |  |

Functions
---

| void | [StaticExecuteDeferredRendering](#StaticExecuteDeferredRendering)() |
| void * | [StaticGetEnvironment](#StaticGetEnvironment)() |
| int | [StaticInitInterface](#StaticInitInterface)() |
| int | [StaticOnDeviceChanged](#StaticOnDeviceChanged)(void device) |
| void | [StaticRemoveView](#StaticRemoveView)(int view_id) |
| void | [StaticRenderOverlays](#StaticRenderOverlays)(void device, void pContext, void externalDepthTexture, float viewMatrix4x4, float projMatrix4x4, int view_id, void colourTarget, simul::crossplatform::Viewport viewports) |
| void | [StaticSetDebugOutputCallback](#StaticSetDebugOutputCallback)(DebugOutputCallback) |
| void | [StaticSetGraphicsDevice](#StaticSetGraphicsDevice)(void device, simul::crossplatform::RenderPlatformType deviceType, UnityGfxDeviceEventType eventType) |
| void | [StaticSetGraphicsDeviceAndContext](#StaticSetGraphicsDeviceAndContext)(void device, void context, simul::crossplatform::RenderPlatformType deviceType, UnityGfxDeviceEventType eventType) |
| void | [StaticSetMemoryInterface](#StaticSetMemoryInterface)(simul::base::MemoryInterface) |
| int | [StaticSetSequence](#StaticSetSequence)(std::string SequenceInput) |
| int | [StaticSetSequenceTxt](#StaticSetSequenceTxt)(char txt) |
| int | [StaticShutDownInterface](#StaticShutDownInterface)() |
| void | [UnitySetGraphicsDevice](#UnitySetGraphicsDevice)(void device, simul::crossplatform::RenderPlatformType deviceType, UnityGfxDeviceEventType eventType) |


Functions
---

### <a name="StaticExecuteDeferredRendering"/>void StaticExecuteDeferredRendering()
Render all the deferred contexts.

### <a name="StaticGetEnvironment"/>void * StaticGetEnvironment()
Returns the simul::clouds::Environment pointer.

### <a name="StaticInitInterface"/>int StaticInitInterface()
Ensure that the renderer is initialized. Subsequent calls have no effect.

### <a name="StaticOnDeviceChanged"/>int StaticOnDeviceChanged(void device)
Assign the platform GPU device pointer.

### <a name="StaticRemoveView"/>void StaticRemoveView(int view_id)
Free up the specified view and its resources.

### <a name="StaticRenderOverlays"/>void StaticRenderOverlays(void device, void pContext, void externalDepthTexture, float viewMatrix4x4, float projMatrix4x4, int view_id, void colourTarget, simul::crossplatform::Viewport viewports)
Render the debug overlays.

### <a name="StaticSetDebugOutputCallback"/>void StaticSetDebugOutputCallback(DebugOutputCallback)
Provide a function that trueSKY can use to output debug warnings, information, and errors.

### <a name="StaticSetGraphicsDevice"/>void StaticSetGraphicsDevice(void device, simul::crossplatform::RenderPlatformType deviceType, UnityGfxDeviceEventType eventType)
Device event handler.

### <a name="StaticSetGraphicsDeviceAndContext"/>void StaticSetGraphicsDeviceAndContext(void device, void context, simul::crossplatform::RenderPlatformType deviceType, UnityGfxDeviceEventType eventType)
Device event handler.

### <a name="StaticSetMemoryInterface"/>void StaticSetMemoryInterface(simul::base::MemoryInterface)
Provide memory allocator for CPU and (on some platforms) GPU memory.

### <a name="StaticSetSequence"/>int StaticSetSequence(std::string SequenceInput)
Loads the sequence as a std::string.

### <a name="StaticSetSequenceTxt"/>int StaticSetSequenceTxt(char txt)
Loads the given sequence

### <a name="StaticShutDownInterface"/>int StaticShutDownInterface()
Shut down the renderer and free all resources.

### <a name="UnitySetGraphicsDevice"/>void UnitySetGraphicsDevice(void device, simul::crossplatform::RenderPlatformType deviceType, UnityGfxDeviceEventType eventType)
Unity-specific device event. Calls StaticSetGraphicsDevice() if needed.

Enums
---

**FloatAtPosition**  The namespace for the plugin render interface.

**RenderStyle**  Different rendering styles
