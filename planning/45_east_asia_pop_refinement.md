# East Asia Population Refinement Audit

Status: approved cleanup implemented.

## Scope

This pass reviewed the East Asia side of `11_east_asia.txt`, focusing on China/Qing, Korea, Japan, Ryukyu, Hokkaido/Ainu, Taiwan/Formosa, Tibet-facing totals, and obvious 1816 pop artifacts.

Files reviewed:

- `common/history/pops/11_east_asia.txt`.
- `common/history/pops/09_central_asia.txt` for Qing/Tibet frontier spillover totals.
- `common/history/pops/14_siberia.txt` and `15_russia.txt` for small Qing frontier spillover totals.
- `common/history/states/00_states.txt`.
- Asia planning notes `08_asia_inventory.md`, `17_mena_central_asia_asia_map_implementation.md`, and `24_population_scaling_plan.md`.

## Current Snapshot

Global owner totals across all pop files:

- `CHI`: 381,000,000.
- `JAP`: 31,000,000.
- `KOR`: 13,800,000.
- `TIB`: 2,860,146.
- `V07` Ryukyu: 264,370.
- `AIN`: 30,939.
- `SKH`: 40,805.

The broad China, Japan, and Korea targets match the implemented global scaling plan. There is no need to rescale those countries overall.

## Implemented Corrections

### 1. Formosa/Taiwan Was Too High

Current setup:

- `STATE_FORMOSA`, `CHI`: 3,017,071.
- Current composition:
  - `min`: 1,538,950.
  - `han`: 853,710.
  - `yuanzhumin`: 623,899.
  - `manchu`: 512.

Nearby historical estimate:

- A modern UN/World Bank-derived historical population series gives Taiwan as 2.00 million in 1820.
- A separate 1800 population table also lists Taiwan as 2,000,000.

Implemented correction:

- Scaled `STATE_FORMOSA` `CHI` from 3,017,071 to 2,000,000.
- Preserved internal culture/religion composition proportionally.
- Did not split Taiwan into a separate `YUZ` owner in this pass. That would be a map-design decision, not a population cleanup.
- Did not redistribute the removed population elsewhere. This lowered global `CHI` by 1,017,071, or about 0.27%, which is smaller than the uncertainty in the broad 1820 China benchmark.

### 2. Ryukyu Was Too High

Current setup:

- `STATE_RYUKYU_ISLANDS`, `V07`: 264,370.
- Current composition is a single `japanese` pop because vanilla has no distinct Ryukyuan culture found in the base-game culture files.

Nearby historical estimate:

- The Satsuma-recorded Ryukyu population table gives Ryukyu as 155,650 in 1800.
- A later Meiji-era Ryukyu-han value in the same demographic table is 166,789 in 1873, suggesting the 1816 population should be much closer to the 1800 value than to the current 264,370.

Implemented correction:

- Scaled `STATE_RYUKYU_ISLANDS` `V07` from 264,370 to 155,650.
- Kept the pop culture as `japanese` for now because there is no usable vanilla `ryukyuan` culture key in the base game.
- Did not redistribute the removed population to Japan. Ryukyu is an approved playable subject/tag, not part of the direct `JAP` total.

## Aggregate Impact

After both corrections, with no redistribution elsewhere:

- East Asia pop file falls from 443,485,450 to 442,359,659.
- Global `CHI` falls from 381,000,000 to 379,982,929.
- `V07` falls from 264,370 to 155,650.

Implemented policy:

- Accepted this small aggregate decrease because both changes correct overlarge edge-region buckets with closer local estimates.
- Kept the broad mainland China, Japan, and Korea population distributions untouched.

## Leave Alone For Now

- `CHI` mainland and frontier totals should stay as-is. The global China target is already exact before the proposed Formosa correction, and a 0.27% post-correction drift is safer than mechanically sprinkling one million people across unrelated mainland states.
- `JAP` should stay exactly 31,000,000. The Hokkaido split already gives `AIN` 30,939 and `JAP` 31,434 in `STATE_HOKKAIDO`, which is close to recorded Ezo/Matsumae-era magnitudes.
- `KOR` should stay exactly 13,800,000.
- `TIB` should stay at 2,860,146 for now. It is plausible enough and sits mostly in the Central Asia/Himalaya pop file, so a Tibet pass can be separate if needed.
- `STATE_HOKKAIDO` should stay split between `AIN` and `JAP` for now. It already carries a small Ainu-majority frontier and a small Japanese/Matsumae foothold.
- `STATE_SAKHALIN` should stay as-is for now. Any Sakhalin/Kuril cleanup is more map/diplomacy-sensitive than this pop pass.

## Validation Snapshot

- `common/history/pops/11_east_asia.txt`: brace depth 0, minimum depth 0, UTF-8 BOM present.
- `STATE_FORMOSA` / `CHI` now totals exactly 2,000,000.
- `STATE_RYUKYU_ISLANDS` / `V07` now totals exactly 155,650.
- Global `CHI` now totals 379,982,929.
- Owner/pop alignment remains clean: 1,069 owner pairs, 1,069 pop pairs, 0 missing owner pop pairs.
- Global pop size check: 0 nonpositive pop sizes.

## Sources Checked

- Helgi Library Taiwan population page, sourced to World Bank / UN World Population Prospects 2019, gives Taiwan as 2.00 million in 1820.
- Demographic history of Japan before the Meiji Restoration, regional population table, records Satsuma-surveyed Ryukyu as 155,650 in 1800 and Ryukyu-han as 166,789 in 1873.

## Approved And Implemented

The user approved this focused East Asia pop cleanup:

- Scale `STATE_FORMOSA` `CHI` to 2,000,000.
- Scale `STATE_RYUKYU_ISLANDS` `V07` to 155,650.
- Keep Ryukyu culture as `japanese` for now because there is no vanilla Ryukyuan culture key.
- Do not redistribute the removed population elsewhere.
- Leave the rest of East Asia alone for this pass.
