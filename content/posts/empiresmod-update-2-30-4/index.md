---
title: Empires Mod 2.30.4 Released!
author: Smithy
date: "2021-01-22"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.30.4 which is live on Steam right now! 

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

# Changelog:

## Bug fixes

- Fixed some bugs relating to the recent additions to the tank cannon penetration checks (System that prevents firing when cannon is inside something other than vehicles/players)
- Fixed some mini-map icons appearing for the wrong team. (An example is being able to see the enemy squad leader icon in some circumstances)
- Fixed vehicle exits being able to be blocked by players on your team
- Fixed a bug with squad aura being applied to squad leaders 100% of the time
- Fixed various possible crashes relating to weapons (and 1 with wall placement)
- Fixed a networking issue causing the player icon on the mini-map not updating when swapping the revive skill on/off.


## Other changes

- Changed the ordering of BE rifleman's pistols to match the other classes in the class menu.
- Enhanced senses is now disabled if the player dies, previously a dead player could continue to receive extra info.
- Removed request/revive icons from drawing above yourself and on your own mini-map icon
- Repair icon on the crosshair now only displays if the engineer is actually in range to build, rather than building health display range.
- Squad aura icon now only displays if the local player is actually receiving the benefits of the aura, previously it only checked if the player was in range but that didn't mean they were receiving the aura. (If they were dead for example)


## Script/Game Balance 

### Changes to homing/guided

- Added a max distance from player that RPG missiles will continue to guide, after this distance they switch to dumb-fire. (15000 units)
- Removed vehicle missile guidance from seat 2, this didn't make any sense to keep. Missiles should only by guided by the driver if he is in seat 1.
- Changed RPG missile guidance to work slightly differently, this should fix situations where just pressing the attack button throws the missile off-center.
- Changed vehicle guided missiles to be influenced by vehicle turret's rotation rather than using a "Laser guided" homing effect.

### Infantry Weapons

- SMG1/2 Melee damage change reverted (Was 70, changed to 50, now back to 70 again)
- BE Pistol 2 Headshot multiplier increased from 2x -> 2.5x
- SMG1 spread increment decreased (33% standing, 50% crouched, 65% prone)
- SMG1 damage increased from 17 -> 18
- Improved BEAR - Base spread improved by 25%, Ironsight spread multiplier decreased from 0.83 to 0.6
- Tweaked scout sway values in reflection of last update
	- Base Sway pattern size reduced very slightly
	- Sway speed is slightly faster
	- Maximum sway speed increased (This is mostly for jumping/sprinting to cause more inaccuracy)
	- Accuracy upgrade sway reduction changed from 25% to 10% (25% proved to be too much so dropping this significantly)
	- Squad Accuracy Aura now affects scout sway, reduces sway by an additional 10% (This will rarely be used, however for consistency with the aura affecting other weapons this has been added.)
	
### Research

- Advanced Machining
	- Changed Cost from 240 to 360
	- Changed Time from 60 to 90
- Composite
	- Changed Cost from 360 to 480
	- Changed Time from 90 to 120
- Gas Turbine
	- Changed Cost from 240 to 360
	- Changed Time from 60 to 90
	
### Engines

- APC
	- Gas Turbine
		- Changed Cost from 20 to 40
		- Changed Heat Output at Idle from 3 to 2
- LT/AFV
	- Gas Turbine
		- Changed Cost from 30 to 50
		- Changed Heat Output at Idle from 3 to 2
- Medium
	- Gas Turbine
		- Changed Cost from 40 to 60
		- Changed Heat Output at Idle from 3 to 2
- Heavy
	- Gas Turbine
		- Changed Cost from 60 to 100
		- Changed Heat Output at Idle from 3 to 2
- Artillery
	- Gas Turbine
		- Changed Cost from 60 to 100
		- Changed Heat Output at Idle from 3 to 2

### Vehicle handling

- Changed skidallow from 1 to 0 on all tracked vehicles


