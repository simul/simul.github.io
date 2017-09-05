---
title: Introduction
layout: reference
weight: 1
---
Introduction
===
TrueSKY is the culmination of many years' research and development. It is based on physical principles
of light scattering and absorption, and is highly optimized for speed. We believe it is the best-performing system
for realistic realtime skies and clouds.
The SDK comes as a set of libraries, under a main "Simul" directory. These can be linked statically or dynamically,
depending on the platform. Binaries reside in the directory "Simul/lib" in the case of static libraries,
and in "Simul/exe" for dll's. Source is found in the subdirectories for the constituent libraries.

In *exe* and *lib*, the following structure is observed:

<ul>
<li>Win32
        <ul>
                <li>VC11
                        <ul>
                                <li>Debug</li>
                        <li>Release</li>
                                <li>Static Debug</li>
                                <li>Static Release</li>
                        </ul>
                </li>
                <li>v140
                </li>
        </ul>
        <ul>
                <li>...</li>
        </ul>
</li>
<li>x64
        <ul>
                <li>...</li>
        </ul>
</li>
<li>{console platforms}
        <ul>
                <li>...</li>
        </ul>
</li>
</ul>

The compiled Windows libraries are in two runtime versions, _MD and _MT.
The runtime is the set of libraries provided by Microsoft that provides basic system functions.
You should generally use the same runtime all the way through a project, although different runtimes can be used for DLL's, because they are self-contained.

For Windows, the Debug and Release configurations are supplied as DLL's linked against the dynamic, MD runtime.
The Static Debug and Static Release configuratons are supplied as static libraries linked against the static, MT runtime.

<hr size="1">
Next: <a href="/gettingstarted">Getting Started</a>

