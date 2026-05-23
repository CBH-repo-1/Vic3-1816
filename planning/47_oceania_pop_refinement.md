# Oceania Population Refinement Audit

Status: approved cleanup implemented.

## Scope

This pass reviewed Australia, New Zealand, Hawaii, Tahiti, Tonga, Fiji, Melanesia, Micronesia, and New Guinea after the Southeast Asia/Indonesia population cleanup.

Files reviewed:

- `common/history/pops/05_north_america.txt` for Hawaii.
- `common/history/pops/12_indonesia.txt` for Pacific island regions.
- `common/history/pops/13_australasia.txt` for Australia and New Zealand.
- `common/history/states/00_states.txt`.
- Oceania planning notes `09_oceania_inventory.md`, `18_oceania_north_america_map_implementation.md`, and `24_population_scaling_plan.md`.

## Current Snapshot

Selected Oceania/Pacific total:

- 1,906,109 across Australia, New Zealand, Hawaii, Tahiti, Tonga, Fiji, Melanesia, Micronesia, and New Guinea.

Current owner totals:

- `PPU`: 408,112.
- `NSW`: 222,064.
- `PLY`: 172,959.
- `WTI`: 149,460.
- `HAW`: 145,000.
- `GML`: 118,994.
- `NTO`: 105,432.
- `VNT`: 93,842.
- `FJI`: 83,642.
- `NTU`: 64,000.
- `KNK`: 57,125.
- `BLA`: 53,449.
- `KAU`: 51,300.
- `MCR`: 49,418.
- `HLA`: 48,961.
- `TNG`: 40,801.

## Implemented Corrections

### 1. Australia Has Too Many 1836-ish Settler Pops

Current setup:

- `STATE_NEW_SOUTH_WALES`, `NSW`: 63,200 Aboriginal, 101,384 Australian, 16,080 Irish.
- `STATE_TASMANIA`, `NSW`: 200 Aboriginal, 41,200 Australian.
- Later/uncolonized mainland states also contain 42,480 Australian-culture pops under Aboriginal/local owners.

Nearby historical estimates:

- Oxley's appendix gives the 1816 New South Wales population, excluding Van Diemen's Land, as 15,175.
- Wentworth/Oxley together imply Van Diemen's Land was still only around 2,000 colonial inhabitants in 1816.
- Aboriginal Australia estimates are broad, but commonly range from several hundred thousand to around three quarters of a million before or near first contact.
- Tasmanian Aboriginal estimates are also broad, usually several thousand in the early colonial period.

Implemented correction:

- Scale `STATE_NEW_SOUTH_WALES` settler pops only from 117,464 to 15,175, preserving the Australian/Irish split. Keep the existing 63,200 Aboriginal population in the `NSW` bucket.
- Scale `STATE_TASMANIA` settler pop from 41,200 to 2,000.
- Raise `STATE_TASMANIA` Aboriginal pop from 200 to 5,000.
- Convert Australian-culture pops in Victoria, Queensland, South Australia, Western Australia, and Northern Territory into Aboriginal culture, preserving those local state totals.
- Do not globally inflate Aboriginal Australia in this pass; keep the correction focused on removing 1836 settler artifacts.

Implemented impact:

- Australia selected total falls from 572,918 to 436,229.
- Active `NSW` total falls from 222,064 to 85,375.
- Mainland Aboriginal/local state totals outside NSW/Tasmania remain unchanged, but become culturally cleaner.

### 2. New Zealand Is High And Too South-Island-Heavy

Current setup:

- `STATE_NORTH_ISLAND`, `NTO`: 93,004.
- `STATE_SOUTH_ISLAND`, `NTO`: 12,428.
- `STATE_SOUTH_ISLAND`, `NTU`: 64,000.
- New Zealand total: 169,432, including 1,432 Australian-culture pops.

Nearby historical estimates:

- Te Ara treats Cook's 1769 estimate of 100,000 Maori as the most realistic eighteenth-century baseline.
- Te Ara gives 1840 Maori population as 70,000 to 90,000 after early contact-era disease and war losses.
- A 100,000-ish 1816 target is therefore more defensible than the current 169,432.

Implemented correction:

- Scale New Zealand to 100,000 total.
- Convert the small Australian-culture pops to Maori.
- Redistribute to a simple 85,000 North Island / 15,000 South Island split.
- Preserve the approved vanilla owner abstraction by giving South Island `NTO` a small 2,000 northern-South-Island foothold and `NTU` the remaining 13,000.

Implemented targets:

- `STATE_NORTH_ISLAND`, `NTO`: 85,000.
- `STATE_SOUTH_ISLAND`, `NTO`: 2,000.
- `STATE_SOUTH_ISLAND`, `NTU`: 13,000.

### 3. Hawaii Total Is Fine, Composition Is Too 1836

Current setup:

- `STATE_HAWAIIAN_ISLANDS`, `HAW`: 145,000 total.
- This includes 37,740 Han pops and large Christian Hawaiian pops.

Nearby historical estimates:

- Hawaii's 1823 population estimate is 145,000, so the total is fine for gameplay.
- The first major American Protestant missionary company arrived in 1820, after the 1816 start.
- The large Han population belongs to later plantation-era migration, not 1816.

Implemented correction:

- Keep `HAW` at 145,000 total.
- Convert the 37,740 Han pop to Hawaiian.
- Convert Hawaiian Protestant/Catholic religion entries to Hawaiian animist for the 1816 start.
- Fold the tiny Yankee clergyman pop into the Hawaiian animist population because it represents post-1820 missionary flavor.
- Keep the 906 foreign capitalist pops as a small foreign merchant/advisor minority.

Implemented target:

- 144,094 Hawaiian animist pops.
- 906 foreign capitalist pops.

## Leave Alone For Now

- Tahiti/`PLY` should stay at 172,959 for this pass. The state region represents a broad Society Islands/Pomare realm abstraction, and early estimates vary wildly.
- Tonga/`TNG` at 40,801 is close to a reasonable 40,000-ish benchmark.
- Fiji/`FJI`, Vanuatu/`VNT`, Kanak/`KNK`, New Guinea/`PPU`, Micronesia/`MCR`, Nauru/`NRU`, Solomon/Bougainville tags, and other Pacific local tags should stay as-is unless an in-game review reveals a specific gameplay issue.

## Sources Checked

- John Oxley, *Journals of Two Expeditions into the Interior of New South Wales*, appendix table for New South Wales 1815-1817 population: https://www.gutenberg.org/cache/epub/5334/pg5334-images.html
- William Charles Wentworth, *Statistical, Historical, and Political Description of the Colony of New South Wales and its Dependent Settlements in Van Diemen's Land*, 1817 combined colonial population: https://www.gutenberg.org/files/15602/15602-h/15602-h.htm
- Te Ara, "Taupori Maori - Maori population change", for Cook's 100,000 baseline and 1840 range of 70,000-90,000: https://teara.govt.nz/en/taupori-maori-maori-population-change/page-1
- Hawaii DBEDT historical data table / Hawaii State Data Book source for the 1823 population estimate of 145,000: https://files.hawaii.gov/dbedt/economic/databook/archive/DB1976/db1976.pdf
- American Antiquarian Society note on the first Hawaiian mission and printing press arriving in 1820: https://www.americanantiquarian.org/printing-hawaiian-language/early-printing-hawaiian

## Validation Snapshot

- `common/history/pops/05_north_america.txt`: brace depth 0, minimum depth 0, UTF-8 BOM present.
- `common/history/pops/13_australasia.txt`: brace depth 0, minimum depth 0, UTF-8 BOM present.
- Selected Oceania/Pacific total now equals 1,699,988.
- `STATE_NEW_SOUTH_WALES` / `NSW` now totals 78,375.
- `STATE_TASMANIA` / `NSW` now totals 7,000.
- Active `NSW` in Australia now totals 85,375.
- New Zealand now totals exactly 100,000 Maori pops.
- `STATE_HAWAIIAN_ISLANDS` / `HAW` remains exactly 145,000.
- Global nonpositive pop-size check remains clean: 0 nonpositive pop sizes.

## Approved And Implemented

The user approved this focused Oceania cleanup:

- Australia: correct 1816 settler totals, convert later mainland settler remnants to Aboriginal culture, and set Tasmania to 2,000 settler / 5,000 Aboriginal.
- New Zealand: scale to 100,000 Maori total with an 85,000 North Island / 15,000 South Island split.
- Hawaii: keep total 145,000, but convert early Han/Christian/missionary artifacts into Hawaiian animist pops while retaining 906 foreign capitalists.
- Leave Tahiti, Tonga, Fiji, Melanesia, Micronesia, and New Guinea unchanged for this pass.
