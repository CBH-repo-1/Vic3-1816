# Pop Ownership Alignment Pass

## Scope

This pass aligns vanilla pop `region_state` ownership with the scripted 1816 map ownership. It is a stability-first pass, not a full 1816 demographic reconstruction.

Implemented files:

- `common/history/pops/00_west_europe.txt`
- `common/history/pops/01_south_europe.txt`
- `common/history/pops/03_north_africa.txt`
- `common/history/pops/04_subsaharan_africa.txt`
- `common/history/pops/05_north_america.txt`
- `common/history/pops/06_central_america.txt`
- `common/history/pops/07_south_america.txt`
- `common/history/pops/08_middle_east.txt`
- `common/history/pops/09_central_asia.txt`
- `common/history/pops/10_india.txt`
- `common/history/pops/11_east_asia.txt`
- `common/history/pops/13_australasia.txt`
- `common/history/pops/15_russia.txt`

## Method

- Copied the affected vanilla pop-history files into the mod using the same filenames, following Paradox's documented pattern for state-control edits.
- Rebuilt only the state blocks touched by the 1816 ownership map.
- For one-owner changes, moved the vanilla state-region population to the 1816 owner.
- For split states, divided each source owner's pops by province overlap between vanilla ownership and the 1816 ownership split.
- Preserved vanilla culture, religion, pop type, and total population in this first pass.

## Validation

- Changed state regions validated: 138.
- All changed state pop-owner lists match the current scripted map owner lists.
- Total population is preserved for every transformed state region.
- Brace balance is clean across edited mod script files.

## Notable Custom Tag Results

- `V03` Andorra now receives a Catalonia pop share.
- `V04` Saxe-Gotha-Altenburg and `V05` Saxe-Hildburghausen now receive Saxony pop shares.
- `V06` Kuwait now receives a Basra pop share.
- `V07` Ryukyu receives the Ryukyu Islands population.
- `V08` Choctaw Nation and `V09` Chickasaw Nation split Mississippi population.
- `V10` Multan receives its Punjab pop share.

## Deferred Work

- True 1816 population scaling is still deferred.
- Literacy, wealth, profession balance, slavery adjustments, migration/community corrections, and country-specific starting population effects are deferred.
- Pops should be tested in game after the current map/pops layer is synced.

## Later Frontier Cleanup

- After in-game review feedback, the approved USA frontier cleanup moved the remaining direct `USA` pop buckets in `STATE_IOWA`, `STATE_MINNESOTA`, `STATE_NORTH_DAKOTA`, `STATE_SOUTH_DAKOTA`, `STATE_NEBRASKA`, `STATE_KANSAS`, `STATE_COLORADO`, `STATE_WYOMING`, and `STATE_MONTANA` to local/decentralized holders while preserving US claims in state history.
- The frontier cleanup preserved pop totals; it changed ownership buckets only.
- After the follow-up map review, `STATE_VICTORIA` and `STATE_QUEENSLAND` pop buckets were moved from `NSW` to `GML` to match the corrected 1816 Oceania ownership.
- Final follow-up validation found zero pop-owner mismatches, zero zero/negative pop sizes, and clean brace depth.

## State Object Merge Fix

- In-game standard-of-living map review found deep red zero-pop states in Brazil, Comancheria, Spain, and other split or remapped regions.
- The root cause was duplicate state objects: the old vanilla state object kept the pop bucket but no longer had provinces, while the later `99_cow_1816_*_states.txt` overlay created a new province-owning state object with no pops.
- The active state history is now a generated `common/history/states/00_states.txt` override that directly replaces vanilla state blocks with the approved 1816 versions.
- The old `99_cow_1816_*_states.txt` files were removed so the merged override is the only state-history layer.
- Static validation now shows one active state-history file, zero duplicate state/country `create_state` pairs, zero province-owning state/country pairs without pop blocks, and clean brace depth.
