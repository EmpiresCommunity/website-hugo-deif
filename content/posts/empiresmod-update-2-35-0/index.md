---
title: Empires Mod 2.35.0 Released!
author: Smithy
date: "2023-06-18"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.35.0 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

Changelog:

## Features

- Added a screen overlay that is applied when players are afflicted with the damage over time effect of biological weapons.
- Added tips to the loading screen. (Similar to when the game was on the 2007 version of the engine)
- Changed the old scout hide screen darkening to use a screen overlay that is essentially a vignette effect instead of darkening the whole screen.


## Bug fixes

- Fixed vehicle spawners autorespawn keyvalue not working as intended. Vehicles would never respawn if the previous vehicle carcass had been recycled.
- Fixed an issue causing vehicles to be sent less throttle input than expected. The expected multiplier input to the physics engine was 1.0 (MAX), actual input was 0.92 because of a bad constant hardcoded in via joystick code. (This also affects keyboard input.)
	- This means vehicles will effectively have 8% increased throttle. This is unlikely to have a big impact on game balance.
- Fixed a bug causing non-solid emp_engineer_map_brush / emp_engineer_map_object entities to receive damage.
- Concussion grenades now only blind alive players.
- Various bug fixes to env_projectedtexture
	- Also increased limit of env_projectedtexture entities from 1 per PVS to 9.
- Fixed a bug preventing the "raise on build" functionality of emp_eng_map_brush & emp_eng_map_model entities from working.
- Fixed a bug involving turrets spawned using the point_template. Turrets would try to upgrade beyond level 3 and would break completely.
- Fixed a bug where you would get the Grenadier RPG view model stuck on screen while in the driver seat of vehicles. This happened when placing your last mine, causing the active weapon to switch right before entering the driver seat.
- Fixed a bug where the repair bar would not display if an entity was parented to another entity.
- Fixed incorrect function assignment in code for emp_params entity - GetBETickets, GetNFResources & GetBEResources would call the incorrect functions; these are now fixed.
- Fixed a bug causing blood spatter decals to spawn when hit by concussion grenades.
- Fixed various console errors.


## Script/Game Balance

- Increased the radius of the engineer radar from 2000 -> 4000 units.
- Reduced the radius of the scout's auto-spotting from 5000 -> 3000 units.

### Infantry Weapons

- Concussion grenades
	- Concussion grenades no longer disable turrets if the damage dealt is lower than 10.
	- The temporary disabled state applied to turrets is now removable by repairing the turret.
		- Repairing 25 units of health or repairing a turret to full health will now end the disabled state early.
	- Reduced the damage from 40 to 35.
	- Reduced the explosion radius from 400 to 350.
	- Reduced the explosion falloff radius from 200 to 175.

### Vehicle Armors

- Removed the 2.5 degree dead-zone from armors using the Angle Modifier script variable (reverted to legacy behavior).
	- This was added back in 2.33.2. It was added to reduce the effectiveness of the Angle Modifier trait if players landed their hits correctly. It is being reverted because it is negatively affecting the identity of 'Deflective' armor, causing it to feel a bit weak.
- Regenerative
	- Increased Health from 75 to 80
- Reactive
	- Reduced Health from 110 to 100

### Vehicle Engines

- All Chassis
	- 3 Phase Motor
		- Increased Heat Output at Idle from 1 to 2
	- Fission Reactor
		- Decreased Heat Output at Max from -3 to -5
	- Gas Turbine
		- Increased Heat Capacity from 100 to 150
		- Increased Stalled Horsepower from from 10% to 50%
		- Increased Cost by 50%


## Maps

### Eastborough

- Ticket issues resolved.
- Map description has been updated/fixed.
- Slight adjustments to one of the flags.
- Changed the lighting and atmosphere, added weather effects.

### Escort

- 4x damage multiplier on the second flag's build-able bridge is now 2x - Respawn timer is unchanged. (60 seconds)
- Tweaked displacements around the last flag to hopefully prevent Brenodi being able to access areas they're not supposed to reach.
- Fixed some exploit spots around the first flag by tweaking the player clip brushes.


## Other/Misc

- Change commander alert hotkey to jump to the most recent alert instead of cycling through the onscreen alerts.
	- This has been changed because new alerts weren't resetting the cycle position and the hot key was confusing to use. It now mirrors behavior typical to other RTS games.
- Updated the Empires FGD with various fixes and additions.
	- Vehicle chassis/engine/weapon ID's have been updated for vehicle spawner entities to work as expected.
	- Added various autovisgroup definitions for ease of hiding/selecting entities in hammer.
	- Added a new keyvalue to vehicle spawners to add a delay when respawning vehicles after a previously spawned vehicle is removed.
	- Updated and improved the FGD definition for env_projectedtexture.
- Reduced screen shake duration caused by building explosions.


