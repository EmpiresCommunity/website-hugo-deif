---
title: Empires Mod 2.31.1 Released!
author: Smithy
date: "2021-03-20"
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.31.1 which is live on Steam right now!

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! https://discord.gg/EXwY2X7

Changelog:
## Features

- Player names and revive icons now follow ragdolls correctly rather than staying at the death location.
- Changed the revive icon to something simpler that is able to be re-colored in code and faded as to not block too much space on screen.
	- Revive icon is now red for team mates and yellow for squad mates.
	- Revive icon now fades out when close to the crosshair and if the player is too far away. (3000 units)
- Tweaked player name fade distance and position on screen in an effort to make them less likely to block your view.
- Player health colors are now drawn Red->Orange->Yellow->Green, rather than a linear transition of Red->Green.
- Tweaked position of ammo/health request icons along with the squad member icon.


## Bug fixes

- Fixed an issue causing spotting/targeting to be unreliable, this was due to  incorrect parameters on the collision traces.
- Fixed bad parameters on prone collision checks causing team mates to be able to block a prone attempt.
- Bullets no longer collide with projectiles, this should fix issues where tanks would shoot their own shells/missiles. (Although this affects all bullets)


## Script/Game Balance

### Vehicle Handling

- Armored Fighting Vehicle
	- Reduced Max Steering at Slow Speed from 50 to 45
- Armored Personnel Carrier (NF)
	- Reduced Max Steering at Slow Speed from 40 to 35
- Medium Tank (BE)
	- Increased Max Steering at Fast Speed from 10 to 12

### Research

- Plasma Cannon Projectile
	- Increased Cost from 240 to 360
	- Increased Time from 60 to 90
- Plasma Tipped Rounds
	- Increased Cost from 240 to 360
	- Increased Time from 60 to 90
- Upgraded Missile Warhead
	- Reduced Cost from 360 to 240
	- Reduced Time from 90 to 60
- Salvo Missile Launcher (NEW)
	- Cost = 180
	- Time = 45
- Guided Missiles
	- Reduced Cost from 360 to 240
	- Reduced Time from 90 to 60
- Chemical Dispersion (NEW)
	- Cost = 120
	- Time = 60
	- Contains Biological Warhead
	- Contains Biological Grenades (NEW)
		- Cost = 120
		- Time = 30
- Projectile Coating (NEW)
	- Cost = 120
	- Time = 60
	- Contains Biological Projectile
		- Reduced Cost from 360 to 240
		- Reduced Time from 90 to 60
	- Contains Biological Cannon
- Upgraded Chassis
	- Increased Cost from 480 to 600
- Medium Tank Chassis
	- Increased Cost from 360 to 450
- Artillery Tank Chassis
	- Increased Cost from 480 to 600
- Advanced Chassis
	- Reduced Time from 150 to 120
- Heavy Tank Chassis
	- Reduced Time from 180 to 120
	- Reduced Cost from 720 to 600.

### Armors

- Increased Composite Cost from 20 to 30.


### Weapons

- Biological Warhead
	- Reduced Player Bio Damage from 5 to 4
	- Reduced Player Bio Time from 10 to 8
	- Reduced Player Bio Interval from 1 to 0.5
	- Increased Vehicle Bio Damage from 7 to 8
	- Reduced Vehicle Bio Time from 10 to 8
- Biological Grenade Launcher (NEW)
- Removed Weapons
	- Machine Guns
		- Plasma Machine Gun (2 slot)
	- Cannons
		- Plasma Cannon (3 slot)
		- Heavy-duty Ranged Cannon (3 slot)
		- Thermobaric Cannon (3 slot)
		- Biological Cannon (2 slot)
	- Missiles
		- Heavy-duty Missile Launcher (3 slot)
		- Virulent Missile Launcher (3 slot)
		- Advanced Salvo Missile Launcher (3 slot)
		- TOW Guided Missile Launcher (3 slot)
		- Homing Missile Launcher (2 slot)
		- Salvo Homing Missile Launcher (3 slot)

### Infantry Weapons

Rather than listing the individual changes (Which would be a long list), please follow the link below for all of the changes.

https://git.empiresmod.com/empires_public/empires_scripts/-/merge_requests/209/diffs


