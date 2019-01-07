---
title: Controlling the Environment
layout: reference
weight: 510
---




Previous: [classes](/ref/classes)


## Updating ##
The [simul::clouds::Environment](/ref/simul/clouds/environment)
object stores an instance of [simul::sky::SkyKeyframer](/ref/simul/sky/skykeyframer)

and two instances of [simul::clouds::CloudKeyframer](/ref/simul/clouds/cloudkeyframer)
, and performs the necessary initialization and updates.

As described in [gettingstarted](/ref/gettingstarted)
, you will declare and create an instance of Environment. If you have a sequence file (.sq or .seq)
saved from the [sequencer](/ref/sequencer)
, you can load this into the Environment and its keyframers will be appropriately initialized with global values
and keyframes.

simul::clouds::Environment *environment=NULL;
...
environment=new simul::clouds::Environment();

You can either load a preconfigured sky sequence (.sq file), control the environment direct from the trueSKY API, or both together.
To load a file (the .sq is a human-readable text file format), create a TextFileInput object.

simul::crossplatform::TextFileInput ifs;
ifs.Load("test_file.sq");
environment->LoadFromText(ifs);

You can use your own text loader class in place of TextFileInput.

The properties and keyframes of each Keyframer can also be modified in real time.
The keyframes each have a timevalue, and the keyframer tracks a current time through these frames, interpolating properties as it does so. This time value is obtained
or set using the skyKeyframer:

float time=environment->skyKeyframer->GetTime();

You don't need to update the keyframers specifically, so long as you're using simul::clouds::Environment::Update() once per frame.

For more information on the two types of keyframer, see:
[classes::env::sky_keyframer](/ref/classes/env/sky_keyframer)

[classes::env::cloud_keyframer](/ref/classes/env/cloud_keyframer)


<hr size="1">
Next: [classes::env::sky_keyframer](/ref/classes/env/sky_keyframer)

