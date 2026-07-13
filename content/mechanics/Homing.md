---
title: "Homing projectiles"
date: 2026-01-15
draft: false
---

## Overview

Using Unreal Engine, in a first person project, I made a projectile that will make a spline from the direction the player is facing and the target so it smoothly curves into the target that is locked on. The projectile updates the spline as it flies and so is able to also hit moving targets.

## Media
# Video Showcase

Curves into the target
<img src="/Homing1.gif" alt="Homing Projectile 1" style="width:100%">

Moves at a set speed regardless of distance to the target
<img src="/Homing2.gif" alt="Homing Projectile 2" style="width:100%">

Checks for if anything is blocking the path
<img src="/Homing3.gif" alt="Homing Projectile 3" style="width:100%">

## Code Snippets
![invalid](/CS_Homing1.png)

![invalid](/CS_Homing2.png)
The code for setting up the three main points of the homing spline; the beggining point, the middle point and the end point along with their respective leaving and arriving tangents so that it makes the desired curve.

![invalid](/CS_Homing3.png)
Used for updating the curve of the spline whulst the projectile is going along it so that moving targets won't be able to evade the homing projectiles.