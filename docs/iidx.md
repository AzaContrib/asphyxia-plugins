# IIDX (`iidx@asphyxia`)

## Game codes

- `GLD`, `HDD`, `I00`, `JDJ`, `JDZ`, `KDZ`, `LDJ`

## Route-prefix strategy

A `MultiRoute` helper registers every route in these forms:

- `<method>`
- `IIDX21<method>` through `IIDX32<method>`

This provides one logical API set across many game versions.

## Registered endpoint groups

### PC/profile

- `pc.common`
- `pc.reg`
- `pc.get`
- `pc.getname`
- `pc.oldget`
- `pc.takeover`
- `pc.visit`
- `pc.save`
- `pc.shopregister`
- `pc.getLaneGachaTicket`
- `pc.drawLaneGacha`
- `pc.consumeLaneGachaTicket`

### Shop

- `shop.getname`
- `shop.savename`
- `shop.getconvention`
- `shop.setconvention`

### Music

- `music.crate`
- `music.getrank`
- `music.getralive`
- `music.appoint`
- `music.reg`
- `music.breg`
- `music.arenaCPU`

### Grade / ranking / system

- `grade.raised`
- `ranking.entry`
- `ranking.oentry`
- `ranking.getranker`
- `gamesystem.systeminfo`

## WebUI events

- `iidxGetProfile`
- `iidxGetSetting`
- `iidxUpdateRival`
- `iidxUpdateCustom`
- `iidxImportScoreData`
- `iidxExportScoreData`

## How the game communicates with the server

1. System and event metadata is loaded (`gamesystem.systeminfo`, `pc.common`).
2. Player identity/profile is created or loaded (`pc.reg`, `pc.get`, `pc.oldget`, `pc.takeover`).
3. Shop, rival, and ranking context are exchanged.
4. Song play data and ranking updates are posted (`music.*`, `grade.raised`, `ranking.*`).
5. Profile/options are persisted (`pc.save`).

## Main stored data domains

- profile and core pc data
- scores and ghosts
- grade/eisei/kiwami
- ranking/expert course data
- rival/custom/lightning settings
- event and auxiliary version-specific state
