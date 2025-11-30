---
title: Visibility System Overhaul
author: Smithy
date: "2025-11-30"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---

___

This article covers the changes made in Empires version 2.39.0 to improve how the game handles entity visibility and networking. The new system is designed to be more efficient, more reliable and more adaptable for future improvements and features.

___
{{< toc >}}

___

## Overview

The new visibility system introduces a robust framework for managing how entities interact and become visible to players. At its core are two fundamental components that work in tandem to control entity visibility:

### How It Works
Visibility components are processed by a new [visibility manager](#visibility-manager) game system.
- The system continuously evaluates interactions between [detectable](#detectable-component) and [detector](#detector-component) components and determines if visibility states should be applied.
- Visibility is determined on a per-entity basis, based on an evaluation of defined factors.
- Detectable entities are only networked to players if the detectable component has a visibility state greater than "Hidden" or if the player is within a server-defined visibility range of the entity ([potentially visible set](https://developer.valvesoftware.com/wiki/PVS) rules still apply).

___

## Visibility Components

### Detectable component
A component added to entities that allows them to be detected by other entities. A detectable component can be in one of four distinct visibility states (see [Visibility States](#visibility-states)), which determine how and when they are revealed to players. When not explicitly assigned a global state, the system determines if the entity should be visible to players based on visibility ranges configured in the server settings.

#### Visibility timers
Detectable components are designed with an interface for setting timed visibility states. The visibility timer component is used to store the visibility state and the time at which it should expire. This is used for spotting and attacker detection. Visibility timers are processed in order of priority, with the highest priority timer taking precedence. If a timer is active, the detection state is set and the detectable will not be evaluated further by the visibility manager.

#### Visibility states
A detectable component can be assigned one of the four visibility states below:
| State | Functionality | Data networked | Notes |
|-------|-------------|-------|-------|
| Hidden | Detectable entity is hidden to all players unless the player is within visibility range of the entity ([potentially visible set](https://developer.valvesoftware.com/wiki/PVS) rules still apply). | Only sent to players within server-defined visibility range of the entity. | See [Server Settings](#server-settings) to check the default visibility ranges for each detectable entity type. |
| Visible | Detectable entity is visible to all players. | Yes | Currently not used, but reserved for potential future use. |
| Detected | Detectable entity is visible to all players and is shown on the enemy mini-map. | Yes |
| Spotted | Detectable entity is visible to all players and is shown on the enemy mini-map. Also enables spotting indicators on the HUD for enemy players (orange diamonds). | Yes |

#### Network recipient list
The detectable component is designed with an interface for building a list of recipient players that should receive the entity's data. As a final check within the visibility manager, the recipient list is compiled and used to determine if the entity should be networked to a specific players ([potentially visible set](https://developer.valvesoftware.com/wiki/PVS) rules still apply).

### Detector component
A detector component controls detection behavior of an entity. It uses a [detection capabilities class](#detection-capabilities), which stores a map of [detection profiles](#detection-profiles).

#### Detection capabilities
- The capabilities class is used to store all of the possible detection profiles for a detector component. It acts as an interface to add, remove and query profiles. It is mainly used by the [Visibility Manager](#visibility-manager) to determine if a [detector](#detector-component) should be able to detect a [detectable entity](#detectable-component).
- [Detection profiles](#detection-profiles) are stored within the capabilities class as a map, the unique key for each profile added to the map is a combination of the detection type and component type. TThis design allows profiles to be added/updated with ease. Example profile with it's respective key: Area detection profile that targets vehicle detectable components.

#### Detection profiles
Profiles define the criteria for detection of a specific detection method for a detectable component type:

| Profile | Description |
| --- | --- |
| Range | Used for checking if the detectable is within range of the detector |
| Team Target | Which teams that this detector targets |
| Spot enabled | Whether or not this detector should spot the target |
| Duration | Duration of the detection - 0 Default, apply [visibility states](#visibility-states) only while detection method applies. |
| Motion Threshold | Detectors only detect detectables moving faster than this velocity threshold |

Profiles will likely be extended in the future, for example to allow for range multipliers and detection effectiveness multipliers.

#### Detection methods
These are the available methods of automatic detection via the detector component:

| Detection Method | Description |
| --- | --- |
| Area detection | Detects everything within range that matches the detector's filter criteria (types, team, etc.) |
| Motion detection | Detects everything moving above a defined speed threshold within range that matches the detector's filter criteria (types, team, etc.) |
| Attacker detection | Automatically reveals attackers that match the detector's filter criteria (types, team, etc.) |

### Visibility Manager
The visibility manager is a game system that is responsible for processing all visibility components and determining if visibility states should be applied.

#### Processing stages
The visibility manager is responsible for processing all visibility components and determining if visibility states should be applied. It does this by:

1. Checking detectables' [visibility timers](#visibility-timers). Update visibility state based on the highest priority active timer. Remove any expired timers.
2. Checking if the detectable is within range of an area detector. Update [visibility state](#visibility-states) accordingly.
3. Checking if the detectable is within range of a motion detector and moving faster than the defined motion threshold. Update [visibility state](#visibility-states) accordingly.
4. Checking if the detectable is within range of players, update network recipient list accordingly.

___

## Detection and Spotting Mechanics
### Manual spotting
The below outlines the duration of spotting for each type of spotting.
| Spot Type | Building | Player | Vehicle |
|--|--|--|--|
| Regular spotting | 8 seconds | 6 seconds | 6 seconds |
| Spotting via binoculars | 2 minutes | 30 seconds | 1 minute |

### Auto detection
The below outlines the various detectors and their detection profiles.

When the table indicates "Active" it means that the detector is actively detecting the entity while its filter criteria is met (no duration is set). Buildings and vehicles use edge-to-edge detection based on their defined collision radius.

#### Buildings
All buildings have detector components, except for walls - which do not detect other entities. The detectable component on walls has a max visibility state of `Visible`, this prevents walls from being spotted or displayed on the mini-map.
| Building Type | Detection Type | Target detectable type | Team Target | Visibility state | Duration | Range | Motion Threshold |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Engineer camera | Motion detection | Player | Enemy | Spotted | 2 second | 2,000 units | 10 units per second |
| Engineer radar | Area detection | Building | Enemy| Detected | `Active` | 4,000 units | N/A |
| Engineer radar | Motion detection | Vehicle | Enemy | Spotted | 2 second | 4,000 units | 10 units per second |
| Engineer Radar | Area detection | Vehicle Carcass | Enemy | Spotted | `Active` | 10,000 units | N/A |
| Radar | Area detection | Building | Enemy (Detects friendlies if sabotaged) | Detected | `Active` | 10,000 units | N/A |
| Radar | Area detection | Vehicle | Enemy (Detects friendlies if sabotaged) | Spotted | 3 second | 10,000 units | N/A |
| Radar | Area detection | Vehicle Carcass | Enemy (Detects friendlies if sabotaged) | Spotted | `Active` | 10,000 units | N/A |
| Radar | Attacker detection | Player & Vehicle | Enemy | Detected | 5 second | 2,000 units | N/A |
| All other buildings | Area detection | Building | Enemy | Detected | `Active` | Collision radius + 500 units | N/A |
| All other buildings | Attacker detection | Player & Vehicle | Enemy | Detected | 5 second | Collision radius + 500 units | N/A |
| All other buildings | Motion detection | Vehicle | Enemy | Detected | 1 second | Collision radius + 500 units | 10 units per second |

#### Players
| Detection Type | Target detectable type | Team Target | Visibility state | Duration | Range | Motion Threshold |
| --- | --- | --- | --- | --- | --- | --- |
| Area detection | Building | Enemy | Detected | 1 second | Class specific (see table below) | N/A |
| Area detection | Vehicle Carcass | Enemy | Detected | `Active` | Collision radius + 2,000 units | N/A |

These are configured within the [player class definition script](https://git.neoony.com/empires_public/empires_scripts/-/blob/develop/emp_classes.txt).
| Class | Building auto-spot range | 
| --- | --- | --- |
| Engineer | Collision radius + 1,000 units | 
| Grenadier | Collision radius + 1,000 units | 
| Rifleman | Collision radius + 1,000 units | 
| Scout | Collision radius + 2,000 units | 

#### Vehicles
| Detection Type | Target detectable type | Team Target | Visibility state | Duration | Range | Motion Threshold |
| --- | --- | --- | --- | --- | --- | --- |
| Motion detection | Vehicle | Enemy | Detected | 1 second | Collision radius + 1,000 units | 10 units per second |
| Area detection | Vehicle Carcass | Enemy | Detected | `Active` | Collision radius + 2,000 units | N/A |

___

### Mini-map

#### Icon colors
The below outlines all of the detectable entity icon colors drawn on the mini-map. These are applied for each type, in the order they appear in the table.
| Entity Type | State | Description |
|-------------|-------|-------------|
| Player | Firing | Brief white flash when friendly player fire weapons |
| Player | Taking damage | Brief dark flash when friendly player take damage |
| Player | Orders | Green pulse for 8 seconds when a player issues a radio command |
| Player | Revive skill | Lighter team color |
| Player | Dead | Gray color |
| Vehicle | Dead (Carcass) | Yellow color (This is new, yellow was chosen to match the 'unbuilt' state on buildings.) |
| Vehicle | Firing | Brief white flash when friendly vehicle fire weapons |
| Vehicle | Taking damage | Brief dark flash when friendly vehicle take damage |
| Vehicle | Unoccupied | Lighter team color |
| Building | Taking damage | Brief white flash when friendly building take damage |
| Building | Unbuilt | Yellow color |
| ALL | Anything else | Team color |

___

### Configuration
#### Server Settings
The below console variables control network visibility range, if the entity is not globally visible:
| Console Variable | Default value | Description |
|------------------|-------------|-------------|
| emp_sv_netvisdist_player | 10,000 | Distance at which a player will be networked/visible to enemies |
| emp_sv_netvisdist_vehicle | 10,000 | Distance at which a vehicle will be networked/visible to enemies |
| emp_sv_netvisdist_building | 10,000 | Distance at which a building will be networked/visible to enemies |


### Fixes or changes introduced as a result of this overhaul
#### Mini-map icon color for player's with the revive skill is updated more reliably
Due to improvements in how player data is networked, the revive icon color is now more reliable. There were situations in previous versions where the icon color would not be updated correctly.

#### Scout 'Enhanced Senses' skill is more reliable
Enhanced Senses skill has been changed to detect players in range regardless of [potentially visible set](https://developer.valvesoftware.com/wiki/PVS).

Previously if a player was within range but optimized away due to [PVS](https://developer.valvesoftware.com/wiki/PVS) - they just wouldn't be detected. That is no longer the case, all players within radius will now be detected.

In practice, this change makes the skill work as originally intended. There were situations where scouts could be missed, despite having the skill; purely because they were not being drawn due to optimization.

#### Vehicle carcasses are now drawn on the mini-map (Yellow color)
Due to previous limitations enforced on the mini-map, vehicles were no longer drawn once they were destroyed. This limitation has been removed so as an experiment, vehicle carcasses are now detected & displayed.

`This change may be subject to change if it is deemed to be detrimental to overall clarity of the mini-map.`


