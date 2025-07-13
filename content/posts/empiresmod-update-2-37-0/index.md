---
title: Empires Mod 2.37.0 Released!
author: Smithy
date: "2024-05-26"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.37.0 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

# Changelog:

## Features
- Grenades and mines make sounds when they bounce against surfaces.
- Added armor impact sounds.
	- Distinct sounds play when a vehicle's armor is damaged, a vehicle's hull is damaged, and when a sticky grenade latches to a tank hull.
	- Different armors can have different sounds, though most armors currently do not.
- Enabled several unused NF taunts.
- Updated the commander view's zoom functionality.
	- Added zoom-to-cursor functionality. The camera will zoom towards the cursor position when enabled. An option will be added to the advanced section of the multiplayer settings menu.
	- Camera smoothing has been updated, updated cvars added to control this.
		- emp_comm_zoom_stepsize - Controls how many units to increment/decrement the target zoom amount per scroll.
		- emp_comm_zoom_speed - Original cvar, original values should still work with updated smoothing method.
- Enabled the trigger_portal brush entity.
	- trigger_portal is an brush entity in the Source base code. 
	- It moves touched entity to a destination trigger_portal, preserving the relative position and velocity of the entity.
	- Warning: This entity can cause teleported entities to become stuck or escape the map, and has not extensively tested. Use at your own risk!
- Added team-limiting spawnflags to all trigger bruah entities.


## Bugfixes
- Fixed the game phase material proxy not updating correctly.
- Fixed MG turrets continuing to play the shooting sound effect after game end.
- Fixed spectator HUD not displaying observer target info correctly.
- Added warning message when the vehicle customization menu fails to open because your team has no chassis researched.
- Changes to team physics content masking.


## Script/Game Balance
### Vehicle Weapons
- Guided Missile
	- Increased Maximum Guiding Range from 5500 to 8000
- Homing Missile
	- Increased Maximum Lock On range from 7000 to 8000
- Biological Missile
	- Reduced Bio Duration from 8 to 5s
	
### Vehicle Armors
- Regenerative
	- Reduced Health Regeneration from 4 to 3
	
### Vehicle Engines
- Bio Diesel
	- Reduced Cooling by 0.25


## Other changes 
- Sever operators can now disable the server inactivity timeout by setting emp_sv_inactivity_timeout to 0.
	- If non-zero, the timeout has a minimum of 120 seconds.
- Deprecate the emp_sv_forceteam convar.
	- This functionality has been replaced by the new AllowedTeams field in emp_info_params.
		- Setting AllowedTeams to 0 allows players to join either team. Setting it to 2 or 3 allows player to only join Northern Faction or Brenodi Empire respectively.
		- This function can still be accessed by setting the emp_sv_forceteam convar, but that variable is now deprecated and will not show up in autocomplete.
- Remove remnants of the PushMap setting in emp_params
- Minimap icons will now be revealed to both teams when the game is over.
- When the game ends, the game timer on the HUD will freeze, displaying the final time for that round.
- When creating workshop packages, you can now specify a preview image.
	- This can be done by adding the "Image" "FilePathRelativeToWorkshopItemFolder.jpg" KV pair to the package.txt`


## Known Issues
- Armor impact sounds are often too quiet to be heard well.