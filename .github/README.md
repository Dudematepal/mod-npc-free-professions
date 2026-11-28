# ![logo](https://raw.githubusercontent.com/azerothcore/azerothcore.github.io/master/images/logo-github.png) AzerothCore

## mod-npc-free-professions

### This is a module for [AzerothCore](http://www.azerothcore.org)

- Latest build status with azerothcore:

[![Build Status](https://github.com/azerothcore/mod-npc-free-professions/workflows/core-build/badge.svg?branch=master&event=push)](https://github.com/azerothcore/mod-npc-free-professions)

## Description

This module makes a NPC who teaches free professions (FULL WITH RECIPES) to players. By default, the NPC teaches profession ranks progressively based on the player's character level, while retaining the ability for players to learn all ranks immediately through configuration.

## How to install

1. Simply place the module under the `modules` folder of your AzerothCore source folder.
2. Re-run cmake and launch a clean build of AzerothCore.

## How to use ingame

1. Add the NPC via GM commands `.npc add 199999` or `.npc add temp 199999` (If you want to add it temporarily) wherever you like.
2. Talk to the NPC to learn professions.

## How to edit the configuration file

1. In the folder where `authserver.exe` and `worldserver.exe` are located, you find a folder called `configs` and within it, one called `modules`.
2. Copy the file `mod_npc_free_professions.conf.dist`, and rename it `mod_npc_free_professions.conf` (but do not delete the original `mod_npc_free_professions.conf.dist`, both must exist).
3. Edit the file `mod_npc_free_professions.conf`.
4. Run `reload config` in the Worldserver console or `.reload config` in the in-game chatbox with a GM account.

## Configuration options explained

### 1. Enable or disable the module. When the module is disabled, the added NPC stays in the world but won't do anything when players talk to the NPC.

- Set `NpcFreeProfessions.Enable` to `1` to enable or to `0` to disable this module.

```
#
#   NpcFreeProfessions.Enable
#       Description: Enables the module
#       Default:    1 - Enabled, default
#                   0 - Disabled
#

NpcFreeProfessions.Enable = 1
```

### 2. Set the minimum character level requried to unlock each profession rank. Unlocking a rank automatically raises the profession skill to its maximum level. You can use this feature to prevent players from getting some of the achivements or abilities like `Lifeblood`, `Toughness` and `Master of Anatomy` too early which can make the early leveling too easy. You can also set the character level requirement for the Grand Master rank to 80 so players can max out the professions immediately.

- Set `NpcFreeProfessions.ApprenticeRankCharacterLevelRequirement` to any valid character level for the Apprentice rank.
- Set `NpcFreeProfessions.JourneymanRankCharacterLevelRequirement` to any valid character level for the Journeyman rank.
- Set `NpcFreeProfessions.ExpertRankCharacterLevelRequirement` to any valid character level for the Expert rank.
- Set `NpcFreeProfessions.ArtisanRankCharacterLevelRequirement` to any valid character level for the Artisan rank.
- Set `NpcFreeProfessions.MasterRankCharacterLevelRequirement` to any valid character level for the Master rank.
- Set `NpcFreeProfessions.GrandMasterRankCharacterLevelRequirement` to any valid character level for the Grand Master rank.

```
#
#   NpcFreeProfessions.EachProfessionRankCharacterLevelRequirement
#       Description: The minimum character level required to unlock each profession rank.
#                    Unlocking a rank automatically raises the profession skill to its maximum level:
#                    Apprentice = 75
#                    Journeyman = 150
#                    Expert = 225
#                    Artisan = 300
#                    Master = 375
#                    Grand Master = 450
#       Range:      1-80
#       Default:    1 - NpcFreeProfessions.ApprenticeRankCharacterLevelRequirement
#                   15 - NpcFreeProfessions.JourneymanRankCharacterLevelRequirement
#                   30 - NpcFreeProfessions.ExpertRankCharacterLevelRequirement
#                   45 - NpcFreeProfessions.ArtisanRankCharacterLevelRequirement
#                   60 - NpcFreeProfessions.MasterRankCharacterLevelRequirement
#                   70 - NpcFreeProfessions.GrandMasterRankCharacterLevelRequirement
#

NpcFreeProfessions.ApprenticeRankCharacterLevelRequirement = 1
NpcFreeProfessions.JourneymanRankCharacterLevelRequirement = 15
NpcFreeProfessions.ExpertRankCharacterLevelRequirement = 30
NpcFreeProfessions.ArtisanRankCharacterLevelRequirement = 45
NpcFreeProfessions.MasterRankCharacterLevelRequirement = 60
NpcFreeProfessions.GrandMasterRankCharacterLevelRequirement = 70
```

### 3. Enable or disable the feature that learning any profession rank automatically unlocks all recipes for that profession, regardless of the rank learned. If disabled, recipes will not be unlocked automatically. Useful for players who want to skip the grind but still want to explore and discover recipes themselves.

- Set `NpcFreeProfessions.Enable.LearnAllRecipes` to `1` to enable or to `0` to disable this feature.

```
#
#   NpcFreeProfessions.Enable.LearnAllRecipes
#       Description: If enabled, learning any profession rank automatically unlocks
#                    all recipes for that profession, regardless of the rank learned.
#                    If disabled, recipes will not be unlocked automatically.
#       Default:    1 - Enabled, default
#                   0 - Disabled
#

NpcFreeProfessions.Enable.LearnAllRecipes = 1
```

### 4. Enable or disable any profession that the NPC teaches. Disabled professions will disappear from the NPC's teaching list.

- Set `NpcFreeProfessions.Enable.Alchemy` to `1` to enable or to `0` to disable Alchemy.
- Set `NpcFreeProfessions.Enable.Blacksmithing` to `1` to enable or to `0` to disable Blacksmithing.
- Set `NpcFreeProfessions.Enable.Leatherworking` to `1` to enable or to `0` to disable Leatherworking.
- Set `NpcFreeProfessions.Enable.Tailoring` to `1` to enable or to `0` to disable Tailoring.
- Set `NpcFreeProfessions.Enable.Engineering` to `1` to enable or to `0` to disable Engineering.
- Set `NpcFreeProfessions.Enable.Enchanting` to `1` to enable or to `0` to disable Enchanting.
- Set `NpcFreeProfessions.Enable.Jewelcrafting` to `1` to enable or to `0` to disable Jewelcrafting.
- Set `NpcFreeProfessions.Enable.Inscription` to `1` to enable or to `0` to disable Inscription.
- Set `NpcFreeProfessions.Enable.Herbalism` to `1` to enable or to `0` to disable Herbalism.
- Set `NpcFreeProfessions.Enable.Skinning` to `1` to enable or to `0` to disable Skinning.
- Set `NpcFreeProfessions.Enable.Mining` to `1` to enable or to `0` to disable Mining.
- Set `NpcFreeProfessions.Enable.Cooking` to `1` to enable or to `0` to disable Cooking.
- Set `NpcFreeProfessions.Enable.FirstAid` to `1` to enable or to `0` to disable FirstAid.
- Set `NpcFreeProfessions.Enable.Fishing` to `1` to enable or to `0` to disable Fishing.

```
#
#   NpcFreeProfessions.Enable.EachProfession
#       Description: Enable/Disable each profession
#       Default:    1 - Enabled, default
#                   0 - Disabled
#

NpcFreeProfessions.Enable.Alchemy = 1
NpcFreeProfessions.Enable.Blacksmithing = 1
NpcFreeProfessions.Enable.Leatherworking = 1
NpcFreeProfessions.Enable.Tailoring = 1
NpcFreeProfessions.Enable.Engineering = 1
NpcFreeProfessions.Enable.Enchanting = 1
NpcFreeProfessions.Enable.Jewelcrafting = 1
NpcFreeProfessions.Enable.Inscription = 1
NpcFreeProfessions.Enable.Herbalism = 1
NpcFreeProfessions.Enable.Skinning = 1
NpcFreeProfessions.Enable.Mining = 1
NpcFreeProfessions.Enable.Cooking = 1
NpcFreeProfessions.Enable.FirstAid = 1
NpcFreeProfessions.Enable.Fishing = 1
```

## World configuration

You can also edit the Worldserver configuration file to change the number of professions players can learn.

1. In the folder where `authserver.exe` and `worldserver.exe` are located, you find a folder called `configs` and within it, the Worldserver confguration file called `worldserver.conf`.
2. Edit the file `worldserver.conf`.
3. Set `MaxPrimaryTradeSkill` to any number between `0` and `11`.
4. Run `reload config` in the Worldserver console or `.reload config` in the in-game chatbox with a GM account.
