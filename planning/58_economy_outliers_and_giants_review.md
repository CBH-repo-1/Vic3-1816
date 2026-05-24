# Economy Outliers And Giants Review

This review follows the approved construction-sector and port floor pass in `planning/57_worldwide_economy_polish.md`.

The approved package has been implemented. The optional stronger rural trim for Pernambuco cotton and the optional Indiana maize frontier trim were not applied; the user approved the core trim package, the light Sweden trim, the Hyderabad package, and the small BIC capacity additions.

## Implemented Summary

- `BRZ`: reduced from 155 to 133 building levels.
- `DEN`: reduced from 40 to 33 building levels.
- `USA`: reduced from 242 to 216 building levels; removed the anachronistic `building_central_park`.
- `SWE`: lightly reduced from 63 to 58 building levels.
- `SC3`, `NET`, `GBR`, and `CHI`: left unchanged as approved.
- `HYD`: increased from 14 to 26 building levels with rural/resource texture in Hyderabad.
- `BIC`: increased from 299 to 304 building levels with construction capacity in Bihar/Agra/Bombay and a small Bombay trade center.

Post-implementation validation:

- Inactive building owners: 0.
- Nonpositive building levels: 0.
- Building brace failures: 0.
- Trade brace failures: 0.
- Banned/anachronistic building tokens, including `building_central_park`: 0.

## Audit Snapshot

Large active countries by explicit building levels per million population:

| Tag | Population | Building levels | Levels per million | Review read |
| --- | ---: | ---: | ---: | --- |
| `BRZ` | 4.40M | 155 | 35.3 | High; meaningful civilian overbuild remains. |
| `DEN` | 1.27M | 40 | 31.6 | High; mostly small-pop denominator plus dense Denmark proper and colonial ports. |
| `USA` | 8.73M | 242 | 27.7 | High; some obvious 1836/late content remains. |
| `SC3` | 2.80M | 71 | 25.4 | High because of 20 barracks; civilian economy is closer to normal. |
| `SWE` | 2.49M | 63 | 25.3 | High but plausibly resource/export driven. |
| `POR` | 5.43M | 99 | 18.2 | High-ish but not part of the original outlier set. |
| `NET` | 6.35M | 115 | 18.1 | No longer a major outlier after current audit; includes United Netherlands and colonies. |
| `GBR` | 20.06M | 327 | 16.3 | No longer a major outlier; keep early-industrial exception. |
| `CHI` | 379.98M | 868 | 2.3 | Low by ratio but very large in absolute terms. |
| `BIC` | 132.12M | 299 | 2.3 | Low by ratio but not empty. |
| `HYD` | 13.61M | 14 | 1.0 | Real underbuilt problem. |

Useful comparison points:

| Tag | Population | Building levels | Levels per million |
| --- | ---: | ---: | ---: |
| `FRA` | 30.82M | 387 | 12.6 |
| `SPA` | 12.48M | 180 | 14.4 |
| `TUR` | 18.50M | 247 | 13.4 |
| `PRU` | 10.35M | 118 | 11.4 |
| `RUS` | 45.80M | 368 | 8.0 |
| `SC2` | 3.11M | 51 | 16.4 |
| `SC1` | 6.12M | 60 | 9.8 |

## Implemented Overbuilt-Outlier Package

### `BRZ` - trim roughly 25 to 30 levels

Brazil is the clearest civilian overbuild. It should still have a visible plantation/export economy, but the current setup overstates coffee, admin, trade, universities, and shipbuilding for 1816.

Implemented trims:

- Reduce early coffee density:
  - `STATE_SAO_PAULO` coffee `5 -> 2`.
  - `STATE_BAHIA` coffee `5 -> 2`.
  - `STATE_MINAS_GERAIS` coffee `5 -> 3`.
- Reduce Rio/Bahia state capacity:
  - `STATE_RIO_DE_JANEIRO` government administration `4 -> 2`.
  - `STATE_BAHIA` government administration `2 -> 1`.
  - `STATE_RIO_DE_JANEIRO` trade center `4 -> 2`.
  - `STATE_BAHIA` trade center `2 -> 1`.
- Reduce early higher education:
  - `STATE_RIO_DE_JANEIRO` university `2 -> 1`.
  - Remove `STATE_SAO_PAULO` university.
  - Remove `STATE_PERNAMBUCO` university.
- Reduce early industrial/naval extras:
  - Remove `STATE_SAO_PAULO` arms industry.
  - Remove `STATE_BAHIA` shipyard.
  - Remove `STATE_BAHIA` military shipyard.
  - Reduce `STATE_RIO_DE_JANEIRO` port `3 -> 2`.
  - Reduce `STATE_BAHIA` port `2 -> 1`.
- Optional rural trim not implemented:
  - `STATE_PERNAMBUCO` cotton remains unchanged.

### `DEN` - trim roughly 6 to 8 levels

Denmark's high ratio is partly because it is small and owns scattered colonial ports, which are useful for map/market access. Do not remove those ports unless in-game testing shows they are silly.

Implemented trims:

- `STATE_JUTLAND` rye farm `6 -> 4`.
- `STATE_JUTLAND` livestock ranch `5 -> 3`.
- `STATE_ZEALAND` government administration `2 -> 1`.
- `STATE_ZEALAND` trade center `2 -> 1`.
- Remove either the `STATE_ZEALAND` arms industry or regular shipyard. Recommended: remove the arms industry and keep Copenhagen's shipbuilding/naval flavor.

### `USA` - trim roughly 20 to 30 levels plus remove a clear anachronism

The US should still be a relatively active agrarian economy, but a few entries feel too large for 1816. The obvious bug is `building_central_park`, which is far too late.

Implemented trims:

- Remove `building_central_park`.
- `STATE_DISTRICT_OF_COLUMBIA` government administration `5 -> 2`.
- `STATE_TENNESSEE` tobacco `10 -> 4`.
- `STATE_TENNESSEE` maize `5 -> 3`.
- `STATE_NEW_YORK` trade center `5 -> 3`.
- `STATE_SOUTH_CAROLINA` trade center `3 -> 1`.
- `STATE_LOUISIANA` trade center `3 -> 1`.
- Cotton frontier moderation:
  - `STATE_ALABAMA` cotton `5 -> 3`.
  - `STATE_NORTH_CAROLINA` cotton `5 -> 3`.
  - `STATE_SOUTH_CAROLINA` cotton `5 -> 3`.
  - `STATE_GEORGIA` cotton `4 -> 3`.
  - `STATE_VIRGINIA` cotton `4 -> 3`.
- Optional frontier moderation not implemented:
  - `STATE_INDIANA` maize remains unchanged.

### `SC3` - no civilian economy change recommended

`SC3` looks overbuilt because it has 20 barracks. Its non-barracks economy is 51 levels, around 18.2 levels per million, which is close to other Spanish colonial starts. Treat this as a military-balance question rather than an economy bug.

Recommendation:

- Leave civilian buildings alone.
- If the user wants military trimming, consider reducing `SC3` barracks from 20 to about 12 in a separate military balance pass.

### `SWE` - light trim only, or leave alone

Sweden is high because it has a small population and a plausible resource/export economy. Nothing looks catastrophically wrong.

Implemented conservative trims:

- `STATE_SVEALAND` logging camp `5 -> 4`.
- `STATE_GOTALAND` logging camp `5 -> 4`.
- `STATE_SCANIA` fishing wharf `3 -> 2`.
- `STATE_SVEALAND` government administration `3 -> 2`.
- `STATE_SVEALAND` trade center `2 -> 1`.

### `NET` and `GBR` - no reduction recommended

- `NET` is not extreme after the current audit, and its density mostly reflects the United Kingdom of the Netherlands plus colonies.
- `GBR` is also not extreme after the current audit and has the approved early-industrial exception.

## Implemented Underbuilt-Giant Package

### `HYD` - add roughly 10 to 12 rural/resource levels

Hyderabad is the true underbuilt giant: 13.61M people and only 14 explicit building levels. It should remain mostly subsistence, but it needs more visible agrarian/resource texture.

Implemented additions in `STATE_HYDERABAD`:

- Add `building_rice_farm` level 3.
- Add `building_livestock_ranch` level 2.
- Add `building_cotton_plantation` level 2.
- Add `building_dye_plantation` level 2.
- Add `building_opium_plantation` level 1.
- Add `building_logging_camp` level 1.
- Add `building_iron_mine` level 1.

This brings Hyderabad from 14 to 26 levels, still far below European density but less empty.

### `BIC` - no broad rural increase; optional gameplay capacity only

The East India Company is low by ratio but already has 299 levels. A broad rural increase would be misleading and would fight the approved "most population remains subsistence" approach.

Implemented gameplay-capacity additions:

- Add one construction sector each in `STATE_BOMBAY`, `STATE_BIHAR`, and `STATE_AGRA`.
- Add a small Bombay trade center, `STATE_BOMBAY` trade center level 2.

This is a gameplay-capacity polish, not an attempt to represent India's full agrarian economy through explicit buildings.

### `CHI` - no building increase recommended in this pass

Qing is low by ratio, but it already has 868 explicit levels, including 162 government administration and major tea/silk/rice/export concentrations. Its low ratio is mostly the correct result of enormous population remaining in subsistence.

Recommendation:

- Do not add more buildings in this pass.
- Revisit Qing only in a dedicated China economy/PM pass if in-game testing shows it is unplayably inert.

## Approved Package

Implemented approval bundle:

1. Implemented the `BRZ`, `DEN`, and `USA` trims above.
2. Applied the light `SWE` trim.
3. Leave `SC3` civilian buildings, `NET`, `GBR`, and `CHI` unchanged.
4. Added the `HYD` rural/resource package.
5. Added the approved `BIC` gameplay-capacity package.
