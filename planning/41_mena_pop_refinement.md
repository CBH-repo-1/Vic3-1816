# MENA Population Refinement Audit

Status: Adana/Ottoman-Egypt correction implemented after approval.

## Scope

This pass covers North Africa, Egypt, the Ottoman Middle East, Arabia, the Persian Gulf, and Persia-facing MENA buckets in:

- `common/history/pops/03_north_africa.txt`.
- `common/history/pops/08_middle_east.txt`.
- Cross-file total checks against all active pop files where needed.

## Current Safety Checks

- Focused MENA owner/pop alignment: 35 focus owner pairs, 35 matching pop pairs, 0 missing, 0 extra.
- Nonpositive scripted pop sizes: 0.
- Current global target totals still line up:
  - `EGY`: 2,500,000.
  - `TUR`: 18,500,000.
  - `PER`: 6,600,000.

## Current MENA Totals Snapshot

Major MENA and adjacent owners:

- `MOR`: 3,389,218.
- `ALD`: 3,885,711.
- `TUN`: 1,373,622.
- `TRI`: 807,188.
- `FZN`: 181,755.
- `EGY`: 2,500,000.
- `TUR`: 18,500,000.
- `PER`: 6,600,000.
- `NEJ`: 241,732.
- `HDJ`: 526,700.
- `OMA`: 313,141.
- `ZAI`: 947,800.

Slavery-law compatibility looks broadly consistent for the main MENA tags checked. The tags with enslaved pop buckets generally have a slavery law such as `law_slave_trade`, `law_debt_slavery`, or an already approved equivalent.

## Main Issue Found

`EGY` still owns and has pops in most of `STATE_ADANA`:

- `STATE_ADANA`, `EGY`: 180,676.
- `STATE_ADANA`, `TUR`: 27,927.

This appears to be a later Muhammad Ali occupation leftover. It conflicts with the January 1, 1816 start. The approved MENA plan already says 1836 Egyptian expansion should be removed from the Levant/Syria sphere, and the same logic applies here.

Source check:

- Britannica places Muhammad Ali's Syria invasion in 1831 and the Ottoman cession of Syrian provinces in 1833.
- Britannica places the further Najd campaign in 1816-1818 and the Sudan conquest in 1820-1821, which supports our earlier decision to avoid 1836 Egyptian territorial reach at game start.

## Recommended Next Changes

1. Move the `EGY` part of `STATE_ADANA` to `TUR`.
   - State ownership: replace the `EGY` create-state block in Adana with `TUR`, or merge its provinces into the existing `TUR` Adana block.
   - Pop ownership: merge the `EGY` Adana pop bucket into the `TUR` Adana pop bucket.

2. Rescale `EGY` back to the existing approved target of 2,500,000.
   - After Adana is removed, Egypt proper falls to 2,319,324.
   - Recommended: proportionally scale the remaining `EGY` buckets in Egypt/Sinai/Matruh back to 2,500,000.
   - This preserves our existing Egyptian target while removing the wrong territory.

3. Rescale direct `TUR` back to the existing approved target of 18,500,000.
   - After absorbing Adana, `TUR` would temporarily rise above target.
   - Recommended: proportionally scale all direct `TUR` buckets back to 18,500,000, as we did for Russia after folding in the Baltic Governorates.

4. Leave the rest of MENA unchanged for this pass.
   - Morocco, Algiers, Tunis, Tripoli/Fezzan, Persia, Arabia, Yemen, and the Gulf are plausible enough for this refinement stage.
   - Their later polish should happen in diplomacy, laws, buildings, and events unless in-game review exposes an obvious population problem.

## Approval Needed

Approved and implemented:

- Move `STATE_ADANA` fully to `TUR`.
- Merge Adana pops into `TUR`.
- Rescale `EGY` to 2,500,000 and `TUR` to 18,500,000.
- Leave other MENA population totals alone for now.

## Implementation Details

- `STATE_ADANA` is now a single `TUR` create-state block in state history.
- The former `EGY` Adana pop bucket was merged into the `TUR` Adana pop bucket.
- Direct `EGY` population before rescale, after losing Adana: 2,319,324.
- Direct `TUR` population before rescale, after gaining Adana: 18,680,676.
- Final `EGY`: 2,500,000.
- Final `TUR`: 18,500,000.
- Final `STATE_ADANA` / `TUR` population: 206,587.

## Post-Implementation Validation

- No `EGY` pop bucket remains in `STATE_ADANA`.
- Province-owning state/country pairs missing pop buckets: 0.
- Nonpositive scripted pop sizes: 0.
- Changed state and pop files have clean brace depth.
- Changed state and pop files are UTF-8 BOM encoded.
