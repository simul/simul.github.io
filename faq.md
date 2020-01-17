---
title: FAQ
layout: reference
weight: 70
---




Frequently Asked Questions
=============================
This is an ongoing section of commonly asked questions. You can skip to a specific section by clicking below.

Sections
------------
[Setup](#setup)                                                                                                                                 |
[Performance](#performance)                                                                                                             |
[Weather Effects and Celestial Objects](#weather-effects-and-celestial-objects) |
[Lighting](#lighting)                                                                                                                   |
[Cloud Appearance](#cloud-appearance)                                                                                   |
[Other Issues](#other-issues)                                                                                                   |

Setup
=============

Could not find or load the QT platform "window"
------------------------------------------
Some Plugins use an incompatible version of the Qt widget system, please deactivate these Plugins to enable trueSKY. Currently known Plugins that have conflict issues can be found [here](#plugin-conflicts).

"createfile2 not found in kernel32.dll"
-----------------------------------------
This will be due to Windows 7. Unforunately, we do not support Windows 7 anymore. You will need to upgrade your OS to be able to use trueSKY.


Getting "DllNotFoundException"
---------------------------------
Windows User Account Control can give false positives when loading trueSKY, and stop it from being loaded. Lowering the notification level can help with this problem.


The trueSKY binary plugin is not working correctly
----------------------------------------
Try deleting the plugin folder Engine/Plugins/TrueSkyPlugin/Content and the plugin binaries Engine/Binaries/ThirdParty/Simul. Then re-install the latest version of the plugin.


When packaging the game, I get errors and/or the sky is black.
----------------------------------------------------
If you are using the binary installer, then you will need to follow some additional steps to be able to package your game with trueSKY. You can read about these [here](/programming/deployment.html).If these steps have been taken, there may be a conflict with another plugin. Currently known Plugins that have conflict issues can be found [here](#plugin-conflicts).


I can't edit the values in the sequencer
---------------------------
Ensure your license key has been entered at the top of the sequencer, and that it is valid.


The camera view is upside down
----------------------------------
Try checking/unchecking the "Flipped View" option in the TrueSkyCamera component. 


{:#emptyfolder}
My trueSKY folder in the content browser is empty
------------------------------
{:.ue4-specific}
You can find the contents by going to "UE4Engine/Engine/Plugins/TrueSkyPlugin/Content". We don't copy the files in to save you having the files in every project. If you want to copy them over that is fine, but you will need to adjust the trueSKY actor's and our material function references if you use them from a different location. 

I Can't Enable Water!
----------------------
This will be because you are using our legacy versions (4.1a), which does not support our Water. Please update to 4.2.

Sky
============

My Sky is Black in editor
--------------
Make sure your trueSKY Actor has an active sequence selected. 

The Sky updates with black spots!
-------------------------------------
Decrease the Atmospheric Amortization setting on the trueSKY actor. This will cause the Sky to update more frequently.

Performance
==============

trueSKY is taking too many milliseconds to render a frame. How can I reduce this value?
------------------------------------------------------------------------------------------
With default settings, the cost of trueSKY should be between 2 and 4 ms per frame. If this is not being achieved or in the use case, speed is a higher priority than visual performance, then this can be improved by altering the Amortization, Atmospherics Amortization and/or Downscale Factor settings in the details panel of the trueSKYSequenceActor. To aid the measurement of performance, trueSKY also provides profiling information (Windows -> Overlays -> Profiling or use the GetProfilingText function in blueprint).

How do I make the clouds appear less pixelated?
--------------------------------------------
Try increasing the Maximum Resolution setting, in the details panel of the trueSKYSequenceActor.


Weather Effects and Celestial Objects
=====================================

I don't see any rain
-----------------------
Make sure there are enough clouds above to produce rain!

I don't see any rain, but rain streaks are working
----------------------------
For rain and lightning to render in UE4, you need to have added trueSKY translucent as a post process material. As of September 2019, this has been made automatic, and added as part of initialization. Firstly, add a post process Volume to your scene, and make sure it is global by enabling "Unbound". Then go to the Rendering Features within the Post process Settings. Add a new element to the post process materials, and choose asset reference when prompted. Finally, add the trueSKY translucent material. If you do not have this material, you need locate the [trueSKY assets](#emptyfolder).


Rain drops are large and blocky
-------------------------------------
Try lowering the rain drop size on the trueSKY Actor.

I can't see Snow!
---------------------
Try increasing the Snowflake size on the trueSKY Actor.


The rain moves too quickly when I move the camera
-------------------------------------
This can happen when the camera is moving quite quickly. If you do not want to lower the speed of the camera's movement, then try lowering the metres per unit setting of the trueSKY object.


The sun is too bright
--------------------------
Post process effects can cause issues with trueSKY. Try lowering the intensity of the volume's bloom setting. Otherwise, there are settings within the Sky Layer settings. Alter the Irradiance or diameter. On the trueSKY Actor you can tick Max Sun Radiance. Then, when you change the Radiance the sun's size will adjust to produce the same amount of power with a limited Radiance.


The sun/moon is too big/small
---------------------------------
Try altering the sun and/or moon diameter setting in the sky layer, or if you have "Adjust Sun Radius" ticked on the trueSKY object, then adjusting the radiance of the sun will change it's radius. 


Lighting
===============

It's too dark at night
------------------------
Try lowering the brightness power setting in the sky layer.

Everything is Grey at night
---------------------------
Deleting UE4's Atmospheric Fog should fix this issue. We do not recommend using UE4's atmospheric fog, as trueSKY produces it's own fog. You can create fog from a Sky Keyframe.

Objects are light too brightly, especially at night
--------------------------------------------
Try disabling Global Illumination, or set Indirect Lighting Intensity to a small vale (e.g. 0.001) on a PostProcessVolume. Adjust your true Sky Light in the scene. Also check if you are creating any light through Cubemaps or alternate lighting methods. 

The sun is flickering
-----------------------
This may be caused by how post-processors deal with large brightnesses, along with the small pixel size of the sun. To get around this, we've introduced MaxSunRadiance as a property of the trueSKySequence Object. When sun radiance goes past this value, the size of the drawn sun is increased, and the radiance decreased, so that the overall energy is kept constant, but the output brightness reduced. *Additionally, if you haven't already, try deleting the default Atmospheric Fog and Sky Sphere actors.*{:.ue4-specific}


Cloud Appearance 
========================

How do I make my clouds the same each time I launch my program?
---------------------
Make sure the sequencer starts at the same time at each launch and the clouds should stay in the same formation.

My Clouds have an obvious pattern in them, how do I make it go away?
-----------
Noise is used to hide repetition, have a look at our [Noise Settings](tutorials/clouds/variables.html#noise) to learn how to hide patterns effectively. If it is still an obvious grid, consider changing the size of the grid. This is done in the trueSKY actor within the world under "Render Grid X" and "Render Grid Y". Reducing both these values will make the grid sections smaller, resulting in higher quality clouds. This may however affect performance. Multiple cloud layers can also be used to help remove the appearance of repetition by making them intersect. Finally, make sure there is breaks within the clouds, as a sheet of clouds will always look the most repetitive.


How do I make the clouds appear less pixelated?
----------------------------------------
Try increasing the clouds resolution in the trueSKY Object.

My Clouds change with only one keyframe
------------------------------------------
Setting the 'Noise Period' value in the cloud layer in the sky sequencer to the minimum possible will stop the clouds from changing shape over time.

How do I make the clouds move independently of time-of-day?
--------------------------------------
Make sure to set the value "Override Wind" to true. It can be found in the cloud layer settings. You can then move the layers individually using the World Grid, and the clouds will move based on layer positions.

<div class="ue4-specific">

On PS4, there is an apparent "trail" in the sky as the camera moves
---------------------------------------
The Unreal Engine screen clear is faulty in some versions: the Hardware Clear option does not work. To fix this, go to Project Settings -> Rendering -> Optimization and change "Clear Scene" to "Clear at Far Plane".

</div>



Other Issues
===============

Plugin Conflicts
----------------------

**Houdini**
Unnconfirmed issues with Houdini. 

<div class="ue4-specific">

**Niagara**
Using Niagara plugin in your scene can result in your packaged product producing a Black Sky. We've resolved the issue on our end, but it also has to be resolved on Epic's end, so we unfortunately cannot give a time frame. We have reached out to Epic and will update when a change has been made.

Mega Scans
----------
This issue has been resolved! Update your trueSKY to use it with Megascan plugins!
</div>

<div class="unity-specific">

**CETO**

Any transparent shaders in use will need to be modified, otherwise the water may render above the clouds. In the OceanTopSide_Transparent shader, find the "Queue" tag and change it from "Transparent-1" to "Transparent-500". Find the same tag in the "OceanUnderSide_Transparent" shader and change this from "Transparent-2" to "Transparent-501".   

This will make it so that trueSKY won't be visible when underwater, so if underwater views are needed, it is advisable to write a script that changes these queue values back to their defaults when the camera is underwater. 

Reloading or switching Unity scenes with both trueSKY and CETO active is not currently supported. This conflict is caused by CETO's OnDestroy() function, which removes the Unity camera and the associated Unity RenderBuffers; trueSKY relies on these RenderBuffers for its rendering.

**Popcorn FX**

If you are using the PopcornFX plugin, you will need to set native rendering to "Before Image Effect" for it to work alongside trueSKY.

</div>

My Question is not in the documentation, what can I do?
--------------------------
If our documentation can't help with your issue, let us know. [Email us at: contact@simul.co](mailto:contact@simul.co) and let us know what you think we should improve on, we're always looking for ways to help improve the quality of life for trueSKY users! Alternatively, you can join our Slack page, which is where our community discussions take place. Your question may have already been answered there! To join our Slack page, follow [this link](https://join.slack.com/t/truesky/shared_invite/enQtNzQwMDMyNzQ3MTIzLWY5NmZmOTQ4NWYyYjk5MGRjNmQ0ZDUzMDQyODE1MWNlMzJmNDlkZTMyMzI4NGQzN2UyZTQwZWExNmMwMDc0Zjk).


