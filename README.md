<p align="center"><img src="logo.png" alt="ZephyCube" width="160"></p>

# ZephyCubeLogs v1.5.8

Activity logger for Minecraft Bedrock Edition: logs are stored in the world (one set per day) and read in game. No Beta APIs.

**Credit:** Originally created by iHarvs (@iharvs). ZephyCubeLogs continues that work.

## Install

Copy the `ZephyCubeLogs` folder into your world's `behavior_packs` folder and add its `uuid` and `version` (from `manifest.json`) to the world's `world_behavior_packs.json`. Needs `@minecraft/server` 2.2.0 and `@minecraft/server-ui` 2.0.0.

## Commands

- `/zc:logs`: Open the ZephyCubeLogs viewer
- `/zc:tps`: Show server TPS (staff)

Operators can open the viewer. Players with the tag `zc_logs` can read logs too.

## Items

- An item renamed `logs` in an anvil opens the viewer.
- An item renamed `scanner` in an anvil, or the Chest Scanner (`/give @s zc:chest_scanner`), shows who opened, took from, put in, broke or placed the container you right-click.

## Notes

- Times use UTC+8 by default; change `timezoneOffsetHours` at the top of `scripts/main.js`.
- To also get readable lines in the ContentLog file set `content-log-file-enabled=true` in `server.properties`.
- Logs are kept for 7 days (`keepDays`).

## License

MIT, as declared in the pack manifest (original author: iHarvs, @iharvs).
