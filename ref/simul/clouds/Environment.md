---
title: Environment
layout: reference
weight: 0
---
class Environment
===

| Include: | Clouds/BaseCloudRenderer.h |

The main class that manages environment data. Usually, you will create a single instance of Environment, which will persist while your
         3D game or simulation world is active.



Functions
---

|  | [Environment](#Environment)(simul::base::MemoryInterface mem) |
|  | [~Environment](#~Environment)() |
| simul::clouds::CloudKeyframer * | [CreateCloudKeyframer](#CreateCloudKeyframer)(simul::base::MemoryInterface m, bool make2d, int id) |
| void | [CreateSubObjects](#CreateSubObjects)() |
| bool | [DeleteCloudKeyframer](#DeleteCloudKeyframer)(int uid) |
| simul::clouds::CloudKeyframer * | [GetCloudKeyframer](#GetCloudKeyframer)(int uid) |
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

If you use environment directly and not via TrueSkyRenderer, you must call the following each frame:

                SetRealTime(time_seconds);
                skyKeyframer->TimeStep(step_days);
                Update();

  


Functions
---

### <a name="Environment"/> Environment(simul::base::MemoryInterface mem)
Constructor - initialize with an optional memory allocator.
Constructor - initialize with an optional memory allocator.

### <a name="~Environment"/> ~Environment()
Destructor
Destructor

### <a name="CreateCloudKeyframer"/>simul::clouds::CloudKeyframer * CreateCloudKeyframer(simul::base::MemoryInterface m, bool make2d, int id)
Override this to create a custom derived keyframer. Valid id's are anything greater than zero.
Override this to create a custom derived keyframer. Valid id's are anything greater than zero.

### <a name="CreateSubObjects"/>void CreateSubObjects()
Call this to create the keyframer sub-objects. If not called before the first Update(), it will be called from there.
Call this to create the keyframer sub-objects. If not called before the first Update(), it will be called from there.

### <a name="DeleteCloudKeyframer"/>bool DeleteCloudKeyframer(int uid)
Delete the specified cloud layer.
Delete the specified cloud layer.

### <a name="GetCloudKeyframer"/>simul::clouds::CloudKeyframer * GetCloudKeyframer(int uid)
Get the cloud keyframer with the specified uid.
Get the cloud keyframer with the specified uid.

### <a name="GetKeyframersChecksum"/>unsigned int GetKeyframersChecksum()
A checksum for the keyframer setup.
A checksum for the keyframer setup.

### <a name="Load"/>void Load(simul::sky::Input is)
Load a sequence from the binary .seq format.
Load a sequence from the binary .seq format.

### <a name="LoadFromText"/>void LoadFromText(simul::crossplatform::TextInput input)
Load a sequence from the text .sq format.
Load a sequence from the text .sq format.

### <a name="New"/>void New()
Clear the sequence.
Clear the sequence.

### <a name="Reset"/>void Reset()
Force recalculation of any cached values.
Force recalculation of any cached values.

### <a name="Save"/>void Save(simul::sky::Output os)
Save a sky sequence as binary (the .seq file format); this is a low-overhead method of storing and retrieving sequences, but is subject to format changes, so
sequences should generally be stored as text (see 
Save a sky sequence as binary (the .seq file format); this is a low-overhead method of storing and retrieving sequences, but is subject to format changes, so
sequences should generally be stored as text (see 

### <a name="SaveToText"/>void SaveToText(simul::crossplatform::TextOutput output)
Save a sky sequence as text (the .sq file format). This is the standard means of storing sequences.
Save a sky sequence as text (the .sq file format). This is the standard means of storing sequences.

### <a name="SetRealTime"/>void SetRealTime(double rt_sec)
Call this once per frame before Update() if you use real-time updates for clouds, rain, lightning, sky keyframes etc.
Call this once per frame before Update() if you use real-time updates for clouds, rain, lightning, sky keyframes etc.

### <a name="Update"/>void Update()
Call this once per-frame
Call this once per-frame

### <a name="CreateSkyKeyframer"/>simul::sky::SkyKeyframer * CreateSkyKeyframer(simul::base::MemoryInterface m, int NumElevations, int NumDistances, float MaxFadeDistanceKm)
Override this to create a custom derived keyframer.
Override this to create a custom derived keyframer.

Fields
---

**cloudKeyframers** The main 3D cloud layer. The main 3D cloud layer.

**skyKeyframer** The atmosphere/sky keyframer. The atmosphere/sky keyframer.
