# Worldwide Economy Polish

This pass follows the broad 1816 building backdate and military pass. It is not a new global resource rewrite; the approved resource policy remains that vanilla state-region potentials stay unchanged.

## Immediate No-Design Fixes Implemented

- Folded stale Baltic `UBD` building ownership into `RUS` in `common/history/buildings/15_russia.txt`.
  - `UBD` was removed as an active start-map country in the Baltic population refinement.
  - Twelve building ownership rows in Tallinn, Tartu, Riga, and Courland still belonged to `UBD`.
  - After the fix, building-owner validation has zero inactive owners.
- Removed the stale `SPC` Basque trade block from `common/history/trade/00_historical_trade.txt`.
  - `SPC` / Carlist Spain is not an 1816 start country.
  - The Basque hardwood/artillery imports were a 1836 Carlist-war artifact rather than a valid 1816 Spanish economy setup.

## Audit Snapshot

- Building-history owner rows: 3,274.
- Parsed building levels: 6,464.
- Inactive building owners: 0.
- Nonpositive building levels: 0.
- Inactive trade region states: 0.
- Construction/port floor target failures: 0 of 36.
- Banned/anachronistic building tokens from prior passes remain absent, except the approved British atmospheric-engine/motor-industry abstraction.
- Outlier/giant package is implemented in `planning/58_economy_outliers_and_giants_review.md`.

## Implemented Cluster 1: Minimal Construction Floor

Many playable countries have no explicit construction sector. This is not always a hard bug because Victoria 3 has baseline construction, but it makes large playable countries feel inert.

Implemented rule:

- Add one `building_construction_sector` using the default wooden construction PM to every active non-decentralized country with at least 1 million population and no construction sector.
- Keep the change to exactly one level per country unless a later targeted economy pass approves more.
- This is a gameplay floor, not a claim that every listed country had a modern construction industry.

Recognized or colonial candidates with population above 1 million:

- `SC2`, `POL`, `PAP`, `PHI`, `WAL`, `SWI`, `TRS`, `WUR`, `MOL`, `GUA`, `HAN`, `SAX`, `HAI`, `CRO`, `FIN`, `BAD`.

Unrecognized candidates above 3 million:

- `HYD`, `DAI`, `PER`, `AWA`, `SOK`, `MYS`, `BER`, `NAG`, `BUR`, `ALD`, `NEP`, `SIA`, `MOR`, `KAB`.

Implemented placements:

- 30 total construction-sector levels were added.
- Recognized/colonial placements: `SC2`, `POL`, `PAP`, `PHI`, `WAL`, `SWI`, `TRS`, `WUR`, `MOL`, `GUA`, `HAN`, `SAX`, `HAI`, `CRO`, `FIN`, `BAD`.
- Unrecognized placements: `HYD`, `DAI`, `PER`, `AWA`, `SOK`, `MYS`, `BER`, `NAG`, `BUR`, `ALD`, `NEP`, `SIA`, `MOR`, `KAB`.

## Implemented Cluster 2: Obvious Port Floor

Several coastal or coastal-hint countries have fishing/sea activity but no port building. This can hurt market access and trade feel.

Implemented rule:

- Add one `building_port` with `pm_basic_port` to active non-decentralized countries above 500k population that already have a fishing, whaling, or shipyard signal but no port.
- Keep it to one level unless the state is a clear regional entrepot.

Implemented placements:

- `PER`: `STATE_LARISTAN`.
- `BER`: `STATE_GUJARAT`.
- `SIA`: `STATE_BANGKOK`.
- `SIN`: `STATE_SINDH`.
- `MAD`: `STATE_NORTH_MADAGASCAR`.
- `MAK`: `STATE_BALUCHISTAN`.

`OYO` was skipped under the stricter inland interpretation.

## Implemented Cluster 3: Overbuilt Outliers

The first global building scaler made the economy broadly smaller, but a few countries remain dense by building levels per million population.

Highest large-country outliers:

- `BRZ`: 35.3 levels per million.
- `DEN`: 31.6 levels per million.
- `USA`: 27.7 levels per million.
- `NET`: 26.9 levels per million.
- `SC3`: 25.4 levels per million.
- `SWE`: 25.3 levels per million.
- `GBR`: 22.9 levels per million.

Implemented result:

- No blind global scaler was applied.
- `BRZ`, `DEN`, `USA`, and `SWE` received targeted reductions.
- `SC3`, `NET`, and `GBR` were left unchanged after review.
- `building_central_park` was removed from the USA as a clear anachronism.
- Britain remains relatively dense because it has the approved early-industrial exception.

## Implemented Cluster 4: Underbuilt Giants

Some high-population states have very few explicit buildings:

- `HYD`: 13.6M people, 13 levels.
- `BIC`: 132.1M people, 189 levels.
- `CHI`: 380M people, 868 levels.

Implemented result:

- Building-level parity with Europe was not pursued.
- `HYD` received a modest rural/resource package, increasing it from 14 to 26 levels.
- `BIC` received three construction-capacity additions and a small Bombay trade center, increasing it from 299 to 304 levels.
- `CHI` was left unchanged; broader China economic texture remains a later focused pass if in-game testing calls for it.

## Design Cluster 5: Historical Trade Polish

Vanilla historical trade is still very small and partly 1836-flavored. After the stale `SPC` block removal, the remaining active trade entries are structurally valid.

Future trade polish could add or adjust:

- Brazil coffee/sugar exports.
- Caribbean sugar and tobacco weighting.
- British textile/tool imports and exports.
- Indian textile/opium/tea balance.
- Qing tea/silk/opium balance.
- Ottoman/Egyptian cotton and grain.

Recommendation:

- Leave detailed trade for a later pass after the construction/port economy floor is approved and tested.
