---
title: Empires Mod 2.39.0 Released!
author: Smithy
date: "2025-11-30"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.39.0 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

# Changelog:
## Features
- Major overhaul to the visibility system that drives the networked information used by the mini-map (and in-game visibility of entities).
    - For more information see the detailed write-up here. https://www.empiresmod.com/posts/visibility-system-overhaul/
- Updated the resource income display on the HUD and mini-map:
    - Resource delta and income values now show up to two decimal places when appropriate (e.g. a refinery output of 1.75 will now display as-is, instead of rounding to 1.8).
    - Decimal places are hidden entirely if the value is a whole number.
    - Slightly increased the width of the top-right HUD panel to accommodate the extra digits.
    - Resource delta now uses a moving average of changes over the last 1 second, instead of displaying changes instantly and clearing them after 1 second. This change was made in response to player feedback that the numbers were updating too frequently and were distracting.

## Bugfixes

- Fixed a server crash relating to the command vehicle being unexpectedly removed.
- Fixed a server crash relating to maps that spawn buildings without an initial team being set.
- Fixed a bug with capture points awarding victory to the incorrect team.
- Fixed a problem with ablative armor's HUD icon. The VTF texture file became corrupt due to an issue in the build pipeline that publishes the game.
- Fixed a bug where the Biological Machine Gun’s damage-over-time effect was being unintentionally reduced by armor angle modifiers.

## Script/Game Balance
### Infantry Weapons
- SMG3 (NF Heavy Carbine)
    - Damage reduced from 32 to 30
    - Minimal Damage reduced from 18 to 14
    - FalloffEnd reduced from 10000 to 5000
    - Clip Size increased from 12 to 14
    - Reduced overall accuracy

### Vehicle Armors
- Adjusted the angle modifier range from 0–45° to 0–60°. Damage now decreases more gradually, reaching the full reduction only at impact angles greater than 60°. The modifier is used by all armor types, most notably Deflective armor.
- Regenerative
    - Increased Regeneration from 3/s to 4/s
- Absorbant
    - Increased Speed to Damage Reduction from -0.00007 to -0.0001
- Capacitive
    - Reduced Damage to Heat from 0.05 to 0.02
    - Reduced Speed to Damage Modifier from 0.000035 to 0
     Ablative
    - Increased Damage to Heat from 0 to 0.01
        - This is something all armors have, it was forgotten until now
- Deflective
    - Reduced Angle Modifier Damage Reduction from 1 to 0.8

### Vehicle Engines
- Engine heat from driving input is now only applied if handbrake is off and the vehicle is moving.
    - This has been changed to combat Fission engine cooling being applied while stationary. (Handbrake or driving against walls etc.)
- Fission
    - Reduced Heat at Max from -4 to -3
- Bio Diesel
    - Increased Cooling by 0.25
- 3 Phase
    - Reduced Heat Output at Max from 4 to 3

### Vehicle Weapons
- Nuclear Warhead
    - Increased Weight from 150 to 180
    - Increased Heat from 75 to 100
- Railgun
    - Added armor penetration. 20% of damage will ignore armor. (Calculated after damage multipliers and armor resistances.)
- Salvo Homing Missiles
    - Heat from 5 to 4

## Other changes 
- Explosions that apply heat or biological damage-over-time now reduce effects based on distance to the explosion (falloff).
- Reduced the rate at which the repair station repairs the armor and hull of command vehicles.
    - Reduced Repair Station Repair (Hull) from 75 to 5
    - Reduced Repair Station Repair (Armor) from 0.25 to 0.025

