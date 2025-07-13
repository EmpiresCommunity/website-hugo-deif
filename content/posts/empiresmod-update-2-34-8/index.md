---
title: Empires Mod 2.34.8 Released!
author: Smithy
date: "2022-09-25"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.34.8 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

# Changelog:

## Features

### Changes to squad menu

- Fixed some alignment issues on text / icons.
- Text should is now set as 'proportional' and should better based on resolution.
- Health values update more reliably and are now colored Red->Green based on health percentage. (Squad aura indicator is now white, to avoid confusion.)
- The Squad Power icon now has text displaying time left on it's timer.
- Fixed some issues with the squad member flashing indicator when squad members fire weapons. (This now flashes their name instead of the whole row background.)

### Changes to squad revive

- Improved the checks used for positioning revived players. Ray casts are more predictable in terms of where players might be revived, using a radius around the squad leader.
- Added extra checks to prevent reviving through terrain. This might not cover every situation but it's a big improvement over the previous method.
- Player's are no longer revived on locations where they would fall down a slope. It will instead try a different location.
- Squad members now revive slightly closer to the squad leader if the revive is successful. Previously players would spawn in very random locations which could be quite far from the squad leader, leaving no opportunity for counter play from the enemy team. This is no longer the case and squad revive is more predictable, both for the squad leader and the enemy!
- Revived squad members now point in the direction that the squad leader was looking, rather than always pointing toward east!


## Bug fixes

- Spotting is now removed when a player dies. Previously the spotting diamond would display until the spotting timer expired.
- Updated console font to be proportional. It should now be readable on most resolutions.
- Updated some mini-map fonts to be proportional. These should now be readable on most resolutions.
- Fixed an issue with chat closing when you get revived. Although there are benefits to this, it can be annoying if you typed out a whole message and lose it all!
- Fixed issues where the engineer tool couldn't detect a ragdoll when attempting to revive players. (Reviving players who died in water is now fixed!)
- Fixed a bug where the squad menu player ordering would break, leaving gaps and breaking the squad menu. This only occurred when the round had ended.


## Script/Game Balance

### Changes to infantry movement

- Speed upgrade now increases swim speed through water. There was previously a bug causing players to move at the maximum speed regardless of having the skill or not.
	- Stamina use in water is now the same regardless of player stance (Crouch/standing), this is because the speed is the same regardless of stance.
- Speed upgrade now affects crouch/prone stances - whereas previously they were set to always consider you having the speed upgrade skill.
- Fixed a few bugs causing low movement speed whilst using weapon iron sights. This is a significant change to the previous move speed as it was setting it lower than it should have been.
	- As a result, the view model bobbing effect has been significantly reduced when using weapon iron sights and moving around.
	- Running while in sniper scopes is slower than standard iron sights. (25% reduction but this may need further tweaking.)

### Infantry weapons

- Concussion grenades
	- Disable effect to turrets is now applied when the damage is applied rather than separately. Explosion damage is more reliable than the single ray cast method that was previously in use.
		- As a result, the damage radius has been increased to be closer to the original disable radius. Damage falloff reduction has been changed to reflect this. Radius is now 400 (up from 300), damage falloff reduction starts at 200 (down from 300).

### Vehicle Engines

- All Engines
	- Gas Turbine
		- Heat Dissipation increased by 1
		- Heat Output At Max decreased by 1
	- Bio Diesel
		- Heat Dissipation increased by 0.5
	- Fission Reactor
		- Heat dissipation increased by 0.5
		- Heat Output At Max decreased by 1


