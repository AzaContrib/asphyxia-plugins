# Asphyxia Plugins Documentation

This folder documents how each plugin in this repository works, how each game talks to Asphyxia Core, and which API endpoints each game expects.

## Repository-level architecture

All plugins follow the same pattern:

- `register()` is the plugin entry point.
- `R.GameCode(...)` binds one or more game codes.
- `R.Route(endpoint, handler)` registers e-amusement/game API endpoints.
- `R.WebUIEvent(event, handler)` registers WebUI-side actions.
- Handlers read request data with `$(data)` and return typed XML-like payloads with `K.ITEM`, `K.ARRAY`, `K.ATTR`, and `send.object(...)`.
- Persistent game state is stored with `DB.Find/FindOne/Upsert/Update` in collection-based documents.

## Common communication flow

Most games follow this lifecycle:

1. **Boot / common**: client requests cabinet/server metadata and event phases.
2. **Card/profile check**: client loads or creates profile by `refid`.
3. **Score/profile load**: client pulls profile options and score records.
4. **Play**: client may send per-stage or per-song updates.
5. **Save**: client writes profile, scores, and feature-specific progress.
6. **Auxiliary endpoints**: logging, lobby/match, ranking, shop, etc.

## Per-game docs

- [BeatStream (`bst@asphyxia`)](./bst.md)
- [DDR (`ddr@asphyxia`)](./ddr.md)
- [Gitadora (`gitadora@asphyxia`)](./gitadora.md)
- [IIDX (`iidx@asphyxia`)](./iidx.md)
- [jubeat (`jubeat@asphyxia`)](./jubeat.md)
- [MGA (`mga@asphyxia`)](./mga.md)
- [MÚSECA (`museca@asphyxia`)](./museca.md)
- [Nostalgia (`nostalgia@asphyxia`)](./nostalgia.md)
- [Pop'n Hello (`popn-hello@asphyxia`)](./popn-hello.md)
- [Pop'n Music (`popn@asphyxia`)](./popn.md)
- [SOUND VOLTEX (`sdvx@asphyxia`)](./sdvx.md)

## Endpoint registration patterns by plugin

- **Single explicit routes**: `bst`, `ddr`, `jubeat`, `popn-hello`, `mga`
- **Route-prefix helpers**: `museca` (`game_3.*`), `sdvx` (`game.sv6_*`), `nostalgia` (`op2_` prefix), `gitadora` (many version prefixes), `iidx` (`IIDX21..IIDX32` prefixes)
- **Mixed by version module**: `popn` (shared base routes plus `player22/23/24.*` module routes)

## Notes

- Endpoint names are the effective API contract used by clients.
- Several plugins intentionally return static/dummy values for unimplemented features (often with `true` route passthroughs or simple success responses).
- WebUI events are admin-side operations and not direct game-client endpoints, but are included in per-game docs where important.
