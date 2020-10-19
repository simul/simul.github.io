---
title: Aurora
layout: reference
weight: 0
---
class Aurora
===

| Include: | Sky/Aurora.h |



Functions
---

|  | [Aurora](#Aurora)(simul::sky::SkyKeyframer pSkyKeyframer) |
| bool | [CheckRenderOncePerFrame](#CheckRenderOncePerFrame)(simul::crossplatform::GraphicsDeviceContext deviceContext) |
| float | [RadianceToRayleigh](#RadianceToRayleigh)(float L, float wavelength) |
| void | [SaveToText](#SaveToText)(simul::crossplatform::TextOutput output) |
| void | [SetAuroraIntensityMapSize](#SetAuroraIntensityMapSize)(uint32_t value) |
| void | [SetAuroralLayerIntensity](#SetAuroralLayerIntensity)(float value) |
| void | [SetCloudWindowOrientation](#SetCloudWindowOrientation)(simul::crossplatform::Quaterniond q) |
| void | [SetDefaultAuroralGlobalCoverage](#SetDefaultAuroralGlobalCoverage)() |
| void | [SetDefaultAuroralLayers](#SetDefaultAuroralLayers)() |
| void | [SetDefaultFACs](#SetDefaultFACs)() |
| void | [SetGeomagneticNorthPole](#SetGeomagneticNorthPole)(simul::crossplatform::Quaterniond q) |


Functions
---
<a name="Aurora"></a>
###  Aurora(simul::sky::SkyKeyframer pSkyKeyframer)
Default class methods
<a name="CheckRenderOncePerFrame"></a>
### bool CheckRenderOncePerFrame(simul::crossplatform::GraphicsDeviceContext deviceContext)
Rendering
<a name="RadianceToRayleigh"></a>
### float RadianceToRayleigh(float L, float wavelength)
Conversion functions
<a name="SaveToText"></a>
### void SaveToText(simul::crossplatform::TextOutput output)
Load/Save
<a name="SetAuroraIntensityMapSize"></a>
### void SetAuroraIntensityMapSize(uint32_t value)
Get and Set Aurora Intensity Map Size
<a name="SetAuroralLayerIntensity"></a>
### void SetAuroralLayerIntensity(float value)
Get and Set Auroral Layers Intensity
<a name="SetCloudWindowOrientation"></a>
### void SetCloudWindowOrientation(simul::crossplatform::Quaterniond q)
Get and Set Cloud Window Orientation
<a name="SetDefaultAuroralGlobalCoverage"></a>
### void SetDefaultAuroralGlobalCoverage()
Get and Set Auroral Global Coverage
<a name="SetDefaultAuroralLayers"></a>
### void SetDefaultAuroralLayers()
Get and Set Auroral Layers
<a name="SetDefaultFACs"></a>
### void SetDefaultFACs()
Others
<a name="SetGeomagneticNorthPole"></a>
### void SetGeomagneticNorthPole(simul::crossplatform::Quaterniond q)
Get and Set Geomagnetic North Pole
