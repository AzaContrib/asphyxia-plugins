# SOUND VOLTEX (`sdvx@asphyxia`)

## Game codes

- `KFC`

## Route-prefix strategy

A helper registers all game endpoints as:

- `game.sv6_<method>`

## Registered game endpoints

- `game.sv6_common`
- `game.sv6_new`
- `game.sv6_load`
- `game.sv6_load_m`
- `game.sv6_save`
- `game.sv6_save_m`
- `game.sv6_save_c`
- `game.sv6_frozen`
- `game.sv6_buy`
- `game.sv6_print`
- `game.sv6_hiscore`
- `game.sv6_load_r`
- `game.sv6_save_ap`
- `game.sv6_load_ap`
- `game.sv6_lounge`
- `game.sv6_shop`
- `game.sv6_save_e`
- `game.sv6_save_mega`
- `game.sv6_play_e`
- `game.sv6_play_s`
- `game.sv6_entry_s`
- `game.sv6_entry_e`
- `game.sv6_exception`
- `game.sv6_log`

Additional non-prefixed endpoints:

- `eventlog.write`
- `package.list`
- `ins.netlog`

## WebUI events

- `updateProfile`
- `updateMix`
- `importMix`
- `deleteMix`
- `easyHexa`
- `import_assets`
- `update_webui_nemsys`
- `update_webui_chat_stamp`
- `update_webui_subbg`
- `update_webui_bgm`
- `update_music_db`
- `getMusicDB`
- `getAssetData`

## How the game communicates with the server

1. Client loads common/event/music unlock metadata (`game.sv6_common`).
2. Profile lifecycle (`game.sv6_new`, `game.sv6_load`, `game.sv6_save`).
3. Score lifecycle (`game.sv6_load_m`, `game.sv6_save_m`, `game.sv6_save_c`).
4. Feature endpoints handle rivals/mixes/shop/lounge/printing and matching.
5. Logging and package/network utility endpoints support launcher/runtime behavior.

## Main stored data domains

- `profile`
- `music` (song records)
- `course`
- `mix`
- `item`
- `skill`
- `param`
