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

## Snowball Visibility

One problem i had to deal with was that the snowball was hard to detect in the snowy landscape.
I mean it's a white object on a white background...
There were two things I added into my project to make the snowball more visible in case of grabbing and in case of throwing the ball.

### Outline

I found a very good free asset in the unity asset store to highlight the snowball in case the player grabs it.<br>
Here is the link to the asset called **Quick Outline**: https://assetstore.unity.com/packages/tools/particles-effects/quick-outline-115488<br>
I just had to make sure that the provided script is activated as soon as the snowball was grabbed.
The asset **Oculus Integration**, which we mentioned in the introduction, has a script named **OVRGrabbable.cs** 
that contains two functions called **GrabBegin** and **GrabEnd**. 
These functions can be used to find out when the snowballs are grabbed and the outline can be activated/deactivated accordingly.
![outline](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/snowing/outline.png)<br>

### Trail Renderer

To ensure that the ball does not merge with the landscape and becomes invisible to the players eyes, I used something called **Trail Renderer**.
This feature is included in unity and can be used by adding this component to an object. <br>
I found this very short, but informative tutorial and added it to my project: https://www.youtube.com/watch?v=9PqPZDqSDWA <br>
In the following picture you can see the options I used and the gif shows the final result. <br>
![trail renderer options](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/snowing/trail_renderer_options.png)<br>
![trail renderer](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/snowing/trail_renderer.gif)<br>

