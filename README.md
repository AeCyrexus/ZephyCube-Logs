<p align="center"><img src="logo.png" alt="ZephyCube" width="160"></p>

# ZephyCubeLogs v1.6.0

Activity logger for Minecraft Bedrock Edition: logs are stored in the world (one set per day) and read in game. **Chat logging needs the "Beta APIs" experiment** enabled on the world; everything else uses stable APIs.

**Credit:** Originally created by iHarvs (@iharvs). ZephyCubeLogs continues that work.

## Install

Copy the `ZephyCubeLogs` folder into your world's `behavior_packs` folder and add its `uuid` and `version` (from `manifest.json`) to the world's `world_behavior_packs.json`. Needs `@minecraft/server` 2.2.0-beta (Beta APIs experiment on) and `@minecraft/server-ui` 2.0.0.

## Features

- **Player:** join, leave, spawn, respawn, death inventory, dimension and gamemode changes, emotes, effects, lag lines
- **Blocks:** break, place, interact, explosions
- **Entities:** interact, hurt, death (player kills), projectile hits, taming, mob farm detection
- **Items:** use, craft, drop, pickup, inventory changes, container take/put
- **Redstone:** levers, buttons, pistons, pressure plates, tripwires, target blocks
- **Dupe detection:** possible-dupe and illegal-stack hints
- **Staff audit:** staff actions via `scriptevent zc:audit player|action|target|detail`
- **Movement:** throttled samples (off by default)
- **Chat:** chat messages (**needs Beta APIs**)
- **Console:** copy of each line to the server console / ContentLog
- **Chest scanner:** see who opened, took from, put in, broke or placed a container
- **In-game viewer:** pick a day, filter by category, search
- **TPS monitor:** `/zc:tps`, plus a LAG line when TPS drops under 15

Each module can be toggled at runtime with `/zc:logsmodules <module> off|on`. Full details: `ZephyCubeLogs/FEATURES.md`.

## Commands

- `/zc:logs`: Open the ZephyCubeLogs viewer
- `/zc:tps`: Show server TPS (staff)

Operators can open the viewer. Players with the tag `zc_logs` can read logs too.

## Items

- An item renamed `logs` in an anvil opens the viewer.
- An item renamed `scanner` in an anvil, or the Chest Scanner (`/give @s zc:chest_scanner`), shows who opened, took from, put in, broke or placed the container you right-click.

## Modules

Every part can be turned off or on at runtime with `/zc:logsmodules <module> off|on` (no argument lists them). Details: `ZephyCubeLogs/FEATURES.md`.

## Notes

- Times use UTC+8 by default; change `timezoneOffsetHours` at the top of `scripts/main.js`.
- To also get readable lines in the ContentLog file set `content-log-file-enabled=true` in `server.properties`.
- Logs are kept for 7 days (`keepDays`).

## License

MIT, as declared in the pack manifest (original author: iHarvs, @iharvs).
