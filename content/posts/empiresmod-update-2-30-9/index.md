---
title: Empires Mod 2.30.9 Released!
author: Smithy
date: "2021-02-25"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.30.9 which is live on Steam right now!

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! https://discord.gg/EXwY2X7

Changelog:

## Bug fixes

- Fixed a bug causing localization to fail for vehicle kill-assist strings.
- Fixed a bug causing simple/critical kill-assists to record the wrong damage amount and potentially award the critical assist to the wrong player.
- Fixed a bug where player's would get stuck in ammo/health crates spawned by capturing flags.
	- Crates will now spawn when the spawn location is free from player obstruction.
- Mortar now uses HL2's AR2 reload animation in third person. (It's the closest animation available without additional artist work)
	- Previously the mortar had no 3rd person reload animation so you couldn't tell when people were reloading.
	- It has also been requested that the lines on the bottom/left of the mortar crosshair display be removed, therefore has now been removed.
- Fixed an issue with the glowing mine outline effect causing the screen to go darker. (This was a side effect of the HDR auto-exposure on some maps scaling the lighting down dramatically)
- Fixed a missing texture caused by moving tool textures. "common/tools/toolsblack"
- Changed the collision mesh for the Brenodi Vehicle Factory as there was a possible exploit that would allow access to the top of the building.


## Maps / Level design

### Cyclopean

- The map has been re-compiled with slightly brighter HDR lighting and using slightly brighter HDR skybox textures.


## Script/Game Balance
- Engineer heal rank points are now only awarded when healing damage caused by the enemy team.
- Shells and missiles will now detonate when they hit a player's hit-boxes instead of bounding box.
	- This was likely the expected behaviour but was not already the case.
	- This change is simply to improve the accuracy of these interactions, however, it will be significant in regards to the grenadier class. Player's will need to adapt their aim because they will need to be more precise.
- Weapon bullet spread is now incremented after a bullet is fired instead of before. The original behaviour has been in the game for many years but it caused some issues:
	- Developers couldn't reliably balance weapons for first-shot accuracy because the weapon base spread was always higher than intended because it was tied to spread increment.
- "Heavy Caliber Machine Gun" research has been split into two separate items, one for "Depleted Uranium Rounds" and one for "High Caliber Rounds" (.50Cal)
	- Depleted uranium rounds:
		- Cost to research is 240 resources
		- Time to research is 60 seconds
	- High Caliber Rounds:
		- Cost to research is 180 resources
		- Time to research is 45 seconds
- Added some developer console commands to help scripters working on weapon balance visualize the bullet spread/impacts.
	- sv_showimpacts_duration - FLOAT - "Duration to display impact points used by sv_showimpacts (Min 1/Max 30)"
	- emp_cl_weapon_draw_spreadcone - BOOLEAN - "Draw debug lines to visualise bullet spread cone"
	- emp_cl_weapon_draw_spreadcone_line_multiplier - INTEGER - "Multiplier for how many lines used to draw the cone 4*value (Min 1/Max5)"
	- emp_cl_weapon_draw_spreadcone_line_duration - FLOAT - "How long to display the debug cone (Min 1/Max10)"


