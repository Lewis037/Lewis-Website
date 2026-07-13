---
title: "Climbing System (WIP)"
date: 2026-05-28
draft: false
---

## Overview

This is a climbing system I made that was inspired by the uncharted series. This climbing system was made with Unreal using its blueprint system, interfaces, structs and components to add in the climbing behaviours. This climbing system contains: jumping up onto a ledge, hanging on a ledge, moving left/right on the ledge, climbing up from hanging, jumping up/left/right from hanging onto another ledge, dropping down into hanging, falling and catching yourself on the ledge.

Animations from Mixamo and the Advanced Locomotion System.

## Media
# Video showcase
https://youtu.be/RNBu8rA2Cck

## Code Snippets
![invalid](/CS_CL1.png)
The code runs through a sequence to see what type of jump it should do and determines if it's a braced hanging spot or freehang spot before going into its respective collapsed graph.

![invalid](/CS_CL2.png)
When jumping left or right across different climbable surfaces, the coordinates of the location, the type of animation to play (braced or freehang) and the offsets so the player is not on the first pixel of the wall are fed into a  macro that handles a check for if its a valid jump point by checking if the top of the wall is there to hold on to and also gets the variables needed for jumping to the wall if its valid.

![invalid](/CS_CL3.png)
A trace is done from the players head to a small bit in front of the player to determine the location of the wall so that those coordinates can be used for later calculations.