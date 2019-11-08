---
title: The Sky Sequencer
layout: reference
weight: 10
---





The Sky Sequencer
====================

The Sky Sequencer is the best way to alter the trueSKY environment. Using the sequencer, you can the different effects present in your scene in real time. This section is a brief tutorial of how the sequencer works. If you are looking for information on the standalone Sky Sequencer executable, please go [here](standalonesequencer.html).

<div class="ue4-specific">
To launch the sky sequencer, simply double click on the sequence you would like to open. These can be found in the contents windows or from the details of the trueSKYSequenceActor if it is the currently active sequence. If you do not have a sequence, you can create one by right clicking in the content window, and selecting "Miscellaneous->New trueSKY Sequence Actor".


![](/images/unreal/contentbrowser.png)

<sup> Simply double click any of the sequences you want to open </sup>

</div>

<div class="unity-specific">
To launch the sky sequencer, select the sequence you want to launch. These can be found in the projects window or your currently active sequence can be found in your trueSKYMaster's inspector window. Then, once you have selected it, you should be able to choose "Show Sequence" in the inspector window.

![](/images/unity/inspector.png)

<sup> After click on a sequence, you can launch it with the buttons in the inspector </sup>
</div>

Before we look at the Sequencer, there are a some features of trueSKY you need to understand. Click [here](#registration) to return to logging into the sequencer.


Keyframes
-------------
Keyframes are what store the information about different cloud formations or skylines. There are 3 types of keyframes: Sky, cloud and storm. Each keyframe holds information on their respective effect, and can be customised in real time.

![](/images/unreal/keyframes.png)


Number                  |       Description                                     
----------------|-------------------
1                               |       This is a Sky Keyframe, these are Blue. Sky keyframes determine the colours of the sky from horizon to zenith, any haze/fog effect, and light colour.
2                               |       This is a Cloud Keyframe, these are white. You can see it is the currently selected keyframe because of the translucent box around it.
3                               |       This is a Storm Keyframe, these are Grey and their size depicts their duration. Storms produce lighting at set intervals for the duration of the keyframe.
4                               |       This is a currently unselected cloud keyframe. Cloud keyframes determine the properties of the clouds at the given time.  



Layers
------------

There are two types of layers in trueSKY: Sky and clouds. Layers store their respective keyframes, and each layer has settings that affect all the keyframes within.

![](/images/unreal/layers.png)

<sup>Image of a Sky layer and a cloud layer</sup>


Although there are only 2 types of layers, you can have numerous clouds layers. There can only be one Sky layer, as there can only be one Sky. Allowing for multiple cloud layers allows different cloud formations to appear at the same time. **To add a cloud layer**, right click anywhere in the timeline, and select "Add cloud layer". You can add as many cloud layers as needed, but the recommended limit is 5. Performance cost per layer is minimal.

![](/images/unreal/manylayers.png)

<sup>5 layers is probably the most you will ever need</sup>

Layers do *not* have any effect on the height of the clouds. Layer 1 can be lower than layer 2, or layer 5 could be in the middle. Height settings are adjusted within the individual keyframes. To add a keyframe to a layer, simply right click within the layer you want the keyframe for (click in the sky layer for a sky keyframe, cloud layer for cloud keyframe), then select the "Add Cloud Keyframe" option.

![](/images/unreal/AddCloudKF.png)

<sup>The keyframe will be created at the position your mouse is at</sup>


You can click on the layer name to access layer specific settings.

Sequence
----------
A sequence is a collection of Layers and keyframes, that can be saved and used in any scene that incorporates trueSKY. There can only be one sequence active at a time, although you can switch between them at run-time. You can use sequences to save specific weather formations for set times of the day.



Sky Sequencer Components
=========================
The sequencer is made up of 4 distinct parts

![](/images/unreal/skysequencer.png)




Number                  |       Section Name                                            |       Definition
----------------|-------------------                                    |------------
1                               |       [Registration](#registration)           |       Here you can login to your account using your username and licence key, this is needed to edit the sequencer
2                               |       [Details](#details)                             |       If you select an option with editable variables, they will appear here.
3                               |       [Cloud Window](#cloud-window)                   |       Top down view of the cloud coverage of the world.
4                               |       [Timeline](#timeline)                           |       A sequential timeline of all the trueSKY effects that will take place in this sequence



Registration
=============
Before you can edit anything on the Sequencer, you need to have entered your username and valid licence key.  This is entered in the registration fields, shown in the picture above. These can be found in your account dashboard at [simul.co/account](https://simul.co/account). If you do not have an account, sign up now at [simul.co/register/](https://simul.co/register/). We offer a 30 day free trial of trueSKY, but after the trial period you will need to purchase a licence. You can find more information about licensing [here.](http://docs.simul.co/Legal)

1: Login to your account at simul.co and click my account. 

![](/images/myaccount.png)


2: Your username and licence key are in the account dashboard. Your username is at the top left, underneath your name. Your licence key is on the right in the licence section.

![](/images/accountdashboard.png)


4: Launch the active sequence asset using the instructions [above.](#the-sky-sequencer)

5: In the sky sequencer, enter your username and licence key under 'registration'. If your details are correct, you will see the text 'OK' displayed under the licence key fields.


trueSKY can now be customised within your scene.


Details
=============

The details panel contains information about the currently selected keyframe or layer. This can all be edited, with changed taking place in real time. This panel will only show up if you have selected a keyframe.

To edit a keyframe, first select it with left click. This will bring up all the keyframes variables in the details column. 

![](/images/unreal/details.png)

<sup>This is the details panel of a selected Cloud Keyframe</sup>

Now you can see all the variables that can be altered within the Sequencer. You can either drag the bar to alter the value, or edit the values by typing. All of the values are clamped to certain ranges. Plus, each value can be returned to its default position with the yellow arrow to the right of the value. This arrow will only appear of the value has been changed from it's default state.

Presets allows you to automatically set a keyframe to one of our example keyframes. Click on a correlating preset (don't click a sky preset if you have a cloud keyframe selected) and then click apply to produce the selected preset on the current keyframe. 

![](/images/unreal/presets.png)

<sup>You can add your own presets with the create option</sup>

Layers also have their own settings which will change the values of all the keyframes in that layer. An example of this is within the Sky layer, you can change the diameter of the sun. This effect will take place for all the Sky Keyframes. To select a layer, just click on its name in the column to the left of the timeline. To see what each of the settings do, head over to our [Cloud](clouds.html), [Sky](sky.html), or [Storm](storms.html) pages.

{:.ue4-specific}
You can also use blueprints to edit the trueSKY environment. Head [here](/unreal/blueprints) to learn how.

{:.unity-specific}
You can also edit the trueSKY environment through scripting. Head [here](/unity/scripting) to learn how.




Cloud Window
========

The Cloud Window is a top down view of the world, where you can see the current cloud formations and layers. You can zoom in and out with the mouse wheel, and drag the world around by holding right click and dragging in a direction. If you select a keyframe, you will be able to drag its wind heading around the Cloud Window, allowing for full control of the angle of the wind. Furthermore, if you enable "override Wind" setting in the cloud layer properties, any cloud keyframes in this layer can also be dragged around and positioned as you see fit.

![](/images/unreal/overrideWind.png)

<sup>Make sure to tick this if you want to move the clouds from the Cloud Window</sup>

If you select a keyframe, the layer width is represented by a blue box, whereas a blue circle represents the [precipitation radius](precipitation.html#radius).

![](/images/unreal/WorldGrid.png)

<sup>You can see the cloud formations from the grey box, the current cloud layers origin and width from the blue box, and finally the precipitation radius with the blue circle.</sup>



Timeline
==========

The Timeline is the where all your keyframes are stored. It is used to adjust which features appear at what time. 

![](/images/timeline.png)



The numbers along the bottom represent the time. Within the timeline, trueSKY shows the time in hours and minutes. Zooming in and out with the mouse wheel will adjust the range of visible time. To change the current time, drag the red vertical line (the time marker) by its handle underneath. To change the visible time-window, drag the timeline at the bottom. To adjust the range of visible time, use the mouse wheel to zoom in and out. To adjust the current time in the timeline, you can drag horizontally by holding right click.

![](/images/unreal/timelineZoom.png)

<sup>I have zoomed in enough to see individual minutes on the timeline</sup>

You can select multiple keyframes at once by either shift clicking them individually, or you can double click within the desired layer to select all keyframes in that layer. You can then alter all their properties at once. Keyframes can be dragged and moved along the timeline with left click or copied and pasted in multiple places. 

If there is only one cloud keyframe present in a layer, then the clouds will not change over time, only move (if there is wind in the scene). If another keyframe is added to the layer, then the clouds will interpolate between the different keyframes based on the current time in the world. Interpolation is applied by layer, so clouds in layer 2 will not change based on clouds in layer 1. While interpolating, a special keyframe is created that stores the information. You can obtain a reference to this using <a href="../ref/simul/clouds/cloudkeyframer.html">#GetInterpolatedKeyframe </a>.

To learn more about progressing time within the world, along with the multiple ways to do so, head to [Progressing Time](time.html).

