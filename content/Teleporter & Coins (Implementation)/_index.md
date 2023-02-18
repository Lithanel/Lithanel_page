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

![snowball collider](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/teleporter/ball_collider.png)

### Street Collider

![street collider](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/teleporter/street_collider.png)