---
title: Empires Mod 2.30.6 Released!
author: Smithy
date: "2021-01-30"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.30.6 which is live on Steam right now! 

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

# Changelog:

## Bug fixes

- Fixed an issue causing degreesSlow/degreesFast vehicle handling variables to be overridden by hard-coded values. (There shouldn't be any issues caused by fixing this as script values have been adjusted to match)
- RPG now uses a different 3rd person reload animation as there was no RPG animation available. (Uses HL2's AR2 reload as it is the closest visual fit)
- Fixed an issue with accuracy upgrade not using the script value when adjusting weapon base spread. (It was hard-coded to 25%, this will now use "AccuracyUpgradeModifier" script variable)
	- For most weapons this will be a small nerf to accuracy but as always any issues identified will be addressed in future updates.


## Script/Game Balance

### Damage Types and Resistances

- Changed GeneralChemistry to GrenadeExplosive (Grenade Launcher and Upgraded Grenade Launcher)
- Changed GeneralPhysics to ShellPlasma and BulletPlasma (Plasma CN and Plasma MG)
	- ShellPlasma inherited the GeneralPhysics values
	- PlasmaBullet
		- Absorbant has 10% resistance
		- Buildings have 100% resistance
		- Turrets have 70% resistance
		- Walls have 100% resistance
		- Infantry has 0 resistance
- Changed BioArt to ShellBiological (Biological CN)
- Changed Kinetic to ShellKinetic
- Changed Explosive to ShellExplosive
- Changed APBullet to BulletAP
- Changed BulletExplosive to BulletExplosive
- Changed KineticArt and ExplosiveArt to Artillery
- Increased Building resistance against Depleted Uranium from 87.5% to 100%.
- Decreased Wall resistance against Plasma Cannons from 94% to 88%.
	- It doubles the damage that plasma cannons do to walls making it a new perk of plasma cannons.

### Research

- Added separate researches for Artillery Cannons
- Removed Turrets research from Electrical Engineering
- Added a new tree called Strutucal Engineering
	- Upgraded Machine Gun Turrets Lvl 2
		- Upgraded Machine Gun Turrets Lvl 3
	- Upgraded Missile Launcher Turrets Lvl 2
		- Upgraded Missile Launcher Turrets Lvl 3

### Classes

- Rifleman and Scout now have access to Seismic Grenades

### Infantry Weapons

- Northern Faction .50cal Rifle
	- Increased recoil across the board

### Vehicle Chassis

- APC
	- Increased cost by 50
	- Reduced the number of Grenade Launcher that can be equipped from 2 to 1.
	- Reduced the size of the Grenade Launcher slot from 3 to 2.
- LT/AFV
	- Increased cost by 30
- Medium
	- Reduced the number of Missile Launcher that can be equipped from 2 to 1.
- Heavy
	- Brenodi Empire
		- Increased the size of the Machine Gun slot from 2 to 3.
		- Reduced the number of Missile Launcher that can be equipped from 3 to 1.
		- Reduced the number of Machine Gun that can be equipped from 2 to 1.
	- Northern Faction
		- Increased the size of the Machine Gun slot from 2 to 3.
		- Reduced the number of Missile Launcher that can be equipped from 6 to 2.
		- Reduced the number of Machine Gun that can be equipped from 2 to 1.

### Vehicle Armor

- Removed Capacitive
- Reactive
	- Increased Health from 120 to 130.

### Vehicle Engines

- APC
	- Increased Weight of Fission Engine from 5 to 10.
- LT/AFV
	- Increased Weight of Fission Engine from 10 to 20.
- Medium
	- Increased Weight of Fission Engine from 10 to 20.
- Heavy
	- Increased Weight of Fission Engine from 10 to 20.
- Artillery
	- Reduced Weight of 3 Phase Engine from 40 to 30.
	- Increased Weight of Fission Engine from 10 to 20.

### Vehicle Weapons

- Plasma MG
	- Decreased Cycle Time from 0.35 to 0.3.
	- Decreased Heat from 0.18 to 0.15.
- Grenade Launcher
	- Decreased Cycle Time from 2 to 1.4.
	- Increased Heat from 8 to 10.
	- Increased Cost from 30 to 50.
	- Increased Weight from 30 to 40.
- Upgraded Grenade Launcher
	- Increased Weight from 40 to 50.
	- Increased Heat from 12 to 14.


