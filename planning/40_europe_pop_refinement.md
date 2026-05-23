# Europe Population Refinement Audit

Status: Baltic Governorates correction implemented after approval.

## Current Safety Checks

- Source mod and live mod were synced after the Central America/New Spain batch.
- Source files: 820.
- Live files: 820.
- Source/live hash differences: 0.
- Nonpositive scripted pop sizes: 0.
- Province-owning state/country pairs missing pop buckets: 0.

## Central America/New Spain Batch Implemented Before This Audit

- `GUA` was reduced from the broad 2,419,000 target to 1,311,469 using the approved Federal Republic of Central America component estimate plus the existing Chiapas fragment.
- `SC1` Texas was cleaned of the later Anglo/slave artifact.
- The removed free Texas population was redistributed into core New Spain.
- The removed enslaved Texas population was moved to Veracruz.
- `SC1` now uses `law_colonial_slavery`.
- `GUA` has no enslaved pop buckets and no slavery law.

## Europe Totals Snapshot

The major Europe country totals still match the previously implemented broad scaling targets closely. Examples:

- `FRA`: 29,992,333.
- `GBR`: 19,505,285, including Great Britain and Ireland.
- `NET`: 6,213,000, including Belgian provinces.
- `PRU`: 10,349,031.
- `POL`: 2,600,000.
- `SWE`: 2,489,000.
- `NOR`: 901,600.
- `SPA`: 12,386,913.
- Italian aggregate remains in the intended range after the earlier peninsula/islands scaling.

The German microstate targets also look mechanically sound:

- `V04` Saxe-Gotha-Altenburg: 180,000.
- `V05` Saxe-Hildburghausen: 33,000.
- `COB` Saxe-Coburg-Saalfeld: 59,000.
- `MEI` Saxe-Meiningen: 34,000.
- `ANH`: 120,000.
- `SCW`: 101,000.
- `HOH`: 44,000.

## Main Issue Found

`UBD` is currently active on the map as a standalone Baltic country:

- `STATE_TALINN`: `UBD`.
- `STATE_TARTU`: `UBD`.
- `STATE_RIGA`: split between `RUS` and `UBD`.
- `STATE_COURLAND`: `UBD`.
- `UBD` scripted population: 1,577,759.
- No subject relationship to Russia was found.

This conflicts with the approved Europe inventory, which says the Baltic Governorates should not be a unified start country and should be inside `RUS` at start, with `UBD` kept as an absent/releasable abstraction.

## Recommended Next Changes

1. Correct the Baltic Governorates.
   - Recommended: fold the `UBD` starting lands and pops into `RUS`, leaving `UBD` as releasable-only.
   - This matches the existing approved Europe plan and is historically cleaner.

2. Recheck Russian total after the Baltic correction.
   - If we fold `UBD` into `RUS`, Russia gains 1,577,759 scripted pops.
   - Recommended: do a focused Russian Empire rescale after the ownership fix so the broad imperial population remains intentional rather than accidentally inflated.

3. Leave German microstate populations alone for now.
   - They are already explicitly targeted and mechanically clean.

4. Leave Britain, Netherlands/Belgium, Italy, Iberia, and Scandinavia alone for this pass.
   - They look good enough for the current population-refinement stage.
   - Their later polish should happen in laws, institutions, diplomacy, and journal/event work rather than raw population totals.

5. Keep Wallachia/Moldavia slave pops and laws for now.
   - Both have `law_legacy_slavery`, which fits the Roma slavery abstraction better than removing the slave pops during this pass.

## Approval Needed

Approved and implemented:

- Start ownership and population were moved from active `UBD` to `RUS`.
- `UBD` remains defined but no longer has start-map ownership or start-population buckets.
- Direct `RUS` population was rescaled back to the existing approved target of 45,800,000 after absorbing the Baltic Governorates.

## Implementation Details

- `STATE_TALINN`, `STATE_TARTU`, the Livonian part of `STATE_RIGA`, and `STATE_COURLAND` now start under `RUS`.
- `STATE_RIGA`'s prior split `RUS` and `UBD` pop buckets were merged into one `RUS` bucket before scaling.
- Focused Baltic `RUS` pop totals after the global direct-Russia rescale:
  - `STATE_COURLAND`: 452,175.
  - `STATE_RIGA`: 644,548.
  - `STATE_TALINN`: 302,422.
  - `STATE_TARTU`: 300,858.

## Post-Implementation Validation

- `RUS`: 45,800,000.
- `POL`: 2,600,000.
- `FIN`: 1,112,400.
- No active `country = c:UBD` ownership remains in state history.
- No `region_state:UBD` pop buckets remain.
- Province-owning state/country pairs missing pop buckets: 0.
- Nonpositive scripted pop sizes: 0.
- Changed state and pop files have clean brace depth.
- Changed state and pop files are UTF-8 BOM encoded.
