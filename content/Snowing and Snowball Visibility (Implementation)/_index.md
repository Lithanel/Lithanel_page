---
title: "Snowing and Snwoball Visibility (Implementation)"
date: 2023-02-18T09:46:32+01:00
draft: false
weight: 60
---

## Snowing

To increase the chances that the player feels present in the snow landscape I wanted to add a snowing animation.
Therefore I used the **Unity Particle System**. <br>
I found a good tutorial on youtube (https://youtu.be/4wzubisvcyI) and tried to implement into my parkour.
I made the mistake of trying to apply the particle system to the whole parkour. 
The system could not keep up with the creation of the particles and there were also some performance issues.
In the end there was not enough snow falling down. 
I realized I it only had to snow close to the player, so I made a smaller particle area and attached it to the player.
This is the result: <br>
![snowing](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/snowing/snowing.gif)<br>

