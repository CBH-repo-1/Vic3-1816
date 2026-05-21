# Dedicated Military Pass Audit

## Scope

This pass should align the 1816 start with:

- military formations loaded from `common/history/military_formations`
- explicit barracks in `common/history/buildings`
- the already-approved 1816 technology tier rebalance
- the already-implemented 1816 map ownership changes

This pass is now implemented.

## Implemented After Approval

The user approved the recommended conservative hybrid cleanup.

Implemented formation-file control:

- Copied the remaining vanilla regional military formation files into the mod:
  - `03_military_formations_north_africa.txt`
  - `04_military_formations_middle_east.txt`
  - `05_military_formations_india.txt`
  - `06_military_formations_asia.txt`
  - `07_military_formations_subsaharan_africa.txt`

Implemented unit-tech cleanup:

- Downgraded all `skirmish_infantry` where the country lacks `general_staff`.
- Downgraded `line_infantry`, `lancers`, `dragoons`, `cuirassiers`, `mobile_artillery`, and `cannon_artillery` where the country's starting tech package does not support that unit type.
- Removed starting `pm_power_of_the_purse` naval-base activations.

Implemented targeted placement cleanup:

- Backdated Egypt by removing the 1836 Levant/Sudan expeditionary deployment and reducing the Egyptian start army/navy.
- Moved the vanilla Algerian formation from `MAS` to the 1816 `ALD` abstraction.
- Moved the Dutch East Indies unit previously placed in `STATE_SOUTH_SUMATRA` back to Java after the outer-island direct-rule shrink.

Implemented barracks cleanup:

- Capped oversized barracks-only starts by starting military tech tier:
  - tier 1-4: cap 30 explicit barracks
  - tier 5: cap 20 explicit barracks
  - tier 6: cap 10 explicit barracks
  - tier 7: cap 5 explicit barracks
- Reduced explicit barracks totals from 1,107 to 892.
- The cap affected `SGU`, `SOK`, `ASH`, `MAD`, `ZUL`, `NEP`, `SIA`, `DAI`, and `JAP`.

Implemented playable-country support:

- Added a simple Zulu starting formation in `STATE_ZULULAND` so `ZUL` is playable with a visible army rather than relying only on buildings.

## Final Validation

The mod now overrides every vanilla regional military formation file:

- `00_military_formations_europe.txt`
- `01_military_formations_north_america.txt`
- `02_military_formations_south_america.txt`
- `03_military_formations_north_africa.txt`
- `04_military_formations_middle_east.txt`
- `05_military_formations_india.txt`
- `06_military_formations_asia.txt`
- `07_military_formations_subsaharan_africa.txt`

The mod also adds:

- `05_cow_1816_india_formations.txt`

Final effective formation totals:

- Formation countries: 129
- Army units: 2,951
- Fleet units: 527
- Explicit barracks levels: 892

Final validation checks:

- No brace mismatches were found in military formation or building history files.
- No `combat_unit_type_skirmish_infantry` references remain.
- No `pm_power_of_the_purse` references remain in military formation files.
- No invalid unit-vs-starting-tech combinations remain under the approved starting tech tier rules.
- No explicit barracks-only country remains over its approved cap.
- Egypt no longer has formation placements in Syria, Palestine, Lebanon, Dongola, Blue Nile, or Kordofan.
- The Dutch East Indies formation no longer places units in `STATE_SOUTH_SUMATRA`.

Largest final formation starts:

| Tag | Army | Fleet | Notes |
| --- | ---: | ---: | --- |
| `CHI` | 485 | 15 | Large vanilla-style Qing start retained but unit-tech compatible. |
| `RUS` | 247 | 73 | Smaller than vanilla Russia's 274 army / 73 fleet block; earlier 179 audit figure was an undercount. |
| `GBR` | 105 | 161 | Wooden navy retained; no era 2 naval PM start. |
| `FRA` | 150 | 100 | Backdated to line infantry, retaining major-power strength. |
| `BIC` | 208 | 1 | India formation retained but unit-tech compatible after the Maratha/Company map pass. |
| `TUR` | 162 | 33 | Ottoman formation retained and unit-tech compatible. |
| `AUS` | 129 | 5 | Habsburg formation retained and unit-tech compatible. |
| `PRU` | 128 | 1 | Prussian formation retained and unit-tech compatible. |
| `PAN` | 86 | 0 | Punjab/Sikh formation retained and unit-tech compatible. |
| `SPA` | 59 | 9 | Spanish formation retained and unit-tech compatible. |
