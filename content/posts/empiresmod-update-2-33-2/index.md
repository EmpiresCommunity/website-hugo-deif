---
title: Empires Mod 2.33.2 Released!
author: Smithy
date: "2021-10-17"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.33.2 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

Changelog:

## Features
- Added resource point icons to the minimap.
	- Resource output for each resource point can be seen on the full-sized map.
	- Resource points on the full-sized map have a color coded glow surrounding them to depict importance. 
		- Yellow (Lowest output) -> Green (2nd lowest output) -> Cyan (2nd highest output) -> Fuchsia (Highest output)


## Bug fixes
- Fixed some problems with how entities are detected by commands issued using the F-Menu. Including commands bypassing the menu using emp_menu_quickcmd. (Spotting/Squad Targets etc...)
	- The commands now do a line ray cast before doing a box ray cast which should reduce the chance of selecting the wrong entity because the box ray cast was big enough to hit something else than what you were aiming at.
		- Commands detect entities using the following method: Line ray cast -> Box ray cast -> Detect entity origins within 10 pixels of the crosshair, then return the closest entity to the player. Line of sight checks still apply for all methods.
		- emp_menu_quickcmd was using these methods in a different order than using the menu itself, this has been corrected. emp_menu_quickcmd was using the least accurate method first, which is the 10 pixel crosshair detection; often leading to picking a different entity than intended.
- Fixed a bug that caused [Steam Enhanced Rich Presence](https://partner.steamgames.com/doc/features/enhancedrichpresence) to display incorrectly.
- Fixed scouts not being networked to commanders in command view, rendering them completely invisible. This might have originally been added to side-step issues with commanders being able to target hidden scouts, those issues have also been resolved. Hidden scouts are no longer highlighted in attack selection boxes and targets cannot be issued if the scout is already hidden.
- Fixed an issue preventing the Bio infantry resist from working.
- Fixed two of the broken [[Tips#Chat_variables|Chat variables]], %_x and %_y. (Used to print the player's co-ordinates to chat.)
- Main menu "Quick Start Guide" button now links to the [website version](https://www.empiresmod.com/docs/quickstart/quick_start.html) using the Steam overlay instead of using an in-game panel. Some of the links in the local version were broken and the website version is slightly more up to date (although a lot of the information is still outdated).
- Removed default.cfg file and prevented the game from searching for it. This file was being used incorrectly and it would revert some of the settings held in the options menu.
	- The game now has a config_default.cfg file instead which executes on first launch of the game. Preventing the above issue from happening.
	- Added chatcommand_binds.cfg as an alternative to using default.cfg for setting client-side chat commands.
- Updated gameinfo.txt to hopefully fix an issue with the game saving files in the wrong directory. (settings.scr as an example - the file that allows the "Create a Server" dialog settings to function correctly)
- Fixed various potential crashes in server vehicle code.
- Fixed a bug causing some movement keys getting stuck down when transitioning from driving to command view.
- Fixed a bug where entering the overheated state in vehicles would still remove 1 tick of heat dissipation.
- Fixed a potential bug where the damage to heat attribute on vehicle armor could remove some of the vehicle's heat before the overheated state actually ended.
- Fixed a bug where applying Vehicle Bio Damage over Time (DoT) would always reset/override the previous effect. This was unintentional, the override code was supposed to be checking if the current Bio DoT drain was less than the new one but a typo caused it to fail and always result in an override.
- Fixed a bug where Bio DoT wouldn't deal the expected amount of damage ticks. (Both Player and Vehicle Bio DoT.)
- Fixed some issues preventing Steam achievements from being awarded.
- Removed some code which was redirecting friendly fire damage applied to the tank directly to the passenger that inflicted it, regardless of falloff or line of sight.
	- For example: If a player was in the second seat of an APC and their own mine was detonated by an enemy next to the APC - they would be given the same amount of damage as the APC regardless of their distance/being blocked by the APC's model geometry.


## Miscellaneous changes
- Controls menu has been updated.
	- Updated the layout and formatting for each category.
	- Removed old key binds that no longer worked.
	- Updated default key assignments, adding assignments where no default was already set.
- Updated the Game's Steamworks SDK version from v1.34 (28th July 2015) to the latest version which is v1.52 (14th September 2021).
	- Some of the Steamworks API calls we use stopped working recently, after updating to the latest SDK version they seem to be fixed. (The game's XP feature was no longer being awarded.)
- Rail cannon has a new firing sound.
- A general optimization pass was conducted on the code base. Small optimizations have been made to client and server, some potential crashes have been fixed.


## Script/Game Balance

### General
- Increased all building (excluding wall/turrets) resistance to Rifleman's Sticky grenades 0.77 -> 0.828 (Dmg 40 -> 30)
- Added a new script variable to control cannon recoil, previously it was using the damage value to scale the recoil. This change just allows us more control when balancing certain weapons. (All of the recoil values have been defaulted to the original values so there is currently no balance changes. This is for future use.)
- Angle Modifier armor attribute now has a 5 degree offset before the reduction kicks in. It was near impossible to land hits parallel to the surface normal angle that would result in dealing full damage.
	- The new angle range is from 5 - 50 degrees of being parallel, ranging from least to most reduction. Anything over 50 degrees would be full damage reduction depending on the armor's script value. (Angles ranges were previously 0 - 45 degrees, meaning damage was pretty much always reduced.)
- Neutral turning on vehicles is now restricted to the engine's output, meaning you can no longer turn on the spot if the engine can't drive while overheated. This is a change that will have to be play tested in order to see if it fits. Vehicles are supposed to be in a vulnerable state when overheated, simply being able to just rotate while in this state defeats the purpose of both sticky stuns and overheat. (Currently only the vehicles with tracks use Neutral turning.)
- Reduced the amount of screen shake that is applied to players from Biological damage over time by 75%. The screen will now have a very slight green overlay effect to indicate damage was taken from a Bio effect.

### Vehicle Weapons
- Biological Machine Gun
	- Changed Biological Interval to 0.5, damage per second and duration remain the same.
- Biological Missile Launcher
	- Changed Player Biological Damage from 4 to 3
### Vehicle Engines
- Bio Diesel (All chassis types)
	- Changed Heat Stall Penalty from 0.75 to 0.5


