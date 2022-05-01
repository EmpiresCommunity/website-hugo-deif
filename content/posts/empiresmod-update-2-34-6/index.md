---
title: Empires Mod 2.34.6 Released!
author: Smithy
date: "2022-05-01"
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.34.6 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! https://discord.gg/EXwY2X7

Changelog:

## Bug fixes

- Fix order distances having incorrect unit conversion from inches to meters.
- Fix an issue allowing an exploit to refill calc charge.
- Disable mine detonation for players on ladders.
- Remove double averaging of scoreboard latency, engine code already handles it.


## Script/Game Balance

### Infantry Resists

- Engineer & Rifleman
	- Increased Mortar Resist from 0 to 0.1
    	- Reduces Mortar Damage from 130 to 117
- Scout
	- Increased Mortar Resist from 0.1 to 0.19
		- Reduces Mortar Damage from 117 to 105
- Grenadier
	- Increased Mortar Resist from 0.2 to 0.28
    	- Reduces Mortar Damage from 104 to 93

### Command Vehicle

- Reduced Engineer Hull Repair from 3 to 1
	- It triples the time it takes to repair the Command Vehicle's Hull
- Reduced Engineer Armor Repair from 0.04 to 0.01
	- It Quadruples the time it takes to repair the Command Vehicle's Armor
- Reduced Command Vehicle's Armor Health from 275 to 250
- Reduced Command Vehicle's Armor Regenaration from 0.004 to 0.002
- Increased Command Vehicle's Armor Damage to Heat Absorbed from 0.025 to 0.04

### Vehicle Armors

- All Armors
	- Increased Squad Artillery Resistance from 0 to 0.25

### Vehicle Weapons

- Extended Range Cannon
	- Increased Gravity from 0.1 to 0.15
- Plasma Cannon
	- Increased Explosion Force from 100 to 500
- Railgun
	- Increased Gravity from 0.04 to 0.05
	- Increased Explosion Force from 50 to 1000
- Biological Cannon
  - Increased Explosion Force from 170 to 300
- Upgraded Missile Launcher
	- Reduced Heat from 6.5 to 6
	- Reduced Weight from 70 to 60
	- Increased Explosion Force from 50 to 100
- Biological Missile Launcher
	- Reduced Weight from 70 to 60
- Salvo Missile Launcher
	- Reduced Weight from 60 to 55
	- Increased Explosion Force from 20 to 50
- Guided Missile Launcher
	- Reduced Heat from 9 to 8
	- Reduced Weight from 70 to 60
	- Increased Clip Size from 4 to 5
	- Increased Explosion Force from 40 to 100
- Homing Missile Launcher
	- Increased Explosion Force from 40 to 500

### Vehicle Weapons

- Mortar & RPG now share the same ammo
	- It effectively reduces the amount of ammo Grenadiers carry by half
- Mortar
	- Reduced Speed from 2000 to 1800
- Northern Faction .50cal Rifle
	- Increased Minimal Damage from 20 to 30
		- It ensures that it takes 4 shots to kill an enemy on distances shorter than ~6000 units


