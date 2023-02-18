---
title: "Throwing (Implementation)"
date: 2023-02-18T09:46:32+01:00
draft: false
weight: 40
---

In this chapter I talk about the throwing method.
The throwing method was done by **Karl Lewis**. I used a lot of his code and approach, so
please check out his website if you want to learn how to implement it yourself or maybe you want to know more about the mathematical background. <br>
https://karllewisdesign.com/how-to-improve-throwing-physics-in-vr/

I will just briefly summarize the approach I used. 
The **Oculus Integration** Unity Asset already has a grab and release function, but the problem is that it feels very unnatural to throw objects with it.
So I just made a few adjustments to my project to make whole process a bit smoother.
Here are some important points to pay attention to:

* The center of mass of the controller.
* The linear and angular velocity of the controller.

These are the two important lines, which made this whole throwing process a lot smoother and natural.
The linear and angular velocity have to be considered to get the full throwing velocity, else the throw would neither be accurate nor would it be long.
```
Vector3 controllerVelocityCross = Vector3.Cross(angularVelocity, m_grabbedObjectPosOff - controllerCenterOfMass);
```
```
Vector3 fullThrowVelocity = (linearVelocity + cross) * ballSpeed;
```

* controllerCenterOfMass = the center of mass of the controller
* angularVelocity = angular velocity of the controller
* linearVelocity = linear velocity of the controller
* controllerVelocityCross = cross
* ballSpeed = manually inserted number to adjust the velocity