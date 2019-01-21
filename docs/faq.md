---
Layout: page
title: FAQ
permalink: /faq/
---

# FAQ

***

Other questions? Send an [email][mail], join [Discord][discord] or create a [GitHub issue][github-issue]

#### Hidden In Game option for Layers in TileMap Editor not working

[Issue UE-22623](https://issues.unrealengine.com/issue/UE-22623) and [AnswerHub link](https://answers.unrealengine.com/questions/322796/bug-layer-display-check-in-tilemaps-not-working-pr.html) describe the issue where the Hidden in Game option for Tile Layers is not working.

__Possible Fix:__ [pull request](https://github.com/EpicGames/UnrealEngine/pull/5354), which in currently in review. Hopefully it will be merged and backported to earlier versions of the engine.
 
__(Temporary) Workaround:__ currently the Rogulike 2D Kit requires a RoomPair (structure), consisting of a SetupRoom and PlayRoom Tile Map, for each playable room. The PlayRooms are duplicates of the matching SetupRooms, but have all the layers that should be 'Hidden in Game' removed. 

I suggest creating all the SetupRooms first and when complete, duplicating the SetupRooms to PlayRooms and removing the obsolete layers. After that add the matching RoomPairs to the BP_TileMapRoom for play your rooms.

[mail]: mailto:gracesgamesbv@gmail.com
[discord]: https://discord.gg/DBwFAES
[github-issue]: https://github.com/GracesGames/Roguelike2DKit/issues