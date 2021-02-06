---
title: Empires Mod 2.30.8 Released!
author: Smithy
date: "2021-02-06"
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.30.8 which is live on Steam right now! 

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! https://discord.gg/EXwY2X7

Changelog:

## Maps / Level design 

- Moved all of the tool textures into the correct folder. (materials/common/tools -> materials/tools)
	- The simple reason for this is that Empires was not overriding the HL2 textures, which causes duplicates to appear in the menus.
	- Mappers will need to use the texture replace feature in hammer to point to the new location before compiling.

### Mvalley

- Re-added high ground areas back into play. (Removed all clip brushes and tweaked the terrain to allow access again.)
- Fixed some texture misalignment issues.
- Fixed the dirt road overlays not being applied to the displacements properly. (Some of them were only showing part of the overlay, example was north under the bridge)
- Fixed the 3d skybox fog not matching the color of the fog in the playable area.
- Fixed a hole in a displacement (Coordinate A3)

### Crossroads

- Improved optimization, specifically to fix issues with middle always being rendered regardless of where you are on the map.
- Standardized critical entity names to match other official maps. (An example is emp_info_params being named inf_params for easy manipulation by developers)
- Reduced HDR bloom scale.
- Fixed a lot of texture misalignment issues.
- Fixed some lighting bugs. (Including smoothing group issues)
- Changed middle to remove access to the top of the towers.


## Script/Game Balance 

- Lobbing/Rolling grenades now removes scout hide.
- Slight improvement to steering at high speeds on all vehicles.
	- Added two new variables "Slow Car Speed" & "Fast Car Speed" to vehicle_engines.txt to allow Empires' vehicle engines to alter the steering start/end interpolation.

### Infantry

- Scout no longer has access to Seismic Grenade.

### Infantry Weapons

- NF .50Cal Rifle
	- Reduced recoil slightly and re-enabled iron-sight recoil reduction.
	
### Buildings

- Armory
	- Increased cost from 75 to 100.
- Walls
	- Decreased Infantry Sticky Resist from 0.94 to 0.916.
		- It increases stickies damage to walls from 18 to 25.
	- Decreased Explosive Grenades Resist from 0.94 to 0.925
		- It increases Grenade Launcher damage to walls from 4 to 6.
		- It increases High Explosive Grenade Launcher damage to walls from 6 to 8
		
### Vehicle Weapons

- Machine Guns
	- Plasma Machine Gun
		- Increased Reload Time from 4 to 4.5.
		- Increased Clip Size from 30 to 35.
	- Plasma Heavy Machine Gun
		- Increased Reload Time from 3.5 to 5.
		- Increased Clip Size from 30 to 40.
	- Depleted Uranium Heavy Machine Gun
		- Decreased Reload Time from 5 to 4.5.
- Grenade Launchers
	- Grenade Launcher
		- Increased Gravity from 0.92 to 1.
		- Increased Grenade Timer from 3 to 4.
	- High-Explosive Grenade Launcher
		- Increased Gravity from 0.88 to 1.
		
### Infantry Resists

- Grenadier
	- Reduced Explosive Bullet Resist from 0.7 to 0.55
	- Reduced AP Bullet Resist from 0.3 to 0.
	- Reduced Bullet Resist from 0.1 to 0. (Affects vehicle bullets only.)
- Rifleman
	- Reduced Explosive Bullet Resist from 0.5 to 0.4.
	- Reduced AP Bullet Resist from 0.3 to 0.
- Scout
	- Reduced Bullet Resist from 0.35 to 0. (Affects vehicle bullets only.)
	- Reduced AP Bullet Resist from 0.3 to 0.
- Engineer
	- Reduced Bullet Resist from 0.1 to 0. (Affects vehicle bullets only.)
	- Reduced AP Bullet Resist from 0.3 to 0.
	
	
	