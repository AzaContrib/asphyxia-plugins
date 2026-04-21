# Gitadora (`gitadora@asphyxia`)

## Game codes

- `M32`

## Route-prefix strategy

A `MultiRoute` helper registers each endpoint for multiple version prefixes:

- base (`<method>`)
- `re_`, `matixx_`, `exchain_`, `nextage_`, `highvoltage_`, `fuzzup_`, `galaxywave_`, `galaxywave_delta_`

## Registered endpoint groups

For every prefix above:

- `shopinfo.regist`
- `gameinfo.get`
- `playablemusic.get`
- `cardutil.regist`
- `cardutil.check`
- `gametop.get`
- `gameend.regist`

Also registered directly:

- `bemani_gakuen.get_music_info` (passthrough)

## WebUI events

- `updatePlayerInfo`

## How the game communicates with the server

1. Client gets cabinet/game capability state (`shopinfo.regist`, `gameinfo.get`, `playablemusic.get`).
2. Card is registered/validated (`cardutil.regist`, `cardutil.check`).
3. Full player data is loaded (`gametop.get`), including GF/DM-specific profile domains.
4. Session writes are committed at end (`gameend.regist`).

## Main stored data domains

- `playerinfo`
- `profile` (GF/DM)
- `record`
- `extra`
- `scores`
- ranking/secret music related collections
