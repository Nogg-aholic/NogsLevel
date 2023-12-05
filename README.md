# Nog's Customizable Level

_This mod currently maintained by Robb. No new features are planned._
_If you enjoy my work, please consider my [completely optional tip jar](https://ko-fi.com/robb4)._

A empty custom world great for mod testing, creative building, and challenge playthroughs!

Pick your options for the map, then get started!

This mod serves as an example mod for creating custom levels for Satisfactory.
A modified version of NogsLevel is included in the SML Example Mod as of SML `3.5.0`.

### Questions? Suggestions? Join the [Nog's Mods Discord server](https://discord.gg/CPeJJrXpth) or leave an issue on the [GitHub issues page](https://github.com/Nogg-aholic/NogsLevel/issues) (slower response time)

![Pick from Main Menu](https://i.imgur.com/Av7HFwr.jpeg)

## Overview

Another game world for you to play in that loads noticeably faster than the base game's world.

The level is great for testing mods or build plans, and it offers the ability to option to start with everything unlocked, and with the No Power and No Build Cost cheats enabled. Even with cheats turned off, the map theoretically has everything you'd need to play a game to completion.

By default the level contains the following:

- A orange **starting platform** with respawning Leaves, Flower Petals, and Wood pickups (since there is no foliage in the world) as well as food items, power slugs, and hard drives that respawn on much longer timers.
- **One of each Resource Node** and Well in Pure quality (and a Geyser)
- A large **body of water** for placing Water Extractors on.
- A [small region of toxic gas (for testing)](https://i.imgur.com/tTGa2p3.jpeg).

## Options

These config options affect every Nogs Level save,
since they are stored with your copy of the game, not the save file.
Per-world saves are coming as an SML feature Eventually ™.

- **Node Spawn**
  - With this option enabled, the mod will automatically spawn a resource node for each loaded ore. This automatically works with other mods you have installed (assuming they registered their resources correctly).
- **Ore Node Copy Count**
  - How many copies of the ore nodes to spawn
- **No Ground**
  - Great for Skyblock/Spaceblock/Void World challenges!
  - There is nothing in the world than the starting cube, water, and resource nodes. You'll need to build out foundations to access things.
  - If you fall off, you'll fall for a very long time before dying - consider using 'Respawn' from the pause menu to avoid the wait.

  ![Void World](https://i.imgur.com/pZiEt1d.jpeg)
- **Water World**
  - Great for Seablock challenges!
  - The entire world is an ocean! Resource nodes are at the surface.

  ![Water World](https://i.imgur.com/GWEh8eY.png)
- **Custom Day&Night**
  - With this option disabled, there is no day/night cycle in the world - it is always daylight, although there is no visible sun in the sky.
- **Unlock All Schematics**
  - Automatically gives you every loaded Schematic, MAM Research Tree, AWESOME Shop Purchase, and Alternate Recipe from all mods when you enter the map.
- **Cheat NoPower**
  - Automatically enables the NoPower cheat, meaning that buildings do not require power to operate (just an electric connection) and vehicles operate without requiring fuel.
- **Cheat NoCost**
  - Automatically enables the NoCost cheat, meaning that constructing things with the Build Gun does not require having the requisite resources in your inventory.
- **Skip Tutorial**
  - Does nearly the same thing as the base game's Skip Tutorial option. This is here so that the map can be automatically launched with the option (for use by other mods down the line). BUG - You might have to reload the save for the HUB to be visually complete
- **Resource Plants**
  - Spawn plants that regrow common pickable resources on the starting platform
- **Gas Cloud**
  - Spawn the gas cloud region (by the body of water) for testing
- **Max Modded Nodes**
  - WIP - controls how many mod resource nodes are allowed to spawn
- **No Vanilla Nodes**
  - No base game ore nodes will be spawned when this is true

## Useful for Testing

Since there are fewer things in the world to load, using NogsLevel as your mod testing map will reduce the amount of time you have to wait for the game to launch to test your mod. It may not seem like much, but the time shaved off every reload will add up.

You can use the directions below to create a Powershell script that will automatically launch the game and load you directly into a save file of your choice, bypassing the main menu:

<details>
<summary> Mod Developer Quick Launch Script Instructions </summary>

To use NogsLevel as your quick-launch save:

1. Launch the game normally and create a NogsLevel game save of your liking. Make sure you pay attention to what Session Name you chose.
2. Make a save from within the game, or allow the game to create an autosave, and make note of what the save is called.
3. Follow the directions [here](https://docs.ficsit.app/satisfactory-modding/latest/Development/TestingResources.html#_automatically_load_a_map_on_launch), but when making the `.ini` file, instead of using the example there, use this:

```ini
[/Script/EngineSettings.GameMapsSettings]
LocalMapOptions=??skipOnboarding?loadgame=NogsLevel_autosave_0
GameDefaultMap=/NogsLevel/NogsLevel.NogsLevel
GameInstanceClass=/Script/FactoryGame.FGGameInstance
```

where `NogsLevel_autosave_0` is replaced with the name of your save.

4. Close the game and run your Powershell script. If everything worked, the game should launch, and you should bypass the main menu, loading directly into NogsLevel and the save you specified.
5. Consider setting up the launch script to load autosave_0 as opposed to a specific named save. This means that when your testing world autosaves, the script will always launch you into your 'updated' testing save.

</details>

## Images

### Level Overview

![Overview Image](https://i.imgur.com/R3CHHCs.jpg)

### Respawning Resources

![Respawning resources](https://i.imgur.com/h8nhB6e.jpeg)

### Resources

![Nodes](https://i.imgur.com/vo4kG5Y.jpg)

### Water

![Water body](https://i.imgur.com/C5tQBxe.jpeg)

### Scale

These images will help you get an idea of how big the world is.

<details>
<summary> Map Scale </summary>

Top-down view from the editor of the level, with scale added in the bottom left.

![Entire map scale](https://i.imgur.com/r57w2L3.png)

The orange block you spawn starting on

![Orange starting block scale](https://i.imgur.com/Ku0Z4eS.png)

</details>

## Coming Soon™

- Configure the respawn frequency of the respawning materials
- Enemy spawn locations

## Special Thanks

- Ben for info on the changes made to the level streaming system in U6
- Archengius for writing the custom FGWorldSettings.cpp class needed to correctly package custom levels
- D4rkL0rd for info on the postprocess materials needed to get build effects working
