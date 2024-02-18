---
title: Empires Mod 2.33.3 Released!
author: Smithy
date: "2021-11-14"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.33.3 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

Changelog:

## Bug fixes
- Fixed a bug on Linux servers which caused vehicles to be able to aim beyond the intended cannon pitch angle restrictions. (You could aim down inside your own tank and self-damage the tank)
- Fixed a bug involving tank cannon shells getting stuck floating in the air when colliding with the tank that fired it. Although this doesn't happen often the issue was brought up recently with the above issue on Linux servers.
- Fixed a problem involving map-edge grid textures not displaying correctly on lower texture settings.
- Fixed a bug where unbuilt buildings would flash as the team color instead of it's intended yellow color when damaged.
- Fixed an issue where the emp_resource_point entity was no longer firing it's outputs when intended. (Used by level designers - OnNFBuilt/OnImpBuilt OnEnable/OnDisable are now working as intended)
    - These are often used to control when smoke should appear, so fixing this may help improve FPS in some situations.
- Fixed an bug causing vehicle steering values to change when recustomizing on a repair station.
- Fixed a few issues where Salvo Missiles would not fire their full volley and fixed another issue where they could fire unexpectedly. (For example: When the wrong attack key was pressed.)


## Miscellaneous changes
- Projectiles are now excluded from explosion damage hit detection. This is simply to ensure that explosion damage doesn't get lowered/blocked by shells/missiles/grenades.
- Missiles no longer have health; previously missiles could be exploded by taking damage from explosions. Although this might seem like an interesting feature, it has never been the same for cannon shells and it causes some balancing issues.


## Script/Game Balance

### Vehicle Weapons
- Cannons
    - Reduced Recoil a little bit for High-Explosive and Plasma.
    - Reduced Recoil a lot for Railgun
	
### Vehicle Armors
- Absorbant
    - Increased Health from 67 to 70
- Reactive
    - Increased Health from 130 to 135


