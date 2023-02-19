---
title: "Interaction Task"
date: 2023-02-18T09:46:32+01:00
draft: false
weight: 80
---

Surprisingly, the most time of the project I spent on the Interaction Task. It took several Bugfixes and adjustments to create a proper system,
which doesn't throw any errors and is fun to play. In this chapter I will explain how I implemented the Interaction Task in my project.<br>
First of all I created some models:<br>

## Carrot (Nose)

The carrot and the branches have two important collider. The **right collider** and the **wrong collider*.
I will explain in a moment what these colliders are good for.

![carrot](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/interaction/carrot.png)<br>

## Two Branches (Arms)
![branch](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/interaction/branch.png)<br>

## Snowman
![snowman](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/interaction/snowman.png)<br>

The snowman model has three sphere collider that check if the nose and arms are thrown the right way around (image: green arrows). 
If the objects **wrong collider** collides with the snowmans collider first than the object respawn at the start position and it is registered as a failed throw.
If the objects **right collider** collides with the snowmans collider first and additionally collides with the head or body (depends on the object)
than the object will be attached on the snowman. The pre-attached transparent carrot and branch objects are supposed to serve as a orientation for the player. <br>

![snowman collider](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/interaction/snowman_collider.png)<br>

## Idle Interaction Portal

The **Idle Interaction Portal** changes to an **Activated Interaction Portal** as soon as a snowball hits the portal. <br>

![tp deactivated](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/interaction/tp_deactivated.png)<br>

## Activated Interaction Portal

This portal has the same functionality as the smaller version of it. The only difference is that the player can activate the 
interaction task by teleporting to this portal.<br>

![tp activated](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/interaction/tp_activated.png)<br>

## Interaction Portal

This is how the Interaction Portal works: <br>

![interaction porta](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/interaction/interaction_portal.png)<br>
