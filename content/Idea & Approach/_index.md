---
title: "Idea & Approach"
date: 2023-02-18T09:46:32+01:00
draft: false
weight: 20
---

## Locomotion Technique
When we think about locomotion techniques, there are several metrics that need to be considered.
The one I wanted to focus on was the "Reduction of Cybersickness". 
When I tried VR for the first time I realised that I myself am very susceptible to cybersickness and that gave me the idea of reducing this sickness as much as possible. <br>
The first few things that came to my mind were:

* Move physically or teleport
* Controller (joystick) shouldn't control the camera
* Add nose
* Framerate > 90 FPS

Only teleportation and the second option made it into the final version.
Why did I not choose to move physically? The answer is simple. 
We were given the restriction of implementing a locomotion technique that can even be used in confined spaces.
Additionally I am very confident that teleportation is less susceptible to cybersickness than moving in place, since moving in place would still create an illusory self-motion in the absence of physical self-motion (vection).
In the following picture you can see my locomotion concept:

### Idea ball & teleportation

![idea tp](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/idea/idea_tp.png)

* The player can throw a ball to collect coins.
* If the ball collides with the ground it creates a portal.
* The player can activate the portal to teleport to the portals position.
* After activation the portal disappears.

I wanted to have some kind of theme that would fit well with my locomotion technique. 
It took a while to think of something suitable, but in the end I decided to go with a winter theme.
The ball thrown by the player shall be a snowball and I wanted to include other things, which will be explained later on, so that the player feels more present. <br>

## Interaction Task
Of course, the winter theme should also be maintained for the interaction task. 
My idea for the interaction task was to build a snowman instead of fitting the two T-shaped objects.
The next image shows my concepts:

![interaction concept](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/idea/interaction_concept.png)

The interaction task consists of 3 phases.
* 1.Phase: Attach the carrot (nose).
* 2.Phase: Attach the branch (left arm).
* 3.Phase: Attach the branch (right arm).

The different objects can be attached by throwing them at the snowman.
In the next chapters I will explain how I implemented my project and also the things I struggled with.