---
title: Empires Mod 2.39.2 Released!
author: Smithy
date: "2025-12-13"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.39.2 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

# Changelog:

## Features
- Further adjustments to the visibility system introduced in 2.39.0:
	- Optimized functionality of the visibility manager game system.
		- Implemented a console variable on the server to control the update rate of the visibility manager processing. **emp_sv_vis_manager_update_interval** - This is in seconds and the default value is 0.01 (update per frame if running at 100 tickrate).
		- Various improvements to speed of processing, reducing the processing of detectable components where possible.
- Remaining vehicle carcass recycle amounts are now shown on the full screen mini-map (default key bind = **M**).
	- This may be subject to change or be removed but this has been added for testing purposes. It may be disabled by default in a future update, with an option to enable it in the multiplayer options menu.


## Bugfixes
- Speculative fix to prevent spotting diamonds appearing on the HUD where they shouldn't.


## Script/Game Balance
### Infantry
#### Weapons
Increased ammo reserves after reviewing & testing the recent changes in 2.39.1.

**Engineer:**
- Increased reserve ammo from 2 clips per weapon to 3 for most weapons.
	- Shotgun ammo increased from 16 to 18
	- SMG1 ammo increased from 70 to 105
	- SMG2 ammo increased from 80 to 120
	- Machine Pistol ammo increased from 30 to 45
	- Pistol 1 ammo increased from 28 to 36
	- BE Pistol 2 ammo increased from 14 to 21
	- NF Shotgun Pistol ammo remains at 8

**Grenadier:**
- No changes to reserve ammo values.

**Rifleman:**
- Increased reserve ammo from 3 clips per weapon to 4 for most weapons. 1 extra seismic grenade.
	- NF Assault Rifle ammo increased from 120 to 150 (5 clips)
	- Burst Rifle ammo increased from 120 to 150 (5 clips)
	- BE Heavy Rifle ammo increased from 120 to 160
	- Machine Pistol ammo increased from 45 to 60
	- Pistol 1 ammo increased from 36 to 48
	- BE Pistol 2 ammo increased from 21 to 28
	- Seismic Grenade ammo increased from 3 to 4

**Scout:**
- Increased reserve ammo from 3 clips per weapon to 4 for most weapons.
	- SMG2 ammo increased from 120 to 160
	- SMG3 ammo increased from 42 to 56
	- Machine Pistol ammo increased from 45 to 60
	- Pistol 1 ammo increased from 36 to 48
	- BE Pistol 2 ammo increased from 21 to 28


