# South Asia And India Population Refinement Audit

Status: approved cleanup implemented.

## Scope

This pass reviewed the Indian subcontinent pop file after the approved 1816 India/Maratha map backdate and global 209,000,000 India-file scaling.

Files reviewed:

- `common/history/pops/10_india.txt`.
- `common/history/states/00_states.txt`.
- `common/history/diplomacy/99_cow_1816_india_subjects.txt`.
- India planning notes `08_asia_inventory.md`, `22_india_maratha_accuracy_pass.md`, and `24_population_scaling_plan.md`.

## Current Snapshot

Before this pass, the India pop file totaled exactly 209,000,000.

Largest owner totals in the file:

- `BIC`: 132,039,117.
- `HYD`: 13,606,199.
- `AWA`: 6,046,666.
- `PAN`: 6,037,325.
- `MYS`: 4,761,122.
- `BER`: 4,645,686.
- `NAG`: 4,486,701.
- `V10`: 2,616,736.
- `SIN`: 2,456,664.
- `JAI`: 2,282,449.
- `ASM`: 2,228,074.
- `SAT`: 2,116,633.
- `GWA`: 2,101,647.
- `KAS`: 1,592,881.
- `BCE`: 1,503,952.

The owner/pop alignment is mechanically clean. The issues below are demographic refinements, not crash-risk map fixes.

## Implemented Corrections

### 1. British Ceylon Was Too High

Current setup:

- `BCE`: 1,503,952 in `STATE_CEYLON`.
- `STATE_CEYLON` also includes small separate `MLD` and `GBR` island buckets.

Nearby historical estimate:

- The first 1824 Sri Lanka/Ceylon estimate gives the island population as 851,940.
- This is after the 1815 Kandyan Convention brought the whole island under British rule, so it is a good nearby anchor for the 1816 start.

Implemented correction:

- Scaled only the `BCE` bucket in `STATE_CEYLON` from 1,503,952 to 851,940.
- Preserved internal culture, religion, pop type, and relative composition.
- Left `MLD` and `GBR` in the state untouched.

This reduced the India pop file total by 652,012.

### 2. Assam/Ahom Bucket Was Too Large And Still Had British Bureaucrats

Current setup:

- `ASM`: 2,228,074 in `STATE_ASSAM`.
- `ASM` includes tiny British and Scottish bureaucrat pops inherited from the later British administrative setup.

Nearby historical evidence:

- A study of Assam's nineteenth-century economy records Assam Proper at about 7-8 lakhs in 1826, 1,059,513 in 1853, and 1,496,705 in 1872.
- It also notes the disorder and depopulation around the late Ahom/Burmese occupation transition.

Implemented correction:

- Scaled the `ASM` bucket in `STATE_ASSAM` from 2,228,074 to 900,000.
- This is intentionally above the 1826 700,000-800,000 figure because January 1, 1816 is before the worst 1817-1824 Burmese occupation period.
- Replaced the British and Scottish bureaucrat remnants inside the `ASM` bucket with a single Assamese bureaucrat pop while preserving the scaled total.
- Left `NGA`, `MNP`, `TIP`, `KKI`, and `MGH` untouched for this pass.

This reduced the India pop file total by 1,328,074.

## Aggregate Impact

After both corrections, with no redistribution elsewhere:

- India pop file falls from 209,000,000 to 207,019,914.
- This is a 0.95% decrease, still well inside the uncertainty of the broad Maddison-style 1820 India benchmark used for the first global scaling batch.

Implemented policy:

- Did not redistribute the removed population into Bengal or other dense regions during this pass.
- Treated these as source-backed corrections to two overlarge frontier/island buckets, not as a reason to preserve the exact earlier aggregate at all costs.

## Leave Alone For Now

- `BIC` at 132,039,117 is huge, but the Company directly controls Bengal, Bihar, Madras, Bombay, Agra/Doab, and other large-population areas. It should stay until a dedicated Company-vs-princely-state tax/law pass.
- `MUG` at 644,719 is large for a politically powerless Delhi court, but it is one map province and still supports the approved playable Delhi puppet abstraction.
- `PAN`, `V10`, `KAS`, and `LAD` should stay as-is for this pass. Their ownership setup matches the approved frontier backdate, and their pop totals are not obviously broken.
- The Maratha and Rajput state totals should stay for now. They are politically sensitive and do not have an obvious single nearby census anchor like Ceylon or Assam.
- Existing slave pops in India/Ceylon should not be removed in this pass. British Indian slavery and bonded servitude need a later laws/slavery pass rather than a quick pop deletion.

## Validation Snapshot

- `common/history/pops/10_india.txt` now totals exactly 207,019,914.
- `ASM` now totals exactly 900,000.
- `BCE` now totals exactly 851,940.
- State/pop owner alignment remains clean after the edit: 1,069 owner pairs, 1,069 pop pairs, 0 missing owner pop pairs.
- Global pop size check after the edit: 0 nonpositive pop sizes.

## Sources Checked

- T. Sabaratnam's Sri Lankan census summary records the 1824 Ceylon/Sri Lanka estimate of 851,940.
- H. K. Nath's paper on Assam's nineteenth-century economy records Assam Proper population estimates of 7-8 lakhs in 1826, 1,059,513 in 1853, and 1,496,705 in 1872, and describes the late Ahom/Burmese transition as depopulating and disorderly.

## Approved And Implemented

The user approved this focused South Asia/India pop cleanup:

- Scale `BCE` in `STATE_CEYLON` to 851,940.
- Scale `ASM` in `STATE_ASSAM` to 900,000.
- Replace the tiny British/Scottish bureaucrat remnants in `ASM` with Assamese bureaucrats.
- Do not redistribute the removed population elsewhere.
- Leave the rest of India/South Asia alone for this pass.
