---
Layout: page
title: Versions
permalink: /versions/
---

# Versions

***

### Version 1.4.0

##### Release date: 21-08-2022

New features:

* Added required damage type option to the HealthComponent
* Added invulnerability window option to the HealthComponent
* Added Campfire object that can be destroyed by player projectiles and bombs
* Added Spike object that damages and pushes the player back on touch
* Added circular pattern option to EnemyShootingOptions
* Added QuadStraightShooter and QuadDiagonalShooter enemy
* Added Candles and Candelabra terrain objects with Flipbook animations
* Added 3 new rooms

Improvements:

* Replaced projectile collision logic with collision object type logic for a cleaner and more maintainable solution
* Exposed sprite color to EnemyBasicOptions
* Exposed projectile speed to EnemyShootingOptions
* Replaced StraightDirections and DiagonalDirections shooting options with CircularPattern option

### Version 1.3.0

##### Release date: 24-07-2022

New features:

* Added button highlighting option for main menu and HUD
* Added Armor and God Mode option to the HealthComponent

Improvements:

* Integrated TileMap 'Separation per Layer' value for spawning instead of static value, allowing proper height based setups (e.g. roofs)
* Extracted Door logic from TileMap to TileMapDoor actor. This allows rooms to have multiple doors. The door positions can be defined in the TileMap using the TileUserData.
* Made SetupData layer clean-up dynamic using a layer name instead of clearing only the top layer
* Added TileUserDataToClassMapping and use a DataTable to clean up tile map analysis and spawn point logic
* Added Room interface making BaseRoom actor obsolete

* Extracted enemy movement collisions to MovementComponent
* Extracted enemy options initialization to components
* Extracted enemy GameMode logic to GameMode using interface messages
* Unified enemy movement speed options into a single value
* Unified enemy projectile and player projectile to a single projectile with exposed options

* Extracted player movement logic to PlayerMovementComponent
* Extracted player shooting logic to PlayerShootingComponent
* Extracted player power up logic to PowerComponent
* Extracted player key and bomb logic to InventoryComponent

### Version 1.2.1

##### Release date: 26-09-2021

Improvements:

* Improved fire input handling and fixed several projectile firing issues

### Version 1.2.0

##### Release date: 19-09-2021

New features:

* Added health regeneration and extracted HealthOptions from BasicOptions
* Added option to spawn specific enemies based on Tile User Data
* Added Restart and Start New Game option to HUD
* Added several maps

Improvements:

* Reparented Player to Pawn instead of PaperCharacter, allowing more collision shapes
* Reparented Enemy to Pawn instead of PaperCharacter, allowing more collision shapes
* Integrated Chase logic into MovementComponent, making ChaseAI obsolete
* Fixed traversal issue where it was hard to enter any door and move along walls
* Fixed animation name issues

### Version 1.1.0

##### Release date: 30-03-2020

New features:

* Completely redesigned the pack using [Kenney 1-Bit Pack][1-bit]{:target="_blank"}{:rel="noreferrer"}.

* Added option to define player start position per room using tile set metadata.
* Added option to set color of power-up.
* Added option to set player death animation.
* Added option to define enemy fly speed in the Data Table.
* Added option to define projectile scale in the Data Table and Player.

* Greatly reduced package size by scaling and updating textures.
* Replace UI text by images, resulting in a clearer look.
* Focused the correct buttons, so the UI can be navigated by gamepad.

Improvements:

* Fixed issue where two player where needed, one for setup and one for player. Now the setup data is cleared properly so only one map is needed.

* Fixed issue where player would pick up health even when already at full health.
* Fixed issue where player would continue to shoot on death.
* Fixed issue where the AI would continue on player death.
* Fixed issue where player score could increase when dead.

### Version 1.0.0

##### Release date: 21-01-2019

* First release


[1-bit]: https://kenney.nl/assets/bit-pack