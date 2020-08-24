---
title: Environment
layout: reference
weight: 0
---
class Environment
===

| Include: | Clouds/CloudRenderer.h |



Functions
---

|  | [Environment](#Environment)(simul::base::MemoryInterface mem) |
|  | [~Environment](#~Environment)() |
| simul::clouds::Environment * | [Create](#Create)(simul::base::MemoryInterface m) |
| simul::clouds::CloudKeyframer * | [CreateCloudKeyframer](#CreateCloudKeyframer)(simul::base::MemoryInterface m, bool make2d, simul::sky::uid uid) |
| void | [CreateSubObjects](#CreateSubObjects)() |
| bool | [DeleteCloudKeyframe](#DeleteCloudKeyframe)(simul::sky::uid uid) |
| bool | [DeleteCloudKeyframer](#DeleteCloudKeyframer)(simul::sky::uid uid) |
| void | [Destroy](#Destroy)(simul::clouds::Environment env) |
| simul::clouds::CloudKeyframer * | [GetCloudKeyframer](#GetCloudKeyframer)(simul::sky::uid uid) |
| unsigned int | [GetKeyframersChecksum](#GetKeyframersChecksum)() |
| void | [Load](#Load)(simul::sky::Input is) |
| void | [LoadFromText](#LoadFromText)(simul::crossplatform::TextInput input) |
| void | [New](#New)() |
| void | [Reset](#Reset)() |
| void | [Save](#Save)(simul::sky::Output os) |
| void | [SaveToText](#SaveToText)(simul::crossplatform::TextOutput output) |
| void | [SetRealTime](#SetRealTime)(double rt_sec) |
| void | [Update](#Update)() |
| simul::sky::SkyKeyframer * | [CreateSkyKeyframer](#CreateSkyKeyframer)(simul::base::MemoryInterface m, int NumElevations, int NumDistances, float MaxFadeDistanceKm) |


Functions
---
<a name="Environment"></a>
###  Environment(simul::base::MemoryInterface mem)
Constructor - initialize with an optional memory allocator.
<a name="~Environment"></a>
###  ~Environment()
Destructor
<a name="Create"></a>
### simul::clouds::Environment * Create(simul::base::MemoryInterface m)
Create an Environment.
<a name="CreateCloudKeyframer"></a>
### simul::clouds::CloudKeyframer * CreateCloudKeyframer(simul::base::MemoryInterface m, bool make2d, simul::sky::uid uid)
Override this to create a custom derived keyframer. Valid id's are anything greater than zero.
<a name="CreateSubObjects"></a>
### void CreateSubObjects()
Call this to create the keyframer sub-objects. If not called before the first Update(), it will be called from there.
<a name="DeleteCloudKeyframe"></a>
### bool DeleteCloudKeyframe(simul::sky::uid uid)
Delete the specified cloud keyframe
<a name="DeleteCloudKeyframer"></a>
### bool DeleteCloudKeyframer(simul::sky::uid uid)
Delete the specified cloud layer.
<a name="Destroy"></a>
### void Destroy(simul::clouds::Environment env)
Destroy an Environment .
<a name="GetCloudKeyframer"></a>
### simul::clouds::CloudKeyframer * GetCloudKeyframer(simul::sky::uid uid)
Get the cloud keyframer with the specified uid.
<a name="GetKeyframersChecksum"></a>
### unsigned int GetKeyframersChecksum()
A checksum for the keyframer setup.
<a name="Load"></a>
### void Load(simul::sky::Input is)
Load a sequence from the binary .seq format.
<a name="LoadFromText"></a>
### void LoadFromText(simul::crossplatform::TextInput input)
Load a sequence from the text .sq format.
<a name="New"></a>
### void New()
Clear the sequence.
<a name="Reset"></a>
### void Reset()
Force recalculation of any cached values.
<a name="Save"></a>
### void Save(simul::sky::Output os)
Save a sky sequence as binary (the .seq file format); this is a low-overhead method of storing and retrieving sequences, but is subject to format changes, so
sequences should generally be stored as text (see 
<a name="SaveToText"></a>
### void SaveToText(simul::crossplatform::TextOutput output)
Save a sky sequence as text (the .sq file format). This is the standard means of storing sequences.
<a name="SetRealTime"></a>
### void SetRealTime(double rt_sec)
Call this once per frame before Update() if you use real-time updates for clouds, rain, lightning, sky keyframes etc.
<a name="Update"></a>
### void Update()
Call this once per-frame
<a name="CreateSkyKeyframer"></a>
### simul::sky::SkyKeyframer * CreateSkyKeyframer(simul::base::MemoryInterface m, int NumElevations, int NumDistances, float MaxFadeDistanceKm)
Override this to create a custom derived keyframer.

Fields
---

**cloudKeyframers**  Map of 3D Cloud Layers

**skyKeyframer**  The atmosphere/sky keyframer.
