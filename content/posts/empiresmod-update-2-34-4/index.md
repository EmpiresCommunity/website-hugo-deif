---
title: Empires Mod 2.34.4 Released!
author: Smithy
date: "2022-02-26"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.34.4 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

Changelog:

## General changes
- Increased all voice line sound attenuation distance by about 1000 units.
- Removed unnecessary binary files from server packages. (Some client files were being shipped to server packages unnecessarily.)
- Added server commands to limit bunny hopping velocity gain and to enable auto bunny hopping, both are disabled by default. sv_enablebunnyhopping & sv_autobunnyhopping


## Bug fixes
- Fixed a server crash relating to mines not being removed correctly.
- Fixed a few minor issues with the squad aura indicator sometimes showing incorrectly.
- Fixed an issue causing prop_physics_multiplayer entities being non-solid to players.
- Fixed player spawn points being able to be blocked by other players.


## Script/Game Balance
- Scout hide is now removed from players who are reviving or being revived.
- Added functionality for explosions to be blocked by multiple entities.
	- This allows damage to be applied with a system where multiple entities reduce the damage toward 0, instead of everything behind an explosion ray being blocked by the same thing. This should be more dynamic and it does fix some instances where people could potentially abuse flaws in the old system. (Like throwing concussion grenades at your feet, blocking the ray and causing the damage to pass through the walls and deal damage to turrets hidden behind them...)
- Large explosions no longer lose damage if player body parts are blocked, this feature was added in version 2.33.1
	- This means that some weapons will always maintain their damage if the player is in radius and in line of sight to the explosion. (Currently this affects all artillery shells and nuclear missiles.)

### Buildings
- Vehicle Factory
	- Increased Health from 250 to 350
	- Increased Cost from 400 to 500
- Radar
	- Increased Health from 200 to 250

### Infantry Weapons
- Concussion Grenades
	- Increased Max Ammo from 3 to 6.
- A few of the weapons have been rebalanced, see the changes here https://git.empiresmod.com/empires_public/empires_scripts/-/merge_requests/231/diffs?commit_id=506bca8eac8be7900d5c799fce0e9c88e9ff66dd
