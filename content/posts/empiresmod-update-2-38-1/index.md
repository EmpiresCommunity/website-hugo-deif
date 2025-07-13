---
title: Empires Mod 2.38.1 Released!
author: Smithy
date: "2025-07-05"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.38.1 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

# Changelog:

## Bugfixes

- Fixed a bug causing mini-map icons to appear as the wrong building / vehicle type.
- Fixed a regression, where the mini-map wouldn't reveal both team's units at the end of the game.
- Fixed a bug where revived players would occasionally be teleported to the map origin.
- Fixed a bug where recycling a radar caused the emp_info_params entity to miscount the number of radars a team currently has. This was due to the counter decrementing twice, requiring teams to build two radars to compensate. The logic has been rewritten to eliminate reliance on manual increment/decrement operations.
- Optimized some of the heavily used functions in the game code. While functionality remains unchanged, these refinements offer small improvements to server performance and enhance overall maintainability.

## Script/Game Balance

### Infantry Weapons
- SMG3 (NF Heavy Carbine)
	- Decreased Damage per bullet from 37 to 32

### Vehicle Weapons
- Homing Missile Launcher (2 slot)
	- Decreased heat from 10 to 8


