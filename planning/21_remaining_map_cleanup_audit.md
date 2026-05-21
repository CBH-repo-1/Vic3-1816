# Remaining Map Cleanup Audit

## Scope

This pass reviewed the approved cleanup items that were still listed after the South America and Caribbean implementation.

## Safe No-Op Items

These items already match the approved 1816 first-pass setup in the current base game files, so no state override was added:

- `STATE_AZORES`: direct `POR`
- `STATE_MADEIRA`: direct `POR`
- `STATE_CAPE_VERDE`: direct `POR`
- `STATE_CANARY_ISLANDS`: direct `SPA`
- `STATE_BALEARIC_ISLANDS`: direct `SPA`
- `STATE_CORSICA`: direct `FRA`
- `STATE_CYPRUS`: direct `TUR`
- `STATE_SOUTH_ATLANTIC_ISLANDS`: direct `GBR`
- `STATE_CEYLON`: `BCE` owns Ceylon, `MLD` owns Maldives, and `BCE` already has a vanilla `GBR` colony pact.
- Dutch East Indies and island Southeast Asia: vanilla already has `NET -> DEI`, `DEI` in Java/Sumatra/Borneo/eastern holdings, and local tags such as `ACE`, `BAL`, `BRU`, `BNJ`, `TID`, `YOG`, and `SRK` represented.

Previously implemented cleanup already covers:

- `STATE_CRETE` moved back to `TUR`.
- `STATE_WEST_AEGEAN_ISLANDS` moved back to `TUR`.
- `STATE_MALTA` moved to playable `MLT` under `GBR`.
- `STATE_RYUKYU_ISLANDS` moved to playable `V07`.
- `STATE_SANTO_DOMINGO`, `STATE_JAMAICA`, `STATE_BAHAMAS`, and the Venezuela-linked West Indies province were handled in the Caribbean pass.

## Resolved Design-Dependent Item

The southeastern Native review was approved and implemented after this audit:

- `V08` Choctaw Nation
- `V09` Chickasaw Nation

Both tags are defined, localized, have starter country history, and now own land. The approved first-pass compromise keeps the split entirely inside `STATE_MISSISSIPPI`: `V09` owns the northern band and `V08` owns the central/southern band. `STATE_ALABAMA` and `STATE_TENNESSEE` were left untouched for the first pass.

## Not Part Of This Cleanup

The detailed India/Maratha/BIC backdate remains a larger dedicated map pass, not a leftover cleanup no-op. The Central Provinces and first deeper Third Anglo-Maratha War settlement cleanup are now implemented in `planning/22_india_maratha_accuracy_pass.md`; remaining India work is the combined Sikh/Punjab/Kashmir, Assam/frontier, and Gujarat/Kathiawar cleanup pass.
