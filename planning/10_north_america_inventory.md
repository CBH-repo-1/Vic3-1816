# North America Country Inventory

This file tracks the country/tag inventory for North America, Central America, and the Caribbean. The batch questions in this file were approved by the user.

## Scope And Rules

- Regional pass: British North America, the United States, Russian Alaska, Spanish North America, Central America, the Caribbean, and North American indigenous polities.
- Panama and New Granada sit on the edge of this pass. Record Panama notes here, but finalize `SC2` / New Granada handling in the South America pass.
- Greenland was already handled in the Europe/Oceania planning as Danish direct or releasable-only, so do not reopen it here unless map scripting forces it.
- Use the same moderately strict tag rule approved for earlier regions.
- Reuse vanilla tags wherever possible. Create `V**` tags only where a historically important polity has no usable vanilla tag and the map can plausibly show it.
- Keep this pass at country/tag and broad start-status level. Detailed population, buildings, resources, exact province ownership, and wars come later.

## Historical Source Notes

- The United States should start after the War of 1812, but before Florida is ceded by Spain and before later western expansion into Texas, California, Oregon, and the Mexican Cession.
- British North America is not Canada yet. Upper Canada, Lower Canada, Nova Scotia, New Brunswick, Newfoundland, and Hudson's Bay Company/Rupert's Land are cleaner start entities than a unified `CAN`.
- New Spain still exists in 1816, and vanilla has a purpose-built `SC1` New Spain tag.
- Central America is still under Spanish rule in 1816. The later United Provinces/Federal Republic setup belongs after independence.
- Haiti is awkward: western Haiti is split between Henri Christophe's northern kingdom and Alexandre Petion's southern republic in 1816, but the vanilla map only gives us a broad Haiti state. Recommended first pass is one playable `HAI` with internal-conflict flavor.
- Santo Domingo is Spanish in 1816. The independent Dominican Republic is much later.
- Russian America is a clean start use for vanilla `ALK`.
- `COM` is approved as a playable Comanche / Comancheria abstraction for variety. This is not a strict centralized-state interpretation, but it gives North America a strong indigenous player country in a strategically interesting region.

## Vanilla Tag Baseline

Useful vanilla support includes:

- Major sovereign or colonial tags: `USA`, `SC1`, `QUE`, `ONT`, `NVS`, `NBS`, `NEW`, `HBC`, `ALK`, `HAI`, `CUB`, `PCO`, `DOM`, `JAM`, `BAH`, and `GUA`.
- Later/formable/releasable tags: `CAN`, `MEX`, `TEX`, `CAL`, `DES`, `NEN`, `CSA`, `FSA`, `ASA`, `LOU`, `UCA`, `ELS`, `HON`, `NIC`, `COS`, `YUC`, `RIO`, `WIN`, `COL`, `ORG`, `MTC`, `PNM`, and `SC2`.
- Indigenous/local tags: `CHE`, `MSC`, `SML`, `IRO`, `MKT`, `MAY`, `PUE`, `COM`, `DKT`, `LKT`, `NVJ`, `APC`, `UTE`, `PWN`, `BLF`, `ABS`, `IRC`, `ATB`, `CSC`, `SLS`, `BNN`, `NNV`, `CCM`, `NZP`, and related vanilla decentralized tags.
- Approved special playability promotion: `COM` should be playable as Comanche / Comancheria for gameplay variety.

Approved custom tags:

- `V08` Choctaw Nation.
- `V09` Chickasaw Nation.

These were added because they were important treaty polities and vanilla appears not to provide clean Choctaw or Chickasaw country tags. The approved map compromise keeps both playable inside `STATE_MISSISSIPPI`: `V09` in the northern band and `V08` in the central/southern band.

## British North America

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Lower Canada | `QUE` | Quebec | Reuse/relocalize | Playable British colony | `GBR` colony | Strong | No | Approved: relocalize to Lower Canada for 1816 if localization is clean. |
| Upper Canada | `ONT` | Ontario | Reuse/relocalize | Playable British colony | `GBR` colony | Strong | No | Approved: relocalize to Upper Canada for 1816 if localization is clean. |
| Nova Scotia | `NVS` | Nova Scotia | Reuse vanilla tag | Playable British colony | `GBR` colony | Strong | No | Approved: maritime setup may need to fold Prince Edward Island depending map support. |
| New Brunswick | `NBS` | New Brunswick | Reuse vanilla tag | Playable British colony | `GBR` colony | Strong | No | Approved strong reuse candidate. |
| Newfoundland | `NEW` | Newfoundland | Reuse vanilla tag | Playable British colony | `GBR` colony | Strong | No | Approved strong reuse candidate. |
| Hudson's Bay Company / Rupert's Land | `HBC` | Hudson's Bay Company | Reuse vanilla tag | Playable chartered company / colony | `GBR` chartered company or colony | Strong | No | Approved strong reuse candidate; should own or claim much of Rupert's Land, with indigenous decentralized countries preserved where appropriate. |
| Canada | `CAN` | Canada | Start absent / formable only | Not present | N/A | Strong | Yes | Confederation is 1867; do not start unified Canada. |
| British Columbia / Columbia | `COL` | Columbia | Start absent / later colony | Not present | N/A | Strong | Yes | British Columbia is a later colony; Pacific Northwest should be claims, HBC activity, and decentralized/local polities. |
| Metis / Red River | `MTC` | Metis | Later/releasable/local | Not a start country in first pass | HBC frontier | Medium | No | Important, but better handled by events or later emergence unless user wants extra frontier playability. |

## United States, Russian America, And Disputed West

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| United States of America | `USA` | America | Reuse vanilla tag | Playable recognized republic | None | Strong | No | Approved: use 1816 borders; no Florida, no Texas, no California/New Mexico, no sole Oregon ownership. |
| Russian America | `ALK` | Alaska | Reuse vanilla tag | Playable Russian colonial company | `RUS` colony/chartered company | Strong | No | Approved: vanilla comments already point at Russian-American Company. |
| Oregon Country / Columbia District | `ORG` | Oregon | Start absent / disputed region | Not a country | US/GBR/HBC claims | Medium | No | Recommended: do not start `ORG`; represent disputed claims later through diplomacy/journals. |
| New England | `NEN` | New England | Start absent / releasable only | Not present | N/A | Strong | Yes | Releasable/alternate-history only. |
| Confederate, Free, and New Africa tags | `CSA`, `FSA`, `ASA` | Multiple | Start absent / later or alternate-history | Not present | N/A | Strong | Yes | Civil War and alt-history tags, not 1816 countries. |
| Texas, California, Deseret, Louisiana, Rio Grande | `TEX`, `CAL`, `DES`, `LOU`, `RIO` | Multiple | Start absent / later or releasable | Not present | N/A | Strong | Yes | In 1816 these should be Spanish/New Spain, US internal, indigenous/local, or later emergence depending region. |

## Spanish North America And Central America

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Viceroyalty of New Spain | `SC1` | Nueva Espana / New Spain | Reuse vanilla tag | Playable Spanish colonial subject | `SPA` colony/viceroyalty | Strong | No | Approved: best vanilla fit for Mexico, Texas, California, New Mexico, and other Spanish North American holdings. |
| Captaincy General of Guatemala | `GUA` | Guatemala | Reuse/relocalize | Playable Spanish colonial subject | `SPA` colony, maybe under `SC1` flavor | Strong | No | Approved: separate playable colonial subject for Guatemala through Costa Rica, instead of starting independent Central America. |
| Mexico | `MEX` | Mexico | Start absent / formable or revolutionary tag | Not independent in 1816 | N/A | Strong | Yes | Mexican independence succeeds later; active independence-war scripting can wait. |
| Central American successor states | `UCA`, `ELS`, `HON`, `NIC`, `COS` | Multiple | Start absent / later or releasable | Not independent in 1816 | N/A | Strong | Yes | Use later emergence/formables; do not start as independent. |
| Yucatan and Maya areas | `YUC`, `MAY` | Yucatan, Maya | Start absent/local | Not independent in first pass | `SC1` / `GUA` frontier | Medium | No | `MAY` can be decentralized/local if province review supports it; `YUC` is later/releasable. |
| Panama | `PNM` / `SC2` | Panama / New Granada | Defer final ownership to South America pass | Not independent | `SC2` Spanish colonial subject likely | Strong | No | Panama is geographically Central America but politically tied to New Granada for this era. |
| Spanish Florida | no separate tag | N/A | Spanish ownership without new tag | Spanish colony | `SPA`, `SC1`, or `CUB` after map review | Medium | No | Vanilla `FLA` is Flanders, so do not use it. Recommended: no new Florida tag. |

## Caribbean

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Haiti | `HAI` | Haiti | Reuse vanilla tag | Playable sovereign state | None | Strong | No | Approved: one playable Haiti despite the north/south split, with internal-conflict flavor later. |
| Spanish Santo Domingo | `DOM` | Santo Domingo | Reuse/relocalize | Playable Spanish colony or direct Spanish possession | `SPA` colony | Strong | No | Not the independent Dominican Republic in 1816. |
| Cuba | `CUB` | Cuba | Reuse vanilla tag | Playable Spanish colony | `SPA` colony | Strong | No | Strong reuse candidate. |
| Puerto Rico | `PCO` | Puerto Rico | Reuse vanilla tag | Playable Spanish colony | `SPA` colony | Strong | No | Strong reuse candidate. |
| Jamaica | `JAM` | Jamaica | Reuse vanilla tag | Playable British colony | `GBR` colony | Strong | No | Strong reuse candidate. |
| Bahamas | `BAH` | Bahamas | Reuse vanilla tag | Playable British colony | `GBR` colony | Strong | No | Strong reuse candidate. |
| West Indies federation | `WIN` | West Indies | Start absent / formable or umbrella only | Not present | N/A | Strong | Yes | Use for later federation or broad releasable, not start. |
| Minor Caribbean possessions | direct European ownership | N/A | Use direct ownership unless map support is unusually clean | Colonial possessions | FRA/NET/DEN/SWE/GBR/SPA as relevant | Medium | No | Avoid creating tiny island tags unless the vanilla map gives a clean state/province hook. |

## Indigenous And Local Polities

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Cherokee Nation | `CHE` | Cherokee | Reuse vanilla tag | Playable unrecognized/treaty polity | US pressure/treaty relation | Medium | No | Strongest indigenous playable candidate in the US southeast. |
| Muscogee / Creek | `MSC` | Muscogee | Reuse vanilla tag | Playable unrecognized/treaty polity | US/Spanish frontier pressure | Medium | No | Good playable candidate if map split works. |
| Seminole | `SML` | Seminole | Reuse vanilla tag | Decentralized/local or playable edge case | Spanish Florida / US frontier | Medium | No | First pass recommendation: keep local/decentralized unless we decide to model the First Seminole War as a start crisis. |
| Comanche / Comancheria | `COM` | Comanche | Reuse vanilla tag and promote to playable | Playable unrecognized abstraction | None / frontier relations with `USA` and `SC1` | Strong | Yes | Approved special playability candidate. This abstracts a powerful band-based equestrian polity into a playable country for variety. |
| Choctaw Nation | `V08` | No clean vanilla tag | Add custom tag | Playable unrecognized/treaty polity | US pressure/treaty relation | Medium | Yes | Implemented with the central/southern `STATE_MISSISSIPPI` province split. |
| Chickasaw Nation | `V09` | No clean vanilla tag | Add custom tag | Playable unrecognized/treaty polity | US pressure/treaty relation | Medium | Yes | Implemented with the northern `STATE_MISSISSIPPI` province split. |
| Haudenosaunee / Iroquois Confederacy | `IRO` | Haudenosaunee | Reuse vanilla tag if map support is tolerable | Playable unrecognized or represented through pops/claims | US/GBR borderland | Weak/Medium | No | Historically important, but vanilla state scale may be the limiting factor. |
| Miskito Kingdom / Coast | `MKT` | Miskitia | Reuse vanilla tag | Playable unrecognized / British-aligned protectorate | British influence | Strong | No | Strong reuse candidate on the Caribbean coast. |
| Pueblo communities | `PUE` | Pueblo | Reuse as local/decentralized or New Spain internal | Local/decentralized | `SC1` frontier | Medium | No | Important, but not recommended as a fully sovereign start country. |
| Maya areas | `MAY` | Maya | Reuse as local/decentralized if map supports | Local/decentralized or absent | `SC1`/`GUA` frontier | Medium | No | Avoid making a unified Maya kingdom at start. |
| Other Plains, Southwest, Northwest, and northern peoples | `DKT`, `LKT`, `NVJ`, `APC`, `UTE`, `PWN`, `BLF`, `ABS`, `IRC`, `ATB`, `CSC`, `SLS`, `BNN`, `NNV`, `CCM`, `NZP`, others | Multiple vanilla tags | Reuse mostly as decentralized/local polities | Decentralized / local polities | None or frontier relations | Strong | No | Keep broad decentralized setup unless a specific polity is deliberately promoted like `COM`. |

## Batch Questions For Approval

These are the design calls for the North America pass. Recommended answers are included so approval can be quick.

1. Scope: treat this pass as Canada, the United States, Mexico/New Spain, Central America, Alaska, and the Caribbean, while leaving final Panama/New Granada details to the South America pass? Approved.
2. British North America: start `QUE`, `ONT`, `NVS`, `NBS`, `NEW`, and `HBC` as playable British colonies/chartered company subjects; keep `CAN` formable/absent and `COL` later/absent? Approved.
3. United States: use `USA` as a playable recognized republic with 1816 borders, excluding Spanish Florida, Texas, California/New Mexico, and sole Oregon ownership? Approved.
4. Russian America: use `ALK` as a playable Russian-American Company style subject under `RUS`? Approved.
5. Pacific Northwest: keep `ORG` and `COL` absent at start and represent Oregon/Columbia through claims, HBC activity, and decentralized/local peoples instead of a start country? Approved.
6. New Spain: use vanilla `SC1` as a playable Spanish colonial subject for New Spain, rather than forcing `MEX` to exist in 1816? Approved.
7. Central America: use `GUA` relocalized as the Captaincy General of Guatemala as a playable Spanish colonial subject; keep `UCA`, `ELS`, `HON`, `NIC`, and `COS` absent/later/releasable? Approved.
8. Mexico independence: keep `MEX` absent/formable/revolutionary at start, and delay active Mexican War of Independence scripting until the war/journal pass? Approved.
9. Spanish Florida: create no new Florida tag and do not use vanilla `FLA` because it is Flanders; assign Spanish Florida to direct `SPA`, `SC1`, or `CUB` after map review? Approved.
10. Caribbean colonies: make `CUB`, `PCO`, `DOM`, `JAM`, and `BAH` playable colonial subjects where map support is clean; keep `WIN` as later/formable and minor island possessions as direct European ownership? Approved.
11. Haiti: use one playable `HAI` for western Haiti despite the 1816 Christophe/Petion split, and represent the split with flavor/internal instability later rather than another start tag? Approved.
12. Indigenous playable candidates: make `CHE`, `MSC`, `MKT`, and approved special candidate `COM` playable unrecognized/protectorate-style countries; review `IRO` for playable status only if the map can support it cleanly? Approved.
13. New custom indigenous tags: reserve `V08` for Choctaw and `V09` for Chickasaw if map review supports them? Approved and implemented with a generous `STATE_MISSISSIPPI` split.
14. Other indigenous/local tags: keep most Plains, Southwest, Northwest, northern, Pueblo, Maya, and Seminole tags decentralized/local rather than centralized playable countries in the first pass, except approved playable `COM`? Approved.
