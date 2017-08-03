---
title: Introduction
layout: reference
---
Introduction
===
TrueSKY is the culmination of many years' research and development. It is based on physical principles
of light scattering and absorption, and is highly optimized for speed. We believe it is the best-performing system
for realistic realtime skies and clouds.
<div>

The SDK comes as a set of libraries, under a main "Simul" directory. These can be linked statically or dynamically,
depending on the platform. Binaries reside in the directory "Simul/lib" in the case of static libraries,
and in "Simul/exe" for dll's. Source is found in the subdirectories for the constituent libraries.

In *exe* and *lib*, the following structure is observed:

- Win32
        - VC11
                - Debug
                - Release
                - Static Debug
                - Static Release
        - v140
                - ...
- x64
        - ...
- {console platforms}
        - ...

The compiled Windows libraries are in two runtime versions, _MD and _MT.
The runtime is the set of libraries provided by Microsoft that provides basic system functions.
You should generally use the same runtime all the way through a project, although different runtimes can be used for DLL's, because they are self-contained.

For Windows, the Debug and Release configurations are supplied as DLL's linked against the dynamic, MD runtime.
The Static Debug and Static Release configuratons are supplied as static libraries linked against the static, MT runtime.

</div>
<hr size="1">
Next: \ref man_2_gettingstarted

