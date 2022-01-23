---
title: Empires Mod 2.34.2 Released!
author: Smithy
date: "2022-01-23"
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.34.2 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! https://discord.gg/EXwY2X7

Changelog:

## Bug fixes

- Fixed a code typo which was causing a bug with explosion damage, meaning double damage could occur to vehicles.
- Fixed a few issues relating to checking a player's team for displaying icons on the minimap. Sometimes player icons wouldn't display even though they should.
- Fixed building smoke not calling StopEmission if the particle system is in a sleep state. (IE not being rendered but inside player's potential visible set)
	- What this essentially means is that building smoke will continue to change state even when you're not looking at the building. Previously you could look away from the building, turn around and notice smoke is still there for a few frames; despite the building being repaired while you weren't looking at it.
- Fixed a typo in vehicle_armor script for BulletExplosiveResist value.


## Script/Game Balance
- Lowered Plasma Heavy Machine gun's minimum damage from 10 -> 8 (It previously had no damage falloff.)


