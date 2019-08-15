---
title: base
layout: reference
weight: 0
---
namespace base
===

| Include: | Base/Base.h |

Base is the base library, containing simple data structures, macros and other useful things.<br>


Classes and Structures
---

| class [BaseProfilingInterface](base/baseprofilinginterface.html) |  |
| class [DefaultProfiler](base/defaultprofiler.html) |  |
| class [EnvironmentVariables](base/environmentvariables.html) |  |
| class [FileLoader](base/fileloader.html) |  |
| class [MemoryInterface](base/memoryinterface.html) |  |
| class [MemoryUsageInterface](base/memoryusageinterface.html) |  |
| struct [ProfileData](base/profiledata.html) |  |
| class [ProfilingInterface](base/profilinginterface.html) |  |
| class [Referenced](base/referenced.html) |  |
| class [RuntimeError](base/runtimeerror.html) |  |
| class [ShowProgressInterface](base/showprogressinterface.html) |  |
| class [Timer](base/timer.html) | A microsecond timer.<br> |
| class [TrackingAllocator](base/trackingallocator.html) |  |
| struct [Variant](base/variant.html) |  |
| struct [Variant32](base/variant32.html) |  |

Functions
---

| void | [find_and_replace](#find_and_replace)(std::string source, std::string find, std::string replace) |
| simul::base::FeatureLevel | [GetFeatureLevel](#GetFeatureLevel)() |
| simul::base::LicenceInfo | [GetLicenceInfo](#GetLicenceInfo)(char lic) |
| char  const * | [GetLicenceValidityText](#GetLicenceValidityText)(char lic) |
| simul::base::FeatureLevel | [GetMaximumFeatureLevel](#GetMaximumFeatureLevel)() |
| THREAD_TYPE | [GetThreadId](#GetThreadId)() |
| bool | [GetUseExternalTextures](#GetUseExternalTextures)() |
| char  const * | [QuickFormat](#QuickFormat)(char format_str) |
| std::vector | [split](#split)(std::string source, char separator) |
| std::string | [stringFormat](#stringFormat)(std::string fmt) |

Static library: (SIMUL)/lib/(PLATFORM)/(COMPILER)/(ConfigurationName)/SimulBase_(RUNTIME).lib

Dynamic library: (SIMUL)/exe/(PLATFORM)/(COMPILER)/(ConfigurationName)/SimulBase_(RUNTIME).dll

The Base library does not depend on any others.
  


Functions
---
<a name="find_and_replace"></a>
### void find_and_replace(std::string source, std::string find, std::string replace)
Proper find-and-replace function for strings:
<a name="GetFeatureLevel"></a>
### simul::base::FeatureLevel GetFeatureLevel()
The current feature level, which determines whether this is the feature-limited trueSKY alpha, or full trueSKY.
<a name="GetLicenceInfo"></a>
### simul::base::LicenceInfo GetLicenceInfo(char lic)
Retrieve information on the specified licence key.
<a name="GetLicenceValidityText"></a>
### char  const * GetLicenceValidityText(char lic)
Get information on the status of the given licence
<a name="GetMaximumFeatureLevel"></a>
### simul::base::FeatureLevel GetMaximumFeatureLevel()
The maximum feature level (see GetFeatureLevel), determined by the current licence.
<a name="GetThreadId"></a>
### THREAD_TYPE GetThreadId()
Get the id of the current thread.
<a name="GetUseExternalTextures"></a>
### bool GetUseExternalTextures()
See SetUseExternalTextures.
<a name="QuickFormat"></a>
### char  const * QuickFormat(char format_str)
A quick-and-dirty, non-re-entrant formatting function. Use this only for debugging.
<a name="split"></a>
### std::vector split(std::string source, char separator)
Divide a string into a vector of smaller strings, based on the given separator
<a name="stringFormat"></a>
### std::string stringFormat(std::string fmt)
Create a std::string using sprintf-style formatting, with variable arguments.

Enums
---

**FeatureLevel**  The feature-level of this trueSKY version.

**LicenceResult**  The type of licence.

**TextStyle**  Style for text output.
