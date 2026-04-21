# DDR (`ddr@asphyxia`)

## Game codes

- `MDX`

## Registered game endpoints

- `playerdata.usergamedata_advanced`
- `playerdata.usergamedata_recv`
- `playerdata.usergamedata_send`
- `system.convcardnumber`
- `eventlog.write`

## WebUI events

- `updateName`
- `updateWeight`
- `updateDisplayCalories`
- `updateArrowSkin`
- `updateGuideline`
- `updateFilter`
- `updateJudgmentPriority`
- `updateDisplayTiming`

## How the game communicates with the server

`playerdata.usergamedata_advanced` is the primary multipurpose endpoint, keyed by `data.mode`:

- `userload`: loads profile, scores, and grade data
- `usernew`: creates profile and DDR code if missing
- `usersave`: saves current session profile/options/scores/ghost/events
- `rivalload`: rival payload
- `ghostload`: ghost payload
- `inheritance`: migration flag/status

Additional flow:

1. Raw profile payload chunks are exchanged with `usergamedata_recv` and `usergamedata_send`.
2. Card conversion and event logging are handled by `system.convcardnumber` and `eventlog.write`.

## Main stored data domains

- `profile`: DDR code, grades, usergamedata blocks, options
- `score`: per-song/per-chart clear and score data
- `ghost`: replay ghost payloads
