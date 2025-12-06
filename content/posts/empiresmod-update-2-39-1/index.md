---
title: Empires Mod 2.39.1 Released!
author: Smithy
date: "2025-12-06"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.39.1 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

# Changelog:
## Features
- Further adjustments to the visibility system introduced in 2.39.0:
	- Commander visibility tweak: Commanders can now see entities within 5000 units of any friendly player, regardless of spotting status. (Also fixes an issue that caused some entities to be hidden from the commander.)
	- Dead player visibility restored: Visibility for dead players has been reverted to the previous behavior, allowing them to see nearby entities. Entities that are visible only to the dead player are not shared to teammates.
	- The mini-map is now disabled for the unassigned team.

## Bugfixes
- Fixed vehicle damage hit-ticks not displaying.

## Script/Game Balance
### Infantry
- Damage resistance against biological damage over time effects have been removed.
	- Grenadier reduced from 0.1 to 0
	- Rifleman reduced from 0.05 to 0
	- Scout reduced from 0.1 to 0

#### Weapons
Rebalanced ammo capacities across all classes to better reflect their combat roles.

**Scout:** Receives additional reserve ammo for extended combat longevity, allowing for sustained engagements while maintaining mobility.
- SMG2 ammo decreased from 200 to 120
- SMG3 ammo decreased from 60 to 42
- BE Pistol 2 ammo decreased from 28 to 21
- NF Shotgun Pistol ammo decreased from 12 to 10
- Machine Pistol ammo decreased from 72 to 45

**Rifleman:** Receives additional reserve ammo for fighting longevity, befitting their role as the primary combat class.
- BE Heavy Rifle ammo decreased from 160 to 120
- BE Pistol 2 ammo decreased from 28 to 21
- NF Shotgun Pistol ammo decreased from 12 to 10
- Machine Pistol ammo decreased from 72 to 45
- Seismic Grenade ammo decreased from 5 to 3

**Grenadier:** Receives extra pistol ammo as it's their only ballistic weapon choice, compensating for their focus on explosive ordnance.
- Pistol 1 ammo decreased from 72 to 60
- BE Pistol 2 ammo decreased from 56 to 35
- NF Shotgun Pistol ammo increased from 12 to 14
- Machine Pistol ammo increased from 72 to 75

**Engineer:** Receives less reserve ammo as they carry ammo crates and can resupply themselves and teammates, reducing the need for large starting reserves.
- SMG1 ammo decreased from 140 to 70
- SMG2 ammo decreased from 160 to 80
- SMG3 ammo decreased from 48 to 28
- Pistol 1 ammo decreased from 36 to 28
- BE Pistol 2 ammo decreased from 28 to 14
- NF Shotgun Pistol ammo decreased from 12 to 8
- Shotgun ammo decreased from 24 to 16
- Machine Pistol ammo decreased from 54 to 30

### Vehicle
#### Weapons
- Railgun
	- Armor penetration damage reduced from 20% to 15%.

