# Africa Map Implementation Notes

This file tracks Africa state-history edits made after the approved Africa country/tag inventory.

## Implemented

### Nile Valley And Sudan

File: `mod/Congress of Vienna 1816/common/history/states/99_cow_1816_africa_states.txt`

The first Africa map-prep batch removes the anachronistic 1836 Egyptian conquest layer from Sudan while keeping vanilla state geometry:

| State | 1836 vanilla owner | 1816 owner in mod | Reason |
| --- | --- | --- | --- |
| `STATE_DONGOLA` | `EGY` | `SUD` | First-pass Sudanese/Funj-Sennar abstraction for the non-Egyptian Nile Valley. |
| `STATE_KORDOFAN` | `EGY` | `DFR` | Darfur held Kordofan before the Egyptian conquest. |
| `STATE_BLUE_NILE` | `EGY` | `SUD` | Core area for Sennar/Funj remnant abstraction. |

`SUD` already exists in vanilla as an unrecognized kingdom with Sudanese, Beja, and Bedouin cultures. The mod relocalizes it as Sennar and now gives it a basic starting history in `common/history/countries/00_cow_1816_custom_countries.txt`.

### Liberia

`STATE_LIBERIA` now removes the anachronistic `LIB` start colony. The four vanilla Liberian colony provinces are reassigned to the existing local `KRU` holder, the 1836 Liberia claim is removed, and the temporary Afro-American homeland marker is removed for the 1816 start.

### Approved Cleanup Batch

The user approved a conservative cleanup approach: when an exact 1816 polity is too fuzzy to model cleanly, use the nearest vanilla local or decentralized holder.

- `STATE_EASTERN_MALI` and the Massina-owned part of `STATE_TIMBUKTU` now go to `SGU` because Massina was founded after the start date.
- `STATE_ERITREA` no longer starts under `EGY`; the Egyptian-held provinces go to `TGR`, while existing Aussa ownership remains.
- `STATE_KENYA` removes later `WTU` ownership; Mombasa keeps the clean city-state piece, and Omani coastal holdings move to playable `ZAN`.
- `STATE_ZANZIBAR` now starts under playable `ZAN`.
- `STATE_LOURENCO_MARQUES` and `STATE_ZAMBEZIA` remove later `GZA` ownership while preserving Portuguese coastal holdings and nearby local/decentralized holders.
- `STATE_ZULULAND`, `STATE_VRYSTAAT`, and `STATE_TRANSVAAL` remove later Basutoland/Boer/Ndebele starts while keeping `ZUL` playable and using nearby local/decentralized holders.

Diplomacy:

- `OMA -> ZAN` is scripted as a tributary relationship.
- Vanilla `GBR -> LIB` protectorate is removed because Liberia is not a start country.

## Deferred Map Calls

These are approved at the broad design level, but still need later review:

- In-game map testing for conservative local/decentralized reassignments, especially southern Africa and Mozambique/Zambezia.
- Population, buildings, resource, government, and journal/event passes.
