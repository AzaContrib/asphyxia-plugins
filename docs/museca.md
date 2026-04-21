# MÚSECA (`museca@asphyxia`)

## Game codes

- `PIX`

## Route-prefix strategy

A helper registers all routes as `game_3.<method>`.

## Registered game endpoints

- `game_3.common`
- `game_3.shop`
- `game_3.exception`
- `game_3.hiscore`
- `game_3.lounge`
- `game_3.frozen`
- `game_3.play_e`
- `game_3.new`
- `game_3.save`
- `game_3.save_m`
- `game_3.load`
- `game_3.load_m`

## How the game communicates with the server

1. Client fetches common metadata/song unlock state (`game_3.common`).
2. New/existing profile lifecycle uses (`game_3.new`, `game_3.load`, `game_3.save`).
3. Score lifecycle uses (`game_3.load_m`, `game_3.save_m`).
4. Non-core endpoints (`shop`, `lounge`, `hiscore`, `exception`, `frozen`) return lightweight responses.

## Main stored data domains

- `profile`
- `scores`

## Notes

- Supports optional custom MDB and force song unlock behavior.
