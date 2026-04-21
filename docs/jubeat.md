# jubeat (`jubeat@asphyxia`)

## Game codes

- `L44`

## Registered game endpoints

- `gametop.regist`
- `gametop.get_info`
- `gametop.get_pdata`
- `gametop.get_mdata`
- `gametop.get_meeting`
- `gameend.final`
- `gameend.regist`
- `shopinfo.regist`
- `lobby.check`
- `lobby.entry`
- `lobby.refresh`
- `lobby.report`
- `netlog.send`
- `logger.report`

## How the game communicates with the server

1. Game top/profile bootstrap (`gametop.regist`, `gametop.get_info`, `gametop.get_pdata`).
2. Score payload retrieval (`gametop.get_mdata`).
3. Match/lobby polling (`lobby.*`, `gametop.get_meeting`).
4. Session finalization and persistence (`gameend.final`, `gameend.regist`).
5. Shop/cabinet registration and logging (`shopinfo.regist`, `netlog.send`, `logger.report`).

## Main stored data domains

- `profile`
- `score`
- `course`
