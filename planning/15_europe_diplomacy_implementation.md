# Europe Diplomacy Implementation

This file records the first Europe subject/diplomacy layer scripted for the 1816 start.

## Scripted Files

- `common/history/diplomacy/99_cow_1816_europe_subjects.txt`
- `common/history/states/99_cow_1816_europe_states.txt`
- `common/history/countries/00_cow_1816_custom_countries.txt`

## Added Or Changed

| Relationship or setup | Scripted result | Notes |
| --- | --- | --- |
| Austrian Lombardy-Venetia | `AUS -> LOM` as `crown_land` | Uses the approved playable Lombardy-Venetia model. |
| British Malta | `GBR -> MLT` as `colony` | `MLT` is set to `colonial` country type in country history so the colony subject type is valid. |
| Congress Poland | `RUS -> POL` as `personal_union` | `STATE_GREATER_POLAND`, `STATE_LESSER_POLAND`, and `STATE_MAZOVIA` now belong to `POL`. |
| Krakow | Removed vanilla `AUS -> KRA` `puppet` pact | Krakow remains a free city landholder; joint protection/guarantee mechanics are deferred. |

## Vanilla Relationships Kept

Vanilla already has these approved relationships, so they were not duplicated in the mod file:

- `GBR -> HAN` personal union.
- `DEN -> HOL` personal union.
- `DEN -> SCH` personal union.
- `NET -> LUX` personal union plus Luxembourg own market.
- `SWE -> NOR` personal union.
- `RUS -> FIN` personal union.
- `GBR -> ION` protectorate.
- `TUR -> MOL`, `TUR -> WAL`, and `TUR -> SER` protectorates.
- `AUS -> HUN`, `AUS -> TRS`, and `AUS -> CRO` crown lands.

## Deferred

- Liberty desire tuning for `LOM`, `MLT`, `POL`, and `KRA`.
- Whether `POL`, `LOM`, or `MLT` should start with own-market pacts or specific subject-interaction pacts.
- Krakow's treaty/guarantee-style protection by Austria, Prussia, and Russia.
- Government, law, character, army, pop, and building setup for `POL`, `LOM`, and `MLT`.
