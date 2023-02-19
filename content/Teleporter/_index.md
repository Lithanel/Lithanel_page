---
title: "Teleporter"
date: 2023-02-18T09:46:32+01:00
draft: false
weight: 50
---

Now that we have the throwing function, we can start implementing the teleport system.
What exactly do we need?

* A portal is created at the point of impact of the snowball. Buildings and objects don't count.
* If the snowball collides with a coin, the coin is collected. Ball is not interrupted.
* The player can press a button to teleport to the portals location. Teleporter disappears when used.

First of all we need a model for the portal. This is the model I came up with:<br>
![teleporter](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/teleporter/teleporter.png)<br>
The teleporter is visible even from a distance thanks to the height of the column.

The portal is supposed to appear as soon as the the snowball hits the ground. For this purpose I used collider.

### Snowball Collider & Rigidbody
The snowball needs to have a **Continuous Collision Detection**, otherwise in too many cases the ball will fly through objects without being detected.
The Trigger will be activated the moment the object is realeased from the hand.<br>

![snowball collider](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/teleporter/ball_collider.png)<br>

### Ground Collider
The standard parkour contains street tiles with mesh colliders. The Collider should be set Convex to increase the change of the snowball being detected.
In cases like the curve tiles the colliders were not set to **Convex**, since the portal would float in the air.
I set the Rigidbody to **Kinematic** and activated all the **Constraints**, as the ground tiles should be not moveable. <br>

![street collider](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/teleporter/street_collider.png)<br>

This image shows the collider of a curve tile. The Mesh Collider is set to convex. 
If you look at the error you can see that the colliders height is too high compared to the ground in the foreground.<br>

![convex collider](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/teleporter/convex_collider.png)<br>

This is the final version of the teleporter system:<br>

![teleporter final](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/teleporter/teleporter_final.gif)<br>

## Errors
### Collision Detection Error
This is my attempt creating the portal without setting the **Mesh Collider** to **Convex**.<br>

![error collider](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/teleporter/error_convex.gif)<br>

The snowball just disappear into the ground, since some collisions are not detected properly.
There were still some snowballs disappearing without creating a portal, even though the Mesh Colliders set to convex.

This problem was solved by creating a big platform underneath the map to catch the balls in case they fall through the ground.<br>

![platform](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/teleporter/platform.png)<br>

### Snowball velocity error

The snowball returns to the spawn location after hitting the ground or an object. 
This error occurs, since the velocity of the ball is still high and it still travels into the thrown direction.
Gravity is also still active, which makes the ball lose height. This state repeats itself until the velocity reaches 0.
You can fix this problem by setting the velocity and gravity to 0 the moment the ball hits an object.<br>

![error_jiggle](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/teleporter/error_jiggle.gif)<br>

## Collect Coins

To collect coins you have to watch for collisions just like with the teleporter.
For the coins i created a seperate tag to ask for this in case of a collision.
If the snowball collides with the coin the coin will be deactivated and the coin counter will be increased by one.