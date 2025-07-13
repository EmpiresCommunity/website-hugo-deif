---
title: Empires Mod 2.38.2 Released!
author: Smithy
date: "2025-07-13"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.38.2 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

# Changelog:

## Bugfixes

- Fixed a number of bugs introduced in 2.38.1:
	- Fixed some issues with visibility of entities when using the commander interface. Most notably, buildings that were not fully built and vehicles were not visible when they should have been.
	- Fixed a bug that prevented team participation score being processed correctly. The following were not working correctly:
		- Commander score bonus.
		- Squad participation bonus.
		- Squad leader bonus.
	- Fixed an issue causing vehicle carcasses to be displayed on the mini-map.
	- Fixed an issue where Brenodi reinforcements weren't being set correctly by map inputs on emp_info_params. (It was using the NF setting for both teams.)
	- Fixed a bug in GetBuildingCount() function in code, it was only able to return a count of team radars, regardless of input parameters.
- Fixed an issue where the radar & engineer radar were trying to spot dead vehicles.
- Fixed an issue where recycling the radar wasn't pausing the radar functionality of the building. (Changed to match all other buildings.)
- Fixed some potential issues in the ray cast detection used when reviving players. These are used to attempt to put the player on the ground and avoid putting the player inside terrain.
	- Added additional safety checks to ensure additional ray casts weren't used if the initial cast failed.
- Added a small delay to unstuck functionality if stuck inside building geometry, rather than attempting to get the player unstuck every frame if attempts failed.



