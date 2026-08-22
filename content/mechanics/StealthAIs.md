---
title: "Stealth game AIs Prototype"
date: 2024-09-28
draft: false
---

## Overview

During the development of Kagemusha, one of my earliest tasks I had was to make the enemies for the game, the AIs have 3 main states where they are passive and just patrol along their path or stand still depending on if they are set to patrol, an investigating state where they head towards a sound or saw a glimpse of the player and finally, an agrressive state where they chase the player and shoot at them. The AIs use a sight bar system to see the player over time instead of immediately noticing the player.

## Try it here

https://geratt.itch.io/kagemusha-public-demo

## Media
# video showcase
Patrolling
<img src="/Kagemusha/StealthAI/AIPatrolling.gif" alt="ai patrol" style="width:100%">

Sight bar
<img src="/Kagemusha/StealthAI/AISight.gif" alt="ai sight" style="width:100%">

Attacking
<img src="/Kagemusha/StealthAI/AIAttack.gif" alt="ai attack" style="width:100%">

## Code Snippets
![invalid](/Kagemusha/StealthAI/CS_AI1.png)
Depending on what the AI sees, it will check its state to make sure it is not already attacking something before checking the gameplay tag of what it sees and then executing some logic based on what it sees.

![invalid](/Kagemusha/StealthAI/CS_AI2.png)
The AI will repeatedly run this code until it is attacking when it sees the player by having a variable for storing how long it has seen the player for and adding the increment time every time this code is ran until the AI has seen the player for long enough to be switched to its aggressive state.

![invalid](/Kagemusha/StealthAI/CS_AI3.png)
When the AI loses sight of the player, it runs this short piece that tells it to stop running the incrementation code and begin running the decrementation code which is essentially just the inverse of the previous code snippet.

![invalid](/Kagemusha/StealthAI/CS_AI4.png)
Using a behaviour tree to determing what the AI should be doing depending on its state by defining the passive and investigating elsewhere as a sub tree since they are commonly used and then making the attack logic in the individual enemy type.