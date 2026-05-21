# Starting Building Level Rebalance Plan

## Scope

This pass should rebalance inherited 1836 starting building levels for the 1816 start.

It should not change state-region resource potentials. That policy is recorded in `planning/30_state_resources_policy.md`.

## Current Inventory

Parsed mod building-history overrides currently contain:

- 2,979 starting building entries.
- 8,212 total building levels.
- 15 regional files under `common/history/buildings`.

Current total levels by broad category:

| Category | Levels |
| --- | ---: |
| Agriculture and plantations | 3,192 |
| Institutions and trade | 1,205 |
| Manufacturing | 1,129 |
| Military barracks | 1,107 |
| Logging, fishing, whaling, and similar extraction | 839 |
| Mines | 323 |
| Ports and infrastructure | 309 |
| Construction sectors | 83 |
| Monuments | 17 |
| Urban services | 8 |

Largest owner totals:

| Owner | Pop | Levels | Levels per million pops |
| --- | ---: | ---: | ---: |
| `CHI` | 381,000,000 | 1,035 | 2.7 |
| `GBR` | 20,060,980 | 593 | 29.6 |
| `FRA` | 30,911,097 | 522 | 16.9 |
| `RUS` | 45,800,000 | 503 | 11.0 |
| `USA` | 8,939,828 | 432 | 48.3 |
| `BIC` | 132,123,571 | 323 | 2.4 |
| `TUR` | 18,500,000 | 276 | 14.9 |
| `JAP` | 31,000,000 | 243 | 7.8 |
| `PRU` | 10,349,031 | 207 | 20.0 |
| `SPA` | 12,487,043 | 196 | 15.7 |

The largest obvious pressure points are 1836-style USA density, industrialized Britain/Prussia/France levels, construction sectors, and active buildings whose owner does not have the required starting technology.

## Obvious Technical Cleanup Candidates

These building types are present at start but do not fit the current 1816 tech package for their owners:

| Building | Current levels | Proposed treatment |
| --- | ---: | --- |
| `building_chemical_plant` | 6 | Remove from start |
| `building_explosives_factory` | 4 | Remove from start |
| `building_munition_plant` | 8 | Remove from start |
| `building_motor_industry` outside `GBR` | 1 | Remove from start |

The remaining `GBR` `building_motor_industry` represents early engine works and can be scaled down rather than removed, because Britain already has the approved `atmospheric_engine` exception.

`building_steel_mill` is not a pure tech mismatch because `steelworking` is part of the approved early tech package, but its levels should still be scaled down with other manufacturing.

## Recommended Rule Set

Use a reproducible data-driven scaler instead of hand-adjusting every state.

1. Compare each current owner tag's 1816 mod population to its vanilla 1836 population when that vanilla owner exists.
2. Use that ratio as an owner-level backdating factor, capped at 1.00 so no building levels increase in this pass.
3. For new or heavily repurposed owners without a clean vanilla comparison, use a conservative fallback factor of 0.85.
4. Apply a sector multiplier:

| Category | Multiplier |
| --- | ---: |
| Agriculture and plantations | 0.90 |
| Logging, fishing, whaling, and similar extraction | 0.85 |
| Mines | 0.85 |
| Manufacturing | 0.65 |
| Institutions and trade | 0.80 |
| Ports and infrastructure | 0.85 |
| Construction sectors | 0.60 |
| Urban services | 0.75 |
| Monuments | 1.00 |
| Military barracks | 1.00 for now |

5. Round to the nearest integer.
6. Preserve a minimum of 1 level for any building that is not explicitly removed.
7. Do not touch military barracks in this pass; army sizing should be handled with the dedicated military formations/barracks pass.

## Expected Effect If Approved

This rule set would change total starting building levels from 8,212 to about 6,715, a reduction of 1,497 levels.

Expected category effects:

| Category | Before | After | Delta |
| --- | ---: | ---: | ---: |
| Agriculture and plantations | 3,192 | 2,747 | -445 |
| Manufacturing | 1,129 | 703 | -426 |
| Institutions and trade | 1,205 | 894 | -311 |
| Logging, fishing, whaling, and similar extraction | 839 | 675 | -164 |
| Mines | 323 | 233 | -90 |
| Ports and infrastructure | 309 | 278 | -31 |
| Construction sectors | 83 | 55 | -28 |
| Urban services | 8 | 6 | -2 |
| Military barracks | 1,107 | 1,107 | 0 |
| Monuments | 17 | 17 | 0 |

Largest expected owner reductions:

| Owner | Before | After | Delta |
| --- | ---: | ---: | ---: |
| `GBR` | 593 | 370 | -223 |
| `USA` | 432 | 240 | -192 |
| `CHI` | 1,035 | 868 | -167 |
| `RUS` | 503 | 353 | -150 |
| `FRA` | 522 | 388 | -134 |
| `PRU` | 207 | 118 | -89 |
| `AUS` | 179 | 113 | -66 |
| `EGY` | 81 | 35 | -46 |
| `BIC` | 323 | 280 | -43 |
| `TUR` | 276 | 247 | -29 |

This preserves the relative shape of the vanilla economy while pulling it back toward the smaller 1816 population base and less-developed early industrial economy.

## Implementation

The user approved this rule set and it was implemented in `common/history/buildings`.

Actual validated result:

- Building entries: 2,981 -> 2,968.
- Total levels: 8,212 -> 6,718.
- Ownership-driven levels: 8,195 -> 6,699.
- Monument or direct `level` fields: 19 unchanged.
- Removed approved tech-inconsistent building blocks: 13.

Actual post-pass category totals:

| Category | Levels |
| --- | ---: |
| Agriculture and plantations | 2,747 |
| Military barracks | 1,107 |
| Institutions and trade | 895 |
| Manufacturing | 703 |
| Logging, fishing, whaling, and similar extraction | 675 |
| Ports and infrastructure | 278 |
| Mines | 233 |
| Construction sectors | 55 |
| Monuments | 19 |
| Urban services | 6 |

Validation:

- No brace parse issues.
- No nonpositive building-level totals.
- No `levels=0` or `level=0` leftovers.
- No `building_chemical_plant`, `building_explosives_factory`, or `building_munition_plant` start buildings remain.
- The only remaining `building_motor_industry` is the approved British early-engine-work abstraction in Yorkshire.
- Previously banned railway and era-2 PM tokens remain absent.

## Next Step

The next pass should be the approved dedicated military pass:

- Audit barracks and naval-base starting levels.
- Compare country military capacity to the 1816 political/military situation.
- Decide whether to scale barracks by population, by historical army establishment, or by a hybrid rule.
- Keep this separate from the civilian economy pass so army balance can be tuned deliberately.
