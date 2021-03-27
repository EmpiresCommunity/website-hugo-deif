---
title: Empires Mod 2.31.2 Released!
author: Smithy
date: "2021-03-27"
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.31.2 which is live on Steam right now!

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! https://discord.gg/EXwY2X7

Changelog:
## Features

- Increased player icon fade distances 4000 units for revive, 3000 for everything else (ammo/health/squad icons).
	- Also increased their scale very slightly as of last patch.
	

## Bug fixes

- Fixed a bug that would cause certain buildings to stop functioning after triggering it to recycle, then cancelling the recycle. (Turrets/Radar(Vehicle scanning function only, research capability was unaffected))
- Fixed a visual bug with melee which would cause the dynamic crosshair to expand even though it didn't increase bullet spread.
- Fixed vehicle preset ordering to fix issues with commander interface dropdowns.
- Fixed a bug with vehicle looping sounds (Engine sounds mostly) being hardcode limited to 2500 attenuation distance, regardless of the sound script's attenuation definition.
	- Along side this general vehicle sound attenuation has been increased, meaning you can hear them from futher away. (And louder for longer distances)


## Script/Game Balance

### Vehicle Armors

- Composite
	- Increased Cost from 30 to 40.
	
### Vehicle Weapons

#### Machine Guns

	- Standard Machine Gun
		- Decreased Heat from 1 to 0.8
		- Increased Reload Time from 3.5 to 4
	- .50cal Machine Gun
		- Decreased Heat from 0.8 to 0.6
		- Decreased Weight from 50 to 45
		- Increased Clip Size from 70 to 80
		- Increased Total Ammo Clip from 4 to 5
		- Increased Reload Time from 6.8 to 7
		- Decreased Projectile Spread from 0.013 to 0.01
	- .50cal Heavy Machine Gun
		- Decreased Cost from 95 to 90
		- Decreased Damage from 23 to 20
		- Decreased Cycle Time from 0.06 to 0.045
		- Increased Clip Size from 110 to 120
		- Increased Total Ammo Clips from 4 to 6
		- Increased Reload Time from 7.5 to 9
		- Decreased Projectile Spread from 0.013 to 0.008
	- Chain Gun
		- Decreased Damage from 14 to 13
		- Increased Heat from 0.35 to 0.7
		- Decreased Weight from 50 to 40
		- Increased Cycle Time from 0.04 to 0.06
		- Decreased Clip Size from 125 to 100
		- Increased Total Ammo Clips from 3 to 4
	- Medium Chain Gun
		- Decreased Cost from 70 to 60
		- Increased Heat from 0.45 to 0.7
		- Decreased Weight from 65 to 50
		- Increased Cycle Time from 0.035 to 0.045
		- Decreased Clip Size from 175 to 150
		- Increased Total Ammo Clips from 3 to 5
		- Decreased Projectile Spread from 0.03 to 0.0275
		
#### Cannons

	- Standard Cannon
		- Reduced Heat from 10 to 9
	- Ranged Cannon
		- Decreased Cost from 85 to 80
	- High-Explosive Cannon
		- Decreased Cost from 80 to 70
		- Decreased Gravity from 0.4125 to 0.4
		- Increased Weight from 60 to 70
	- Plasma Cannon
		- Decreased Cost from 130 to 110
		- Decreased Gravity from 0.4 to 0.35
		- Railgun
		- Decreased Cost from 160 to 120
	- Biological Cannon
		- Decreased Cost from 130 to 100
		- Decreased Gravity from 0.37 to 0.35
		- Decreased Projectile Spread from 1 to 0.5
		- Decreased Explosion Radius from 200 to 150
		- Increased Vehicle Bio Time from 4.25 to 5
		- Increased Vehicle Bio Interval from 0.4 to 0.5
		- Increased Infantry Bio Damage from 3 to 4
		- Decreased Infantry Bio Time from 7 to 5
		- Decreased Infantry Bio Interval from 1 to 0.5
		
#### Missiles Launchers

	- Standard Missile Launcher
		- Increased Weight from 30 to 40
		- Decreased Cycle Time from 1.2 to 1.1
	- Upgraded Missile Launcher
		- Decreased Heat from 8 to 6.5
		- Increased Explosion Radius from 100 to 150
	- Biological Missile Launcher
		- Increased Heat from 6 to 12
	- Nuclear Missile Launcher
		- Increased Cost from 140 to 200
	- Guided Missile Launcher
		- Increased Heat from 7.5 to 9
	- Homing Missile Launcher
		- Decreased Cost from 140 to 100
		- Increased Damage from 55 to 60
		- Decreased Lock Range Modifier from 0.00029 to 0.0002
		-- This means it increases the time it takes to lock onto a target by 0.2s by 1000 units
- Grenade Launchers
	- Biological Grenade Launcher
		- Decreased Cost from 60 to 50
		- Increased Weight from 40 to 50
		- Increased Damage from 30 to 40
		- Decreased Cycle Time from 2.5 to 2
		- Decreased Heat from 14 to 13
		- Increased Total Ammo Clips from 4 to 5
		- Decreased Grenade Timer from 6 to 3
		- Increased Player Bio Damage from 10/s for 3s to 10/s for 4s
		- Increased Vehicle Bio Damage from 5/s for 5s to 10/s for 4s
		
### Vehicle Engines

- Bio Diesel
	- All Chassis
		- Decreased Heat At Max from 1 to 0
		
### Research

- High Caliber Rounds (.50cal)
	- Moved from Projectile Physics to Electrical Engineering
	- Increased Cost from 180 to 240
	- Increased time from 45 to 60
- Advanced Machining
	- Increased Cost from 360 to 600
	- Increased Time from 90 to 120
- Composite Armored
	- Increased Cost from 480 to 600
- Gas Turbine
	- Increased Cost from 360 to 450
	
### Chassis

- Armored Fighting Vehicle
	- Increased Available Weight from 320 to 330
	
	
	