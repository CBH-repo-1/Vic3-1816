# South America Country Inventory

This file tracks the country/tag inventory for South America and the remaining Central America edge cases. The batch questions in this file were approved by the user.

## Scope And Rules

- Regional pass: Spanish South America, Brazil, the Rio de la Plata region, Paraguay, Banda Oriental/Federal League, Guianas, South American indigenous/local polities, and Panama/New Granada carryover from the Central America pass.
- New Spain and the Captaincy General of Guatemala are already handled in `planning/10_north_america_inventory.md`.
- Use the same moderately strict tag rule approved for earlier regions.
- Reuse vanilla tags wherever possible. Create `V**` tags only where a historically important polity has no usable vanilla tag and the map can plausibly show it.
- Keep this pass at country/tag and broad start-status level. Detailed population, buildings, resources, exact province ownership, and wars come later.

## Historical Source Notes

- Spanish South America is still mid-war in 1816. The clean first pass should separate de facto start countries from later independence tags and handle active liberation wars in a later war/journal pass.
- New Granada is in the 1815-1816 Spanish reconquest moment. A Spanish `SC2` New Granada setup is cleaner than starting `CLM`, `VNZ`, and `ECU` as normal independent countries.
- Peru remains the major Spanish royalist stronghold. `SC3` is a strong fit for a playable Spanish Peru/Royalist Peru colonial subject.
- Chile is in the royalist reconquest period on January 1, 1816; Chilean independence belongs after Chacabuco and the 1818 declaration, so `CHL` should not start independent.
- The United Provinces of the Rio de la Plata are de facto independent before their July 1816 declaration, so `ARG` is a reasonable playable start tag even though the formal declaration happens during the first game year.
- Paraguay is already independent in practice and Jose Gaspar Rodriguez de Francia receives dictatorship for life in 1816, making `PRG` a strong playable start.
- Artigas dominates Banda Oriental by 1815 and leads a federal alternative to Buenos Aires, making `URU` a useful playable 1816 abstraction.
- Brazil is already covered by the approved Portugal decision: `POR` represents the United Kingdom of Portugal, Brazil and the Algarves. `BRZ` should be later/releasable/independence content, not a start country.

## Vanilla Tag Baseline

Useful vanilla support includes:

- Active/start candidate tags: `ARG`, `PRG`, `URU`, `SC2`, `SC3`, and existing `POR` from Europe/global planning.
- Later/formable/releasable tags: `BRZ`, `CHL`, `CLM`, `VNZ`, `ECU`, `PEU`, `BOL`, `GCO`, `PBC`, `NPU`, `SPU`, `IQU`, `FND`, `PNM`, `SC4`, and possibly `YUC`/Central American successors already covered in North America.
- Indigenous/local tags: `PAT`, `AYM`, `TPI`, `ORN`, `MUI`, `WYU`, `GNI`, and related vanilla decentralized/unrecognized tags.

No new `V**` tags are proposed for South America at this stage.

## New Granada, Venezuela, Ecuador, And Panama

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Viceroyalty / Captaincy complex of New Granada | `SC2` | Nueva Granada / New Granada | Reuse vanilla tag | Playable Spanish colonial subject | `SPA` colony/viceroyalty | Strong | No | Approved: use as the broad Spanish royalist authority for Colombia, Venezuela, Ecuador, and Panama after the 1815-1816 reconquest. |
| Colombia / New Granada republic | `CLM` | Colombia | Start absent / revolutionary or later | Not stable start country | N/A | Strong | Yes | Use for later independence or post-war setup, not January 1816. |
| Venezuela | `VNZ` | Venezuela | Start absent / revolutionary or later | Not stable start country | N/A | Strong | No | Patriot forces can be represented later by journals/wars; do not start as normal independent Venezuela. |
| Ecuador / Quito | `ECU` | Ecuador | Start absent / later | Not independent | N/A | Strong | Yes | Remains under Spanish/Peruvian/New Granada royalist structure in first pass. |
| Gran Colombia | `GCO` | Gran Colombia | Start absent / formable or later event | Not present | N/A | Strong | Yes | Created later; useful formable/event outcome. |
| Federation of the Andes | `FND` | Federation of the Andes | Start absent / formable only | Not present | N/A | Strong | Yes | Alt-history or late-game formable only. |
| Panama | `PNM` | Panama | Start absent / later or releasable | Not independent | `SC2` | Strong | Yes | Central America loose end: Panama should be part of `SC2`, not a start country. |

## Peru, Upper Peru, And Chile

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Viceroyalty of Peru / Royalist Peru | `SC3` | Peru colonial tag | Reuse vanilla tag | Playable Spanish colonial subject | `SPA` colony/viceroyalty | Strong | No | Approved: main royalist Spanish South America tag for Peru, Upper Peru, and royalist Chile where map support allows. |
| Peru | `PEU` | Peru | Start absent / later independence tag | Not independent | N/A | Strong | Yes | Peru declares independence later in 1821. |
| Upper Peru / Bolivia | `BOL` | Bolivia | Start absent / later independence tag | Not independent | N/A | Strong | Yes | Upper Peru remains royalist/contested; Bolivia is later. |
| Chile | `CHL` | Chile | Start absent / revolutionary/later tag | Not independent in 1816 | N/A | Strong | No | Chile is in the royalist reconquest period; liberation starts in 1817 and independence is declared in 1818. |
| Peru-Bolivia and Peru split tags | `PBC`, `NPU`, `SPU`, `IQU` | Multiple | Start absent / later or formable | Not present | N/A | Strong | Yes | Later 19th-century or event/formable material, not start countries. |

## Rio De La Plata, Paraguay, And Banda Oriental

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| United Provinces of the Rio de la Plata | `ARG` | Argentina | Reuse/relocalize | Playable de facto independent state | None | Strong | No | Approved: relocalize to United Provinces / Rio de la Plata for 1816; formal independence occurs July 9, 1816. |
| Paraguay | `PRG` | Paraguay | Reuse vanilla tag | Playable sovereign/unrecognized or recognized republic/dictatorship | None | Strong | No | Approved strong reuse candidate under Francia. |
| Banda Oriental / Artigas Federal League | `URU` | Uruguay | Reuse/relocalize | Playable Artiguist state/federal league abstraction | None | Strong | No | Approved playable abstraction; model Federal League ties through diplomacy/journals rather than giving all allied provinces to `URU` by default. |
| Spanish Rio de la Plata colonial tag | `SC4` | Rio de la Plata | Start absent / fallback colonial tag | No clean start land | `SPA` if used | Medium | No | The old viceroyalty has collapsed for practical gameplay. Keep `SC4` absent unless map scripting needs a Spanish remnant. |

## Brazil And Guianas

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| United Kingdom of Portugal, Brazil and the Algarves | `POR` | Portugal | Reuse approved global tag | Playable transatlantic monarchy | None | Strong | No | Approved: `POR` represents the whole monarchy, including Brazil. |
| Brazil | `BRZ` | Brazil | Start absent / later independence or releasable | Not separate at start | `POR` internal kingdom | Strong | Yes | Brazil is a coequal kingdom inside `POR`, not a separate start country in the first pass. |
| Brazilian regional revolts | possible vanilla releasables | N/A | Later events/journals | Not start countries | `POR` | Medium | No | Pernambuco 1817 and later revolts can wait for event/journal work. |
| Guianas | direct European ownership | N/A | Use direct ownership | Colonial possessions | `GBR`, `NET`, `FRA` as relevant | Strong | No | No new Guiana tag recommended; vanilla `GUI` is Guizhou, not Guiana. |

## Indigenous And Local Polities

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Mapuche / Araucania / Patagonia | `PAT` | Mapuche | Reuse vanilla tag | Decentralized/local polity | None | Strong | No | Recommended: keep decentralized/local rather than a centralized playable country in first pass. Vanilla `ARA` is Arabia, so do not use it. |
| Aymara / Andean local polities | `AYM` | Aymara | Reuse as local/releasable if needed | Local/decentralized or absent | `SC3` frontier | Medium | No | Avoid over-splitting Upper Peru in the first pass. |
| Amazon, Orinoco, Muisca, Wayuu, Tupinamba, Guarani areas | `ORN`, `MUI`, `WYU`, `TPI`, `GNI`, related tags | Multiple | Reuse mostly as decentralized/local polities | Decentralized/local | None or colonial frontiers | Medium | No | Keep broad decentralized/local treatment unless a later map review finds a compelling playable case. |

## Batch Questions For Approval

These are the design calls for the South America pass. Recommended answers are included so approval can be quick.

1. Scope: use this pass to cover South America plus the Panama/New Granada loose end from Central America? Approved.
2. New Granada/Panama: use `SC2` as a playable Spanish New Granada colonial subject covering Colombia/Venezuela/Ecuador/Panama where map support allows; keep `PNM`, `CLM`, `VNZ`, `ECU`, `GCO`, and `FND` absent/later/formable? Approved.
3. Peru/Chile/Upper Peru: use `SC3` as playable Spanish Royalist Peru, including Peru, Upper Peru, and royalist Chile where the map supports it; keep `PEU`, `BOL`, and `CHL` absent/later/revolutionary? Approved.
4. Rio de la Plata: use `ARG` relocalized as the United Provinces / Rio de la Plata as a playable de facto independent state, even though formal independence is July 9, 1816? Approved.
5. Paraguay: use `PRG` as a playable independent Paraguay under Francia-style dictatorship/isolation? Approved.
6. Banda Oriental/Federal League: use `URU` relocalized as Banda Oriental / Artigas Federal League as a playable abstraction, with Federal League influence modeled by diplomacy/journals rather than automatically giving it all allied Argentine provinces? Approved.
7. Old Spanish River Plate: keep `SC4` absent/fallback rather than starting a Spanish Rio de la Plata country with land? Approved.
8. Brazil: keep the already-approved `POR` transatlantic monarchy controlling Brazil; keep `BRZ` absent/later/releasable rather than a separate start country? Approved.
9. Guianas: use direct European ownership for British/Dutch/French Guianas and create no new Guiana tag? Approved.
10. Indigenous/local South America: keep `PAT`, `AYM`, `ORN`, `MUI`, `WYU`, `TPI`, `GNI`, and related tags decentralized/local or releasable rather than centralized playable start countries in the first pass? Approved.
11. New tags: create no new `V**` tags for South America in this pass? Approved.
