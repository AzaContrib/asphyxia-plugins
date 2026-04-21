# MGA (`mga@asphyxia`)

## Game codes

- `I36`

## Registered game endpoints

- `eventlog.write`
- `system.getmaster`
- `playerdata.usergamedata_send`
- `playerdata.usergamedata_recv`
- `playerdata.usergamedata_scorerank`

## How the game communicates with the server

1. Startup master data is fetched via `system.getmaster`.
2. Player data blobs are uploaded (`playerdata.usergamedata_send`).
3. Player data blobs are downloaded (`playerdata.usergamedata_recv`).
4. Score rank endpoint currently returns a basic stub response.
5. Event logs are accepted via `eventlog.write`.

## Main stored data domains

- `data`: raw `str[]` and `bin[]` slots for player payload blocks
