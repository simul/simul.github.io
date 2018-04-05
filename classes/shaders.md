---
title: Shaders
layout: reference
weight: 0
---
Shaders
===

=======<br>=======

Previous: <cloud\_keyframer>

trueSKY uses *effects* for rendering. An effect is a collection of shaders - vertex shaders, pixel shaders and so on, along with information on
how to combine them, how to set render state when they are used, and what inputs they take.

Platform-specific derived classes of ::crossplatform::Effect Effect created with ::crossplatform::RenderPlatform::CreateEffect RenderPlatform::CreateEffect\endlink,
usually with an extensionless filename passed to the function.

The RenderPlatform first looks for a platform-specific shader source file by appending its platform shader file extension - .fx effect files for DirectX,
.glfx files for GLSL etc. If this is not found, the cross-platform .sfx extension is appended.

The \#include directive has been enabled - DirectX handles this by design; while
Simul has implemented \#include for GLSL. Platform-specific include files have the suffix .hlsl, .glsl, etc., while cross-platform includes have extension .sl.

As far as possible, the functional aspects of shading are defined
in cross-platform shader include files, which have been given the .sl suffix,
and can be found in the Simul/Platform/CrossPlatform/SL directory.

In order for the different shader languages to use these common files, each
platform has a special file that is included before any .sl files, and which
contains definitions needed for the .sl files, including macros and functions - see CppHlsl.hlsl, etc.

Constant Buffers
----------------
Older versions of GLSL, and DirectX 9, pass constants to shaders individually.

	(in HLSL)
	float brightness;

	(in C++)
	D3DXHANDLE h=effect->GetParameterByName(NULL,"brightness");
	effect->SetFloat(h,1.0);

OpenGL 3.0 and DirectX 11 have the capability to use **constant** **buffers** instead,
so if we define in the shader:

	(in GLSL)
	layout(std140) uniform ShaderConstants
	{
		uniform float brightness;
		uniform float gamma;
		uniform float bloom;
	};

etc., and in C++:

	struct ShaderConstants
	{
		float brightness;
		uniform float gamma;
		uniform float bloom;
	};
 
it is then possible to set the values of the whole structure in C++, and pass it complete to the shader. For cross-platform constant buffers, we define:

	SIMUL_CONSTANT_BUFFER

	SIMUL_CONSTANT_BUFFER_END

and these macros have different expansions depending on whether the header is being used in C++, or in a shader compilation.

<hr>
Next: <a href=".">The trueSKY Classes</a>::mixed
