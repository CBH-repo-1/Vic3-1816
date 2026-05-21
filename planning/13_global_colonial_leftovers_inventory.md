# Global Island And Colonial Leftovers Inventory

This file catches the small state regions and colonial edge cases that do not belong cleanly to a single regional pass. This is a cleanup pass, not a new major world region.

## Scope And Rules

- Pass status: approved at the country/tag and broad ownership level.
- Keep this at country/tag and broad ownership level.
- Do not add new playable tags for tiny island possessions unless a vanilla tag already exists and playability has already been approved.
- Use direct ownership for minor naval stations, island colonies, and isolated colonial possessions unless there is a strong gameplay reason to make them playable.
- Use the vanilla map. Several historically important islands are represented only as sea regions or not at all, so they may not need any country-history scripting.

## Major Regions Already Covered

The main country/tag planning sweep now covers every major inhabited region:

- Europe
- Middle East and North Africa
- Africa
- Central Asia and Afghanistan
- Rest of Asia
- Oceania
- North America and Central America
- South America
- Caribbean

The remaining items below are mostly island state-region cleanup and 1836-to-1816 ownership corrections.

## Atlantic Islands

| State region / place | Vanilla baseline | Proposed 1816 action | Start status | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- |
| `STATE_AZORES` | `POR` | Keep direct `POR` ownership | Portuguese integral island possession | Yes | No new tag. |
| `STATE_MADEIRA` | `POR` | Keep direct `POR` ownership | Portuguese integral island possession | Yes | No new tag. |
| `STATE_CAPE_VERDE` | `POR` | Keep direct `POR` ownership | Portuguese colony | Yes | No new tag. |
| `STATE_CANARY_ISLANDS` | `SPA` | Keep direct `SPA` ownership | Spanish integral/colonial island possession | Yes | No new tag. |
| `STATE_BALEARIC_ISLANDS` | `SPA` | Keep direct `SPA` ownership | Spanish integral island possession | Yes | No new tag. |
| `STATE_BERMUDA` | `GBR` | Already approved: keep direct `GBR` ownership | British colony/naval station | Yes | Covered in Caribbean pass. |

## South Atlantic And Unrepresented Islands

| State region / place | Vanilla baseline | Proposed 1816 action | Start status | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- |
| `STATE_SOUTH_ATLANTIC_ISLANDS` | Direct `GBR` | Keep direct `GBR` ownership as a first-pass gameplay abstraction | British possession / disputed claim abstraction | Yes | The mapped hubs are Falklands-style, which is anachronistic for firm British control in 1816. Recommended compromise: leave vanilla `GBR` ownership for stability and handle Spanish successor/Argentine claim pressure later through claims or events if desired. |
| Saint Helena / Ascension / Tristan da Cunha | Sea-region references only | No country-history action | Not represented as land state | Yes | `STATE_COAST_OF_SAINT_HELENA` is a sea region, not a land ownership target in the audited files. |
| Easter Island | Sea-region reference only | No country-history action | Not represented as land state | Yes | `STATE_EASTER_ISLAND` appears under sea state regions in the audited files, not as a normal owned state. |
| Galapagos area | Sea-region reference only | No country-history action | Not represented as land state | Yes | `STATE_GALAPAGOS_RISE` is a sea region, not an owned island state. |

## Mediterranean Islands

| State region / place | Vanilla baseline | Proposed 1816 action | Start status | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- |
| `STATE_CORSICA` | `FRA` | Keep direct `FRA` ownership | French integral island possession | Yes | No new tag. |
| `STATE_SARDINIA` | `SAR` | Keep under `SAR` | Core part of Sardinia-Piedmont | Yes | Already fits the Italian pass. |
| `STATE_IONIAN_ISLANDS` | `ION` | Already approved: keep `ION` as British protectorate | Playable British protectorate | Yes | Covered in Europe/Italy pass. |
| `STATE_MALTA` | Direct `GBR` | Already approved: make `MLT` playable British crown colony if technically feasible | British colony | No | Needs country-history and subject setup. |
| `STATE_CYPRUS` | `TUR` | Keep direct `TUR` ownership; keep `CYP` absent/releasable | Ottoman direct possession | Yes | Already approved in Europe/MENA pass. |
| `STATE_CRETE` | `EGY` | Move from `EGY` to direct `TUR` ownership | Ottoman direct possession | Yes | Backdates the 1836 Egyptian setup to 1816. |
| `STATE_WEST_AEGEAN_ISLANDS` | `GRE` | Move from `GRE` to direct `TUR` ownership | Ottoman direct possession | Yes | Greece is absent at start; Greek independence begins later. |
| `STATE_EAST_AEGEAN_ISLANDS` | `TUR` | Keep direct `TUR` ownership | Ottoman direct possession | Yes | Already fits 1816. |

## Indian Ocean And Asian/Oceanian Islands

| State region / place | Vanilla baseline | Proposed 1816 action | Start status | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- |
| `STATE_CEYLON` | `BCE` and `MLD` | Already approved: keep `BCE` as British Ceylon and `MLD` as independent Maldives if map support is clean | British colony plus Maldives | No | Covered in Asia pass; exact subject and state split need scripting review. |
| `STATE_RYUKYU_ISLANDS` | `JAP` | Already approved: create `V07` Ryukyu and move Ryukyu provinces to it | Playable Ryukyu subject/flavor state | No | Covered in Asia pass. |
| `STATE_MASCARENES` | Sea strategic region | No land ownership action | Not represented as normal land state | Yes | Mauritius, Reunion, Seychelles, and nearby islands do not appear as normal owned land states in the audited vanilla files. |

## Approved Batch Decisions

1. Keep Azores, Madeira, Cape Verde, Canary Islands, and Balearic Islands as direct `POR`/`SPA` ownership with no new playable tags.
2. Keep `STATE_SOUTH_ATLANTIC_ISLANDS` as direct `GBR` ownership for the first pass, despite the 1816 anachronism, and optionally model Argentine/Spanish-successor claim pressure later.
3. Take no action for Saint Helena, Ascension, Tristan da Cunha, Easter Island, Galapagos, and Mascarenes unless a later map audit proves they are normal owned land states.
4. Keep Corsica, Sardinia, Balearics, and Cyprus as above; keep already-approved `ION` and `MLT` plans; move Crete plus West Aegean Islands from 1836 owners back to `TUR`.
5. Treat Ceylon, Maldives, and Ryukyu as already covered by the Asia pass and do not reopen them in this cleanup pass.
6. Create no new `V**` tags in this global leftovers pass.
