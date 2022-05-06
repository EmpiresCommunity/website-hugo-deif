---
title: Empires Mod 2.34.1 Released!
author: Smithy
date: "2022-01-16"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.34.1 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! https://discord.gg/EXwY2X7

Changelog:

## Features

- Added cvar "emp_sv_drop_cooked_grenades", this is disabled by default until some gameplay testing can be conducted and feedback gathered.
	- Causes grenades to drop when players die if they had already pulled the pin out. (Excluding mines)


## Bug fixes

- Fixed an issue with e-repair preventing mines from being defused inside a damaged friendly building.
- Fixed an issue that was preventing wall gibs from spawning when destroyed. This was caused by a bug fix last patch.
- Fixed an issue that prevented the commander wall limit from functioning correctly.
- Fixed an bug relating to removal of attack targets on a player entering command view or a player entering scout hide. Both actions now remove targets instantly.
- Fixed some issues with how mines are triggered/detonated. Previous to this change, mines would detonate if a vehicle's "absbox" overlapped the mine bounding box. The problem with this is that the "absbox" is calculated every frame and doesn't rotate, it grows in size to encapsulate it's target. This lead to situations where a vehicle that wasn't perfectly aligned to the world origin would have a greater chance of triggering surrounding mines. The new system should be a lot more accurate and result in less frustration/guess work when trying to avoid mines.
- Fixed some issues relating to tanks receiving damage:
	- Physics impact damage on tanks no longer prevents repair stations from repairing your tank. It would often be the case that a small bump when trying to enter the repair station would trigger the repair delay, this damage type is now filtered out of this feature. (For reference the delay is 10 seconds, so this can be quite frustrating for the driver.)
	- Tanks no longer trigger the repair delay if they didn't actually take any damage from the entity trying to damage it. Previous to this change you could use a weapon that doesn't deal damage to delay a tank from repairing. This has long been an issue and the feature should now work as intended. (As an example, bullets can no longer delay a tank trying to use a repair station.)
	- Fixed some issues where damage was being mis-attributed to players with regards to calculating assists/critical assists.
	- Fixed an issue with tank turrets not transferring damage to the hull appropriately.
		- Fixed an issue with tanks taking explosion damage from the turret first, despite the hull being closer; resulting in a damage reduction. This will mostly impact gameplay when explosions occur on the top surface of tanks, they will now deal the expected amount of damage without a drop in damage. Explosions now prioritise dealing maximum possible damage in this situation, in terms of possible falloff reductions etc. This is likely going to have a bigger impact on chassis where the turret is often in the line of sight of explosions; for example NF light tanks, where the turret is easier to hit because it's shorter.
	- Removed some code which was trying to prevent two sets of the same damage applying to vehicles per frame, this was added to prevent a vehicle's turret from transferring duplicate damage. This was crudely implemented and was preventing damage from occurring in certain situations.


## Script/Game Balance

### Command Vehicle

- Reduced the Heat to Damage Absorbed on the Command Vehicle's armor by half.
- Increased Max Speed from 25 to 30 mph.

### General Balance Changes

- Removed the hard-coded variable damage on mines.
	- It was previously written in code that mines would deal double damage if triggered by a vehicle. This has been removed because the damage resistance system should have been utilized to ensure that everything in the explosion radius was receiving the expected amount of damage. With the old method, it meant that everything in the explosion radius would receive double damage if the mine had been detonated by a vehicle.
- Removed the hard-coded variable damage on explosive sticky grenades.
	- It was previously written in code that sticky grenades would deal double damage to all vehicles except the command vehicle. Again, this has been removed because the damage resistance system should have been utilized to ensure that everything in the explosion radius was receiving the expected amount of damage. With the old method, it meant that everything in the explosion radius would receive double damage if the grenade had been attached to a vehicle (Excluding CV).
	- Damage resistances have been adjusted to compensate in the scripts.
- Added a new script variable for use with vehicle armors "Flat Damage Reduction". This change is to give reactive more of a unique identity, being quite resistant early game but being less effective as the game progresses and the enemy unlocks stronger weapons.
	- Reactive now has a flat damage reduction of 5. (Resistances have been adjusted to ensure all anti-vehicle machine guns deal damage.)
	- Reactive now has 120 HP per plate instead of 135.
	- Composite now has a flat damage reduction of 1.


