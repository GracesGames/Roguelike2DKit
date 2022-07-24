---
Layout: page
title: Documentation
permalink: /documentation/
---

# Documentation

***

### Components

__HealthActor Interface__

I_HealthActor defines an abstract way to let an actor know it died.

__Health Component__

BP_HealthComponent handles taking damage, changes the maximum health and checking if the character is dead. Next to that, it handles the armor value and health regeneration options.

### Directions

__Direction Functions__

BP_DirectionFunctionLibrary defines several functions used to manipulate and convert directions. Used for bouncing movement, shooting directions and more.

__Enemy__

BP_Enemy is the generic enemy class. It serves as the base class for all enemy types and can be easily customized using the different property structures and components.    
Adding a new enemy is as easy as creating a new row in the EnemyType data table and specifying its properties.

__Enemy Movement Component__

Used to implement the movement functionality of the enemies. Support multiple types and options defined by a enumeration.

__Enemy Shooting Component__

Used to implement the shooting functionality of the enemies. Support multiple types and options defined by a enumeration.

### Game

__Main Menu Game Mode__

BP_MainMenuGameMode is the game mode and specifies the BP_MainMenuPlayerController as default controller. It is used as the game mode in the Main Menu map.

__Roguelike 2D Game Mode Interface__

I_Roguelike2DGameMode defines abstract events for the game mode to reduce coupling.

__Roguelike 2D Game Mode__

BP_Roguelike2DGameMode is the game mode and handles the current room, room transitions, score, and game over actions. It is used as the game mode in the Test map.

__Game State__

BP_Roguelike2DGameState is the game state and handles the saving and loading of the save game.

__Save Game__

BP_Roguelike2DSaveGame is the save game and acts as a container for the save data (e.g. high score).

### Items

__Bomb__

BP_Bomb is the bomb object that can be placed by the player.   
It destroys BaseBreakable objects or children of BaseBreakable objects and damages Pawns (e.g. enemies and player). 

### Pickups

__Base Pickup__

BP_BasePickup is the parent class of all the pickup types. It handles the activation of the pickup when overlapping with the player.

__Bomb Pickup__

BP_BombPickup is a pickup that adds one bomb to the player.

__Health Pickup__

BP_HealthPickup is a pickup that adds a set amount of health to the player.

__Pickup Interface__

I_Pickup adds the pickup events to the objects that implement it. BasePickup implements I_Pickup.

__Key Pickup__

BP_KeyPickup is a pickup that adds one key to the player.

__Powerup Pickup__

BP_PowerupPickup is a pickup that chooses a random powerup and on pickup upgrades the player using the chosen powerup. 

### Player

__Player__

BP_Player is the player of the game. It handles player input for movement, firing projectiles and placing bombs. The logic is handled in specific components to split complexity and logic.

__Inventory Component__

BP_InventoryComponent is an container for the player items. Defines types, amounts and max amounts and ways to increment and decrement the amounts.

__Player Movement Component__

BP_PlayerMovementComponent moves the player using the movement input it receives from BP_Player.

__Player Shooting Component__

BP_PlayerShootingComponent handles the shooting input from the player and fires projectiles.

__Player Power Component__

BP_PlayerPowerComponent handles the powers of the player and the interaction with the components that query the power level. The player has several powers that can be upgraded. Examples are: damage, movement speed, fire rate and fire range.

### PlayerControllers

__Main Menu Player Controller__

Is responsible for creating and interacting with the Main Menu.

__Roguelike 2D Player Controller__
 
Is responsible for creating and interacting with the HUD (HUD changes, Pause Menu and Game Over screen).

### Projectiles

__Projectile__

BP_Projectile is the projectile fired by both the player and enemies.
On collision with a hostile class, it damages the hostile actor and destroys itself.  
On collision with the room, it destroys itself.
It has several exposed options, for example: color, life span, movement speed, damage.

### Rooms

__Tile Map Door__

BP_TileMapDoor keeps the player in the room and let the player progress when all enemies are dead. 

__Tile Map Room__

BP_TileMapRoom is the default room type used by the Roguelike 2D Game Mode. It chooses a room from the PossibleRooms array. 
The room analyses the TileMap TileUserData and uses it to spawn all the actors (e.g. enemies, terrain and pickups), after which the setup data is cleared.
Users can easily add new playable rooms by creating new Tile Map objects using drag-and-drop. 

__Door Interface__

Interface used to lock and unlock all doors in a room.

__Room Interface__

The Room interface adds the Lock, Unlock, Create, Finish and Destroy events to the rooms.   

__Spawnable Interface__

Interface implemented by object that are spawned into the room. Used to clean-up all objects on room completion. 

### Terrain

__Base Breakable__

BP_BaseBreakable is the parent object for all breakable objects. These objects can be destroyed by the bomb.

__Breakable Crate__

BP_BreakableCrate is an example of a breakable object. It is visually represented as a create.

__Chest__

BP_Chest requires a key to be opened. Else it just blocks the player.   
When opened it spawns a random pickup from a predefined set (e.g. health, key, bomb or powerup).

### Widgets

All user interfaces support mobile input.   
Based on the platform the UI is automatically updated.

__HUD__

The BP_HUD is the in-game user interface and shows the player the current health / maximum health, bombs, keys, and amount of rooms cleared.  
It also defines the game over screen with the high score, current score, enemies killed, rooms cleared and an option to start a new game or return to the main menu.  
The pause menu user interface is also integrated in the HUD and allows the player to continue the game, start a new game and return to the main menu.

__Main Menu__

BP_MainMenu is the main menu user interface and allows the player to start the game, show the controls and quit the game.  