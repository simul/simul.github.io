trueSKY Lighting
--------------
Place a reference to the trueSKY actor, and the directional light, on the master Level Blueprint. Connect the Get Sun Rotation output from trueSKY to the Directional Light's Rotator input; and connect the Sun Colour ouput from trueSKY to the SetLightColor input of the light.

<a href="SetLightColourDirection.png"><img src="https://simul.co/wp-content/uploads/documentation/html/SetLightColourDirection.png" alt="Blueprint"/></a>

To change the time of day, use the SetTime function of the trueSKY sequence actor (time is in days, from midnight on the first day (0.0):

<a href="SetTime.png"><img src="https://simul.co/wp-content/uploads/documentation/html/SetTime.png" alt="Blueprint" /></a>


Setting keyframe properties from Blueprint
--------------------------------------------------------------------------------------------------

To set a keyframe's value from Blueprint, use the SetKeyframeFloat, or SetKeyframeInt functions. You must pass the keyframe's integer uid, the name of the property as a string, and the value.

Similarly, GetKefyrameFloat and GetKeyframeInt are used to obtain current values.

You can get the next uid in the future that can be modified without recalculation using GetNextModifiableCloudKeyframe. 
