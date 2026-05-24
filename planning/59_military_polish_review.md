# Military Polish Review

## Scope

This review follows the worldwide economy polish pass. It checks the current 1816 military setup for:

- military formation file health
- late/anachronistic unit references
- formation placement mismatches after the map rewrites
- barracks/naval/arms-building support
- playable countries that have military buildings but no starting formation

The approved implementation package is now applied.

## Validation Snapshot

- Military formation countries: 129
- Formation units: 2,883 army / 527 fleet
- Explicit military building levels:
  - `building_barrack`: 890
  - `building_military_shipyard`: 22
  - `building_arms_industry`: 50
  - `building_artillery_foundry`: 12
- No brace mismatches found in the military formation files.
- No late unit or PM tokens found in military formations:
  - `skirmish_infantry`
  - `trench_infantry`
  - `squad_infantry`
  - `shrapnel_artillery`
  - `siege_artillery`
  - `ironclad`
  - `monitor`
  - `torpedo_boat`
  - `submarine`
  - `dreadnought`
  - `aeroplane`
  - `carrier`
  - `pm_power_of_the_purse`
- No `building_naval_base` history entries were found.

## Definite Structural Findings

### Baltic Formation Mismatch

The only formation placement mismatch found is stale `UBD` military history:

| Tag | State | Current owner | Units |
| --- | --- | --- | ---: |
| `UBD` | `STATE_TALINN` | `RUS` | 3 army |
| `UBD` | `STATE_RIGA` | `RUS` | 2 army |
| `UBD` | `STATE_COURLAND` | `RUS` | 1 army |

Recommended fix: fold these 6 army units into Russia or remove them. Folding them into Russia is more consistent with the earlier Baltic building cleanup.

### USA Ahistorical Fleet Blocks

`common/history/military_formations/01_military_formations_north_america.txt` still contains three USA naval `# Ahistorical` blocks. Current USA start:

- 11 army
- 21 fleet
- 15 frigates
- 6 man-o-wars

Recommended fix: remove the explicitly marked ahistorical frigates and leave the historically grounded wooden navy.

## Balance / Flavor Findings Needing Approval

### Countries With Barracks But No Formation

The pass found many playable countries with barracks but no starting army formation. The highest-priority cases are:

| Tag | Country | Barracks |
| --- | --- | ---: |
| `JAP` | Japan | 30 |
| `KOR` | Korea | 30 |
| `SIA` | Siam | 30 |
| `DAI` | Dai Nam | 30 |
| `NEP` | Nepal | 30 |
| `MOR` | Morocco | 27 |
| `SC3` | Peru | 20 |
| `SOK` | Sokoto | 20 |
| `BUK` | Bukhara | 20 |
| `KOK` | Kokand | 20 |
| `KHI` | Khiva | 20 |
| `TIB` | Tibet | 18 |
| `TRI` | Tripolitania | 15 |
| `TUN` | Tunis | 13 |
| `SWI` | Switzerland | 10 |
| `GUA` | Guatemala | 8 |

Recommended fix: create simple starting formations for playable countries with meaningful barracks, prioritizing the list above. Use mostly `irregular_infantry` for unrecognized countries, line infantry for recognized European/American states where appropriate, and keep the counts conservative rather than matching every barracks level one-for-one.

### Native North America

`COM` and `LKT` are intended playable starts through country history overrides, but both currently have:

- 0 army
- 0 barracks
- 0 fleet

Recommended fix: add very small formations for playability:

- `COM`: 2 hussars + 1 irregular infantry
- `LKT`: 1 hussar + 1 irregular infantry

This keeps them playable without giving them a conventional state army.

### Major Power Outliers

The largest current starts are:

| Tag | Country | Army | Fleet | Note |
| --- | --- | ---: | ---: | --- |
| `CHI` | China | 485 | 15 | Huge, but all irregular/hussar/fleet and intentionally low-tech. |
| `GBR` | Great Britain | 105 | 161 | Main naval hegemon. |
| `RUS` | Russia | 179 | 73 | Large European land power. |
| `FRA` | France | 150 | 100 | Still very strong after the Napoleonic Wars. |
| `BIC` | East India Company | 208 | 1 | Company armies remain very large. |
| `TUR` | Ottoman Empire | 162 | 33 | Mixed irregular/line setup. |
| `AUS` | Austria | 129 | 5 | Large but plausible post-Vienna land power. |
| `PRU` | Prussia | 128 | 1 | Large but plausible post-Vienna land power. |
| `PAN` | Punjab | 86 | 0 | Strong Sikh start. |

Recommended fix: leave the major-power army totals alone for this pass, except for the small Baltic/Russia decision above. The biggest visible oddity is less "too much army" and more "some important playable countries have barracks but no formation."

## Recommended Implementation Package

Approved and implemented in this order:

1. Fix the stale `UBD` Baltic formations by folding them into Russia.
2. Remove the USA naval blocks already marked `# Ahistorical`.
3. Add conservative formations for high-priority playable countries with barracks but no army.
4. Add tiny Comanche and Lakota formations for playability.
5. Re-run validation for brace balance, banned unit tokens, owner placement mismatches, and source/live copy parity.

## Implemented Changes

- Folded the stale `UBD` Baltic formation units into `RUS`:
  - `STATE_TALINN`: 3 line infantry
  - `STATE_RIGA`: 2 line infantry
  - `STATE_COURLAND`: 1 lancer
- Removed the now-empty `UBD` start formation.
- Removed the three USA naval combat-unit blocks explicitly marked `# Ahistorical`, reducing `USA` fleet from 21 to 16.
- Added a new military polish formation file:
  - `common/history/military_formations/99_cow_1816_military_polish_formations.txt`
- Added conservative starting armies:
  - `JAP`: 18 irregular infantry
  - `KOR`: 16 irregular infantry
  - `SIA`: 15 irregular infantry, 3 hussars
  - `DAI`: 15 irregular infantry, 2 hussars
  - `NEP`: 18 irregular infantry
  - `MOR`: 15 irregular infantry, 4 hussars
  - `SC3`: 10 line infantry, 2 hussars, 1 cannon artillery
  - `SOK`: 12 irregular infantry, 4 hussars
  - `BUK`: 12 irregular infantry, 3 hussars
  - `KOK`: 10 irregular infantry, 4 hussars
  - `KHI`: 8 irregular infantry, 4 hussars
  - `TIB`: 12 irregular infantry, 2 hussars
  - `TRI`: 8 irregular infantry, 2 hussars
  - `SWI`: 7 line infantry
  - `GUA`: 6 line infantry, 1 hussar
  - `COM`: 2 hussars, 1 irregular infantry
  - `LKT`: 1 hussar, 1 irregular infantry
- Added a Tunis army directly to `03_military_formations_north_africa.txt`:
  - `TUN`: 8 irregular infantry, 2 hussars

## Post-Implementation Validation

- Military formation files: 10
- Formation units: 3,112 army / 522 fleet
- Brace problems: 0
- Banned late unit or naval-base tokens: 0
- `# Ahistorical` formation markers remaining: 0
- Formation owner-placement mismatches: 0
- `UBD` formation units remaining: 0
