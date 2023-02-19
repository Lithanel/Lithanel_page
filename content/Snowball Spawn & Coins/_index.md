---
title: "Snowball Spawn & Coins"
date: 2023-02-18T09:46:32+01:00
draft: false
weight: 70
---

## Snowball Spawn

Until now the snowball spawned at a designated location, which is not what we want. We want the snowball spawner to move and rotate with the player.
I tried to implement something similar to this video (https://youtu.be/FFM2oyLUysk) and partly succeeded.
The only thing I failed at was to move the spawn slightly to the players right side, but now the snowball always spawns at the players hip area
and also moves and turns around with the player.


## Collect Coins

To collect coins you have to watch for collisions just like with the teleporter.
For the coins i created a seperate tag to ask for it in case of a collision.
If the snowball collides with the coin the coin will be deactivated and the coin counter will be increased by one.<br>
This is how the result looks like: <br>

![collect coin](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/spawn/collect_coin.gif)<br>
