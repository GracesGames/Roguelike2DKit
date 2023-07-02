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

### Enemies

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

__Roguelike 2D Game Instance Interface__

I_Roguelike2DGameInstance defines abstract events for the game instance to reduce coupling.

__Roguelike 2D Game Instance__

BP_Roguelike2DGameInstance is the game instance and keeps track of the selected art style.

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

__Bomb Cartoon__

BP_Bomb_Cartoon is the cartoon style version of BP_Bomb.

__Bomb Damage Type__

BP_BombDamageType is a damage type used to identify bomb damage. This makes sure bushes can only be destroyed by bombs. 

### Pickups

__Base Pickup__

BP_BasePickup is the parent class of all the pickup types. It handles the activation of the pickup when overlapping with the player.

__Bomb Pickup__

BP_BombPickup is a pickup that adds one bomb to the player.

__Bomb Pickup Cartoon__

BP_BombPickup_Cartoon is the cartoon style version of BP_BombPickup.

__Health Pickup__

BP_HealthPickup is a pickup that adds a set amount of health to the player.

__Health Pickup Cartoon__

BP_HealthPickup_Cartoon is the cartoon style version of BP_HealthPickup.

__Pickup Interface__

I_Pickup adds the pickup events to the objects that implement it. BasePickup implements I_Pickup.

__Key Pickup__

BP_KeyPickup is a pickup that adds one key to the player.

__Key Pickup Cartoon__

BP_KeyPickup_Cartoon is the cartoon style version of BP_KeyPickup.

__Powerup Pickup__

BP_PowerupPickup is a pickup that chooses a random powerup and on pickup upgrades the player using the chosen powerup. 

__Powerup Pickup Cartoon__

BP_PowerupPickup_Cartoon is the cartoon style version of BP_PowerupPickup.

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

__Tile Map Door Cartoon__

BP_TileMapDoor_Cartoon is the cartoon style version of BP_TileMapDoor.

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

__Bush__

BP_Bush is an example of a destroyable object. It is visually represented as a bush and can only be destroyed by bomb damage.

__Barrel Cartoon__

BP_Barrel is a cartoon style version of BP_Bush.

__Campfire__

BP_Campfire is another destroyable object but can be damaged by both player projectiles and bombs.

__Candelabra__

BP_Candelabra is a static blocking object with an animation to visually improve the level.

__Candle__

BP_Candle is also a static blocking object with an animation to visually improve the level.

__Chest__

BP_Chest requires a key to be opened. Else it just blocks the player.   
When opened it spawns a random pickup from a predefined set (e.g. health, key, bomb or powerup).

__Chest Cartoon__

BP_Chest_Cartoon is the cartoon style version of BP_Chest.

__Crate Cartoon__

BP_Crate_Cartoon is a cartoon style version of BP_Bush.

__Spike__

BP_Spike damages the player on touch and pushes the player away. It cannot be destroyed but it does have a reactivation time.

__Spike Cartoon__

BP_Spike_Cartoon is a cartoon style version of BP_Spike.

__Target Cartoon__

BP_Target_Cartoon is a cartoon style version of BP_Campfire.

### Widgets

All user interfaces support mobile input.   
Based on the platform the UI is automatically updated.

__HUD__

The BP_HUD is the in-game user interface and shows the player the current health / maximum health, bombs, keys, and amount of rooms cleared.  
It also defines the game over screen with the high score, current score, enemies killed, rooms cleared and an option to start a new game or return to the main menu.  
The pause menu user interface is also integrated in the HUD and allows the player to continue the game, start a new game and return to the main menu.

__Main Menu__

BP_MainMenu is the main menu user interface and allows the player to start the game, show the controls and quit the game.  