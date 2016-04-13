---
title: Instructions
layout: unreal
weight : 2
---

Adding trueSKY to your level
---
* Press "Window->Add Sequence to Scene" -- this adds a TrueSkySequenceActor to the current level.

 <a href="http://simul.co/wp-content/uploads/2014/07/UE4_AddSequence.png"><img src="http://simul.co/wp-content/uploads/2014/07/UE4_AddSequence-81x300.png"/></a> 

This actor provides a reference to a sequence asset which is rendered. Choose the actor (from "World Outliner" window). In the "Details" window, set the reference to a TrueSky Sequence asset (read below how to create one) in the "Active Sequence" property.

* To create a new TrueSkySequence asset, go to the "Content Browser" window. Press "New Asset" button (or do a right mouse click inside the window) to open an asset selection window. Choose "Miscellaneous / TrueSky Sequence Asset". A new asset will be created. Now you can rename/save/delete it.

<a href="http://simul.co/wp-content/uploads/2014/07/UE4_CreateAsset.png"><img src="http://simul.co/wp-content/uploads/2014/07/UE4_CreateAsset-233x300.png"/></a> 

 In the World Outliner, select your trueSKY sequence actor, and in the Details panel, set its Active Sequence to be the newly created asset: 
 
<a href="http://simul.co/wp-content/uploads/2014/07/Clipboard-Image-8.png"><img src="http://simul.co/wp-content/uploads/2014/07/Clipboard-Image-8-150x150.png"/></a> 

* To edit the TrueSkySequence asset just double-click on it:

<a class=" id=" title="" href="http://simul.co/wp-content/uploads/2014/07/Editor.png"><img src="http://simul.co/wp-content/uploads/2014/07/Editor-150x150.png" /></a>

* Enter your licence key in the Sequencer Window. This enables the window's editing functions.

* You can see changes to the properties (e.g. "preview") only if the edited asset is also assigned to the level's TrueSkySequenceActor! The trueSky plugin renderer uses only the asset which is referenced from that actor. If you are editing some other asset (which is not assigned to the TrueSky actor of the current level) then you won't see any visualization of it.

* If the TrueSkySequence asset has been changed, it can be saved to the disc by right-clicking on it and choosing "Save".

* You can edit any number of TrueSkySequence assets at once. However, only that which is also assigned to the active TrueSkySequenceActor is visible in editor's rendering window.

* To add clouds, double-click the TrueSKY Sequence Asset and right-click on the timeline to add cloud keyframes.

* It may be that the default UE4 sky obscures the trueSKY image. Remove the Atmospheric Fog and Sky Sphere objects from your scene.

Multiple Sequence Actors and Transitions
---
You can have any number of trueSKY Sequence Actors in your level, all with different Sequence Assets assigned. In the Editor, check the Actor's property "Active in Editor" to see its weather state in the 3D view. In-game, the active Actor is determined by bounds. By default, a Sequence Actor is unbounded - it is always active. You can create bounding by adding a Box Collision component to the Actor.

<a href="http://docs.simul.co/unrealengine/images/AddBounds.png"><img src="http://docs.simul.co/unrealengine/images/AddBounds.png" alt="Add Bounds"/></a>

When this is done, the Actor will have limited bounds, and only affect the weather when the player is within the bounding box. You should have at most one unbounded trueSKY Sequence Actor in your level: this will apply when the player is not in the bounds of any other Sequence Actor.

To allow a smooth transition between weather states, you should adjust the Mode property of the Sky and Cloud Layers in all the Sequence Assets to allow a gradual transition between the different weather states. If you're using real-time transition (this is simplest), you can adjust the Interval in seconds (default 10.0) to determine how quickly the change takes place. Otherwise, use the Interval in days.

<a href="http://docs.simul.co/unrealengine/images/GradualMode.png"><img src="http://docs.simul.co/unrealengine/images/GradualMode.png" alt="Gradual Mode"/></a>

Console commands
---
*ts\_cross\_sections* Show/hide cloud cross-sections.

*ts\_compositing* Show/hide compositing overlay.

*ts\_profile* Dump profiling text to output.

Next: <a href="/unrealengine/Blueprint">Blueprint</a>