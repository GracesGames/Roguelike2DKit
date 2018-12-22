---
Layout: page
title: Features
permalink: /features/
---

# Features

***

The Roguelike 2D Kit provides:

__Player__

* Top down movement
* Fire in straight directions (up, down, left, right)
* Place bombs
* God mode
* Several statistics (e.g. damage, fire rate and movement speed)

__Rooms__

* Simply create rooms using tile maps and tile sets (drag and drop)
* Define spawn locations using tile set metadata

__Terrain__

* Chests: requires key, provides pick-up
* Breakable crates, destroyed by bombs

__Enemies__

* Separated functionality over components
* Easily define component properties using defined options
* Define and modify enemy options using enumeration and Data Table
* Custom property examples:
    * Health
    * Score
    * Collision damage
    * Speed

_Enemy movement options_

* Static
* North-South
* East-West
* Random straight direction
* Random diagonal directions
* Random multi-directions (8 directions) 
* Bouncing straight direction
* Bouncing diagonal direction
* Chase player

_Enemy shooting options_

* Melee (no shooting)
* Shoot facing direction
* Shoot player position
* Shoot all straight directions
* Shoot all diagonal directions

__Health System__

* Shared logic for Player and Enemies
* Custom health values
* Modify maximum health
* Death state

__Pickups__

* Health
* Key
* Bomb
* Powerup

__Powerup__

* Easily to add/modify using player statistics and Data Table (see screenshot)
* Define selection of player statistics and level per statistic
* Several examples provided

__Items__

* Bombs, damages characters and destroy breakable crates

__HUD__

* Current health / Maximum health
* Key amount
* Bomb amount
* Rooms cleared
* Game over
    * Game over text
    * High score
    * Current score
    * Enemies killed
    * Rooms cleared
    * Return to main menu
    
* Joystick and buttons (Mobile)
* Pause button (Mobile)

__Menus__

* Pause menu
    * Continue
    * Quit
* Main menu
    * Start
    * Controls
    * Quit
    
__Save Game File__

* High score
* Easily extended
    
__Other__

* Example animations (Flipbooks)
* Example sound effects
* Example game sounds

Fully customizable to support the needs of your game