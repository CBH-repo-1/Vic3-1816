# Caribbean Country Inventory

This file tracks the detailed Caribbean and adjacent Central American coastal setup. The design batch in this file has been approved; rows marked not ready still need province-level map review before scripting.

## Scope And Rules

- Pass status: approved at the country/tag and broad start-status level.
- Regional pass: Cuba, Puerto Rico, Hispaniola, Jamaica, Bahamas, Bermuda, the Lesser Antilles / West Indies state region, Danish/Dutch/French/British/Swedish island possessions, and the Belize/British Honduras carryover from Central America.
- Broad Caribbean decisions were already approved in the North America pass. This file refines the island-by-island handling before scripting.
- Use vanilla Victoria 3 state/province geometry. The `STATE_WEST_INDIES` region is a many-island abstraction, so exact island ownership must be tested province by province later.
- Reuse vanilla tags wherever possible. Create `V**` tags only where a historically important polity has no usable vanilla tag and the map can plausibly show it.
- Keep this pass at country/tag and broad start-status level. Detailed population, buildings, resources, exact province ownership, and event content come later.

## Historical Source Notes

- Cuba and Puerto Rico remain Spanish colonies in 1816 and are clean playable colonial-subject candidates using vanilla `CUB` and `PCO`.
- Eastern Hispaniola is Spanish Santo Domingo in 1816. The 1836-style Haitian occupation of Santo Domingo should be removed from the start setup.
- Western Haiti is split between Henri Christophe's northern Kingdom of Haiti and Alexandre Petion's southern Republic of Haiti. The approved first pass keeps one playable `HAI` and handles the split later as internal instability/flavor.
- Jamaica, Bahamas, Bermuda, Barbados, Trinidad, Tobago, and several Lesser Antilles possessions are British in 1816.
- Martinique and Guadeloupe are French by the post-Napoleonic settlement.
- The Danish West Indies are Danish again after the Napoleonic occupation period.
- Dutch Caribbean possessions, especially Curacao/Aruba/Bonaire and nearby islands, are Dutch again by 1816.
- Saint Barthelemy is Swedish from 1784 to 1878 and should be preserved as direct Swedish ownership if the vanilla `STATE_WEST_INDIES` province split allows it.
- Belize/British Honduras is not a separate start country, but vanilla already supports a small British-owned enclave in `STATE_GUATEMALA`.

## Vanilla Tag Baseline

Useful vanilla support includes:

- Playable or start candidate tags: `HAI`, `CUB`, `PCO`, `DOM`, `JAM`, and `BAH`.
- Later/formable/umbrella tags: `WIN` and `ATL`.
- Direct European owner tags: `GBR`, `SPA`, `FRA`, `NET`, `DEN`, and `SWE`.
- Adjacent approved tags from earlier passes: `SC2` for Spanish New Granada and `GUA` for the Captaincy General of Guatemala.

No new `V**` tags are proposed for the Caribbean at this stage.

## Greater Antilles

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Spanish Cuba | `CUB` | Cuba | Reuse vanilla tag | Playable Spanish colony | `SPA` colony | Strong | No | Approved in broad North America pass; detailed pass confirms all Cuba state regions should be under Spanish Cuba. |
| Spanish Puerto Rico | `PCO` | Puerto Rico | Reuse vanilla tag | Playable Spanish colony | `SPA` colony | Strong | No | Approved in broad North America pass; relocalize from vanilla "Porto Rico" if needed. |
| Western Haiti | `HAI` | Haiti | Reuse vanilla tag | Playable sovereign state | None | Strong | No | Approved in broad North America pass as one playable Haiti despite the Christophe/Petion split. Own `STATE_HAITI`, not Santo Domingo. |
| Spanish Santo Domingo | `DOM` | Santo Domingo | Reuse vanilla tag | Playable Spanish colony or direct Spanish possession | `SPA` colony | Strong | No | Approved in broad North America pass. Use for eastern Hispaniola; do not start as independent Dominican Republic. |
| Jamaica | `JAM` | Jamaica | Reuse vanilla tag | Playable British colony | `GBR` colony | Strong | No | Approved in broad North America pass; vanilla has tag but no country-history file, so scripting will need a small setup file. |

## Bahamas, Bermuda, And British Honduras

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Bahamas | `BAH` | Bahamas | Reuse vanilla tag | Playable British colony | `GBR` colony | Strong | No | Approved in broad North America pass; vanilla has tag but uses direct British ownership at 1836 start. |
| Bermuda | direct `GBR` | No dedicated country tag found | Direct British ownership | British colony/naval station | `GBR` direct | Strong | No | Keep direct British ownership, not a playable tag. |
| Belize / British Honduras settlement | direct `GBR` enclave | No dedicated country tag found | Direct British enclave in `STATE_GUATEMALA` | British settlement/logging enclave | `GBR` direct | Medium | No | Vanilla already has British-owned provinces in Guatemala. Keep no separate tag; leave most of Guatemala under `GUA`/Spain. |

## Lesser Antilles And West Indies State Region

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| British Lesser Antilles / Trinidad / Tobago / Barbados group | direct `GBR` | No separate tags | Direct British ownership | British colonies | `GBR` direct | Medium | No | Keep direct ownership in `STATE_WEST_INDIES`; no extra playable tags in first pass. |
| French Antilles | direct `FRA` | No separate tags | Direct French ownership | French colonies | `FRA` direct | Medium | No | Martinique/Guadeloupe-style holdings. |
| Dutch Caribbean | direct `NET` | No separate tags | Direct Dutch ownership | Dutch colonies | `NET` direct | Medium | No | Curacao/Aruba/Bonaire and nearby Dutch islands where map supports them. |
| Danish West Indies | direct `DEN` | No separate tag | Direct Danish ownership | Danish colony | `DEN` direct | Medium | No | Saint Thomas, Saint John, and Saint Croix if the province split can represent them. |
| Swedish Saint Barthelemy | direct `SWE` if province support exists | No separate tag | Direct Swedish ownership if map support is clean | Swedish colony | `SWE` direct | Weak/Medium | No | Preserve only if the `STATE_WEST_INDIES` province split gives a tolerable one-province hook; otherwise abstract into the nearest West Indies owner. |
| Venezuelan/New Granada Caribbean islands | `SC2` | New Granada | Assign to Spanish New Granada | Spanish colonial possession | `SC2` under `SPA` | Medium | No | Vanilla has a `VNZ` province in `STATE_WEST_INDIES`; since `VNZ` is absent in 1816, move it to `SC2` if it represents a Venezuela-linked island. |
| West Indies federation | `WIN` | West Indies | Start absent / formable or releasable | Not present | N/A | Strong | Yes | Use later/federal/alternate-history content only. |
| Antillean Confederation | `ATL` | Antillean Confederation | Start absent / formable or alt-history | Not present | N/A | Strong | Yes | Useful later tag, not a start country. |

## Approved Batch Decisions

1. Keep `CUB` and `PCO` as playable Spanish colonial subjects under `SPA`.
2. Use one playable `HAI` for western Haiti only, remove 1836-style Haitian ownership of Santo Domingo, and use `DOM` as Spanish Santo Domingo under `SPA`.
3. Make `JAM` and `BAH` playable British colonies under `GBR`.
4. Keep Bermuda as direct British ownership, not a playable tag.
5. Keep the British enclave in `STATE_GUATEMALA` as direct `GBR` ownership, with no new tag.
6. Keep British, French, Dutch, Danish, and possible Swedish island possessions as direct European ownership in `STATE_WEST_INDIES`, rather than creating new playable micro-colony tags.
7. Preserve direct Swedish ownership of Saint Barthelemy if the vanilla province split gives a tolerable hook; otherwise abstract it into the closest West Indies owner.
8. Move any vanilla `VNZ` island ownership in `STATE_WEST_INDIES` to `SC2` because Venezuela is not a start country.
9. Keep `WIN` and `ATL` absent, formable, or alternate-history rather than start countries.
10. Create no new `V**` tags for the Caribbean in this pass.
