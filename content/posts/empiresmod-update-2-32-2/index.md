---
title: Empires Mod 2.32.2 Released!
author: Smithy
date: "2021-05-30"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.32.2 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

# Changelog:

## Bug fixes
- Fixed an issue with how explosions determine if they were blocked by the world, this would sometimes false flag as being blocked by the world even if it wasn't. (Because the world entity is the fall-back entity for a missed entity-trace)
- Added the default mod_hl2 project's detail.vbsp definitions with Empires specific definitions appended to the end of the file. (Used to define detail sprites on textures)


## Script/Game Balance

### Infantry weapons

- Increased BEAR damage from 22 to 25. (Burst rifle)
- Reduced the recoil of the NF .50 Cal rifle.
- Reduced the recoil of the NF Heavy Carbine SMG.
- Reduced the cycle time of the NF Heavy Carbine SMG from 0.15 to 0.12 (Faster rate of fire)
- Reduced the damage per pellet for the NF shotgun from 20 to 15. (So that it matches the Brenodi shotgun)
- Increased the number of shotgun pellets for both shotguns from 9 to 10.
- Increased the number of shotgun pellets for the NF shotgun pistol from 7 to 8.

### Vehicle Armors

- Reactive
	- Reduced cost from 18 to 15
- Regenerative
	- Increased Bio Damage by 25%
- Deflective
	- Increased Health from 75 to 80
	
### Infantry Resistances

Infantry Resistances have been redone so that Engineer is the baseline, Grenadier takes 20% less damage from explosions, Rifleman takes 20% less damaga from bullets and Scout takes 10% less damage from explosions and 10% less damage from bullets
- Engineer
	- Engineer is now the baseline for infantry resistances
- Grenadier
	- Grenadier has 20% resistance against explosions
- Rifleman
	- Rifleman has 20% resistance against bullets
- Scout
	- Scout has 10% resistance against explosions and 10% resistance against bullets
	
### Vehicle Weapons

### Cannons

- Standard Cannon
	- Reduced Explosion Radius from 300 to 250
	- Reduced Heat from 9 to 8
- Extended Range Cannon
	- Reduced Explosion Radius from 250 to 200
	- Increased Heat from 8 to 9
- High-Explosive Cannon
	- Increased Heat from 12 to 14
- Rail Cannon
	- Reduced Explosion Radius from 250 to 200
	- Reduced Projectile Spread from 0.1 to 0.01
- Plasma Cannon
	- Increased Explosion Radius from 270 to 300
	- Reduced Projectile Spread from 1 to 0.3
	- Increased Heat to Target from 8 to 10
- Biological Cannon
	- Reduced Projectile Spread from 0.5 to 0.3
	- Reduced Player Bio Time from 5 to 3
	- Reduced Vehicle Bio Time from 5 to 3
	- Increased Vehicle Bio Damage from 6 to 8
	
### Missile Launchers

- Standard Missile Launcher
	- Reduced Explosion Radius from 200 to 150
- Guided Missile Launcher
	- Reduced Explosion Radius from 200 to 150
- Homing Missile Launcher
	- Reduced Explosion Radius from 200 to 150
- Upgraded Missile Launcher
	- Reduced Explosion Radius from 250 to 200
	
### Machine Guns

- Plasma Heavy Machine Gun
	- Reduced Damage from 12 to 10
	
### Buildings

Cannon Shells and Missiles (other than nukes) will now deal 1/6th damage to buildings, 1/12th damage to walls (Plasma CN does double damage), 1/3rd damage to turrets and 2/3rd damage to surveillance.
- Buildings
	- Increased ShellKineticResist from 0.8 to 0.833
	- Increased ShellBiologicalResist from 0.85 to 0.833
	- Increased ShellPlasmaResist from 0.85 to 0.833
- Turrets
	- Increased ShellKineticResist from 0.6 to 0.666
	- Increased ShellExplosiveResist from 0.6 to 0.666
	- Increased ShellBiologicalResist from 0.6 to 0.666
	- Increased ShellPlasmaResist from 0.6 to 0.666
	- Increased MissileResist from 0.65 to 0.666
- Walls
	- Increased ShellKineticResist from 0.9165 to 0.9165
	- Increased ShellExplosiveResist from 0.933 to 0.9165
	- Increased ShellBiologicalResist from 0.94 to 0.9165
	- Increased ShellPlasmaResist from 0.88 to 0.833
	- Increased MissileResist from 0.925 to 0.9165
- Surveillance
	- Increased ShellKineticResist from 0.25 to 0.332
	- Increased ShellExplosiveResist from 0.25 to 0.332
	- Increased ShellBiologicalResist from 0.25 to 0.332
	- Increased ShellPlasmaResist from 0.25 to 0.332
	- Increased MissileResist from 0.25 to 0.332


