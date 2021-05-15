---
title: Empires Mod 2.32.1 Released!
author: Smithy
date: "2021-05-15"
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.32.1 which is live on Steam right now!

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! https://discord.gg/EXwY2X7

Changelog:

## General changes

- Added a 1 second delay after placement before walls can be recycled.
- Refactored Steam Rich Presence code to hopefully optimize things.
- Vehicle "Base weight" values have all been set to 0. This is so that the weight value shown in the menu's is only displaying the current equipment weight and the total available weight.
- Buildings now store the remainder of floating point damage that is applied in an accumulator. (This was already the case for player damage)
	- With the below explosion changes, it's important that all damage to buildings is accounted for. Damage values were previously truncated and a small amount of damage would be lost; with the accumulator this is no longer the case.
- All projectiles now collide with player hitboxes rather than the player's axis-aligned bounding box. (Grenades/shells/missiles)
	- Improved on the previous version of hitbox detection for projectiles, which should now be a lot more accurate than the previous version.
	- Projectile sizes are now fully respected, whereas previously they were restricted to being a very small size; which would lead to the some shells and missiles missing, even if the model seemed to hit.
	- The aim of these changes are to increase accuracy and allow for a better experience. Nobody likes to die to things that clearly missed them.
- Mines no longer collide with players. Mines can still be triggered by players but they will fall straight to the ground without colliding with other players when thrown.


## Bug fixes

- Fixed a memory leak on the client relating to loading and storing values in game_particles.txt. (It wasn't being deleted on map change.)
- Fixed a memory leak on the server relating to the method used to save/restore player information if they disconnect/reconnect. The information was things like kills/deaths/tickets used etc. (It wasn't being deleted on map change.)
- Speculative fix for scoreboard muting when the server is at a high player count.
- Fixed the Scout weapon silencer skill. Previously it was only applying the volume change to the local player, other players would hear it as normal.
- Fixed a bug causing Zulu squad to not generate squad points.
- Fixed the scout silencer skill only working for the local player. (Volume changes only.)
- Fixed rifleman vehicle damage skill not being applied to cannons.
- Fixed an issue with footstep raycasts only hitting world surfaces.
	- For example if a player was inside a building, the raycast would ignore the building entirely and only play sounds that were corresponding to the ground below. If the player was on top of the building, no sound would play because the raycast missed everything.
- Fixed a bug that was preventing all HUD-element reset functions from being called.
	- This was causing hud-hints to get stuck on screen after map change because the "hide" HUD animation wasn't being called by the reset function.


## Sound changes

- Added footstep sounds for the snow/ice surface property.
- Made some changes to make higher attenuation sounds fade out a little nicer, rather than starting at near-full volume when you enter it's radius.
	- This does mean that some sounds are audible from longer distances, but they should fade out the same way as smaller attenuation sounds do.
	- This change means a lot of the higher attenuation sounds have been reduced so that the audible distances are sensible.

### Sound-mixer changes
- Reduced the volume for the following categories:
	- Ambient (This mostly affects soundscapes.)
	- UI
	- Music
	
### Soundscape changes
- Disabled the Auto DSP (Digital Signal Processor) effect for emp_duststorm, emp_midbridge and emp_mvalley.
	- The behaviour of the Auto DSP setting isn't ideal for wide open spaces and quite often will cause the DSP settings to enter an echoed state but never get reset. (Without forcibly restarting the sound system)


## Script/Game Balance
### Rank Points
- Reduced the amount of wages provided from repairing 100 units from 5 to 3
- Reduced the amount of sabotages required to generate a rank-point from 2 to 1
- Reduced the amount of sabotages required to generate a rank-point from 2 to 1

### Explosion changes
- Seismic grenades now have 25% damage bleed through effect like Nuclear missiles/Arty shells.
	- What this means is that if the explosion was blocked something that would normally block all the damage, it will now bleed throu
- **Explosions damage falloff is now also applied when damaging buildings.**
	- Previously there were some technical issues that made the default explosion falloff not work very well when damaging buildings because of their size.
	- Buildings resistances have been adjusted to work with the new fall-off damage. See below for more information
	- Infantry and Vehicle Weapons Explosion Radius have been adjusted to work with the new fall-off damage. See below for more information
- Explosions now have a "falloff offset", anything inside this zone will not have falloff applied.
	- You can think of this as an inner radius for which the explosion will always deal it's full damage. (Resistances still apply, after the falloff calculation)
- Vehicle/infantry weapons can script different offsets to allow custimization of the damage (Script variable is named "Explosion Falloff Offset" for both veh/inf scripts, default offset is 10% but script variable is 0-1)
- Fixed a couple of general bugs to do with blocked explosion damage.
- Seismics now have a damage bleed through of 25%. (Basically if blocked by something else, damage will still apply at the reduced value)
- New CVAR has been added - "emp_sv_debug_visualize_explosions", this will allow you to visualize some of the explosion parameters (Radius, offset radius, explosion parameters etc)


### Changes to RPG/Mortar

- Tidied up the code for both weapons, condensed some statements and shortened code where possible.
- Removed unused functions from mortar/rpg. (Some of these were remnants from HL2 like RPG laser effect)
#### RPG

- Fixed a bug with the holster function not cancelling the missile guidance mode. (Allowing players to continue guiding with a different weapon out)
- Removed a traceline raycast that was being fired every time the RPG was fired but the result was never being used. (Very small optimization)
- Reload now uses prediction/networking and the timings should be more reliable in general.
- There is a 0.5s reload delay after firing. This delay is only applied right after firing and will not affect when you can reload after guiding a missile.

#### Mortar

- Mortar can no longer fire backwards, the firing angle offset (16.4°) eases out once the player aims up too far.
- Removed the right click function. This opened the "artillery map", but this feature was unfinished and has remained in a broken state for a number of years.
- Reload now uses prediction/networking and the timings should be more reliable in general.
- Automatic reload delay is 0.5s after firing.

### Infantry Weapons

- RPG
	- Increased Explosion Radius from 50 to 75
	- Decreased turn speed from 1.75 to 1.65
- Concussion grenades
	- Explosion Falloff Offset of 100% (No explosion damage falloff for these grenades)
- Seismic grenades
	- Increased radius from 200 to 300
	- Explosion Falloff Offset of 50% (150 units)
	- Seismic grenade "ScreenShake" effect now matches the radius, it was previously hard-coded to 600 units.

### Vehicle Armor
- Commander
	- Increased Health from 250 to 275
	- Increased Squad Artillery Resist from 0.5 to 0.625
		- Reduces damage from squad artillery by 25%
- Reactive
	- Increased Health from 120 to 130
- Composite
	- Reduced Regeneration from 2 HP/s to 1.5 HP/s
	- Increased Biological Resist from 0 to 0.2
- Regenerative
	- Reduced Regeneration from 5 HP/s to 4 HP/s

### Vehicle Weapons

#### Missile Launchers

- Homing Missile Launchers
	- Increased Missile Range from 6000 to 8000
	- Decreased Heat from 10 to 9
	- Increased Clip Size from 7 to 8
- Standard Missile Launcher
	- Increased Explosion Radius from 100 to 200
- Upgraded Missile Launcher
	- Increased Explosion Radius from 150 to 250
- Guided Missile Launcher
	- Increased Explosion Radius from 100 to 200
- Homing Missile Launcher
	- Increased Explosion Radius from 100 to 200
- Biological Missile Launcher
	- Increased Projectile Spread from 0.5 to 1
- Nuclear Missile Launcher
	- Reduced Projectie Spread from 1.25 to 1
	
#### Machine Guns

- Depleted Uranium Machine Gun
	- Reduced Cost from 70 to 60
	- Reduced Cycle Time from 0.121 to 0.1
	- Reduced Damage from 5 to 4
		- Combined with the Cycle Time reduction it reduces DPS from 43 to 38
	- Reduced FalloffStart from 5000 to 4000
	- Reduced FalloffEnd from 10000 to 8000
	- Reduced Minimal Damage from 4 to 3
- Depleted Uranium Heavy Machine Gun
	- '''REMOVED'''
- Plasma Heavy Machine Gun
	- Increased Cost from 100 to 110
- High-Explosive Heavy Machine Gun
	- Reduced Cost from 125 to 100

#### Cannons

- Standard Cannon
	- Increased Explosion Radius from 275 to 300
- Ranged Cannon
	- Increased Explosion Radius from 150 to 250
- Railgun
	- Increased Explosion Radius from 100 to 200
- High-Explosive Cannon
	- Decreased Projectile Spread from 1 to 0.5

#### Grenades

- Explosion Damage Falloff Offset of 20% for all grenades

### Buildings

- Buildings
	- Reduced Recycle Time from 20 to 10
	- Decreased Kinetic Shell Resistance from 0.833 to 0.8
	- Decreased Explosive Shell Resistance from 0.89 to 0.833
	- Decreased Plasma Shell Resistance from 0.88 to 0.85
	- Decreased Explosive Missile Resistance from 0.833 to 0.75
	- Decreased Artillery Resistance from 0.85 to 0.775
- Turrets
	- Decreased Kinetic Shell Resistance from 0.7 to 0.6
	- Decreased Explosive Shell Resist from 0.75 to 0.6
	- Decreased Biological Shell Resistance from 0.75 to 0.7
	- Decreased Plasma Shell Resist from 0.76 to 0.6
	- Decreased Explosive Missile Resistance from 0.65 to 0.5
	- Decreased Artillery Resistance from 0.7 to 0.55
- Walls
	- Decreased Kinetic Shell Resistance from 0.925 to 0.91
	- Decreased Explosive Shell Resistance from 0.94 to 0.933
	- Decreased Explosive Missile Resistance from 0.94 to 0.92
	- Decreased Artillery Resistance from 0.94 to 0.9


