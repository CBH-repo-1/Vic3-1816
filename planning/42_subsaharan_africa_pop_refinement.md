# Sub-Saharan Africa Population Refinement Audit

Status: approved cleanup implemented.

## Scope

This pass reviewed Sub-Saharan Africa and the Nile/Horn follow-through from the MENA cleanup, focusing on obvious 1816 mismatches rather than trying to redesign every decentralized/local polity.

Files reviewed:

- `common/history/pops/03_north_africa.txt`.
- `common/history/pops/04_subsaharan_africa.txt`.
- `common/history/states/00_states.txt`.
- Africa planning notes `06_africa_inventory.md` and `16_africa_map_implementation.md`.

## Current Safety Checks

- The broad Africa scaling target is still mechanically stable after the MENA pass.
- No zero or negative pop sizes were found during the current validation pass.
- The main Africa map/pop alignment appears mechanically clean enough for this stage.

## Current Snapshot

Major African owner totals include:

- `SOK`: 5,670,280.
- `MOR`: 3,389,218.
- `IBO`: 2,450,570.
- `MAD`: 2,029,507.
- `BEN`: 1,752,574.
- `OYO`: 1,646,253.
- `SUD`: 1,581,063.
- `ZAN`: 1,292,242.
- `ASH`: 1,241,276.
- `SAF`: 653,382.
- `ZUL`: 315,357.

The fragmentation choices for Ethiopia, Sudan/Darfur, Sokoto, Oyo/Dahomey, Zanzibar/Omani coast, Cape Colony, Zulu, and Madagascar are broadly consistent with the approved Africa plan.

## Implemented Corrections

### 1. French Cote d'Ivoire Was Too Early

`FRA` previously owned the port province in `STATE_IVORY_COAST`:

- `STATE_IVORY_COAST`, `FRA`: 91,923.

This is not a good January 1, 1816 fit. French protectorate/occupation around Assinie and Grand-Bassam belongs to the 1840s, not 1816.

Implemented correction:

- Moved the `FRA` `STATE_IVORY_COAST` province `xA0BFCF` to `AYI`.
- Removed the matching `region_state:FRA` pop bucket.
- Folded its Akan population into the existing `AYI` bucket.
- `AYI` now has 183,845 total pops in `STATE_IVORY_COAST`.
- Kept France in Senegal, where French posts are already an approved 1816 abstraction.

Why `AYI`:

- The French province is the port in the southeastern Cote d'Ivoire state.
- `AYI` is already present in the same state and is the cleanest local Akan/Anyi-side holder for that coastal piece.

### 2. Fernando Po/Bioko Was Still a British/Sierra Leone Bucket

`SIL` previously owned one province in `STATE_SOUTH_CAMEROON`:

- Province `x902089`.
- Base-game files identify this province in Fernando Po/Bioko-related events and decisions.
- `STATE_SOUTH_CAMEROON`, `SIL`: 6,893.

This is later than our start. Spain received Fernando Po/Bioko in 1778, while the British anti-slave-trade lease begins in 1827.

Implemented correction:

- Moved province `x902089` from `SIL` to `SPA`.
- Replaced the matching `SIL` pop bucket in `STATE_SOUTH_CAMEROON` with a `SPA` bucket.
- Replaced the explicitly later British/liberated-African flavor in that bucket with a local island population abstraction:
  - `equatorial_bantu`: 6,843.
  - `spanish`: 50.
- Kept the total population unchanged at 6,893.

This keeps the island small, Spanish-owned, and free of post-1827 British settlement flavor.

Final focus totals after implementation:

- `AYI`, `STATE_IVORY_COAST`: 183,845.
- `POR`, `STATE_SOUTH_CAMEROON`: 16,349.
- `SPA`, `STATE_SOUTH_CAMEROON`: 6,893.

## Leave Alone For Now

- `SIL` in `STATE_SIERRA_LEONE` stays as the playable British colony.
- `SIL` in `STATE_SENEGAL` and `STATE_GOLD_COAST` is awkwardly named, but it is currently acting as a small British West African coastal-post abstraction. I recommend leaving it alone until a dedicated British West Africa pass, because changing it cleanly is more design-sensitive than this first Africa refinement.
- `ZUL` stays at 315,357 for now. It is probably generous for strict 1816 Zulu power, but it supports the user's explicit playable-Zulu goal and avoids another map-size debate.
- `MAD` stays as the whole-island Merina/Imerina abstraction for now, per the approved Africa plan.
- `ZAN` stays as the Omani/Swahili coast abstraction for now.

## Validation

- `common/history/states/00_states.txt`: brace depth 0, minimum depth 0, UTF-8 BOM present.
- `common/history/pops/04_subsaharan_africa.txt`: brace depth 0, minimum depth 0, UTF-8 BOM present.
- Global owner/pop alignment after the edit: 770 owner pairs, 1,069 pop pairs, 0 missing owner pop pairs.
- Global pop size check: 0 nonpositive pop sizes.

## Sources Checked

- Britannica on Cote d'Ivoire: French protectorate relationships and colonial claim are later than 1816.
- 1911 Britannica / Wikisource on Ivory Coast: French cessions at Assini and Grand Bassam were obtained in 1842 and occupied in 1843.
- Britannica on Equatorial Guinea: Portugal ceded Fernando Po/Bioko and Annobon to Spain in 1778; the Spanish lease to Britain begins in 1827.
- Base-game files identify province `x902089` in Fernando Po-related decisions/events.

## Approved And Implemented

The user approved this focused Sub-Saharan Africa cleanup:

- Move `STATE_IVORY_COAST`'s `FRA` province and pops to `AYI`.
- Move `STATE_SOUTH_CAMEROON` province `x902089` and its `SIL` pops to `SPA`.
- Replace the `SIL` Fernando Po pop composition with `equatorial_bantu` 6,843 and `spanish` 50.
- Leave the rest of Africa alone for this pass.
