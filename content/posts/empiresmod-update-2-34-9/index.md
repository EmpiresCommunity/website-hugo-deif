---
title: Empires Mod 2.34.9 Released!
author: Smithy
date: "2023-03-05"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.34.9 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

Changelog:

## Features

- Double clicking of weapons/armor/engine in vehicle customization now adds/removes. Armor and engine will swap what is equipped if trying to add a different armor.


## Bug fixes

- Fixed a bug causing engineer tool to lose charge if the player triggered a re-equip before deploying the weapon.
- Fixed a bug preventing vehicles from repairing on repair stations when taking DMG_CRUSH damage type. (Physics crush damage/Damaged caused by crashing into walls)
- Fixed a client crash relating to guard/attack orders.
- Minor fixes to mini-map player icons.
- Minor fix to cross-hair alignment.
- Minor fix to artillery feedback skill showing hits that occurred before having the skill.
- Minor fix to prevent console spam on the server - caused by vehicle engine heat variables.


## Script/Game Balance

### Vehicle Armors

- Regenerative
	- Reduced Cost from 12 to 11
	- Reduced Weight from 15 to 13
	- Reduced Biological Damage Multiplier from 1.25 to 1.1
- Absorbant
	- Increased Cost from 10 to 11
	- Increased Biological Damage Multiplier from 0.5 to 0.8
	- Reduced BulletPlasmaResist from 0.1 to 0
	- Reduced ShellPlasmaResist from 0 to -0.1
- Reactive
	- Increased Cost from 15 to 16
	- Reduced Health from 120 to 110
- Composite
	- Increased Angle modifier from 0.35 to 0.5
	
### Vehicle Weapons

- Homing Missile
	- Increased Reload Time from 5s to 8s
- Plasma Cannon
	- Increased Clip Size from 30 to 40
- Biological Cannon
	- Increased Clip Size from 30 to 40
- Depleted Uranium Machine Gun
	- Reduced Cycle time from 0.105 to 0.09
	
### Vehicle Engines

- Bio Diesel
	- Decreased Heat Stall Penalty from 50% to 25%
	
### Infantry Weapons

- Mines
	- Disabled mine detonation by vehicle carcasses. (This is back to the old behavior.)
- RPG
	- Reduced Explosion Radius from 75 to 50
	- Reduced Turning Speed from 1.65 to 1.5


