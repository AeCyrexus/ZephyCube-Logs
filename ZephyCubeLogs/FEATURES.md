# ZephyCubeLogs 1.6.0

Activity logger with an in-game viewer, a chest scanner and a TPS monitor. Originally created by iHarvs (@iharvs). Logs are stored in the world, one set per day.

## Features (modules)
`/zc:logsmodules <module> off|on` (no argument lists them). Saved in the world. Turning a module off stops new lines of that kind; saved lines stay readable.

| Module | What it logs / does |
| --- | --- |
| `player` | join, leave, spawn, respawn, death inventory, dimension change, gamemode change, emotes, effects, lag lines |
| `blocks` | block break, place, interact, explosions |
| `entities` | entity interact, hurt, death (player kills), projectile hits, taming, mob farm notes |
| `items` | item use, craft, drop, pickup, inventory changes, container take/put, cursor grab/release |
| `redstone` | levers, buttons, pistons, pressure plates, tripwires, target blocks |
| `dupes` | possible-dupe and illegal-stack hints (per-second scan of what players carry) |
| `staff_audit` | staff actions sent by AdminTools (`scriptevent zc:audit player\|action\|target\|detail`) |
| `movement` | throttled movement samples (off in the config by default) |
| `chat` | chat messages (requires the Beta APIs experiment and the `-beta` @minecraft/server dependency) |
| `console` | copy of each line to the server console / ContentLog file (needs `content-log-file-enabled=true`), rate limited per player and event type |
| `scanner` | chest scanner: right-click a container to see who opened it, what was taken or put in, and who broke or placed it |

Other built-in behaviour: farm animals killed in bulk are detected as a mob farm and logging stops there; common mob kills and common blocks are kept out of the console file; a LAG line is logged when TPS drops under 15; every player's inventory is snapshotted so a death can list what they carried.

## Commands
| Command | Who | Use |
| --- | --- | --- |
| `/zc:logs` | operators, or players with the `zc_logs` tag | Open the viewer (pick a day, filter Player/Blocks/Entity/Items/Redstone/Dupe/Staff, search) |
| `/zc:tps` | operators | Show server TPS |
| `/zc:logsmodules [module] [on\|off]` | operators | List or toggle modules |

## Items
| Item | Use |
| --- | --- |
| Any item renamed `logs` in an anvil | Use it to open the viewer |
| `zc:chest_scanner` (no recipe: `/give @s zc:chest_scanner`) or any item renamed `scanner` | Right-click a chest, barrel, shulker, hopper, furnace and similar to see its history |

## Tags
| Tag | Effect |
| --- | --- |
| `zc_logs` | Non-operators with this tag can open the viewer and the scanner |

## Storage
World properties `zclogs:index`, `zclogs:<day>:<n>` (log pages), `zclog:modules`.
