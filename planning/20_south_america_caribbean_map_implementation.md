# South America And Caribbean Map Implementation

## Scope

This pass implements the approved first-pass map ownership for South America, Panama/New Granada, and the Caribbean.

## State Ownership Added

New files:

- `common/history/states/99_cow_1816_south_america_states.txt`
- `common/history/states/99_cow_1816_caribbean_states.txt`

South America ownership uses the approved broad remaps:

- `SC2` New Granada now holds vanilla Colombia, Venezuela, Ecuador, Panama, and the Venezuela-linked West Indies province.
- `SC3` Royalist Peru now holds vanilla Peru, Upper Peru, Chile, and relevant frontier splits.
- `POR` now holds Brazil-facing tags that should not start independently in 1816, including vanilla `BRZ`, `PRA`, and `PNI` land.
- `ARG`, `PRG`, and `URU` remain playable where vanilla already gives them land.
- Existing decentralized/local holders in Patagonia, Araucania, Chaco, and Amazonian frontier areas are preserved unless a province was part of an approved Spanish or Portuguese remap.
- European Guianas and direct European Caribbean islands remain direct European possessions.

Follow-up cleanup:

- `STATE_ICA` was consolidated from two adjacent `SC3` create-state blocks into one `SC3` block after the pop validation audit flagged the duplicate owner entry.

Caribbean ownership:

- `DOM` now owns `STATE_SANTO_DOMINGO` as Spanish Santo Domingo.
- `JAM` now owns `STATE_JAMAICA` as a British colony.
- `BAH` now owns `STATE_BAHAMAS` as a British colony.
- `STATE_WEST_INDIES` keeps direct British, French, Danish, and Dutch ownership, while the vanilla Venezuela-linked province moves to `SC2`.
- No Swedish Saint Barthelemy hook was added in this pass because the vanilla split did not expose an obvious safe one-province assignment without in-game review.

## Country And Diplomacy Setup

New support files:

- `common/history/countries/99_cow_1816_south_america_countries.txt`
- `common/history/countries/99_cow_1816_caribbean_countries.txt`
- `common/history/diplomacy/99_cow_1816_south_america_caribbean_subjects.txt`

Added minimal colonial setup for:

- `SC2`
- `SC3`
- `DOM`
- `JAM`
- `BAH`

Added subject relationships:

- `SPA -> SC2` colony
- `SPA -> SC3` colony
- `SPA -> DOM` colony
- `GBR -> JAM` colony
- `GBR -> BAH` colony

Removed stale vanilla `BOL -> NPU/SPU/IQU` puppet pacts if they exist.

## Start-History Safety

Added blank character-history overrides for absent 1816 start tags:

- `BOL`
- `BRZ`
- `CHL`
- `CLM`
- `ECU`
- `NPU` / `SPU` / `IQU`
- `PNI`
- `PRA`
- `VNZ`

Added `common/history/military_formations/02_military_formations_south_america.txt`, keeping only the still-valid vanilla `ARG`, `URU`, and `PRG` formation blocks.

Adjusted existing formation overrides:

- Removed two Haitian combat units in `STATE_SANTO_DOMINGO`.
- Removed one British fleet combat unit in `STATE_JAMAICA`.

Removed stale `CHL` and `BRZ` declared interests from the adapted interests file.

## Validation

- Brace balance passes across common script files.
- All executable province IDs in mod state history exist in current base map data.
- No unexpected duplicate province IDs across executable mod state ownership overrides.
- Stale military formation references for removed South American start tags are absent.
