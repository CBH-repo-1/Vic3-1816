# Central Asia And Afghanistan Population Refinement Audit

Status: approved cleanup implemented.

## Scope

This pass reviewed the Afghanistan, Baluchistan, Central Asian khanate, Kazakh zhuz, and immediate frontier pop setup after the Europe, MENA, and Sub-Saharan Africa refinement passes.

Files reviewed:

- `common/history/pops/09_central_asia.txt`.
- `common/history/pops/10_india.txt`.
- `common/history/states/00_states.txt`.
- `common/history/diplomacy/99_cow_1816_central_asia_subjects.txt`.
- Central Asia planning notes `07_central_asia_afghanistan_inventory.md` and `17_mena_central_asia_asia_map_implementation.md`.

## Current Snapshot

Major owner totals in the audited area:

- `KAB`: 3,364,505.
- `KAN`: 1,088,284.
- `HER`: 932,107.
- `KUN`: 139,270.
- `MAI`: 60,613.
- `KAF`: 26,748.
- `BUK`: 1,477,596.
- `KHI`: 1,043,388.
- `KOK`: 1,619,460.
- `TRM`: 510,125.
- `KZH`: 616,122.
- `OZH`: 459,420.
- `UZH`: 196,745.
- `KAL`: 577,392.
- `MAK`: 589,507.

The Afghan fragmentation, Khanate setup, Kalat/Makran setup, and limited Russian frontier ownership are broadly consistent with the approved country/tag design.

## Implemented Correction

### Semireche Was Assigned To `OZH`, But Fits `UZH`

Current setup:

- `STATE_SEMIRECHE`, owner: `OZH`.
- `STATE_SEMIRECHE`, `OZH` pop total: 242,674.
- Composition preserved from current file:
  - `russian`: 23,130.
  - `kazak`: 216,124.
  - `tatar`: 3,420.

Why this looks wrong:

- Our approved design uses `UZH` for Senior/Uly Zhuz and says it should be more autonomous than the Russian-influenced middle/northern hordes.
- Semireche/Jetisu is the classic Senior/Uly Zhuz area, while `OZH` is the Middle/Orta Zhuz and belongs more cleanly in central/northern/eastern Kazakhstan.
- A source checked during the audit places the Senior Zhuz in Semirechye, the Ili basin, and the Chu/Talas area, while placing the Middle Zhuz in central, northern, eastern, and part of southern Kazakhstan.

Implemented correction:

- Changed `STATE_SEMIRECHE` ownership from `OZH` to `UZH`.
- Changed the matching `STATE_SEMIRECHE` pop bucket from `region_state:OZH` to `region_state:UZH`.
- Preserved all existing pop sizes and composition.

Result:

- `OZH` total falls from 459,420 to 216,746.
- `UZH` total rises from 196,745 to 439,419.
- No country or regional total population is created or destroyed; this is a state-owner alignment fix.

This also strengthens the already-approved decision to remove the vanilla `RUS -> UZH` protectorate and keep Senior Zhuz more autonomous at game start.

## Leave Alone For Now

- `RUS` frontier ownership in `STATE_URALSK` and `STATE_AKMOLINSK` should stay for now. It is limited and fits the approved frontier/fort-line abstraction.
- `STATE_SYRDARYA` should stay split between `UZH`, `OZH`, `KZH`, and `KOK` for now. The state straddles Kazakh and Kokand influence zones, and changing it cleanly is more design-sensitive than the Semireche fix.
- Afghan tag totals should stay as-is for this pass. The current fragmented total is plausible enough for gameplay and not obviously a zero-pop or ownership bug.
- `BUK`, `KHI`, `KOK`, and `TRM` should stay as-is for this pass. The available 1816-ish population evidence is too rough to justify a new rescale without drifting into low-confidence estimation.
- `KAL` and `MAK` should stay as-is for now. Makran is large compared with Kalat, but changing it would be a broader Baluchistan design pass rather than a clear bug fix.

## Validation

- `common/history/states/00_states.txt`: brace depth 0, minimum depth 0, UTF-8 BOM present.
- `common/history/pops/09_central_asia.txt`: brace depth 0, minimum depth 0, UTF-8 BOM present.
- Global owner/pop alignment after the edit: 1,069 owner pairs, 1,069 pop pairs, 0 missing owner pop pairs.
- Global pop size check after the edit: 0 nonpositive pop sizes.

## Source Checked

- Allied Business Academies article on Kazakh nomadic stratification: Senior/Uly Zhuz is placed in Semirechye/Ili/Chu-Talas territory, while Middle/Orta Zhuz is placed in central/northern/eastern Kazakhstan.

## Approved And Implemented

The user approved this focused Central Asia/Afghanistan cleanup:

- Move `STATE_SEMIRECHE` from `OZH` to `UZH`.
- Move the matching `STATE_SEMIRECHE` pop bucket from `OZH` to `UZH`.
- Preserve all pop sizes and composition.
- Leave the rest of Central Asia/Afghanistan alone for this pass.
