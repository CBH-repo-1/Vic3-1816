# Starting Buildings Sweep

## Scope

This pass is a first mechanical cleanup of 1836 starting buildings for the 1816 start. It does not rebalance building levels, add new historical industries, or redistribute split-state buildings by province.

## Implemented Files

Building-history overrides now exist for:

- `common/history/buildings/00_west_europe.txt`
- `common/history/buildings/01_south_europe.txt`
- `common/history/buildings/02_east_europe.txt`
- `common/history/buildings/03_north_africa.txt`
- `common/history/buildings/04_subsaharan_africa.txt`
- `common/history/buildings/05_north_america.txt`
- `common/history/buildings/06_central_america.txt`
- `common/history/buildings/07_south_america.txt`
- `common/history/buildings/08_middle_east.txt`
- `common/history/buildings/09_central_asia.txt`
- `common/history/buildings/10_india.txt`
- `common/history/buildings/11_east_asia.txt`
- `common/history/buildings/12_indonesia.txt`
- `common/history/buildings/13_australasia.txt`
- `common/history/buildings/15_russia.txt`

## Production Method Cleanup

Era 2 or otherwise anachronistic active production methods were downgraded to earlier equivalents:

- `pm_vertical_filing_cabinets` -> `pm_horizontal_drawer_cabinets`
- `pm_sulfite_pulping` -> `pm_pulp_pressing`
- `pm_military_shipbuilding_wooden_2` -> `pm_military_shipbuilding_wooden`
- `pm_soil_enriching_farming` -> `pm_simple_farming`
- `pm_sheep_farms` -> `pm_simple_ranch`
- `pm_slaughterhouses` -> `pm_butchering_tools`
- `pm_steel` -> `pm_pig_iron`
- `pm_sugar_beets` -> `pm_no_secondary`
- Non-British `pm_atmospheric_engine_pump_*` mine PMs -> matching `pm_picks_and_shovels_*` mine PMs

The approved British exception was preserved: Britain keeps atmospheric-engine mine PMs in British Isles states where the country-specific tech pass grants `GBR` `atmospheric_engine`.

All starting railways found in the affected 1836 building files were removed. This removed 11 `building_railway` start buildings from `00_west_europe.txt`.

## Building Owner Alignment

The sweep also fixed stale `region_state:*` building blocks where the current 1816 state history has exactly one owner. This remapped 86 single-owner building blocks from their 1836 owner to their current 1816 owner, including:

- `STATE_LOMBARDY` and `STATE_VENETIA`: `AUS` -> `LOM`
- `STATE_MALTA`: `GBR` -> `MLT`
- Greek mainland and islands already returned to the Ottomans: `GRE`/`EGY` -> `TUR`
- Congress Poland states: `RUS` -> `POL`
- New Spain and Spanish America states that no longer use later successor tags
- Single-owner colonial/local corrections such as Newfoundland, Jamaica, Bahamas, Ryukyu, Zanzibar, and selected Australia/New Zealand state owners

## Split-State Building Allocation

The user approved this allocation rule:

- Whoever owns the state or majority of the state in 1816 gets the building.
- Downgrade or remove the building if it is too 1836-specific for the 1816 start.
- Avoid handing out rural buildings unless they make sense.
- If a state is split roughly evenly, copy or split the building unless one owner is historically much more likely to have that building type.

Implemented split-state decisions:

- Deleted 27 empty stale region-state blocks.
- `STATE_WALLONIA`: moved the old Belgian block to `NET`, reduced heavy 1836 industry, and removed chemical/explosives factories.
- `STATE_CATALONIA`: moved the extra old Spanish/Carlist wheat farm to `SPA`, not Andorra.
- `STATE_ERITREA`: moved Red Sea fishing/port buildings to `AWS` as the coastal owner.
- `STATE_CONSTANTINE`: moved the old Constantine/French blocks to `ALD`, with administration and barracks reduced.
- `STATE_LIBERIA`: removed the 1836 Liberia colony buildings entirely.
- `STATE_KENYA`: moved the old Omani fishing building to `MBS`; removed the later Witu block.
- `STATE_ZULULAND`: removed the stale Basotho block because `ZUL` already has a strong local start.
- `STATE_VRYSTAAT`, `STATE_TRANSVAAL`, and `STATE_LOURENCO_MARQUES`: kept modest rural buildings for the local majority owners and removed later Boer/Gaza barracks.
- `STATE_BRITISH_COLUMBIA`: kept logging for `SLS` and removed Oregon barracks.
- `STATE_TEXAS`, `STATE_CHIAPAS`, `STATE_GUATEMALA`, `STATE_NICARAGUA`, and `STATE_WEST_INDIES`: moved buildings to the approved 1816 majority/colonial owners.
- `STATE_PASHTUNISTAN`: moved the old Punjab block to `KAB`.
- `STATE_ASSAM`: removed Company administration/tea additions and kept only logging for `ASM`.
- `STATE_CENTRAL_PROVINCES`: moved the Company block to `NAG`.
- `STATE_LAOS`: kept opium for `LUA` and removed the extra Siamese barracks.
- `STATE_TENASSERIM` and `STATE_ARAKAN`: moved pre-Yandabo Company blocks back to `BUR`, reducing Tenasserim dye.
- `STATE_EAST_BORNEO`: split the equal-share block by type, with rice to `BNJ` and port to `KTI`.
- `STATE_NORTH_SUMATRA`, `STATE_ACEH`, `STATE_CELEBES`, and `STATE_SUNDA_ISLANDS`: moved or reduced old Dutch blocks to the relevant local owners.
- `STATE_SOUTH_AUSTRALIA` and `STATE_WESTERN_AUSTRALIA`: removed later Australian colonial buildings.

## Validation

- All mod building-history override files have clean brace depth.
- Effective building history has zero active PM tech issues, except the approved British atmospheric-engine exception.
- No disallowed starting railways remain in the mod building overrides.
- No mechanical single-owner building-region mismatches remain.
- No stale split-state building-region mismatches remain.

## Next Building Work

The next building pass should be a broader level/resource rebalance:

- Rebalance building levels from 1836 to 1816.
- Review resource and urban/industrial starts, especially Britain, France, Brazil/Portugal, India, China, Ottoman/Egyptian areas, New Spain, and colonial/decentralized frontiers.
- Review existing non-stale anachronistic industries such as commercial tea in Assam.
