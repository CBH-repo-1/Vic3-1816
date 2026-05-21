# Country Starting Technology Audit

This pass audits and implements country-specific starting technology and tier assignment cleanup after the 1816 generic tier rebalance.

Game-facing country history overrides have been implemented after approval.

## Implementation Note

There is no clear existing `remove_technology_researched` pattern in vanilla history files. For vanilla tags that need techs removed, use same-relative-path country history overrides in the mod instead of additive `c:TAG ?=` blocks.

Additive `c:TAG ?=` files remain useful for custom countries and extra setup, but they should not be relied on to erase vanilla country-history technology grants.

## Implemented Special Exceptions

Approved generic rule remains:

- Tier 1 gets full era 1.
- Tier 2 gets the advanced partial era 1 package.
- Tiers 3-7 remain vanilla for now.

Implemented country-specific 1816 exception:

- `GBR`: add `atmospheric_engine`.

Implemented removals from `GBR`:

- Remove `labor_movement`.
- Remove `joint_stock_companies`.

Reasoning: Britain should lead in practical steam power, but the broader labor-movement and joint-stock-company techs are better left to early-game research.

## Implemented Era 2 Cleanup

Removed individual non-era-1 grants from these vanilla country histories:

| Tag | Remove |
| --- | --- |
| `AUS` | `central_archives`, `railways` |
| `BAV` | `intensive_agriculture`, `railways` |
| `BIC` | `mechanical_tools`, `atmospheric_engine`, `railways`, `corporate_charters` |
| `BRA` | `railways` |
| `CUB` | `atmospheric_engine`, `mechanical_tools`, `railways` |
| `DEN` | `dialectics` |
| `GBR` | `labor_movement`, `joint_stock_companies`; add `atmospheric_engine` |
| `HAW` | `egalitarianism` |
| `KRA` | `dialectics` |
| `POR` | `atmospheric_engine` |
| `PRG` | `egalitarianism`, `central_archives` |
| `RUS` | `corporate_charters`, `fractional_distillation` |
| `SAX` | `railways` |
| `SPA` | `atmospheric_engine` |
| `SPC` | `atmospheric_engine` |
| `SWE` | `dialectics` |
| `SWI` | `dialectics` |

Implemented stricter cleanup:

- `CUB`: also remove `lathe`, because the vanilla line appears tied to the 1834-1837 railway setup rather than an 1816 condition.

## Implemented Tier Assignment Cleanup

Keep tier 1 for now:

- `GBR`
- `FRA`
- `PRU`
- `USA`

Question to revisit later:

- `USA` could be downgraded to tier 2 if we decide industrial accuracy should matter more than giving the player-facing United States a strong start. For now, keeping it tier 1 is the simpler gameplay-friendly choice.

Keep tier 2 for recognized European advanced states and German minors:

- Austria, Prussia-adjacent German minors, Denmark, Sweden, Switzerland, Netherlands, Sardinia-Piedmont, Finland, Norway, etc.
- Custom Saxon duchies `V04` and `V05`.

Implemented downgrades from tier 2 to tier 3:

| Tag | Reason |
| --- | --- |
| `BCE` | Colonial Ceylon should not have the same independent tech profile as advanced European states. |
| `HBC` | Hudson's Bay Company is administratively European but not an advanced state economy. |
| `NBS` | British North American colony; use tier 3 like Newfoundland. |
| `NVS` | British North American colony; use tier 3 like Newfoundland. |
| `ONT` | British North American colony; use tier 3 like Newfoundland. |
| `QUE` | British North American colony; use tier 3 like Newfoundland. |
| `NSW` | Australian colony; use tier 3 unless we want it to inherit metropolitan tech more aggressively. |
| `SAF` | Cape Colony/South Africa start; use tier 3. |

Likely absent/later tags that can be ignored for now:

- `BEL`
- `ORG`
- `SAS`
- `TAS`
- `WAS`

Implemented design calls:

- `BIC` and `DEI` stay tier 2 for now, but `BIC` has its era 2 freebies removed.
- `V03` Andorra moved from tier 2 to tier 3.

## Implemented Files

Same-name vanilla country history overrides were added under `common/history/countries/` for:

- `aus - austria.txt`
- `bav - bavaria.txt`
- `bce - ceylon.txt`
- `bic - british east india company.txt`
- `bra - braunschweig.txt`
- `cub - cuba.txt`
- `den - denmark.txt`
- `gbr - great britain.txt`
- `haw - hawaii.txt`
- `hbc - hudson bay company.txt`
- `kra - krakow.txt`
- `nbs - new brunswick.txt`
- `nsw - new south wales.txt`
- `nvs - nova scotia.txt`
- `ont - ontario.txt`
- `por - portugal.txt`
- `prg - paraguay.txt`
- `que - quebec.txt`
- `rus - russia.txt`
- `saf - south africa.txt`
- `sax - saxony.txt`
- `spa - spain.txt`
- `spc - carlist spain.txt`
- `swe - sweden.txt`
- `swi - switzerland.txt`

The custom country file `00_cow_1816_custom_countries.txt` was also updated to move `V03` Andorra to tier 3.

Validation passed:

- Removed tech grants are absent from the intended override files.
- `GBR` has `atmospheric_engine` and no longer has `labor_movement` or `joint_stock_companies`.
- Approved tier downgrades point to `effect_starting_technology_tier_3_tech`.
- Country-history brace depth is clean.
