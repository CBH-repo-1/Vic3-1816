# Bug Cleanup Static QA

## Scope

This pass cleaned mechanical startup risks found after the first GitHub baseline. It avoided new historical design changes except removing 1836 vanilla startup content that referenced countries absent from the 1816 start.

## Static Checks

- Active state/country owner pairs: 1,072
- Active start tags: 413
- Duplicate state/country owner pairs: 0
- Province-owning state/country pairs without pop blocks: 0
- Stale pop region-state pairs: 0
- Stale building region-state pairs: 0
- Stale military formation placement pairs: 0
- Active-code brace problems: 0
- Active country definitions/history/localization/adjective localization gaps: 0

Remaining inactive `c:TAG` references are only in `common/history/states/00_states.txt`, where they are claim or claim-removal hooks for non-start/releasable countries.

## Fixes

- Closed missing final braces in `common/history/characters/swe - sweden.txt`.
- Disabled vanilla 1836 diplomatic plays for:
  - First Carlist War
  - Texas War of Independence
  - Ragamuffin War
  - Cabanagem War
- Removed the matching forced military deployments for inactive or disabled wars:
  - `MEX`, `TEX`, `BRZ`, `PRA`, `PNI`, `SPC`, and the Carlist-specific `SPA` deployment.
- Removed treaty blocks referencing inactive start tags:
  - `BEL`
  - `TEX`
  - `ORA`
  - `TRN`

## Deferred

Future-dated treaties between active countries were left in place for the dedicated diplomacy/laws pass. They are not a startup-reference bug, but many probably need an 1816 historical review.
