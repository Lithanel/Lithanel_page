---
title: "Teleporter & Coins (Implementation)"
date: 2023-02-18T09:46:32+01:00
draft: false
weight: 50
---

Now that we have the throwing function, we can start implementing the teleport system.
What exactly do we need?

* A portal is created at the point of impact of the snowball. Buildings and objects don't count.
* If the snowball collides with a coin, the coin is collected. Ball is not interrupted.
* The player can press a button to teleport to the portals location. Teleporter disappears when used.

First of all we need a model for the portal. This is the model I came up with:
![teleporter](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/teleporter/teleporter.png)
The teleporter is visible even from a distance thanks to the height of the column.

The portal is supposed to appear as soon as the the snowball hits the ground. For this purpose I used collider.

### Snowball Collider & Rigidbody
The snowball needs to have a **Continuous Collision Detection**, otherwise in too many cases the ball will fly through objects without being detected.
The Trigger will be activated the moment the object is realeased from the hand.

![snowball collider](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/teleporter/ball_collider.png)

### Ground Collider
The standard parkour contains street tiles with mesh colliders. The Collider should be set Convex to increase the change of the snowball being detected.
In cases like the curve tiles the colliders were not set to **Convex**, since the portal would float in the air.
I set the Rigidbody to **Kinematic** and activated all the **Constraints**, as the ground tiles should be not moveable. 

![street collider](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/teleporter/street_collider.png)

This image shows the collider of a curve tile. The Mesh Collider is set to convex. 
If you look at the error you can see that the colliders height is too high compared to the ground in the foreground.
![convex collider](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/teleporter/convex_collider.png)


## Error (No Collision Detection)
My first attempt looked like this:
![error collider](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/teleporter/street_collider.png)