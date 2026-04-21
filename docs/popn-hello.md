# Pop'n Hello (`popn-hello@asphyxia`)

## Game codes

- `JMP`

## Registered game endpoints

- `game.common`
- `game.shop`
- `game.new`
- `game.load`
- `game.load_m`
- `game.save`
- `game.save_m`

## WebUI events

- `setUnlockState`

## How the game communicates with the server

1. Client loads common/shop state (`game.common`, `game.shop`).
2. Profile lifecycle (`game.new`, `game.load`, `game.save`).
3. Score lifecycle (`game.load_m`, `game.save_m`).

## Main stored data domains

- `profile` (unlock state, character affinity, play history)
- `scores` (music/style/level indexed clear + score)
