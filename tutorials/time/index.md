---
title: Progressing Time
layout: reference
weight: 20
---






Progressing Time
=====================

Though we can now see clouds, you will notice that they aren't moving, even if the Wind Speed has been increased above 0. This is because time must progress for effects to take place. To get some movement in the scene, we will want to progress time.

TrueSKY supports three different modes of update - Game Time, Fixed Time and Real Time.


![](/images/unreal/updateoptions.png)



In all cases, the number of Subdivisions controls how finely the interpolation is performed. It’s the number of intermediate steps between keyframes (for Fixed Intervals), or in the Game Time or Real Time period specified.


Update Modes
==============
There are different ways in which we allow you to interpolate, each with it's own advantages and disadvantages

Game Time
===============
In Game-Time, it takes a specified amount of time in game hours, and split that into a given amount of intervals. The weather won’t change if game time does not. This is helpful go the weather does continue when paused, or can go slower based on the speed of the game. 


Fixed Time
============
Fixed Intervals mode is similar to Game time, only there’s a specified number of interpolated intervals between any two keyframes. You can use this mode to create more detailed transitions around sunrise/sunset for example.


Real Time
==============
If you’re using real-time transition, you can adjust the Interval (in seconds) to determine how quickly the change takes place.

