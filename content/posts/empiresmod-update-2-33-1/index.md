---
title: Empires Mod 2.33.1 Released!
author: Smithy
date: "2021-09-11"
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.33.1 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! https://discord.gg/EXwY2X7

Changelog:

### Features

- Implemented a system that checks which player body parts are blocked by other objects before applying explosion damage.
	- Explosion damage and Bio DoT now scales based on the mass of the objects blocking each body part. (Bio Dot is only changed for explosions, Bio MG is unaffected)
	- Each body part is checked separately and scales the damage for that part depending on the blocking object's mass.
		- This uses the same mass checking system as was previously in the game, only that now each part is checked and scaled separately. Previously there was a single check done using the detection raycast that detected the player being visible to the explosion.
		- For reference the system scales the damage based on objects of 0-350 kg mass. (350+ kg objects will block all of the damage.Player mass is 85kg, turrets are 280kg. This is here just to provide an example.)
		- Note - Body parts are an approximation based on player bounding box size and therefore may not line up exactly where the model's geometry is. (Example below)
		
		
		
| Body part | Maximum damage percentage loss |
|---|---|
| Chest | 40% |
| Head | 20% |
| Feet | 20% |
| Left Arm | 10% |
| Right Arm | 10% |

| Standing body parts | Crouching body parts | Proning body parts |
|---|---|---|
| ![Standing body parts!](/Standing_body_parts.png "Note: Chest position is hidden inside player geometry but is in line with the arm positions") | ![Crouching body parts!](/Crouch_body_parts.png "Note: Chest position is hidden inside player geometry but is in line with the arm positions") | ![Proning body parts!](/Prone_body_parts.png "Note: Chest position is hidden inside player geometry but is in line with the arm positions") |


### Bug fixes

- Updated the Source Engine SDK Base files to the latest version.
	- [Valve's patch notes for the update simply reads - "Numerous security and stability improvements."](https://steamcommunity.com/games/320/announcements/detail/2971794942853258240)
- Identified and resolved an issue causing Half-Life 2: Lost Coast content to be missing in the server packages. (Both Windows/Linux)


### Maps / Level design 

#### Minor update to emp_canyon

- Fixed [Cubemaps](https://developer.valvesoftware.com/wiki/Cubemaps) not being built when the map was last published.
- All player/vehicle clip brushes have been remade, increasing accuracy in order to prevent players from using exploits to reach the top of the hills.
	- B4 hill is now player/vehicle clipped and has restrictions in place for placing buildings.
- Standardized core entity names to match other official maps.
- Fixed the env_sun entity not displaying because of bad entity settings.

#### Minor update to emp_coast

- Remade all clip brushes/comm/engy restrict brushes
	- Fixed various exploit spots
- Standardized core entity names with other official maps.

#### Minor update to emp_mvalley

- Added player/vehicle/comm building clips to the high ground again. After hearing feedback from a lot of players, the majority of people suggested that they preferred the gameplay without high ground being accessible.


### Script/Game Balance

Script changes are visible via the [empires_scripts](https://git.empiresmod.com/empires_public/empires_scripts/-/commits/develop) repo on our Gitlab. Please follow the link if you would like to check exactly how the script values have changed.

#### Infantry weapons

- Both shotguns now have a FalloffEnd value of 7500, they were previously mismatched. (Previously BE was 5000, NF was 10000; This was unintentional.)

#### Vehicle chassis

- Reduced BE AFV Max Weight by 10
- Reduced NF Light Tank Max Weight by 10
- Fixed a few issues with vehicle chassis armor angle values being slightly wrong. (Used for determining which armor side took damage)
	- NF Jeep armor angle values were for the old model, these have been updated to reflect the geometry of the new model.
	- Both command vehicles had non-symmetrical armor angles for the back of the vehicle. Only by a few degrees, however both have been updated to resolve this.

#### Vehicle engines

- APC Engines' cooling has been reduced by 1.
- Heavy Tank Engines' cooling has been increased by 1.
- Removed researchable Artillery Engines as they served little purpose, standard engine has been adjusted to fit its new purpose and to be more fragile (with penalties).
- Stalling Penalties have been changed to be less impactful for armor hits and more impactful for some hull hits and generally reduced stall on heat threshold penalties.
- Horsepower Health Penalty has been increased slightly.
- Bio Diesel has been tweaked so it's no longer "unstoppable".

#### Vehicle weapons

- Removed High-Explosive Heavy Machine Gun
- Artillery weapons have been slightly rebalanced.
	- The trajectory of artillery projectiles have been adjusted.
	- Weight, Damage, cycle time and heat have also been adjusted.


