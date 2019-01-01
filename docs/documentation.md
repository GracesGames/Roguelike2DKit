---
Layout: page
title: Documentation
permalink: /documentation/
---

# Documentation

***

### General

__iSpawnable__

Interface implemented by object that are spawned into the room. Used to clean-up all objects on room completion. 

### AI Controllers

__Chase AI__

Enemy AI that makes the enemy pawn fly towards the player location. The goal of the AI is to collide with the player to deal the defined collision damage.

### Characters

__Character Health__

BP_CharacterHealth is the health component used by both the enemy and player. It implements the health system.   
The health system handles taking damage, changes the maximum health and checking if the character is dead.  
    
__Enemy__

BP_Enemy is the generic enemy class. It serves as the base class for all enemy types and can be easily customized using the different property structures and components.    
Adding a new enemy is as easy as creating a new row in the EnemyType data table and specifying its properties.

__Enemy Movement__

Used to implement the movement functionality of the enemies. Support multiple types and options defined by a enumeration.

__Enemy Shooting__

Used to implement the shooting functionality of the enemies. Support multiple types and options defined by a enumeration.

__Player__

BP_Player is the player of the game. It handles player input for movement, firing projectiles and placing bombs.    
The player has several powers that can be upgrades. Examples are: damage, movement speed, fire rate and fire range.

### Directions

__Direction Functions__

BP_DirectionFunctionLibrary defines several functions used to manipulate and convert directions. Used for bouncing movement, shooting directions and more.

### Game

__Main Menu Game Mode__

BP_MainMenuGameMode is the game mode and specifies the BP_MainMenuPlayerController as default controller. It is used as the game mode in the Main Menu map.

__Roguelike 2D Game Mode__

BP_Roguelike2DGameMode is the game mode and handles the current room, room transitions, score, and game over actions. It is used as the game mode in the Test map.

__Game State__

BP_Roguelike2DGameState is the game state and handles the saving and loading of the save game.

__Save Game__

BP_Roguelike2DSaveGame is the save game and acts as a container for the save data (e.g. high score).

### Items

__Bomb__

BP_Bomb is the bomb object that can be placed by the player.   
It destroys BaseBreakable objects or children of BaseBreakable objects and damages Paper Characters objects (e.g. enemies and player). 

### Pickups

__Base Pickup__

BP_BasePickup is the parent class of all the pickup types. It handles the activation of the pickup when overlapping with the player.

__Bomb Pickup__

BP_BombPickup is a pickup that adds one bomb to the player.

__Health Pickup__

BP_HealthPickup is a pickup that adds a set amount of health to the player.

__iPickup__

Interface that adds the pickup events to the objects that implement it. BasePickup implements iPickup.

__Key Pickup__

BP_KeyPickup is a pickup that adds one key to the player.

__Powerup Pickup__

BP_PowerupPickup is a pickup that chooses a random powerup and on pickup upgrades the player using the chosen powerup. 

### PlayerControllers

__BP_MainMenuPlayerController__

Is responsible for creating and interacting with the Main Menu.

__BP_Roguelike2DPlayerController__
 
Is responsible for creating and interacting with the HUD (HUD changes, Pause Menu and Game Over screen).

### Projectiles

__Enemy Projectile__

BP_EnemyProjectile is the projectile fired by enemies.
On collision with the player, it damages the player an amount specified by the public variable and destroys itself.  
On collision with other objects, it destroys itself.

__Player Projectile__

BP_PlayerProjectile is the projectile fired by the player.
On collision with an enemy, it damages the enemy an amount specified by the public variable and destroys itself.
On collision with other objects, it destroys itself.

### Rooms

__Base Room__

BP_BaseRoom is the parent object for all rooms. It is used by the Game Mode to spawn levels/rooms. It implements the iRoom interface.

__iRoom__

The iRoom interface adds the Lock, Unlock and Destroy events to the rooms.   
The Lock events, locks the room to keeps the player in the room.   
On room clear (all enemies are dead), the room is unlocked using the Unlock event.   
The Destroy event is used for clean-up.

__Tile Map Room__

BP_TileMapRoom is the default room type used by the Roguelike 2D Game Mode. It defines a playable room using a RoomPair, consisting of a SetupRoom and PlayRoom.   
The SetupRoom is analyzed and used to spawn all the actors (e.g. enemies, terrain and pickups).   
Due to a bug in the UE4 Engine (see [FAQ](https://gracesgames.com/Roguelike2DKit/faq/)), the game also uses a PlayRoom to spawn the room which the users see while playing.   
Users can easily add new playable rooms by creating new Tile Map objects using drag-and-drop. 

### Terrain

__Base Breakable__

BP_BaseBreakable is the parent object for all breakable objects. These objects can be destroyed by the bomb.

__Breakable Crate__

BP_BreakableCrate is an example of a breakable object. It is visually represented as a create.

__Chest__

BP_Chest requires a key to be opened. Else it just blocks the user.   
When opened it spawns a random pickup from a user-defined set (e.g. health, key, bomb or powerup).

### Widgets

All user interfaces support mobile input.   
Based on the platform the UI is automatically updated.

__HUD__

The BP_HUD is the in-game user interface and shows the player the current health / maximum health, bombs, keys, and amount of rooms cleared.  
It also defines the game over screen with the high score, current score, enemies killed, rooms cleared and an option to return to the main menu.  
The pause menu user interface is also integrated in the HUD and allows the player to continue the game and return to the main menu.

__Main Menu__

BP_MainMenu is the main menu user interface and allows the player to start the game, show the controls and quit the game.  