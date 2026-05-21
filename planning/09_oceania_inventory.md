# Oceania Country Inventory

This file tracks the country/tag inventory for Oceania and the Pacific. The batch questions in this file were approved by the user.

## Scope And Rules

- Regional pass: Australia, New Zealand, Hawaii, Tahiti, Tonga, Fiji, New Caledonia, Vanuatu, Micronesia, Nauru, New Guinea, Solomon Islands, and the remaining Pacific islands represented by vanilla state regions.
- Island Southeast Asia and the Philippines are handled in `planning/08_asia_inventory.md`.
- Use the same moderately strict tag rule approved for earlier regions.
- Reuse vanilla tags wherever possible. Create `V**` tags only where a historically important polity has no usable vanilla tag and the map can plausibly show it.
- Keep this pass at country/tag and broad start-status level. Detailed population, buildings, resources, and exact province ownership come later.

## Historical Source Notes

- Hawaii was unified under Kamehameha I by 1810 and is a clean playable 1816 kingdom.
- Pomare II had re-established dominance in Tahiti after 1815, making Tahiti a reasonable playable start.
- New South Wales was the only separate Australian colony we should model as a start country; Van Diemen's Land was still under New South Wales until 1825, Western Australia begins in 1829, and South Australia begins in 1836.
- The United Tribes of New Zealand are too late for 1816, because the Declaration of Independence belongs to 1835 and British annexation/Treaty of Waitangi to 1840.
- Tonga was in a long period of war and disorder before later unification under Taufa'ahau/George Tupou I, so a unified playable Tonga is not recommended at start.
- Fiji was not unified in 1816; the short-lived Kingdom of Fiji is much later.

## Vanilla Tag Baseline

Useful vanilla support includes:

- Playable or candidate sovereign tags: `HAW`, `PLY`, and possibly `PNS` as a formable.
- British colonial tags: `NSW`, `TAS`, `WAS`, `SAS`, `AST`, `NZL`, and `UNT`.
- Maori/local New Zealand tags: `NTO`, `NTU`, `AOT`, and `UNT`.
- Aboriginal Australian tags: `ULR`, `NNG`, `KAU`, `GML`, `WTI`, and `MRN`.
- Pacific local/decentralized tags: `TNG`, `FJI`, `KNK`, `PPU`, `HLA`, `BLA`, `MCR`, `VNT`, and `NRU`.

No new `V**` tags are proposed for Oceania at this stage.

## Australia

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Colony of New South Wales | `NSW` | New South Wales | Reuse vanilla tag | Playable British colony | `GBR` colony | Strong | Yes | Approved: main Australian British colony in 1816. It should absorb/represent Van Diemen's Land for now. |
| Van Diemen's Land / Tasmania | `TAS` | Tasmania | Start absent / later colony or releasable | Not separate in 1816 | `NSW` administration | Strong | Yes | Approved: became separate from New South Wales in 1825; do not start as separate playable colony. |
| Western Australia | `WAS` | Western Australia | Start absent / later colony | Not present | N/A | Strong | Yes | Swan River colony begins in 1829, so not an 1816 start country. |
| South Australia | `SAS` | South Australia | Start absent / later colony | Not present | N/A | Strong | Yes | South Australia begins in 1836, after the mod start. |
| Australia / federation tag | `AST` | Australia | Start absent / formable only | Not present | N/A | Strong | Yes | Keep as later/federation outcome. |
| Aboriginal Australian polities | `ULR`, `NNG`, `KAU`, `GML`, `WTI`, `MRN` | Multiple vanilla tags | Reuse mostly as decentralized/local polities | Decentralized / non-state polity | None | Strong | Yes | Approved: keep decentralized/local rather than playable centralized countries. Remove inappropriate 1836 British protectorate-style setup for `KAU`; keep most of Australia decentralized outside colonial settlements. |

## New Zealand

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| North Island Maori polities | `NTO` | Ngati Toa | Reuse vanilla tag | Decentralized/local Maori polity | None | Medium | Yes | Approved: vanilla split is imperfect but useful; no British protectorate in 1816. |
| South Island Maori polities | `NTU` | Ngai Tahu | Reuse vanilla tag | Decentralized/local Maori polity | None | Medium | Yes | Approved: vanilla split is imperfect but useful; no British protectorate in 1816. |
| United Tribes | `UNT` | United Tribes | Start absent / later event country | Not present | N/A | Strong | Yes | Declaration of Independence is 1835, so `UNT` is too late for start. |
| Aotearoa | `AOT` | Aotearoa | Start absent / formable only | Not present | N/A | Strong | Yes | Use as later formable or alternate-history unification, not a start country. |
| New Zealand colony | `NZL` | New Zealand | Start absent / later colony | Not present | N/A | Strong | Yes | British colony belongs after 1840/1841, not 1816. |

## Polynesia

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Kingdom of Hawaii | `HAW` | Hawaii | Reuse vanilla tag | Playable sovereign/unrecognized kingdom | None | Strong | Yes | Approved: strong reuse candidate; Kamehameha I is still alive at start. |
| Kingdom of Tahiti / Pomare realm | `PLY` | Tahiti | Reuse vanilla tag | Playable sovereign/unrecognized kingdom | None | Strong | Yes | Approved: strong reuse candidate for Pomare II's Tahiti after 1815. |
| Tonga | `TNG` | Tonga | Keep decentralized/local | Decentralized / non-state polity | None | Strong | Yes | Approved: do not start as unified playable Tonga because the later unified kingdom is post-1816. |
| Polynesia | `PNS` | Polynesia | Start absent / formable only | Not present | N/A | Strong | Yes | Use as later formable or flavor tag only. |

## Melanesia, Micronesia, And New Guinea

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Fiji | `FJI` | Fiji | Keep decentralized/local | Decentralized / non-state polity | None | Strong | Yes | Approved: Fiji is not unified in 1816; Kingdom of Fiji is much later. |
| New Caledonia / Kanak | `KNK` | Kanak | Reuse vanilla tag | Decentralized/local polity | None | Strong | Yes | No French colony in 1816. |
| Vanuatu | `VNT` | Vanuatu | Reuse vanilla tag | Decentralized/local polity | None | Strong | Yes | No colonial condominium or unified state in 1816. |
| Nauru | `NRU` | Nauru | Reuse vanilla tag | Decentralized/local polity | None | Strong | Yes | Strong vanilla support. |
| Micronesia | `MCR` | Micronesia | Reuse vanilla tag | Decentralized/local polity | None | Strong | Yes | Broad vanilla abstraction; no new tag recommended. |
| Eastern New Guinea / Papuan areas | `PPU` | Papua | Reuse vanilla tag | Decentralized/local polity | None | Strong | Yes | No colonial ownership at start. |
| Solomon / Bougainville areas | `BLA`, `HLA` | Bilua, Halia | Reuse vanilla tags | Decentralized/local polities | None | Strong | Yes | Keep vanilla decentralized treatment. |

## Batch Questions For Approval

These are the design calls for the Oceania pass. Recommended answers are included so approval can be quick.

1. Australia: use `NSW` as the only playable British Australian colony at start, with Van Diemen's Land/Tasmania represented under `NSW` rather than as separate `TAS`? Approved.
2. Later Australian colonies: keep `WAS`, `SAS`, `TAS`, and `AST` absent/releasable/later rather than start countries? Approved.
3. Aboriginal Australia: keep `ULR`, `NNG`, `KAU`, `GML`, `WTI`, and `MRN` as decentralized/local polities, and remove inappropriate 1836 British protectorate setup for `KAU`? Approved.
4. New Zealand: keep `NTO` and `NTU` as decentralized/local Maori polities; keep `UNT`, `AOT`, and `NZL` absent/later/formable, with no British protectorate in 1816? Approved.
5. Hawaii: use `HAW` as a playable sovereign kingdom under Kamehameha I? Approved.
6. Tahiti: use `PLY` as a playable Kingdom of Tahiti/Pomare realm with no French subject status? Approved.
7. Tonga: keep `TNG` decentralized/local rather than a unified playable kingdom at start? Approved.
8. Fiji: keep `FJI` decentralized/local rather than a unified playable kingdom at start? Approved.
9. Melanesia/Micronesia/New Guinea: keep `KNK`, `VNT`, `NRU`, `MCR`, `PPU`, `BLA`, and `HLA` as decentralized/local polities with no European colonial ownership in 1816? Approved.
10. New tags: create no new `V**` tags for Oceania in this pass? Approved.
