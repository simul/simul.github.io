---
title: Blueprints
layout: reference
weight: 10
---




Unreal Blueprints with trueSKY
=============================

{:.unity-specific}
Unity does not support Blueprints, but you can edit trueSKY via [scripting](/unity/scripting).

The trueSKY Blueprints provide a wide array of functionality while your game is playing or simulating. We have aimed to make sure our blueprints are as accessible as possible, while still being able to alter all of our different variables.

If you have never used blueprints before, [Unreal](https://docs.unrealengine.com/en-US/Engine/Blueprints/index.html) have a large number of tutorials on understanding and using blueprints.

Getting Values from trueSKY Actor
----------------------------------
You can edit any of the variables present in the keyframes, layers or attached to the trueSKY Actor. To access these nodes, we have split our variables based on their location. For example, if you want to edit a value on a cloud keyframe, you would use the SetCloudKeyframeValue blueprint node. There is also a correlating GetCloudKeyframeValue for retrieving data

![](/images/unreal/getsetblueprint.png)



From the image above, Property is the value that you want to change, which is selected using the dropdown. For the keyframe nodes, a Keyframe Unique Identifier (UID) is needed to access the correct keyframe. You can get this by manually going to your keyframe and looking for the UID at the top of the details panel, or there are multiple blueprint nodes available to help you select the correct keyframe. See more of these [here](#accessingKeyframesThroughBlueprints).

There are nodes for keyframes and layers. To access the trueSKY actor values, reference it within the blueprints.


Getting Keyframe Values 
----------------------

UID
----
To get a keyframe's properties, you will first need its Unique ID (UID) to identify it. UIDs can be retrieved using a variety of provided Blueprint functions. At this time, the UID displayed on the keyframe and the UIDs returned are not the same. Only use the value returned while this is fixed.

There is a Cloud Keyframe version of all these functions, just replace sky with cloud in the function name. For Cloud Keyframes, you must specify the layer. Layers values are the number displayed on the layer. 

* **GetSkyKeyframebyIndex:** Returns a keyframe's Uid, given an index (this is zero-indexed; the first sky keyframe in a sequence is 0, the second is 1 and so on).

* **GetPreviousSkyKeyframeBeforeTime:** Given a time, returns the Uid of the last sky keyframe before the given time.

* **GetNextSkyKeyframeAfterTime:** Given a time, returns the Uid of the next keyframe after the given time.

* **GetNextModifiableSkyKeyframe:** Returns the Uid of the next keyframe that can be modified without requiring any recalculation (this will be the next sky keyframe + 1).

* **GetInterpolatedSkyKeyframe:** Returns the current interpolated keyframe's Uid (Note: this cannot be used to set any values; it is read-only).

Once you have a keyframe's Uid, you can Get and Set its properties. Select a Property from the Dropdown, input a keyframe UID and can you get or set the value.


Get/Set Keyframe + Layer Values
--------------------------
We have get and set nodes for both Cloud and Sky Keyframes. Make sure you are inputting the correct UID.

The Nodes have been streamlined to output the correct of data type. Make sure you take from the correct node if your data is a float. 

* **GetSkyKeyFrameValue:** 

* **SetSkyKeyframeValue:** 

* **GetCloudKeyFrameValue:** 

* **SetCloudKeyframeValue:** 

* **GetCloudLayerValue:** 

* **SetCloudLayerValue:** 


Get/Set Values on trueSKYSequenceActor
------------------------
To Get/Set these values, just create a reference of the trueSKYSequenceActor, and all the variables have been made public.

![](/images/unreal/createactorreference.png)

To make a reference, make sure the actor is selected in the world view, and context sensitive is ticked.

![](/images/unreal/actorvariables.png)

As you can see there is a list of all the editable variables, organised the same was as they are on the actor.

Getting Layer Values
---------------------

The Layer UID is the number displayed on the Sequencer. Sky Layers do not need a UID, as there can only ever be one.

The number of the layer you are on is shown in the layer's name, as you can see the image below has a layer 44.

![](/images/cloudlayernumber.png)




Tools
--------

There are Blueprint functions provided to test a scene for lightning and for rain. For lightning, the "Get Lightning" function will provide the start position, end position, colour and magnitude of any lightning present. A magnitude of 0 means there is no lightning present. Additionally, the "Get Precipitation Strength at Position" function will take a given position and return a float between 0.0 and 1.0, indicating the strength of the rain (or snow) at this position.

![](/images/unreal/LightningRainTest.png)
Example of testing the weather conditions in blueprint.



Queries
------------

To test how much cloud (from 0 to 1) is at a specified point, use the function CloudPointTest. **Note**: The Query Id can be set to any integer value, but should differ from any Query Ids used in separate queries (or else they will be overwritten).

![](/images/unreal/CloudPointTest.png)

<sup>Sample usage of the Cloud Point Test functionality</sup>

To test if there is cloud between two points, use CloudLineTest:

![](/images/unreal/CloudLineTest.png)

<sup>Sample usage of the Cloud Line Test functionality</sup> 


Managing Sequences
------------------------

Though you can only set the active sequence in the editor, it is possible to change the sequence in use mid-game using Blueprint. To do this, create a reference to your TrueSkySequenceActor in Blueprint, then drag the output pin onto the canvas. In the Action List, search for and select "Set Active Sequence". Repeat for as many sequences as you wish and connect them to relevant events. 

![](/images/unreal/SetActiveSequence.png)

<sup>Example of how to change the active trueSKY sequence at runtime in blueprint </sup>

You can also get the active sequence in Blueprint. Similarly, just drag the output pin of your TrueSkySequence actor onto the canvas and search for and select "Get Active Sequence". This will return the Sequence Asset in use. 

![](/images/unreal/GetActiveSequence.png)


<sup>Example of how to query the active trueSKY sequence at runtime in blueprint</sup>

Measuring Performance
------------------

trueSKY has a built-in profiler for GPU and CPU performance. Use "Get Profiling Text" to obtain the values, with the inputs "cpu_level" and "gpu_level" to determine how far down the call tree to display.

The outputs are in milliseconds.

![](/images/unreal/GetProfilingText.png)

<sup> How to retrieve profiling text </sup>


