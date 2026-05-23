# Russia And Siberia Population Refinement Audit

Status: audit complete; no focused pop correction recommended.

## Scope

This pass checked the remaining Russia/Siberia-facing population setup after the regional reviews for Europe, MENA, Africa, Asia, Oceania, and the Americas.

Files reviewed:

- `common/history/pops/02_east_europe.txt`.
- `common/history/pops/09_central_asia.txt`.
- `common/history/pops/14_siberia.txt`.
- `common/history/pops/15_russia.txt`.
- `common/history/pops/05_north_america.txt` for Russian America / Alaska.
- `common/history/states/00_states.txt`.
- Population scaling notes in `24_population_scaling_plan.md`.

## Current Snapshot

Key owner totals across all pop files:

- Direct `RUS`: 45,800,000.
- `FIN`: 1,112,400.
- `POL`: 2,600,000.
- `ALK`: 14,028.
- `CHC`: 310,309.
- `KZH`: 616,122.
- `OZH`: 216,746.
- `UZH`: 439,419.

Direct `RUS` population by pop file:

- `01_south_europe.txt`: 18,895.
- `02_east_europe.txt`: 10,687,912.
- `09_central_asia.txt`: 5,790,970.
- `14_siberia.txt`: 1,639,876.
- `15_russia.txt`: 27,662,347.

Largest direct `RUS` state buckets:

- `STATE_ORYOL`: 2,927,437.
- `STATE_KIEV`: 2,890,485.
- `STATE_YAROSLAVL`: 2,625,609.
- `STATE_KHARKOV`: 2,579,086.
- `STATE_TAMBOV`: 2,306,519.
- `STATE_KURSK`: 1,910,190.
- `STATE_SAMARA`: 1,389,773.
- `STATE_NIZHNY_NOVGOROD`: 1,380,742.
- `STATE_VYATKA`: 1,318,868.
- `STATE_GREATER_CAUCASUS`: 1,267,747.

Direct `RUS` largest culture totals:

- Russian: 25,331,645.
- Ukrainian: 8,541,246.
- Byelorussian: 1,986,118.
- Ashkenazi: 1,356,323.
- Tatar: 987,577.
- Latvian: 816,289.
- Georgian: 726,555.
- Estonian: 592,475.
- Lithuanian: 567,238.
- East German: 505,225.

## Findings

### 1. Direct Russia Already Matches The Approved Target

The implemented direct `RUS` total is exactly 45,800,000.

This is the approved population-scaling target from `24_population_scaling_plan.md`, based on an 1810-to-1820 interpolation/estimate while keeping Finland and Congress Poland separate.

Recommendation:

- Do not rescale direct `RUS` in this pass.

### 2. Finland And Congress Poland Are Properly Separate

Current setup:

- `FIN`: 1,112,400.
- `POL`: 2,600,000.

Both are separated from direct `RUS` population, matching the mod's political setup:

- Finland exists as a Russian subject/autonomous grand-duchy abstraction.
- Congress Poland exists separately under Russia.

Recommendation:

- Leave `FIN` and `POL` as-is for this pass.

### 3. Siberia And The Qing Frontier Look Reasonable

Current setup:

- `14_siberia.txt` gives direct `RUS` 1,639,876 across Siberian state regions.
- `CHI` still controls Tuva, Altai, Outer Manchuria, and Amur-facing buckets where appropriate for the 1816 pre-Aigun/Peking border.
- Siberian frontier pops remain small and mixed rather than being filled with later Russian settler totals.

Recommendation:

- Leave Siberia and the Qing frontier as-is.

### 4. Alaska / Russian America Is Plausible

Current setup:

- `ALK`: 14,028.
- `STATE_ALASKA` is owned by `ALK`, with Russian claim/support handled by the country/subject setup rather than direct `RUS` population.

Recommendation:

- Leave Alaska as-is for this pass.

## No Proposed Pop Edits

No immediate Russia/Siberia pop edits are recommended.

This region is a better candidate for later government, subject, claims, institutions, and diplomacy polish than for more raw population work.

## Validation Snapshot

- Direct `RUS`: 45,800,000 exactly.
- `FIN`: 1,112,400.
- `POL`: 2,600,000.
- `ALK`: 14,028.
- Owner/pop alignment remains clean after the preceding Oceania edits.
- Global nonpositive pop-size check remains clean after the preceding Oceania edits.

## Sources Checked

- Existing project population-scaling notes in `24_population_scaling_plan.md`, especially the approved direct `RUS`, `FIN`, `POL`, and broad Siberia/Russian Empire treatment.
