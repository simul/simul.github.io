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

| class [FileLoader](base/fileloader.html) |  |
| struct [LicenceInfo](base/licenceinfo.html) |  |
| class [Referenced](base/referenced.html) |  |
| class [ShowProgressInterface](base/showprogressinterface.html) |  |
| class [TrackingAllocator](base/trackingallocator.html) |  |
| struct [Variant](base/variant.html) |  |
| struct [Variant32](base/variant32.html) |  |

Functions
---

| simul::base::FeatureLevel | [GetFeatureLevel](#GetFeatureLevel)() |
| simul::base::LicenceInfo | [GetLicenceInfo](#GetLicenceInfo)(char lic) |
| char  const * | [GetLicenceValidityText](#GetLicenceValidityText)(char lic) |
| simul::base::FeatureLevel | [GetMaximumFeatureLevel](#GetMaximumFeatureLevel)() |

Static library: (SIMUL)/lib/(PLATFORM)/(COMPILER)/(ConfigurationName)/SimulBase_(RUNTIME).lib

Dynamic library: (SIMUL)/exe/(PLATFORM)/(COMPILER)/(ConfigurationName)/SimulBase_(RUNTIME).dll

The Base library does not depend on any others.
  


Functions
---
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

Enums
---

**FeatureLevel**  The feature-level of this trueSKY version.

**LicenceResult**  The type of licence.
