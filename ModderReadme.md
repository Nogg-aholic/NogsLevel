If you are looking to make a level of your own, this info might help.

## Compiling This Mod Requires A Source File Change

For reasons described in the below section,
you must obtain a custom edited version of `FGWorldSettings.cpp`
to be able to build this mod (or any mod with a custom level)

## Creating A New Level Asset

When creating a new level asset,
you need to make sure the engine World Settings class at the time of creation
is the FGWorldSettings class instead of the UE default.

To do this, go in your Project Settings and search 'World Settings Class' and change it there

After changing this, restart your editor for it to take effect.

However, having this selected will crash your editor when trying to open any level,
because we don't have the real implementation for world settings, so it tries to call a bunch of mystery junk!

Also, if you try to build the mod,
it will package the level into a corrupt asset because of the level streaming changes made in U6.

This corrupt asset will crash the game when anything tries to load it
(even if not loading into the level, ex. get asset data via ContentInspector)

### Get Custom FGWorldSettings.cpp

So - replace your FGWorldSettings.cpp file with this one created by Arch from looking at IDA output:

https://discord.com/channels/555424930502541343/601030071221878784/1016823734826442812

and recompile dev editor and shipping.

You might have to edit it to conditionally include LevelEditor.h like this:

```cpp
#if WITH_EDITOR
#include "LevelEditor.h"
#endif
```

After you make this change,
your editor will still crash when trying to load levels with FGWorldSettings selected,
but you can package working level assets that WON'T crash on load.

## Switch Back to UE Default After Creating your Level

The World Settings Class setting does NOT need to be on FGWorldSettings at compile time -
just when you create your level asset.

Once you have created and want to edit the level,
you can switch your world settings back and restart the editor again.

A quick way to check if your level is of the right base class
is if you have the option to pick an `M Minimap Capture Actor` in the World Settings.

Although you may not need FGWorldSettings again, you do still need the custom `FGWorldSettings.cpp`

## Level Blueprints

Level blueprints are easy to miss if you aren't familiar with UE.

Nog's Level does the schematic unlocking logic and node spawning logic in its level blueprint.

To edit a level's blueprint, open the level asset in the editor,
then in the editor "Toolbar" window, press Blueprints > Open Level Blueprint

## Post Process Region

You need to have a post process region with a number of materials configured to get build effects working.
The `BuildEffectsPostProcessVolume` actor in the level is configured with them.

However, they screw with your vision in the editor, so I left the volume disabled.
The level blueprint's begin play will turn it on for real play.