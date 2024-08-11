---
title: Empires Mod 2.37.1 Released!
author: Smithy
date: "2024-08-11"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.37.1 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

Changelog:

## Features
- Added the recycleGivesRefund ("Give Refund on Recycle?" in Hammer) parameter for building entities.
	- If set to 1 (the default), then when the building is recycled the resources are refunded. 
	- If set to 0, then when the building is recycled, no resources are given to the team.
	- The commander will get feedback for what the refund cost will be when triggering a recycle on a building.
	- This change allows level designers to strategically place buildings without worrying about commanders using them to gain additional resources through recycling. For instance, pre-spawned turrets are placed in starting locations to prevent early rushes. However, in the past, commanders have used these turrets to gain small resource advantages during the early phase of the game.
	- Although none of the official maps have been changed to adopt the above behaviour, this may be implemented in the future.
- Buildings can now require research to be placed.
	- If a building has the "Research" parameter set to the name of a research node, then the building will not be able to be placed until that research is completed.
		- Previously, this parameter was only used for turret upgrades.
	- If a building is unresearched, then it will show up in purple in the build menu.
	- The highlight color of unresearched buildings are purple, and have a tooltip indicating that they are not researched.


## Bugfixes
- Reverted grenade physics behaviour back to how it was prior to 2.37.0. 
	- We now fake the grenade bounce sound without detecting surface type. The previous VPhysics based detection did not actually detect the right surface type most of the time, so this is not much of a regression.
- Changed physics timestep to match server tickrate. (Instead of DEFAULT_TICK_INTERVAL - for Empires that's currently 66 tick)
- Removed code that disables vertex-lit materials being applied to detail models. (It no longer replaces the model with error.mdl)
- Comprehensive refactoring of vehicle code, both client & server. The aim of this is to improve code readability & maintainability while implementing minor bug fixes and reducing code complexity. It will allow us to iterate easier in the future when adding new features. Some related bug fixes
	- Fixed some bugs caused by the vehicle self-destruct functionality. When the self-destruct timer had elapsed it would cause the self-destruct damage to be applied first, then ignore any subsequent damage/regeneration that may happen in that frame. Essentially, if a vehicle was taking self-destruct damage it would be invincible to biological damage-over-time and armor would stop regenerating.
	- Fixed a number of potential crashes.
	- Fixed some issues with how vehicle water level is detected/set in code. This has no impact on gameplay but is now working as intended.
	- Fixed a bug with vehicle damage assists. Assists had the potential to be awarded because other entities had damaged the vehicle. (trigger_hurt for example).
	- Significantly reduced memory required to store a vehicle object through removing unused variables and optimization.
	- Reduced CPU usage by optimized code in various places.


## Script/Game Balance
### Infantry weapons
- Modified the Heavy Machine Gun for both teams to deliver sustained fire with decent accuracy, despite initially lower accuracy compared to rifles and SMGs, thanks to its low increment for longer, stable bursts.
	- HMG spread is based on DuckingSpread
		- HMG is 100% less accurate while Standing
			- HMG is 200% less accurate than Standing while Jumping
		- HMG is 20% more accurate while proning
	- HMG Spread Modifier is based on Spread
		- HMG is 200% less accurate while moving
	- HMG increment is based on Standing Increment
		- HMG increment is 20% slower while Crouching
		- HMG increment is 40% slower while Proning
- Adjusted the cycle time for the following weapons to align with servers operating at a 100 tick rate.
	- SMG 1(Both teams)
		- CycleTime 0.09 -> 0.08
	- SMG 2 (Both teams)
		- CycleTime 0.075 -> 0.07
	- NF Assault rifle
		- CycleTime 0.106 -> 0.1
- Engineer Tool
	- Increased heal amount from 4 to 6
	- Reduced Heal Modifier from 3 to 2 (Heal upgrade multiplier)

### Vehicle Weapons
- Biological Machine Gun
	- Reduced Clip Size from 80 to 60
- High-Explosive Machine Gun
	- Reduced Clip Size from 70 to 50
- Depleted Uranium Machine Gun
	- Reduced Clip Size from 100 to 80
- Railgun
	- Increased Clip Size from 30 to 40
- Biological Cannon
	- Reduced Bio Time from 10 to 5 seconds
- Homing Missile Launcher
	- Increased Lock On Time from 0.4 to 0.5
	- Reduced Lock On Modifier from 0.4 to 0.25
		- Homing Lock On Time reduced from 0.4-3.6 to 0.5-2.5 seconds
			- Homing Lock On Speed increased is 25% faster on average

### Vehicle Armors
- All armors
	- Increased Sticky Resist from -0.714 to -0.6
		- This reduces Sticky Bomb damage from 300 to 280 which means they won't destroy LT/APC with 1 grenade when equiped with plain or absorbant armor
- Plain Armor
	- Increased Health from 60 to 70
- Absorbant Armor
	- Increased Speed to Damage Modifier from 0.00005 to 0.00007
- Composite Armor
	- Increased Speed to Damage Modifier from 0.000025 to 0.000035
- Introduced new Capacitive Armor research under Electrical Engineering.
	- Research cost: 240 resources
	- Research time: 60 seconds
	- Capacitive Armor is intended to be resistant to infantry weapons but vulnerable to enemy tanks, key armor statistics below:
		- Weight: 13 per plate
		- Cost: 20 resources per plate
		- Health: 80 per plate
		- Damage to Heat Absorbed: 0.02 (2% of damage received is converted to heat)
		- Resistances:
			- HE Grenades: 70% resistance
			- Mines: 55% resistance
			- RPG: 45% resistance
			- Mortars: 45% resistance
			- Explosive Sticky Grenades: 42.5% resistance
			- Stun Sticky Grenades: 42.5% resistance
			- Squad Arty: 55% resistance

### Vehicle Engines
- Standard Engine
	- Increased cooling by 0.5

### Research
- New Research
	- Vehicle Factory
		- Parent: Structural Engineering
		- Time: 60s
		- Cost: 240
	- LT/AFV Chassis
		- Parent: Mechanical Engineering
		- Time: 60s
		- Cost: 240
	- APC Chassis
		- Parent: Mechanical Engineering
		- Time: 90s
		- Cost: 360

### Buildings
- Radar
	- Reduced Cost from 600 to 300
	- Reduced Health from 250 to 200
- Vehicle Factory
	- Reduced Cost from 700 to 500

## Other changes 

- Updated armor descriptions

## Known Issues
- Armor impact sounds are often too quiet to be heard well. (Carried over from previous update.)


