# Pop'n Music (`popn@asphyxia`)

## Game codes

- `K39` (Tune Street)
- `L39` (Fantasia)
- `M39` (Sunny Park)

Also includes modular route registration for later versions:

- Lapistoria (`info22.*`, `player22.*`)
- Éclale (`info23.*`, `player23.*`)
- Usaneko (`info24.*`, `player24.*`)

## Registered game endpoints

### Shared/base routing

- `game.get`
- `playerdata.new`
- `playerdata.conversion`
- `playerdata.get`
- `playerdata.set`
- `playerdata.friend`
- `playerdata.town`

### Lapistoria routes

- `info22.common`
- `player22.new`
- `player22.read`
- `player22.write_music`
- `player22.write`
- `player22.friend`

### Éclale routes

- `info23.common`
- `player23.new`
- `player23.read`
- `player23.start`
- `player23.buy`
- `player23.read_score`
- `player23.write_music`
- `player23.write`
- `player23.friend`

### Usaneko routes

- `info24.common`
- `player24.new`
- `player24.read`
- `player24.start`
- `player24.buy`
- `player24.read_score`
- `player24.write_music`
- `player24.write`
- `player24.friend`

## WebUI events

- `updatePnmPlayerInfo`
- `deleteRival`
- `addRival`

## How the game communicates with the server

1. Version-dependent common/profile routes are selected by game version.
2. Profile create/load/update endpoints are used per version family.
3. Song score read/write endpoints are used for music records.
4. Friend/rival endpoints exchange rival lists and score snapshots.
5. Later versions include additional `start` and `buy` flows.

## Main stored data domains

- `profile`
- `scores`
- `rivals`
- achievements/params/extra version-specific state
