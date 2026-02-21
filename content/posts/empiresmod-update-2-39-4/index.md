---
title: Empires Mod 2.39.4 Released!
author: Smithy
date: "2026-02-21"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.39.4 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

# Changelog:

## Bugfixes
- Fixed a server crash caused by players repairing tanks that have been parented to other entities.

## Script/Game Balance
### Infantry
#### Weapons
- Northern Faction's .50cal Rifle
  - Increased Cycle Time from 0.25 to 0.3
- Brenodi Empires' Burst Rifle
  - Reduced Cycle Time from 0.5 to 0.4

### Vehicles
#### Armor
- Transferred Absorbant Heat Dissipation property to Ablative
  - Increased Absorbant's Damage to Heat Absorbed from -0.15 to 0.01
  - Reduced Ablative's Damage to Heat Absorbed from 0.01 to -0.15
- Increased Ablative's Regeneration from 1 hp/s to 2 hp/s

#### Chassis
- Artillery
  - Reduced Cost from 775 to 650
  - Increased available Weight from 255 to 270

#### Engine
- Changed Engine Heat Zones to have better defined identities (See https://git.neoony.com/empires_public/empires_scripts/-/merge_requests/327)
  - Standard Engine: Low, Medium and High Heat Zones are equal, and critical is small
  - 3 Phase: Smaller High Heat Zone, and Smaller Critical Heat Zone
  - Fission: Larger High Heat Zone, and Larger Critical Heat Zone
  - Bio Diesel: Larger Medium Heat Zone
  - Adv. Coolant: Much Larger Low Heat Zone, Much Smaller High Heat Zone, and Much Smaller Critical Heat Zone
  - Gas Turbine: Larger Low Heat Zone, and Smaller Medium Heat Zone

#### Weapons
- Railgun
  - Reduced Damage from 130 to 120
- TOW Guided Missile Launcher
  - Reduced Cycletime from 1.25 to 1.1
