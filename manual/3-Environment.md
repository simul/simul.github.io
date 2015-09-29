Controlling the Environment	{#environment}
===========================

Updating
--------
The \link simul::clouds::Environment Environment\endlink object stores an instance of \link simul::sky::SkyKeyframer SkyKeyframer\endlink
and two instances of \link simul::clouds::CloudKeyframer CloudKeyframer\endlink, and performs the necessary initialization and updates.

As described in \ref gettingstarted, you will declare and create an instance of Environment. If you have a sequence file (.sq or .seq)
saved from the \ref sequencer, you can load this into the Environment and its keyframers will be appropriately initialized with global values
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
The keyframes each have a \a time value, and the keyframer tracks a current time through these frames, interpolating properties as it does so. This time value is obtained
or set using the skyKeyframer:

	float time=environment->skyKeyframer->GetTime();

You don't need to update the keyframers specifically, so long as you're using simul::clouds::Environment::Update() once per frame.

For more information on the two types of keyframer, see:
\subpage sky_keyframer
\subpage cloud_keyframer

<hr size="1">
Next: \ref sky_keyframer