# Oceania And North America Map Implementation Notes

This file tracks the approved first-pass ownership/diplomacy backdate for Oceania, North America, and Central America.

## Oceania

Implemented in `common/history/states/99_cow_1816_oceania_states.txt`:

| State | 1836 vanilla setup | 1816 mod setup |
| --- | --- | --- |
| `STATE_TASMANIA` | `TAS` | `NSW` |
| `STATE_VICTORIA` | `NSW` | `GML`; no `NSW` ownership |
| `STATE_QUEENSLAND` | `NSW` | `GML`; no `NSW` ownership |
| `STATE_SOUTH_AUSTRALIA` | `SAS`, `WTI`, `KAU` | `WTI`, `KAU`; no `SAS` ownership |
| `STATE_WESTERN_AUSTRALIA` | `WAS`, `NNG`, `WTI`, `MRN` | `WTI`, `NNG`, `MRN`; no `WAS` ownership |
| `STATE_NORTHERN_TERRITORY` | `WTI`, `NSW` | `WTI` |
| `STATE_NORTH_ISLAND` | `UNT`, `NSW`, `NTO` | `NTO` |
| `STATE_SOUTH_ISLAND` | `NTO`, `NTU` with late claims | `NTO`, `NTU`; late claims removed |

Implemented in `common/history/diplomacy/99_cow_1816_oceania_subjects.txt`:

- Remove `GBR -> WAS`, `GBR -> SAS`, and `GBR -> TAS` colony pacts.
- Remove `GBR -> UNT` and `GBR -> KAU` protectorate pacts.
- Remove the premature `FRA -> PLY` protectorate pact.

Implemented in `common/history/countries/99_cow_1816_oceania_countries.txt`:

- Set `KAU` to decentralized and traditional after removing the British protectorate setup.

## North America And Central America

Implemented in `common/history/states/99_cow_1816_north_america_states.txt`:

| State or area | 1836 vanilla setup | 1816 mod setup |
| --- | --- | --- |
| `STATE_NEWFOUNDLAND` | direct `GBR` | playable `NEW` |
| Washington/Oregon/Idaho/British Columbia Oregon-tag holdings | `ORG` | local/decentralized holders (`SLS`, `NZP`, `BNN`) |
| `STATE_OKLAHOMA` | `SEQ`, `COM` | `COM` |
| `STATE_FLORIDA` | `USA`, `SML` | `SPA`, `SML` |
| `STATE_MISSISSIPPI` | `USA` | `V09` northern Chickasaw split; `V08` central/southern Choctaw split |
| Texas, California, Arizona, New Mexico, Baja California, Nevada, Utah, and Mexican state regions | `MEX`/`TEX` plus local holders | `SC1` New Spain plus local holders |
| Guatemala, Chiapas, Honduras, Nicaragua, Costa Rica, San Salvador | `UCA`/`MEX` plus enclaves | `GUA`/`SC1` plus existing `GBR`/`MKT` enclaves |

Implemented in `common/history/diplomacy/99_cow_1816_north_america_subjects.txt`:

- Remove `GBR -> ORG` colony pact.
- Remove `USA -> SEQ` puppet pact.
- Add `GBR -> NEW` colony pact.
- Add `SPA -> SC1` and `SPA -> GUA` colony pacts.

Implemented in `common/history/countries/99_cow_1816_north_america_countries.txt`:

- Add starting country setup for `NEW`, `SC1`, and `GUA`.
- Add starting country setup for `V08` and `V09` in the shared Mississippi capital state.
- Promote `COM` from decentralized to unrecognized so it is playable.

## Deferred

- No in-game visual map check was performed by request; save visual checks until the full map-region pass is complete.
- Caribbean ownership and subject cleanup was handled in the later Caribbean pass.
- Panama/New Granada was handled in the later South America pass.
- USA frontier cleanup was later approved and implemented: direct `USA` ownership was removed from `STATE_IOWA`, `STATE_MINNESOTA`, `STATE_NORTH_DAKOTA`, `STATE_SOUTH_DAKOTA`, `STATE_NEBRASKA`, `STATE_KANSAS`, `STATE_COLORADO`, `STATE_WYOMING`, and `STATE_MONTANA`, while preserving `USA` claims.
- `DKT` was introduced as a landholder for the Dakota abstraction and given minimal decentralized country/population history.
- After in-game review, the frontier cleanup province IDs were normalized to the correct lowercase `x` prefix so the overrides take effect in game. Final validation shows no start ownership for `MEX`, and direct `USA` ownership is gone from the approved frontier-cleanup states.
- After in-game review, `STATE_VICTORIA` and `STATE_QUEENSLAND` were returned from vanilla `NSW` to the vanilla decentralized eastern Aboriginal tag `GML`, leaving `NSW` with `STATE_NEW_SOUTH_WALES` and `STATE_TASMANIA`.
- After later in-game review, the Old Southwest was cleaned up so the playable Choctaw and Chickasaw starts are not tiny islands inside an overlarge USA. `STATE_ALABAMA` is now split between `MSC`, `V08`, and `V09`; `STATE_GEORGIA` is split between `USA`, `MSC`, and `CHE`; and `STATE_TENNESSEE` is split between `USA`, `CHE`, and `V09`.
