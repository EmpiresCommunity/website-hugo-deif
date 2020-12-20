---
title: Empires Mod 2.30.3 Released!
author: Smithy
date: "2020-12-20"
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.30.3 which is live on Steam right now! 

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! https://discord.gg/EXwY2X7

Changelog:

## Bug fixes
- Fixed a bug where infantry weapon spread wasn't decrementing when going to iron-sights.
- Fixed a bug with squad aura effects not being reapplied properly. (Most noticeable with squad accuracy upgrade as it wasn't consistently being applied, using cl_dynamiccrosshair it appeared to cause spread to pulse)
- Fixed an issue where players would appear to be hovering when entering a vehicle while in mid air. (The sitting animation wasn't being set properly)
- Fixed an issue with the scout rifle sway being able to be disabled if the player turned off prediction. (Sway speed will be slightly different than before given that it had to be re-implemented using a different method.)
- Fixed the "Grenade Timer" script variable not being set for vehicle grenades, previously they were hard-coded to a 3 second detonation time.
- Fixed an issue with "BioResist" script property not being set properly for Bio DoT damage on players. (Bio damage was using the wrong resist type)
- Fixed some issues with the buildings script file which caused issues with the commander selection box display. (When selecting some engineer build-ables the selection box size was wrong or missing.)
- Fixed an issue with concussion grenades being able to damage vehicles.

## Script/Game Balance
- Tanks are no longer able to fire if their cannon is penetrating an object. (The exception to this is other vehicles/players)
- Changed BEHR iron-sight zoom to match the other rifles, previously it had less zoom than the other rifles in the game.
- Scout rifle sway is now affected by the accuracy upgrade skill. (At first this will be a 25% sway reduction, this might be change based in the future if it needs balancing)
- **Increased** explosion force to vehicles slightly as the previous change reduced it too much.
- **Increased** APC cost by **50**
- **Reduced** all turret costs by **25**
- BE Heavy Rifle
	- **Reduced** recoil for all stances
- BE Assault Rifle
	- **Reduced** recoil for all stances
	- **Reduced** base spread and spread increment, slightly slower spread recovery for all stances
	- **Increased** maximum damage from **20** to **22**
	- **Increased** minimum damage from **10** to **11**
- BE .44 Pistol
	- Firing cycle time **increased** from **0.25** to **0.3**
- BE Machine Pistol
	- **Increased** firing speed
	- **Reduced** Spread Increment
	- Clip size **reduced** from **18** to **15**
- NF 50cal
	- Damage **reduced** from **43** to **40**
- NF Heavy Carbine SMG
	- Melee cycle time **reduced** from **0.55** to **0.45**
- All SMGs (excluding SMG3)
	- Melee damage **reduced** from **70** to **50**
- All Armors
	- **Increased** Seismic Grenade Resist from **0.95** to **1**
	- **Increased** Concussion Grenade Resist from **0** to **1**
- Deflective Armor
	- **Increased** Biological Damage Multiplier from **0.75** to **1**
	- Reduced damage resistances from **0.1** to **0**
- Absorbant Armor
	- **Increased** Infantry Missile Resistance from **0** to **0.1**
	- **Increased** Plasma Resistance from **0** to **0.1**
	- **Decreased** AP Bullet and Explosive Bullet Resistances from **0.15** to **0.1**


