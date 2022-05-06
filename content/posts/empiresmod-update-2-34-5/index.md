---
title: Empires Mod 2.34.5 Released!
author: Smithy
date: "2022-04-02"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.34.5 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! https://discord.gg/EXwY2X7

Changelog:

## Bug fixes
- Fixed a bug/exploit that was allowing refineries to be placed at no resource cost.
- Fixed a bug where the engineer tool kit would not recharge the correct amount if you changed your skills while it was holstered.
- Fixed the "Just in time" achievement being awarded to the local player even if it was a different player that triggered the achievement.
- Fixed some issues where the squadleader.cfg file would not execute when expected, leaving you with the wrong key binds if you specified key binds inside the file.


## Script/Game Balance

### Infantry Weapons
- Heavy Machine Gun
	- Increased firing rate from 660 RPM to 792 RPM.
- SMG1
	- Reduced Max Falloff from 10k to 6k
	- Changed Moving Accuracy so it accounts for the moving speed
		- This results in lower accuracy while moving
	- Changed Kick to be more consistent
- SMG2
	- Reduced Max Falloff from 10k to 4k
	- Changed Moving Accuracy so it accounts for the moving speed
		- This results in lower accuracy while moving
	- Changed Kick to be more consistent
- BEHR/NFAR
	- Reduced Max Falloff from 10k to 8k
	- Changed Moving Accuracy so it accounts for the moving speed
		- This results in lower accuracy while moving
- Shotgun
	- Reduced Melee Cycle Time from 1 to 0.8
	- Increased Melee Damage from 70 to 80
- NF Shot Pistol
	- Reduced Damage from 20 to 14
	- Reduced Cycle Time from 0.6 to 0.5
	- Reduced Max Falloff from 10k to 2k
	- Changed Accuracy
	- Changed Kick

### Vehicle Chassis
- Artillery Tank
	- Removed Cannon's Yaw (movement left and right)
- Northern Faction Artillery Tank
	- Increased minimum pitch (movement up and down) so the cannon does not go inside the vehicle

### Vehicle Weapons
- Artillery Cannons
	- Removed Recoil

### Vehicle Armor
- Reflective angle modifier effective angle range has been reduced from 5 -> 50 degrees to 2.5 -> 47.5 degrees.
	- This is a direct buff to all armors using the reflective angle modifier script attribute as it will reduce the size of the angle modifier "dead zone" (The zone in which there is no damage reduction).


