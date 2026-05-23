# Claims And Diplomacy Clean Pass

This pass follows the playable government/laws/interest-group cleanup.

## Scope

- Audit active diplomacy files after the mod's empty `00_*` diplomacy overrides.
- Restore already-approved 1816 subject relationships that were previously assumed to come from vanilla.
- Inventory claims structurally, but do not prune historical/gameplay claim pressure without approval.

## Key Finding

The mod overrides vanilla `common/history/diplomacy/00_subject_relationships.txt` with an empty file. That means vanilla subject pacts do not reliably carry forward. Several approved 1816 relationships were therefore missing unless we recreated them explicitly in the `99_cow_1816_*_subjects.txt` files.

## Implemented Subject Restoration

All items below were either already approved in planning notes or were previously assumed to be present through vanilla.

- Europe:
  - `AUS -> HUN`, `AUS -> TRS`, `AUS -> CRO`, and `AUS -> LOM` as `crown_land`.
  - `GBR -> HAN` as `personal_union`; `GBR -> ION` as `protectorate`; `GBR -> MLT` as `colony`.
  - `DEN -> HOL` and `DEN -> SCH` as `personal_union`.
  - `NET -> LUX` as `personal_union` plus `grant_own_market`.
  - `SWE -> NOR` as `personal_union`.
  - `RUS -> FIN` and `RUS -> POL` as `personal_union`.
  - `TUR -> MOL`, `TUR -> WAL`, and `TUR -> SER` as `protectorate`.
- North America and Caribbean:
  - `GBR -> NEW`, `ONT`, `QUE`, `NBS`, and `NVS` as `colony`.
  - `GBR -> HBC` and `RUS -> ALK` as `chartered_company`.
  - `SPA -> SC1`, `GUA`, `CUB`, `PCO`, `SC2`, `SC3`, `CHL`, and `DOM` as `colony`.
  - `POR -> BRZ` as `personal_union`; `GBR -> JAM` and `GBR -> BAH` as `colony`.
- MENA and Africa:
  - `TUR -> ALD`, `TUN`, `TRI`, and `EGY` as Ottoman dependents; `EGY` also receives `grant_own_market`.
  - `TRI -> FZN` and `EGY -> HDJ` as `tributary`.
  - `PER -> ARB` as `vassal`.
  - `OMA -> ZAN` and `OYO -> DAH` as `tributary`.
- Asia and India:
  - `GBR -> BIC` as `chartered_company`; `GBR -> BCE` and `SPA -> PHI` as `colony`.
  - `NET -> DEI` as `dominion`; `DEI -> YOG` and `DEI -> SRK` as `puppet`.
  - `CHI -> TIB` as `vassal`; `CHI -> KOR` as `tributary`.
  - `JAP -> V07` as `tributary`.
  - `SIA -> CHP`, `SIA -> CMI`, `SIA -> LUA`, and `SIA -> VIE`; `DAI -> CAM`; `BUR -> SHS`.
  - `KAL -> MAK` as `vassal`.
  - `BIC` now has explicit restored influence over `AWA`, `HYD`, `MYS`, `TRA`, `COC`, `ALW`, `PTA`, and `MUG`, while preserving the approved looser setup for Maratha and selected frontier states.

## Static Validation

After implementation:

- Diplomatic pact create count: 82.
- Brace failures in diplomacy files: 0.
- Bad pact references: 0.
- Duplicate created pacts: 0.
- All pact actors and targets are defined country tags and own at least one starting state.
- All created pact types resolve through base subject types or diplomatic actions.

## Claims Audit

Effective state claims currently total 79 entries across 70 states. All claim tags are defined.

No structural claim bug was found. Many claims are intentional pressure or split-state claims, but several are policy-sensitive enough to need a design pass before editing:

- `USA` western and upper-frontier claims: supports Louisiana Purchase gameplay, but speeds pressure on playable `COM` and `LKT`.
- `SWE` claims on Finland: plausible revanchism, but may overstate Swedish near-term ambition.
- `GRE`, `SER`, `MOL`, and Balkan/Ottoman claims: useful nationalist pressure, but should be tuned with the future revolution/nationalism system.
- `PER`, `RUS`, `CHC`, and `CIR` Caucasus claims: historically plausible tension, but needs a Caucasus-specific review.
- `ARG`, `CHL`, `BRZ`, and South American frontier claims: mostly gameplay pressure and successor-state abstraction.
- `HBC`, `ALK`, and company/colonial claims: should align with later colonial and frontier journal content.
- `PHI`, `MGD`, and `SUL` Mindanao claims: needs a Philippines/Sulu/Maguindanao-specific decision.

## Deferred Design Decisions

- Whether to prune or soften USA claims to protect indigenous playability.
- Whether inactive/releasable national movements should start with claims before their historical revolts.
- Whether to add more BIC subject relationships for the remaining Indian princely minors, or leave them independent until a dedicated India diplomacy pass.
- Whether `DEI` should start with only `YOG`/`SRK` as explicit puppets, or also pull the outer-island tags into Dutch subject pacts.
- Whether `MBS` should be an Omani tributary or remain autonomous.
- How to model Krakow's joint protection by Austria, Prussia, and Russia without making it a single-overlord subject.

## Next Recommendation

Do an in-game subject-map check after this sync. If the subject layer looks right, the next claims step should be a claims policy pass, starting with the USA frontier and the largest 1816 nationalist/revanchist claim clusters.
