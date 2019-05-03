---
title: base
layout: reference
weight: 0
---
namespace base
===

| Include: | Base/MemoryUsageInterface.h |



Classes and Structures
---

| class [BaseProfilingInterface](base/baseprofilinginterface) |  |
| class [DefaultProfiler](base/defaultprofiler) |  |
| class [EnvironmentVariables](base/environmentvariables) |  |
| class [FileLoader](base/fileloader) |  |
| class [MemoryInterface](base/memoryinterface) |  |
| class [MemoryUsageInterface](base/memoryusageinterface) |  |
| struct [ProfileData](base/profiledata) |  |
| class [ProfilingInterface](base/profilinginterface) |  |
| class [Referenced](base/referenced) |  |
| class [RuntimeError](base/runtimeerror) |  |
| class [ShowProgressInterface](base/showprogressinterface) |  |
| class [Timer](base/timer) | A microsecond timer.<br> |
| class [TrackingAllocator](base/trackingallocator) |  |
| struct [Variant](base/variant) |  |
| struct [Variant32](base/variant32) |  |

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
| void | [SetUseExternalTextures](#SetUseExternalTextures)(bool t) |
| std::vector | [split](#split)(std::string source, char separator) |
| std::string | [stringFormat](#stringFormat)(std::string fmt) |


Functions
---

### <a name="find_and_replace"/>void find_and_replace(std::string source, std::string find, std::string replace)
Proper find-and-replace function for strings:

### <a name="GetFeatureLevel"/>simul::base::FeatureLevel GetFeatureLevel()
The current feature level, which determines whether this is the feature-limited trueSKY alpha, or full trueSKY.

### <a name="GetLicenceInfo"/>simul::base::LicenceInfo GetLicenceInfo(char lic)
Retrieve information on the specified licence key.

### <a name="GetLicenceValidityText"/>char  const * GetLicenceValidityText(char lic)
Get information on th status of the given licence

### <a name="GetMaximumFeatureLevel"/>simul::base::FeatureLevel GetMaximumFeatureLevel()
The maximum feature level (see GetFeatureLevel), determined by the current licence.

### <a name="GetThreadId"/>THREAD_TYPE GetThreadId()
Get the id of the current thread.

### <a name="GetUseExternalTextures"/>bool GetUseExternalTextures()
See SetUseExternalTextures.

### <a name="QuickFormat"/>char  const * QuickFormat(char format_str)
A quick-and-dirty, non-re-entrant formatting function. Use this only for debugging.

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
