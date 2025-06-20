---
title: Empires Mod 2.38.0 Released!
author: Smithy
date: "2025-06-20"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.38.0 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

Changelog:

## Features
- Replaced vehicle shell particle effects with the new [particle systems](https://developer.valvesoftware.com/wiki/Particle_System_Overview). Each cannon can (and now does) have a different trail of particles.
	- This may make it easier to identify the locations of artillery tanks, and notice incoming artillery shells.
- Large rework of the vehicle heat mechanics
	- Added a fourth "Overheat" heat region.
		- Now there is "Low" (Green), "Medium" (Yellow), "High" (Orange), and "Overheat" (Red)
	- The portion of the heat bar that is not filled will still be displayed, but in a way more muted color.
	- The positions of the various heat regions can be defined per-engine.
	- When a weapon cannot fire due to overheating, the ammo indicator for that weapon will turn red. 
		- This was already in the code, but the definition of overheating used was incorrect so this condition was never actually triggered.
	- Engines will now begin stalling at the High region, and completely stall at the Overheat region.
	- Weapons can have a "Critical Heat Zone". When a weapon is fired while the vehicle is in this zone or above, then it will fire a crit.
		- Crit shells can have a different firing sound, impact sound, and trail particles.
		- Crit shells do increased damage
		- Only the Plasma cannon currently uses this feature, and likely only the plasma weapons will use this mechanic.
		- Only shells have crits implemented. If this idea is kept, then we'd want to implement the same for MGs, missiles, and grenades.
	- Due to simplifications of the engine stall code, the "Heat Stall Penalty" value on engines now indicates the maximum amount the throttle can be reduced to via engine overheating, instead of the square root of the maximum amount the throttle can be reduced to via engine overheating.
- Added an additional info panel to the vehicle HUD
	- This panel is displayed to players currently inside a tank
	- The panel shows the following information, from left to right:
		- The armor the vehicle has equipped
		- The engine the vehicle has equipped
		- The current number of passengers, out of the vehicle's total capacity
		- Whether the vehicle will not detonate mines (i.e., the driver or a passenger has the Defuse skill)
		- Whether the vehicle has a spawn point
- Added Pykrete Armor
	- Pykrete armor is made of ice reinforced with complex hydrocarbon chains.
	- It uses ambient humidity to slowly regenerate when vehicle heat is in the low region, but melts faster in higher heat regions. This introduces a new melting/regeneration mechanic to the game.
- Research now drains resources over time, instead of spending all of the resources up-front.
	- Commanders can pause and resume research at any time.
	- If there is insufficient resources for research to continue, then research is paused automatically. 
		- The entire team will hear the "Insufficient Resources" sound clip.
	- When research is complete, the entire team (and all spectators) will hear the "Research is now complete" sound effect, instead of just the commander.
	- Added a new mapmaking entity <code>emp_logic_resource_drain</code> to allow mapmakers to specify their own similar resource drains.
- Improved the resources HUD display. The resource total and income are now displayed more accurately than before.
	- Resource total updates more frequently, to better reflect the actual value. Previously it was tied to a timer.
	- Resource income now displays all manual adjustments to income, not just income from refineries. This should cover all gains/losses but to list some examples it includes resource adjustments from vehicle purchases, vehicle carcass recycling and building purchases/refunds.
	- Recurring resource income is now displayed alongside the dynamic income, this figure excludes manual adjustments and resource drains. Essentially, this displays income from recurring sources, for example refineries.
- Engineer and Commander radars now also spot fully-built enemy buildings, in addition to enemy vehicles.
- Added additional HUD icons for certain F-menu requests.
- Added additional cancellation and suppression criteria for certain F-menu requests.
	- Notably, requests for ammo, health, and repairs are automatically cancelled as soon as any health or ammo is recieved, as appropriate.
- Added new listener mapmaking entities, <code>emp_logic_resource_listener</code>, <code>emp_logic_ticket_listener</code>, and <code>emp_logic_research_listener</code>. 
- Added a sound effect that plays when a tank loads ammo.
- Pressing the suicide hotkey (delete by default) while already dead force-kills you, preventing engineers from reviving you.
- The debug console command <code>emp_debug_spawn_shell</code> now has three parameters:
	- 1: The weapon index of the shell to spawn
	- 2: The number of shells to spawn (between 1 and 128)
	- 3: Whether or not the shell is a crit shell.
- Commanders can now see player request icons from further away, especially requests for commander attention.
	- This distance is 12k units for commander attention requests and 6k units for other requests
	- For comparison, requests are normally 3k units and revive icons 4k units
## Bugfixes
- The C++ code for the mini-map has been extensively refactored. This update resolves several longstanding issues and improves maintainability, making it easier for developers to add new features and enhancements.
- Fixed a bug causing homing missiles to fire without any spread when fired without entering missile lock.
- Fixed a crash involving the vehicle info HUD element.
- Fixed a bug where reviving in water would cause the player to appear far beneath the surface.
- Fixed a bug where players changing teams to spectator while in a vehicle retain collision.
- Fixed some issues with the method in which tips were selected to be displayed on the loading screen.

## Script/Game Balance

### Buildings
- Armory
	- Reduced Carcass Removal Time from 30 to 10
- Barracks
	- Reduced Carcass Removal Time from 30 to 20
- Radar
	- Reduced Carcass Removal Time from 30 to 15
- Repair Pad
	- Reduced Carcass Removal Time from 30 to 15

### Research
- All research costs have been divided by 60, to account for the change from up-front costs to res/second costs.
- Added a research item for APC spawn points.
	- Costs 4 resources per second for 120 seconds. (480 resources in total.)
- Added a research item for Pykrete Armor in the Chemistry tree within Improved Heat Transfer Fluids, next to Advanced Coolant Engine.
- APC Chassis is researched by default
- The Homing Missiles research now unlocks the 2-slot homing missile instead of the 3-slot homing missile
- Re-enabled research for Salvo Homing Missiles and TOW Guided Missiles
- Nuclear Warhead
	- Increased research cost from 4 to 5 (Total cost 1200)
	- Increased research time from 180 to 240

### Infantry Weapons
- NF Heavy Carbine (SMG3)
	- Improved Overall Weapon Spread
	- Increased damage per bullet from 27 to 37
	- Increased Time between shoots from 0.12 to 0.20
	- Increased minimal damage per bullet from 13 to 18
	- Decreased clip size from 20 to 12
		- Also adjusted spawn/max ammo counts - engineer spawns with 4 clips and scout spawns with 5 clips. (Without ammo increase skill.)

### Vehicle Chassis
- NF & BE APC
	- Increased available weight from 235 to 265

### Vehicle Armors
- Capacitive Armor
	- Buff
		- Decreased Cost per plate from 20 to 18
		- Increased Health per plate from 80 to 110
		- Decreased Damage To Heat Absorbed from 0.1 to 0.05
	- Nerf
		- Increased Weight per plate from 15 to 18
		- Added Speed To Damage Modifier 0.000035
		- Decreased Infantry Grenade Resist from 0.55 to 0.35
		- Decreased Infantry Mine Resist from 0.55 to 0.50
		- Decreased Infantry Missile Resist from 0.40 to 0.20
		- Decreased Infantry Mortar Resist from 0.40 to 0.20
		- Decreased Infantry Explosive Sticky Resist from 0.25 to 0.20
		- Decreased Infantry Sticky Stun Resist from 0.25 to 0.15
		- Decreased Squad Arty Resist from 0.55 to 0.40
- Composite
	- Increase Sticky Bomb Resistance from -0.716 to -0.6

### Vehicle Engines
- All Chassis
	- Increased Heat Dissipation for Advanced Coolant Engine by 1

### Vehicle Weapons
- Shells and missiles now use uniform circular distribution when applying spread instead of bounded uniform distribution.
	- All this means is that spread is applied using a radius around the crosshair instead of using random min/max bounds. (Circular distribution instead of square.)
- Plasma Cannon
	- Decreased damage from 84 to 60
	- Now fires 2x damage crit shells when in the high (orange) heat region or above
- Salvo Homing Missiles
	- Increased cost from 105 to 150
	- Increased clip size from 4 to 10
	- Increased reload time from 3.75 to 8
	- Increased missile lock on range from 5000 to 8000
	- Decreased lock on time from 0.6 to 0.5
	- Decreased lock on radius from 0.35 to 0.2
	- Decreased lock on range modifier from 0.00040 to 0.00025
	- Decreased damage from 40 to 28
	- Increased Heat from 3 to 5
	- Decreased weight from 100 to 80
	- Increased Explosion range from 80 to 150
- Homing Missiles (2-slot)
	- Increased cost from 80 to 95
	- Decreased missile Speed from 2500 to 2300
	- Decreased weight from 70 to 60
- TOW Guided Missiles
	- Increased cost from 135 to 150
	- Increased Missile speed from 2100 to 2300
	- Increased Missile Range from 6500 to 8000
	- Increased clip size from 5 to 6
	- Increased Explosion Radius from 115 to 150
	- Decreased Cycle Time from 1.3 to 1.25
- Biological Cannon
	- Increased Damage from 80 to 90
	- Reduced Biological Damage from 10 to 5
- Biological Missile Launcher
	- Increased Damage from 50 to 60
	- Reduced Biological Damage from 10 to 5
- Homing Missile Launcher
	- Increased Lock On Radius from 0.1 to 0.2
	- Reduced Lock On Range Multiplier from 0.00025 to 0.0001875
		- Lock On time increased from between 0.5 to 2.5 seconds to between 0.5 to 2 (up to 40% faster)
- Biological Grenade Launcher
	- Reduced Cycle Time from 2 to 1.6
	- Increased Clip Size from 6 to 8
	- Reduced Total Ammo Clips from 5 to 4
	- Reduced Vehicle Biological Damage from 10 to 5
	- Increased Vehicle Bio Time from 4 to 5
- Medium Artillery Cannon
	- Increased Projectile Spread from 0.001 to 0.25
- High-Explosive Artillery Cannon
	- Increased Projectile Spread from 0.001 to 0.30
- Ranged Artillery Cannon
	- Increased Projectile Spread from 0.001 to 0.15

## Other changes 

- Several unused features have been removed:
	- Research can no longer upgrade ammo damage.
	- Vehicle weapons can no longer be "disabled", and research cannot disable vehicle weapons.
	- Servers can no longer disable vehicle horns with the <code>emp_sv_vehicle_allow_horns</code> cvar
- Increased the default value of the <code>emp_sv_vehicle_fadeout_time</code> cvar from 30 seconds to 180 seconds.
- Increased the default value of the <code>emp_sv_vehicle_fadeout_time_partial</code> cvar from 30 seconds to 60 seconds.
- We did a large refactor to the minimap code. You shouldn't notice any huge changes, but the scaling might be slightly off from what it was before. This can be adjusted with the <code>emp_map_size</code> cvar.
- Removed some less useful statistics from the vehicle preview in the vehicle creation panel.


