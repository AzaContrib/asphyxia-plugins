# BeatStream (`bst@asphyxia`)

## Game codes

- `NBT`

## Registered game endpoints

- `info2.common`
- `pcb2.boot`
- `player2.start`
- `player2.continue`
- `player2.succeed`
- `player2.read`
- `player2.write`
- `player2.stagedata_write`
- `player2.course_stage_data_write`
- `player2.course_data_write`

## WebUI events

- `bst2UpdateSettings`
- `removeWebUIMessage`

## How the game communicates with the server

1. Cabinet boot and common-state retrieval (`pcb2.boot`, `info2.common`).
2. Player session startup (`player2.start` / `player2.continue`).
3. Profile and progression load (`player2.read`).
4. Per-stage and per-course writes while/after play (`player2.stagedata_write`, `player2.course_stage_data_write`, `player2.course_data_write`).
5. Final profile/session persistence (`player2.write`, `player2.succeed`).

## Main stored data domains

- Profile/account state
- Stage logs
- Course logs
- Event/unlock/settings data
