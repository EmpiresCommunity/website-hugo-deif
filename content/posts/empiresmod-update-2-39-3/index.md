---
title: Empires Mod 2.39.3 Released!
author: Smithy
date: "2026-01-25"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.39.3 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

# Changelog:

## Bugfixes
- Minor optimizations to the visibility system.
- Minor fixes to the layout of the vehicle weapon HUD.
- Vehicle weapon reload is now properly telegraphed via the vehicle HUD. Previously, no progress bar would display if reloading a weapon.
- Fixed an issue with prop_static entities not blocking explosion damage as intended.
- Fixed a regression that allowed players using hide to be spotted by other players.
- Fixed a bug where players could detect enemy commanders in the command interface using the scout's enhanced senses skill.
- Improved mine defusal while inside buildings.
- The player camera angles are now snapped to the vehicle turret position when entering the driver seat.
- Speculative fix to prevent spotting diamonds appearing on the HUD where they shouldn't.
- Speculative fix for a client crash while using the research menu.


## Script/Game Balance
### Vehicles
#### Armor
- Increased Deflective Angle Modifier from 0.8 to 1

### Engine
- Increased Fission Reactor's cooling at max from -3 to -4

### Weapons
- Medium Chain gun
  - Projectile Spread decreased from 0.0275 to 0.0225
  - FalloffEnd increased from 1250 to 2000
- Nuclear Missile Launcher
  - Changed ammo pool to be 10 clips of 1 missile. This allows the reload sound to play when ready to fire again.


