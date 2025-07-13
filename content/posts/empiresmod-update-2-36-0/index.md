---
title: Empires Mod 2.36.0 Released!
author: Smithy
date: "2024-02-17"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.36.0 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

# Changelog:

## Features
- Added angle snapping to commander building placement. This shares a key bind with multi-unit selection. (Default key is shift.)
- Added firing sounds to MG turrets.

### The vehicle health HUD has been improved:
- The health of each armor plate and hull are overlaid as a number. This feature can be enabled in the advanced options section. (Default is off)
- Each armor plate is no longer drawn as a sequence of overlapping lines. They're now drawn correctly as polygons.
- The corners of armor plates no longer have large gaps. Armor plates are drawn as trapezoids with a defined gap between them, resulting in the armor display looking more rectangular overall.
- Armor plates that are missing are now drawn as a grey outlined shape. This should help to communicate to players that there are plates that can be repaired.
- Armor plates (or hull) that are affected by biological DoT are now drawn as a darker shade of the current health color and if HP text is enabled, the text will turn green.
- The following console variables have been added to customize the vehicle HUD:
	- '''emp_hud_vehicle_show_health''': Controls whether to display the amount of armor and hull health numerically in the vehicle HUD.
	- '''emp_hud_vehicle_armor_offset''': How many pixels to offset the armor plates from the chassis in the vehicle HUD.
	- '''emp_hud_vehicle_armor_thickness''': How many pixels thick to draw the armor plates in the vehicle HUD.
	- '''emp_hud_vehicle_armor_proportional''': How much the thickness of armor plates in the vehicle HUD is affected by the maximum health of each plate, with 50 hp/plate as a baseline.
	- '''emp_hud_vehicle_armor_spacing''': How many pixels thick the gap is between the armor plates in the vehicle HUD.
	- '''emp_hud_vehicle_armor_spacing_corner''': How many pixels thick the gap is between the corners of the armor plates in the vehicle HUD.
	- '''emp_hud_vehicle_chassis_scale''': 

### Added emp_logic_playercount_listener entity.
- This entity fires outputs when the player count changes. You can specify whether to search for Brenodi or Northern Faction players or both, and whether to check for just alive players or all players.
- More information is available on the [https://developer.valvesoftware.com/wiki/Emp_logic_playercount_listener Valve Developer Wiki].
- This release includes <code>emp_variable_playercount_template.vmf</code>, an example map to show how you might use this feature to dynamically open and close map lanes as player count changes.

### Added outputs to emp_params on almost every game phase transition:
- OnPhaseBeginTactics
	- Note: Since the tactics phase is not currently implemented, this fires at the same time as OnPhaseBeginGame
- OnPhaseBeginWait
- OnPhaseBeginGame
- OnPhaseBeginInfSuddenDeath
- OnPhaseBeginCVSuddenDeath
- OnGameEnd
- OnGameOutcomeNFWin
- OnGameOutcomeNFLose
- OnGameOutcomeBEWin
- OnGameOutcomeBELose

### Added the following inputs and outputs to all buildings: (Used by level designers.)
- Inputs
	- SetHealth : "Sets the health of the building, clamped between 0 and the building's maximum health."
	- Destroy : "Set the health of the building to 0."
	- RecycleStart : "Begin the recycle process."
	- RecycleStartDuration : "Begin the recycle process, with the countdown set to the given number of seconds."
	- RecycleCancel : "Cancel the recycling process, returning the building to a functional state."
	- SabotageStart : "Mark this building as sabotaged. If the activtor is a player, give them points for it."
	- SabotageEnd : "Mark this building as no longer sabotaged."
- Outputs
	- OnBuilt : "Fired when this building is fully built."
	- OnNFBuilt : "Fired when this building is fully built by the Northern Faction."
	- OnImpBuilt : "Fired when this building is fully built by the Brenodi Empire."
	- OnKill : "Fired when this building is destroyed."
	- OnSpotted : "Fired when this building is spotted by an enemy using any method. The spotter is the activator."
	- OnSpottedBinoculars : "Fired when this building is spotted by an enemy using the binoculars. The spotter is the activator."
	- OnSabotageStart : "Fired when this building has become sabotaged. The saboteur is the activator."
	- OnSabotageEnd : "Fired when this building is repaired."
	- OnRecycleStart : "Fired when a commander has started the recycling process on this building."
	- OnRecycleCancel : "Fired when a commander has canceled the recycling process on this building."
	- OnRecycleComplete : "Fired when this building has been recycled."
	- There are also two additional outputs for the Radar, Engineer Radar, and Engineer Camera that fire whenever an entity is detected.
		- OnVehicleSpotted, OnVehicleFirstSpotted, OnPlayerSpotted, OnPlayerFirstSpotted

## Bug fixes
- Applied a potential fix for player muting via the scoreboard. When the server reaches enough players, player muting would stop working as intended.
- Fixed squad heal not removing Bio damage over time effect properly.
- Fixed unintended behaviour where the biological damage over time effect wouldn't extend it's duration if it was applied to vehicle armor by the same weapon repeatedly.
- Fixed an issue where squad recon would spot squad hidden players for longer than intended.
- Fixed various issues where the game's code would skip over the last player when processing through all players in a full server. Unknown what bugs this may have caused.
- Changed building smoke to always emit fire when the building is destroyed, instead of sometimes showing unbuilt/sabotage smoke.
- Neutral tank turning now rotates around the tank's local axis instead of world space. This was causing strange behaviour when driving up/down slopes.
	- Neutral turn is no longer unconstrained in applying angular velocity. Prior to this version, angular velocity was set directly; instead of being applied as an angular force impacting the angular velocity. This will mean that tanks are no longer able to rotate beyond the capability of the force being applied.
- Fixed the emp_infantry_restrict team filters being inverted.
- 3x Crashes have been fixed.
- Fixed some minor issues in the vehicle HUD. For example, no longer displaying the armor detection overlay for your own vehicle or dead vehicles.
- Map info script parsing system has been refactored. 
	- All parameters present in the map info file have sensible defaults, allowing a map to be played even if there is no map info file or the client fails to download it.
	- Line breaks can be placed in the objective and description panels using the <code>\n</code> escape sequence.
	- Map info can be reloaded client-side using the mapinfo_flushscript command, though this currently requires the map to be reloaded for the changes to take effect.
- Fixed commander vote count not resetting between rounds.
	- There are still some client-side vote count issues to resolve but these will be addressed in a future version as it requires large changes to rewrite the client-side vote count system.
- Fixed a bug where spotting a building with regular spotting would override the longer spotting provided by binoculars.
- The emp_info_params entity inputs SetNFResources and SetBEResources now function correctly. Previously, they would double the current resource value and then subtract the desired value.
- The vehicle weapon HUD now displays properly when using a vehicle equipped with weapons that are not researched. Previously, unresearched weapons would not show up in the HUD. This was only an issue for maps that spawned in vehicles.

## Other Changes
- Added prop_sphere to the FGD and updated code to allow a radius to be set.
- Added various team colored developer textures for use when designing maps. ('''materials/dev''' directory)
- Added the startResearched research script variable. Researches that have startResearched = 1 will already be researched when the game starts (if this is the correct team).
	- This allows specific maps to use the emp_sv_unresearch_item command to set the starting chassis as restricted (Jeep/APC/Light tank/AFV).
	- If there are no chassis available the vehicle menu will not open when players attempt to open it.
- Changed all turret/camera/radar models to use metal surface property instead of default.
- Lobby server auto-connect has been disabled by default. Auto-connect to lobby can be re-enabled by adding -lobby to the launch options within Steam.

### Changes to team joining functionality

- The code that decides whether a player can join a team has been reworked
	- The skill based auto-balance system which decided how players are put into teams has been disabled.
		- Removed convars 'mp_autoteambalance', 'mp_autoteambalance_smart', and 'mp_autoteambalance_skilldifference' as these were used by this system.
	- Auto-assign has been reverted to a random selection of the available teams.
- Added the emp_sv_forceteam convar, which will force all players to join either BE or NF if enabled.
- Completely rewrote the 'jointeam' console command code.
	- Jointeam respects emp_sv_forceteam, emp_sv_forceautoassign, emp_sv_forcespec, and emp_allowspectators.
- Added convar 'mp_teams_unbalance_limit'
	- This controls the maximum numbers advantage a team can have before players are no longer allowed to join.
	- The default value is 1, which allows each team to have one extra player.
	- Setting this convar to 0 disables the limit.

## Script/Game Balance

### Changes to stamina usage when jumping
Jumping stamina usage has been tweaked so that the stamina requirement to jump is 50% of the actual stamina deduction.  Additionally, stamina upgrade now reduces the amount of stamina deducted per jump by 1/4 instead of 1/3.
- This means a jump spends 20 stamina (roughly displayed as 3 bars), but you can still jump so long as you have 10 stamina (roughly displayed as 1.5 bars) left. With stamina upgrade, each jump will spend 15 stamina instead of 13.3.
- This change was made to make navigating the map less frustrating when out of combat. This should be less punishing when you have completely depleted your stamina, but still enforce the usual restrictions to combining sprinting and jumping while in combat. The values were tweaked to ensure that even with stamina upgrade, you cannot bunny hop when you're out of stamina.

### Vehicle Chassis

- Brenodi Empire Heavy Tank
	- Increased Max Weight from 470 to 490

### Vehicle engines

- Increased 3 Phase engine heat dissipation by 1
- Decreased Advanced coolant engine heat dissipation by 1
- Decreased Fission engine heat dissipation by 0.5 (0.7 for medium tank)

### Vehicle Weapons

- Homing Missile Launcher
	- Reduced Lock On Radius from 0.42 to 0.1
		- It should make it easier to pick which target you're locking, but it also means you have to track it more accurately
	- Increased Lock On Time from 0.3 to 0.5 seconds
	- Increased Lock On Range Modifier from 0.2s/1000u to 0.5/1000u (a wall is 256 units)
	- Reduced Missile range from 8000 to 7000
	- Reduced Turning Ability from 3.15 to 3.0
	- Increased Cost from 100 to 150
- Nuclear Missile Launcher
	- Increase Cost from 200 to 300
- Biological Missile Launcher
	- Increased Player Bio Damage from 3 to 5
	- Increased Vehicle Bio Damage from 8 to 10
- High-Explosive Cannon
	- Increased Cost from 70 to 90
	- Reduced Damage from 75 to 70
- Upgraded Missile Launcher
	- Increased Cost from 70 to 80
- Biological Cannon
	- Increased Weight from 80 to 120
	- Increased Cost from 100 to 180
	- Increased Cycle Time from 2.25 to 2.5
	- Increased Heat from 15 to 20
	- Vehicle Biological Effect Properties
		- Damage: 10
		- Duration: 10
		- Interval: 0.5
		- Total Damage: 200
	- Infantry Biological Effect Properties
		- Damage: 5
		- Duration 10
		- Interval: 0.5
		- Total Damage: 100
- Plasma Cannon
	- Increased Cost from 110 to 140
	- Increased Weight from 80 to 90
	- Increased Heat to Target from 10 to 12
- Railgun
	- Increased Cost from 120 to 150
	- Increased Weight from 80 to 90
	- Increased Damage from 120 to 130
- Depleted Uranium Machine Gun
	- Reduced Cost from 60 to 50
- High-Explosive Machine Gun
	- Reduced Cost from 70 to 60
- Plasma Heavy Machine Gun
	- Increased Cost from 110 to 120
	- Increased Weight from 55 to 60
- Biological Machine Gun
	- Increased Player Bio Duration from 1 to 4
	- Increased Vehicle Bio Duration from 1 to 2
- Standard Machine Gun
	- Reduced Cost from 40 to 30
- Chain Gun
	- Reduced Cost from 60 to 45
- Grenade Launcher
	- Reduced Cost from 50 to 40
- High-Explosive Grenade Launcher
	- Increased Cost from 60 to 75
- Small Artillery Cannon
	- Increased Cost from 70 to 90
- Medium Artillery Cannon
	- Increased Cost from 80 to 110
- High Explosive Artillery
	- Increased Cost from 120 to 170
- Ranged Artillery Cannon
	- Increased Cost from 130 to 170
- Biological Grenade Launcher
	- Increased Damage from 40 to 60
	- Increased Vehicle Bio Damage from 5 to 10
	- Increased Infantry Bio Duration from 4 to 5

### Vehicle Armors

- Absorbant
	- Reduced Speed to Damage modifier from -0.000112 to -0.00005
	- Increased Health from 70 to 75
- Composite
	- Reduced Speed to Damage modifier from -0.00005 to -0.000025
- Reactive
	- Increased Health from 100 to 120

### Infantry Weapons

- Rifleman
	- Fixed BE's Assault Rifle starting ammo

### Wages

- Defuse
	- Decreased from 5 to 3
- Capturing a flag
	- Increased from 0 to 3
- Destroying an enemy vehicle
	- Increased from 5 to 10

### Structures

- NF/BE Walls
	- Increased Cost from 10 to 15
- Barracks
	- Increased Cost from 200 to 300

## Known Issues

- Turret sounds do not play on clients who are too far away from a firing turret, even if they approach the turret as it is firing.
- In some circumstances, the button to join a team will be selectable when you cannot actually join that team.
	- If mp_teams_unbalance_limit is set to 1, you are on team A, and team B has the same number of players as team A, then the button to join team B will be active, even though you are correctly not allowed to join.