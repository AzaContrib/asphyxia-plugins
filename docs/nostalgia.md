# Nostalgia (`nostalgia@asphyxia`)

## Game codes

- `PAN`

## Route-prefix strategy

Each logical route is registered in two forms:

- `<method>` (First/Forte)
- `op2_<method>`

Logical method groups:

- `common.get_common_info`
- `common.get_music_info`
- `player.get_musicdata`
- `player.get_playdata`
- `player.regist_playdata`
- `player.set_total_result`
- `player.set_stage_result` (passthrough)

## WebUI events

- `nosFixIndexBug`

## How the game communicates with the server

1. Loads common and music catalog metadata (`common.*`).
2. Loads player profile and song records (`player.get_playdata`, `player.get_musicdata`).
3. Writes session/profile/song updates (`player.regist_playdata`, `player.set_total_result`).
4. Optional stage-result route currently stubbed (`player.set_stage_result`).

## Main stored data domains

- `profile`
- `scores`
- version-specific auxiliary fields (events, brooches, islands/courses metadata handling)
