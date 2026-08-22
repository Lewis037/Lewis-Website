---
title: "Split Screen"
date: 2025-01-28
draft: false
---

## Overview

For this, I used visual studio with Raylib to make it so that the game splits the screen based on the number of players up to 4 and assigns them a unique controller that allows them to move around and fire a bullet and determine a winner based on the last person to lose all their lives.

## Media
# 1 Player
![invalid](/SplitScr/SplitScr1.png)

# 2 Players
![invalid](/SplitScr/SplitScr2.png)

# 3 Players
![invalid](/SplitScr/SplitScr3.png)

# 4 Players
![invalid](/SplitScr/SplitScr4.png)

## Code Snippets
![invalid](/SplitScr/CS_SPL1.png)
Iterating through all the players to set up their respective cameras to reference later on.

![invalid](/SplitScr/CS_SPL2.png)
Based on the number of players selected, the screen is split with thin lines drawn to clearly seperate the screens from each other.

![invalid](/SplitScr/CS_SPL3.png)
The code checks for how many controllers are plugged in and assigns them to a player first before defining the movement for that player with the controller logic.

![invalid](/SplitScr/CS_SPL4.png)
If there isn't a controller for the player, the code will then fall back on default keyboard inputs for that player that have been defined in the creation of the player so that each player has unique keyboard inputs in the event of no controllers being detected.