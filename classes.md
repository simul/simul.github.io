---
title: The trueSKY Classes
layout: reference
weight: 50
---

Previous: <a href="pri">The Plugin Rendering Interface</a>

If you include the trueSKY headers, you can use the rendering classes directly.
This will usually involve creating an instance of simul::clouds::Environment to store the data and an instance of simul::clouds::BaseWeatherRenderer to draw the sky.

<a href="classes/env">The Cloud Keyframer</a>

<a href="classes/shaders">Shaders</a>

<a href="classes/mixed">Mixed Resolution Compositing</a>

The renderer classes are in the Clouds and Sky libraries.
To build the samples, use the solution file appropriate to your Visual Studio version:

- SimulSamples_Win32_VC10.sln
- SimulSamples_x64_VC11.sln

![](/Images/SimulOverview.png)


The two main elements to implementing trueSKY in a project are: an Environment object, which will encapsulate sky and cloud data;
a WeatherRenderer, and a RenderPlatform.

You should create an instance of simul::clouds::Environment, which is persistent.
~~~~~~~~~~~~~~~
#include "Simul/LicenseKey.h"
#include "Simul/Base/EnvironmentVariables.h"
simul::clouds::Environment *environment=NULL;
~~~~~~~~~~~~~~~

The Environment is API-neutral, it calculates and updates environment data. We will create a persistent <a href="ref/simul/crossplatform/renderplatform">RenderPlatform</a>,
whose class depends on the graphics API we use:

~~~~~~~~~~~~~~~{.c}
simul::dx11::RenderPlatform renderPlatformDx11;
~~~~~~~~~~~~~~~

The RenderPlatform classes implement platform-specific rendering functions called from a cross-platform interface.
And we will create a weather renderer, which is also API-neutral:
~~~~~~~~~~~~~~~{.c}
simul::clouds::BaseWeatherRenderer *weatherRenderer=new simul::clouds::BaseWeatherRenderer(environment);
~~~~~~~~~~~~~~~

In the case of
DirectX 11, we initialize the RenderPlatform with a pointer to our ID3D11Device:
~~~~~~~~~~~~~~~{.c}
void OnD3D11CreateDevice(struct ID3D11Device* pd3dDevice)
{
renderPlatformDx11.RestoreDeviceObjects(pd3dDevice);

~~~~~~~~~~~~~~~
Having done this, we can now pass the render platform pointer to the device-specific initialization of our renderers:
~~~~~~~~~~~~~~~{.c}
weatherRenderer->RestoreDeviceObjects(&renderPlatformDx11);
}
~~~~~~~~~~~~~~~

In-game, we update the environment, usually once per frame:
~~~~~~~~~~~~~~~{.c}
environment->update(time_step_days);
~~~~~~~~~~~~~~~

The time step is given in days - a floating point value, usually some small fraction less than one.
This is the simulation time step, rather than real-time.
Then to render:

~~~~~~~~~~~~~~~{.cpp}
void Render(ID3D11DeviceContext* pContext)
{
simul::crossplatform::DeviceContext                     deviceContext;
deviceContext.platform_context                          =pContext;
deviceContext.renderPlatform                            =&renderPlatformDx11;
deviceContext.viewStruct.view_id                        =view_id;
deviceContext.viewStruct.depthTextureStyle      =crossplatform::PROJECTION;
deviceContext.viewStruct.view                           =viewMatrix;
deviceContext.viewStruct.proj                           =projectionMatrix;
~~~~~~~~~~~~~~~
We've created a <a href="ref/simul/crossplatform/devicecontext">deviceContext</a>object that we will pass to the render functions.
This object encapsulates the platform-specific context - in this case it's
an ID3D11DeviceContext pointer - and view-specific information: the view and projection matrices for example.

There are different types of projection matrix, and some are better than others. The classic projection transforms a viewspace position 
into a clip position and depth value, where depth=0 is the near plane and depth=1 is the far. But this forward projection has
a very inefficient distribution of depth values with respect to distance, and causes a loss of precision. Superior to this is the reverse
projection, where depth=0 represents the far plane, and depth=1 the near. It's strongly recommended that you use reverse projection to get the best
visual results from trueSKY. The projection matrix that you send to trueSKY should be the same one that was used to create your depth buffer.

Each individual view that you want to draw simultaneously on screen should have its own unique view_id.
You don't have to explicitly create views, but you should call:

~~~~~~~~~~~~~~~{.cpp}
weatherRenderer->RemoveView(view_id);
~~~~~~~~~~~~~~~

to free up GPU memory if a view is removed.

We specify the depth texture style so that trueSKY knows how to interpret the
depth information you pass to it. The matrices (<a href="ref/simul/math/matrix4x4">Matrix4x4</a>) are row-major view and projection matrices stored as a simple block of 16 floats - you can cast from most standard matrix classes directly.

Once per frame, before rendering , we must call [simul::clouds::BaseWeatherRenderer::PreRenderUpdate](/ref/simul/clouds/baseweatherrenderer/prerenderupdate)
, passing
a deviceContext that refers to mainview.
~~~~~~~~~~~~~~~{.cpp}
weatherRenderer->PreRenderUpdate(deviceContext,real_time_s);
~~~~~~~~~~~~~~~
The parameter *real_time_s* is real time in seconds - as distinct from simulation time, which might be greatly accelerated, or change instantly, real time is used mainly for effects like rain that we might not want to appear accelerated. 

For each view, we render the sky, passing an appropriate device context.
~~~~~~~~~~~~~~~{.cpp}
weatherRenderer->Render(deviceContext,
,(bool)is_cubemap
,(float) exposure
,(float) gamma
,mainDepthTexture
,depthViewport);
~~~~~~~~~~~~~~~

The *exposure* is a brightness multiplier - 1.0 is a good value,
but the chosen number depends on how bright you want the sky to be relative to your scene. We can also perform *gamma* correction.

We use *is_cubemap* to specify whether we're doing a cubemap render. If so,
shortcuts will be used to draw with less detail. We pass a depth texture, because the atmospherics and clouds need to use this.
The *depthViewport* specifies what area of the texture is being used for the current view (some engines store a larger texture and use a portion of it): pass NULL here to use the entire texture.
See also <a href="classes/mixed">Mixed Resolution Rendering</a>.


Platform considerations
=======================

DirectX 11
----------

To use DirectX 11, build the DirectX11 platform library in Simul/Platform/DirectX11.

The DirectX platform library used the DirectX SDK by default, but can be recompiled from the provided source to run on the Windows 8 SDK.

The location of the most recent DirectX SDK on your hard drive is usually given by the
DXSDK_DIR environment variable - it is usually of the form 'C:/Program Files (x86)/Microsoft DirectX SDK (June 2010)' etc.

To build with the Windows 8 SDK, ensure that both the DirectX11 library and the executable are using the standard toolset (e.g. v110, not v110_xp), remove the
SimulDXSDK.props property sheet from the projects, then add the SimulWin8SDK.props property sheet to both projects. Rebuild Simul/Platform/DirectX11 and the executable.

To add True Sky to a DirectX 11 project, you need to link with the Simul core libraries, and also with the DirectX11 project. You can use the Simul property
sheets - e.g. Simul/Platform/DirectX/SimulUseDXSDK.props, alternatively:

* In the project properties, select Configuration:All, then under "Configuration Properties, C++, General" add the following to "Additional Include Directories":
~~~~~~~~~~~~~~~{.cpp}
$(SIMUL)/../;$(DXSDK_DIR)/include
~~~~~~~~~~~~~~~
The SIMUL environment variable is set by the trueSKY installer, while the DXSDK_DIR variable is set when you install DirectX.

* Under "Configuration Properties, Linker, General" set "Additional Library Directories" to:

~~~~~~~~~~~~~~~{.cpp}
$(SIMUL)/lib/$(Platform)/VC11/$(Configuration);$(DXSDK_DIR)/Lib/x86
~~~~~~~~~~~~~~~
where VC11 should be replaced by VC12 etc for different Visual Studio versions, and x86 by x64 for 64-bit builds.

* In your initialization code, setup file loading and paths if needed, before creating the weather renderer:
~~~~~~~~~~~~~~~{.cpp}
simul::dx11::SetFileLoader(myFileLoader);
simul::dx11::PushShaderPath("my_shader_path");
simul::dx11::PushTexturePath("my_texture_path");
simul::dx11::SetShaderBinaryPath("my_binary_path");
~~~~~~~~~~~~~~~
For example, the DirectX11 sample uses the default file loader, and the paths to shaders in "Simul/Platform/DirectX11/HLSL" and textures in "Simul/Media/Textures".

OpenGL
------

In order to build the OpenGL sample you will need GLUT, and GLEW (both included in Simul/External). GLSL is used for shaders.
You should build the OpenGL platform library in Simul/Platform/OpenGL.

To add True Sky to an OpenGL project:

* In the project properties, select Configuration:All, then under "Configuration Properties, C++, General" add the following "Additional Include Directories":

~~~~~~~~~~~~~~~{.cpp}
"$(SIMUL)/../";"$(SIMUL)/External/OpenGL/include";"$(SIMUL)/External/FreeImage/Dist"
~~~~~~~~~~~~~~~

* Under "Configuration Properties, Linker, General" set "Additional Library Directories" to:

~~~~~~~~~~~~~~~{.cpp}
"$(SIMUL)/lib/$(PlatformName)/VC11/$(ConfigurationName)";"$(SIMUL)/External/OpenGL/lib";"$(SIMUL)/External/FreeImage/Dist"
~~~~~~~~~~~~~~~
* The libraries themselves are linked automatically when the headers are included.

* On scene initialization, initialize the shader path and the weather object:

~~~~~~~~~~~~~~~{.cpp}
simul::opengl::PushShaderPath("shaders/");
~~~~~~~~~~~~~~~


<hr size="1">
Next: <a href="classes/env">The Cloud Keyframer</a>
  