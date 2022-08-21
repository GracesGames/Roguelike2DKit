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
* Several statistics (e.g. damage, fire rate, health and movement speed)

__Rooms__

* Simply create rooms using tile maps and tile sets (drag and drop)
* Define spawn locations and player start location using tile set metadata

__Terrain__

* Chests: requires key, provides pick-up
* Damaging spikes that push the player back
* Destroyable bushes, destroyed by bombs
* Destroyable campfires, destroyed by projectiles and bombs
* Static Candle and Candelabra object with animations

__Enemies__

* Six predefined enemies included
* Separated functionality over components
* Easily define component properties using defined options
* Define and modify enemy options using enumeration and Data Table
* Custom property examples:
    * Health
    * Health regeneration
    * Score
    * Projectile damage
    * Projectile scale
    * Collision damage
    * Movement speed

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
* Shoot circular pattern

__Health System__

* Shared logic for Player and Enemies
* Custom health values
* Custom armor values
* Death state
* Health regeneration
* Invulnerability window

__Pickups__

* Health
* Key
* Bomb
* Powerup

__Powerup__

* Easily to add/modify using player statistics and Data Table
* Define selection of player statistics and level per statistic
* Several examples provided

__Items__

* Bombs that damage surrounding actors

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
    * Start new game
    * Return to main menu
    
* Joystick and buttons (Mobile)
* Pause button (Mobile)

__Menus__

* Pause menu
    * Continue
    * Start new game
    * Quit
* Main menu
    * Start
    * Controls
    * Quit
    
__Save Game File__

* High score
* Easily extended
    
__Other__

* Example rooms
* Example animations (Flipbooks)
* Example sound effects
* Example game sounds

Fully customizable to support the needs of your game