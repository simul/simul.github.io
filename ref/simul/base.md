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

| class [BaseProfilingInterface](base/BaseProfilingInterface) |  |
| class [DefaultProfiler](base/DefaultProfiler) |  |
| class [EnvironmentVariables](base/EnvironmentVariables) |  |
| class [FileLoader](base/FileLoader) |  |
| class [MemoryInterface](base/MemoryInterface) |  |
| class [MemoryUsageInterface](base/MemoryUsageInterface) |  |
| class [ProfilingInterface](base/ProfilingInterface) |  |
| class [Referenced](base/Referenced) |  |
| class [RuntimeError](base/RuntimeError) |  |
| class [ShowProgressInterface](base/ShowProgressInterface) |  |
| class [Timer](base/Timer) | A microsecond timer.<br> |
| class [TrackingAllocator](base/TrackingAllocator) |  |
| struct [Variant32](base/Variant32) |  |

Functions
---

| void | [find_and_replace](#find_and_replace)(std::string source, std::string find, std::string replace) |
| simul::base::FeatureLevel | [GetFeatureLevel](#GetFeatureLevel)() |
| simul::base::LicenceInfo | [GetLicenceInfo](#GetLicenceInfo)(char lic) |
| simul::base::FeatureLevel | [GetMaximumFeatureLevel](#GetMaximumFeatureLevel)() |
| simul::base::ProfilingInterface * | [GetProfilingInterface](#GetProfilingInterface)(THREAD_TYPE thread_id) |
| THREAD_TYPE | [GetThreadId](#GetThreadId)() |
| bool | [GetUseExternalTextures](#GetUseExternalTextures)() |
| char  const * | [QuickFormat](#QuickFormat)(char format_str) |
| void | [SetFeatureLevel](#SetFeatureLevel)(simul::base::FeatureLevel f) |
| void | [SetProfilingInterface](#SetProfilingInterface)(THREAD_TYPE thread_id, simul::base::ProfilingInterface p) |
| void | [SetUseExternalTextures](#SetUseExternalTextures)(bool t) |
| std::vector | [split](#split)(std::string source, char separator) |
| std::string | [stringFormat](#stringFormat)(std::string fmt) |

Static library: (SIMUL)/lib/(PLATFORM)/(COMPILER)/(ConfigurationName)/SimulBase_(RUNTIME).lib

Dynamic library: (SIMUL)/exe/(PLATFORM)/(COMPILER)/(ConfigurationName)/SimulBase_(RUNTIME).dll

The Base library does not depend on any others.
  


Functions
---

### <a name="find_and_replace"/>void find_and_replace(std::string source, std::string find, std::string replace)
Proper find-and-replace function for strings:

### <a name="GetFeatureLevel"/>simul::base::FeatureLevel GetFeatureLevel()
The current feature level, which determines whether this is the feature-limited trueSKY alpha, or full trueSKY.

### <a name="GetLicenceInfo"/>simul::base::LicenceInfo GetLicenceInfo(char lic)
Retrieve information on the specified licence key.

### <a name="GetMaximumFeatureLevel"/>simul::base::FeatureLevel GetMaximumFeatureLevel()
The maximum feature level (see GetFeatureLevel), determined by the current licence.

### <a name="GetProfilingInterface"/>simul::base::ProfilingInterface * GetProfilingInterface(THREAD_TYPE thread_id)
Returns a pointer to the current CPU profiler.

### <a name="GetThreadId"/>THREAD_TYPE GetThreadId()
Get the id of the current thread.

### <a name="GetUseExternalTextures"/>bool GetUseExternalTextures()
See SetUseExternalTextures.

### <a name="QuickFormat"/>char  const * QuickFormat(char format_str)
A quick-and-dirty, non-re-entrant formatting function. Use this only for debugging.

### <a name="SetFeatureLevel"/>void SetFeatureLevel(simul::base::FeatureLevel f)
Change the feature level. It is only possible to change to a lower feature level than the maximum one (see GetMaximumFeatureLevel).

### <a name="SetProfilingInterface"/>void SetProfilingInterface(THREAD_TYPE thread_id, simul::base::ProfilingInterface p)
Set the CPU profiler. Future use of SIMUL_PROFILE_START or SIMUL_COMBINED_PROFILE_START will use that profiler.

### <a name="SetUseExternalTextures"/>void SetUseExternalTextures(bool t)
The current feature level, which determines whether this is the feature-limited trueSKY alpha, or full trueSKY.

### <a name="split"/>std::vector split(std::string source, char separator)
Divide a string into a vector of smaller strings, based on the given separator

### <a name="stringFormat"/>std::string stringFormat(std::string fmt)
Create a std::string using sprintf-style formatting, with variable arguments.

Enums
---

**FeatureLevel**  The feature-level of this trueSKY version.

**LicenceResult**  The type of licence.

**TextStyle**  Style for text output.
