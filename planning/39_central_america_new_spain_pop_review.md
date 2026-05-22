# Central America And New Spain Population Review

This is the next population review area after North America, the Caribbean, and South America.

The proposed batch in this note was approved and implemented.

## Current Audit

Current relevant scripted totals:

| Tag | Current total | Enslaved pops | Notes |
| --- | ---: | ---: | --- |
| `SC1` New Spain | 6,122,300 | 5,284 | Hits the approved New Spain target, but the enslaved pops are all in Texas and the country history currently has no slavery law. |
| `GUA` Captaincy General of Guatemala | 2,419,000 | 0 | This appears too high for 1816/1820 Central America. |
| `MKT` Miskitia | 62,000 | 1,000 | Looks serviceable for now; already has `law_legacy_slavery`. |
| `SC2` Panama/New Granada share in this file | 127,945 | 4,430 | Already covered by the South America slavery-law correction. |

Owner/pop alignment is clean for the reviewed states:

- `STATE_TEXAS`
- `STATE_CHIAPAS`
- `STATE_SAN_SALVADOR`
- `STATE_GUATEMALA`
- `STATE_HONDURAS`
- `STATE_NICARAGUA`
- `STATE_COSTA_RICA`
- `STATE_PANAMA`

## High-Confidence Issues

### `GUA` Total Is Likely Too High

The current `GUA` total of 2,419,000 is much higher than near-date Central America figures.

The strongest easy replacement target is the 1824 Federal Republic of Central America total of 1,287,491 for the five Central American states:

- Costa Rica: 70,000.
- El Salvador: 212,573.
- Guatemala: 660,580.
- Honduras: 137,069.
- Nicaragua: 207,269.

The mod also gives `GUA` a small Chiapas fragment of 23,978. If kept as-is, the proposed `GUA` total would become 1,311,469.

Recommended implementation:

- Set `STATE_SAN_SALVADOR` `GUA` total to 212,573.
- Set `STATE_GUATEMALA` `GUA` total to 660,580.
- Set `STATE_HONDURAS` `GUA` total to 137,069.
- Set `STATE_NICARAGUA` `GUA` total to 207,269.
- Set `STATE_COSTA_RICA` `GUA` total to 70,000.
- Leave the `GUA` Chiapas fragment at 23,978 unless a later Chiapas-specific review changes it.
- Preserve each state's existing internal culture split while scaling the state total.

Implemented result:

- `GUA` now totals 1,311,469, including the unchanged 23,978 Chiapas fragment.
- The five Central American state totals now match the 1824 federation-state table exactly.

### `SC1` Texas Composition Is A Later Texas Artifact

The `SC1` Texas bucket currently contains:

- 36,937 Dixie pops.
- 5,284 enslaved Afro-American pops.
- 20,120 Native/Mexican/other pops.

That looks like a scaled-down version of later Anglo Texas rather than Spanish Texas on 1816. Anglo-American empresario colonization starts in the 1820s, and near-1836 figures show how quickly it grew after that point.

Recommended implementation:

- Remove the 1816 Dixie and enslaved Afro-American Texas start from `SC1`.
- Keep `SC1` Texas small and frontier-like, weighted toward Mexican/Tejano and local Native cultures.
- Preserve the overall `SC1` New Spain target by shifting any removed Texas population into the core New Spain states, preferably proportionally across `STATE_MEXICO`, `STATE_BAJIO`, `STATE_JALISCO`, `STATE_OAXACA`, and `STATE_VERACRUZ`.

Implemented result:

- Removed 36,937 Dixie pops and 5,284 enslaved Afro-American pops from `SC1` Texas.
- Left the existing Mexican and local Native Texas pops in place, for a reduced `SC1` Texas total of 20,120.
- Added 5,284 enslaved Afro-Caribeno pops to Veracruz as the small enslaved New Spain representation.
- Distributed the remaining 36,937 removed Texas pops proportionally across Veracruz, Bajio, Mexico, Oaxaca, and Jalisco.

### `SC1` Slavery Law

New Spain has a small scripted enslaved population and slavery had not been cleanly eradicated across all royalist-held territory in 1816.

Recommended implementation:

- Add `law_colonial_slavery` to `SC1`, matching the approach just used for `SC2` and `SC3`.
- Do not add enslaved pops to `GUA` yet. Sources indicate slavery existed in Guatemala, but on a small scale, so that should wait for a dedicated small-pop composition pass unless we want the law-only representation.

Implemented result:

- `SC1` now has `law_colonial_slavery`.
- `GUA` was not given a slavery law or enslaved pops in this pass.

## Source Backbone

- Federal Republic of Central America 1824 state population table.
- National Park Service summary of Texas demographic change before 1836, including the post-1823 Anglo-American migration surge.
- SciELO article on Mexican abolition noting the 1810 Hidalgo decree did not fully remove slavery in all territories under wartime conditions.
- Universidad del Valle de Guatemala thesis summary noting Black slavery in colonial Guatemala existed, but on a small scale, through 1824.
