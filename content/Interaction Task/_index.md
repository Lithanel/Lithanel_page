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
![carrot](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/interaction/carrot.png)<br>

## Two Branches (Arm)
![branch](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/interaction/branch.png)<br>

## Snowman
![snowman](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/interaction/snowman.png)<br>

The snowman model has three collider that check if nose and arms were attached the right way around (image: green arrows). 
If the objects **wrong collider** collides with the snowmans collider first than the object respawn at the start position and it is registered as a failed throw.


![snowman collider](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/interaction/snowman_collider.png)<br>

## Idle Interaction Portal
![tp deactivated](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/interaction/tp_deactivated.png)<br>

## Activated Interaction Portal
![tp activated](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/interaction/tp_activated.png)<br>

