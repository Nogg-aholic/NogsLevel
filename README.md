# Nog's Customizable Level

_This mod currently maintained by Robb. No new features are planned._
_If you enjoy my work, please consider my [completely optional tip jar](https://ko-fi.com/robb4)._

A empty custom world great for mod testing, creative building, and challenge playthroughs!

Pick your options for the map, then get started!

### Questions? Join the [Nog's Mods Discord server](https://discord.gg/CPeJJrXpth) or leave an issue on the [GitHub issues page](https://github.com/Nogg-aholic/NogsLevel/issues) (slower response time)

![Pick from Main Menu](https://i.imgur.com/Av7HFwr.jpeg)

This mod originally served as an example mod for creating custom levels for Satisfactory.
SML 3.5 includes an enhanced copy of this mod's level in the Example Mod, demonstrating more features like foliage and hazards.

## Overview

Another game world for you to play in that loads noticeably faster than the base game's world.

The level is great for testing mods or build plans. Even with cheats turned off, the map theoretically has everything you'd need to play a game to completion, but not unlocking everything (ex. no Somersloops or Mercer Spheres).

By default the level contains the following:

- A orange **starting platform** with respawning Leaves, Flower Petals, and Wood pickups (since there is no foliage in the world) as well as food items, power slugs, and hard drives that respawn on much longer timers.
- **One of each Resource Node** and Well in Pure quality (and a Geyser)
- A large **body of water** for placing Water Extractors on.
- A [small region of toxic gas (for testing)](https://i.imgur.com/tTGa2p3.jpeg).

## Options

The level offers numerous configuration options via the "Mod Savegame Settings" system.
Most options can only be set when creating the save file, but some can be adjusted mid-game.

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

Follow the directions on the [Satisfactory Modding Documentation](https://docs.ficsit.app/satisfactory-modding/latest/Development/TestingResources.html#LaunchScript) to set up the quick launch script and use custom level asset path `/NogsLevel/NogsLevel.NogsLevel`.

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

## Special Thanks

- Ben for info on the changes made to the level streaming system in U6
- Archengius for writing the custom FGWorldSettings.cpp class needed to correctly package custom levels
- D4rkL0rd for info on the postprocess materials needed to get build effects working
