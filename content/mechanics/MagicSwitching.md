---
title: "Magic Switching System"
date: 2026-08-22
draft: false
---

## Overview

For my first solo game, in Unreal Engine, the key feature of this game is the ability to switch between multiple classes of spells in a similar method to switching guns in a shooter where each gun has a unique type i.e. Snipers, ARs, Pistols etc. However, in the case of this mechanic, the spells have different types which changes how the spell works once activated based on the type of spell: Straight, Arc, Area of Effect, Beam and Buff. The spells have all their important variables stored within a data table that when spawned, fetches the values to store in a variable based on a row name that is set within each individual spells blueprint. The majority of the logic for all the spells is done within a single C++ class that switches to different functions and firing logic depending on what type of spell the spell data reads from the data table, leaving the unique logic to be done within blueprints like what the spell looks like and what it is meant to do with the actor that it collides with.

## Media
# Full video showcase
https://youtu.be/2fvrPHWM9WE

# Straight shot
<img src="/AAC/Spells/Straight.gif" alt="Straight" style="width:100%">

# Arc shot
<img src="/AAC/Spells/Arc.gif" alt="Arc" style="width:100%">

# Area of Effect
<img src="/AAC/Spells/AOE.gif" alt="AOE" style="width:100%">

# Beam
<img src="/AAC/Spells/Beam.gif" alt="Beam" style="width:100%">

# Buff
<img src="/AAC/Spells/Buff.gif" alt="Buff" style="width:100%">

## Code Snippets
# Set-up
![invalid](/AAC/Spells/SetUp.png)
The spells will first check that the variable spell data table is set and once confirming it is, the spell row then checks if its a valid row within the data table before setting the spell data struct with the variables from the data table. After that, the spells collision detection is told to ignore its owner which would be set in the parameters of the actor spawning the spell. Due to how the area of effect is not a one time hit like the rest of the spells are but instead something that repeatedly applies, it also sets up two events that add/remove an actor to an array for the specific spell blueprint to use when deciding what to do.

# Firing logic
![invalid](/AAC/Spells/Firing1.png)
![invalid](/AAC/Spells/Firing2.png)
When fired, the spells all have different logic depending on their type as a straight shot should travel in its direction, whereas a beam should instantly pierce everything in that direction. By using a switch statement on the spell type, the important variables are set before the respecive functions are called, in the case of the area of effect and buff spells, they immediately call upon their collision event instead of the other spells that check what they hit as the area of effect needs to change that constantly which is just easier with an array that adds and removes actors and a buff is already told who it is applying itself to.

# Arc shot calculations
![invalid](/AAC/Spells/ArcVel.png)
The arc shot is the most complicated spell within the system as it takes a start and end point along with an angle to then calculate the velocity it should be shot at to reach the end point based on the inputted parameters. By calculating the distance between the two points and using that to calculate the denominator for the quadratic formula, the initial speed can be calculated for the shot and then that speed can be converted to a vector for the equivalent velocity based on the direction its being fired in.

# Switching spells
![invalid](/AAC/Spells/SpellSwitch.png)
By using an array, the equipped spells are stored and then referenced when needed. As well as the logic to selecting the previous and next spell in the array, inputs for selecting a certain index are also setup. 