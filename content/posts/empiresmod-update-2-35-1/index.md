---
title: Empires Mod 2.35.1 Released!
author: Smithy
date: "2023-07-08"
tags: [ "Source" ]
post_type: Source
post_type_future: ["Source", "Changelog"]
---


We're happy to announce version 2.35.1 is live on Steam.

{{< rawhtml >}}
<iframe src="https://store.steampowered.com/widget/17740/" frameborder="0" width="646" height="190"></iframe>
{{< /rawhtml >}}

Join us on Discord! {{< discordlink >}}

Changelog:

## Bug fixes

- Fixed an issue causing Sourcemod plugins to malfunction on Linux servers.
- Fixed a divide-by-zero bug in emp_engineer_map_brush / emp_engineer_map_object entities' "raise on build" functionality. This was causing entities to not spawn in correctly. In some cases where these entities were parented to other entities, it would crash the server.
- Fixed a few issues with how scout hide is applied to players. A code change in the last update was causing the server to reapply the hide effect constantly. This resulted in some strange behaviour, such as flickering invisibility and flickering screen overlays. This has now been fixed.
- Spectators can now see screen overlay effects from players affected by biological damage over time & scout hide.
- Applied a few fixes to building smoke. Smoke states should now update a bit more reliably. There was an issue where sabotage smoke would still appear, even after the effect ended.


## Maps

### as_escort

- Fixed some displacement seams having holes near the last flag.

### emp_duststorm

- Changed initial team owner of the emp_engineer_map_object entities in ruins (wood barricades). Now that this functionality is actually working properly, the map has been updated to reflect this.


