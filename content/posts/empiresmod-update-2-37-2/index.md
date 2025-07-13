---
title: Empires Mod 2.37.2 Released!
author: Smithy
date: "2024-08-18"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.37.2 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

# Changelog:

## Bugfixes
- Fixed a few bugs caused by a large refactor of the game's codebase:
	- Fixed a bug with ML turret targeting.
	- Fixed a bug with wall preview models not being visible.
	- Removed a left over debug statement from vehicle code. (Console would spam "WL_WAIST" if vehicle was partially submerged in water)

## Script/Game Balance
### Research
- AFV and LT are now set to be researched at the start of the game (Start_Researched 1).
	- Map creators can still set disable AFV/LT by using emp_sv_unresearch_item in the map's cfg file.
- Increased Upgraded Chassis time from 120s to 200s
- Increased Advanced Chassis time from 150s to 250s
- Increased Advanced Machining time from 120s to 150s
### Buildings
- Increased Radar cost from 300 to 400
### Infantry Weapons
- SMG1
	- Reduced Damage from 18 to 16
	- Reduced Minimal Damage from 11 to 7
	- Reduced Spread Increments by 10%
- SMG2
	- Reduced Damage from 19 to 17
	- Reduced Minimal Damage from 12 to 8
	- Reduced Spread Increments by 10%
### Vehicle Weapons
- .50 Cal Machine Gun
	- Increased clip size from 80 to 120

## Other changes 
- Updated material surface properties:
	- Reduced Snow friction from 0.75 to 0.6
	- Reduced Ice friction from 0.6 to 0.3
- Upgraded the platform toolset for compiling the Windows version of the game from v120 to v143. The codebase has been refactored to support this update, and no issues or new bugs are anticipated.
	- Alternate names for these toolsets are Visual Studio 2013 (MSVC 12.0) & Visual Studio 2022 (MSVC 14.3).

## Known Issues
- Armor impact sounds are often too quiet to be heard well. (Carried over from 2.37.0)


