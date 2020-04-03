---
title: Variables
layout: reference
weight: 30
---





Storms
====================

{:.keyframe}
Variable                                                                                |       Definition                                                                                                                                                      |       Value
--------------                                                                  |--------------                                                                                                                                                 |--------------
Real time                                                                               | Sets frequency/duration of strikes to real time. If false, then simulation time.              |Bool
Motion                                                                                  | How much a bolt should move/animate during a strike.                                                                                          |0 to 10
Strike Duration                                                                 | The time each strike should last, in (simulated) seconds.                                                             |0.1 to 1000
Strike Frequency                                                                | How many strikes per (simulated) second.                                                                                              |0.1 to 10
Branch Angle                                                                    | Mean angle of branching, in degrees from 0 - 90.                                                                              |0 to 90
Random seed                                                                             | Pseudo-random seed.                                                                                                                                   |0 to 1000
Levels                                                                                  | Number of levels of branching.                                                                                                                |1 to 5
Branches                                                                                | Mean number of branches to generate from each parent.                                                                 |1 to 12
Vertical to Sheet                                                               | How much of the lighting should stay within the clouds.                                                               |0 to 1
Roughness                                                                               | How rough/smooth to make the lightning branches.                                                                              |0 to 1
Storm Radius                                                                    | Radius of the lightning storm, in km.                                                                                                 |1 to 100
Thickness                                                                               | Thickness of the lightning trunk, in metres.                                                                                  |1 to 100
Min Pixel Width                                                                 | Minimum pixel size for rendering the lightning strikes.                                                               |0 to 8
Radiance                                                                                | Maximum radiance of the strikes.                                                                                                              |0.1 to 10000





