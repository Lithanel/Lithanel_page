---
title: "Snow landscape (Implementation)"
date: 2023-02-18T09:46:32+01:00
draft: false
weight: 30
---

Since I decided on the winter theme and to give the player the impression that they are in a winter landscape, 
the first thing i wanted to do was cover everything with snow. 
Therefore we used something integrated in Unity, which called "Shader Graph". <br>
I have oriented myself on this youtube video from Brackeys: https://youtu.be/IC9g5hlfV6o

This was my first try:

![snow layer house before](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/snow_layer/house_before.PNG) 
![snow layer house after](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/snow_layer/house_after.PNG)

The shader was not working correctly and instead of covering only the top side of an object, it covered the whole object in snow, which made totally white.
The youtube video contained a little older version, which was the reason for this error and after a fix the house looked like this.

![snow layer house completed](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/snow_layer/house_completed.png)

Much better :) As you can see in the result image the snow only lies on the top layer of the object.
This was possible thanks to a raycast from above. <br>
The next image contains my Shader Graphs for the snow layer:

### Snow layer (Shader Graphs)

![snow layer shader graphs](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/snow_layer/snow_layer.png)




The result is like day and night. The environment looks totally different:

### Parkour Before

![snow layer before](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/snow_layer/before.png)

### Parkour After

![snow layer after](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/snow_layer/after.png)

### Eye Error

![snow layer eye error yes](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/snow_layer/eye_error_yes.png)
![snow layer eye error no](https://raw.githubusercontent.com/Lithanel/Lithanel_page/master/images/snow_layer/eye_error_no.png)