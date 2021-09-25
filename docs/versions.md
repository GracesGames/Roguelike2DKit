---
Layout: page
title: Versions
permalink: /versions/
---

# Versions

***

Want more? Send an [email][mail], join [Discord][discord] or create a [GitHub issue][github-issue]

### Version 1.2.1

##### Release date: TBD

Improvements:

* Improved fire input handling and fixed several projectile firing issues

### Version 1.2.0

##### Release date: 19-09-2021

New features:

* Added health regeneration and extracted HealthOption from BasicOptions
* Added option to spawn specific enemies based on Tile User Data
* Added Restart and Start New Game option to HUD
* Added several maps

Improvements:

* Reparented Player to Pawn instead of PaperCharacter, allowing more collision shapes
* Reparented Enemy to Pawn instead of PaperCharacter, allowing more collision shapes
* Integrated Chase logic into MovementComponent, making ChaseAI obsolete
* Which traversal issue where it was hard to enter any door and move along walls
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
* Fixed issue where the Ai would continue on player death.
* Fixed issue where player score could increase when dead.

### Version 1.0.0

##### Release date: 21-01-2019

* First release


[mail]: mailto:gracesgamesbv@gmail.com
[discord]: https://discord.gg/DBwFAES
[github-issue]: https://github.com/GracesGames/Roguelike2DKit/issues
[1-bit]: https://kenney.nl/assets/bit-pack