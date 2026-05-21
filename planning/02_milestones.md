# Milestones

## Milestone 1: Bootable Shell

- Create local mod metadata.
- Override approved campaign start/end dates.
- Verify the launcher can see the mod.

## Milestone 2: 1816 Country/Tag Inventory

- Decide the starting country list.
- Identify vanilla tags that can be reused.
- Identify new tags required.
- Add localization placeholders only after tags are approved.
- Current status: global country/tag planning pass is complete at the broad level, and `V00` through `V09` have initial game-facing definitions, flags, history skeletons, and localization.

## Milestone 3: Europe Political Ownership

- Convert vanilla state ownership to 1816 borders using existing state/province geometry.
- Handle split states only where vanilla already supports them or where an approved compromise is needed.
- Verify no orphaned state, pop, or building ownership remains.
- Current status: initial clear ownership overrides have started in `common/history/states/99_cow_1816_europe_states.txt` for Spain, the Low Countries, Greece/Ottoman islands, Lombardy-Venetia, Malta, Congress Poland, Andorra, and the selected Ernestine duchy split. Monaco, Liechtenstein, and San Marino were removed from start ownership after in-game map review showed their vanilla provinces were too large.
- Still pending: wider German/Italian/Polish/Austrian border work and follow-up diplomacy/government layers.

## Milestone 3A: Africa Political Ownership

- Convert approved Africa map differences to 1816 ownership while keeping vanilla state/province geometry.
- Current status: Sudan/Nile Valley correction is scripted in `common/history/states/99_cow_1816_africa_states.txt`: Dongola and Blue Nile now start under `SUD`/Sennar, and Kordofan now starts under `DFR`/Darfur. The anachronistic Liberia start colony has also been removed, with its 1836 colony provinces returned to `KRU`.
- Current status: the approved Africa cleanup batch also removes Massina, Egyptian Eritrea, Witu, later Boer republics, Ndebele, Basutoland-style setup, and Gaza from start ownership where vanilla province geometry allows.
- Still pending: later diplomacy/government refinement, population/building/resource passes, and in-game map testing.

## Milestone 3B: MENA, Central Asia, And Asia Political Ownership

- Convert clear approved MENA and Asia backdates to 1816 ownership while keeping harder border questions deferred.
- Current status: first-pass MENA, Central Asia, and Asia overrides are scripted in `99_cow_1816_mena_states.txt`, `99_cow_1816_central_asia_states.txt`, and `99_cow_1816_asia_states.txt`.
- Implemented: Algerian unification under `ALD`, Egyptian Levant returned to `TUR`, `STATE_HAIL` to `NEJ`, Kars to `TUR`, Peshawar/Pashtunistan to `KAB`, Arakan/Tenasserim/Pegu back to `BUR`, Vientiane restored as `VIE`, and Ryukyu placed as `V07`.
- Still pending: Kuwait, Persia/Caucasus post-Gulistan border work, and the full India/Maratha/BIC backdate.

## Milestone 4: Diplomacy and Government Setup

- Add or revise subjects, treaties, rivals, alliances, interests, laws, and governments.
- Review major 1816 settlement systems before scripting them.
- Current status: first Europe subject layer is scripted in `common/history/diplomacy/99_cow_1816_europe_subjects.txt` for `AUS -> LOM`, `GBR -> MLT`, `RUS -> POL`, and Krakow puppet removal.
- Still pending: liberty desire, own-market choices, Krakow joint-protection mechanics, government/law setup, and non-European subject cleanup.

## Milestone 5: Pops and Economy

- Replace 1836 population data with 1816 estimates.
- Adjust literacy, cultures, religions, professions, buildings, and resource starts.
- Current status: population ownership/scaling passes are implemented; first mechanical building sweep and split-state building allocation are implemented in `planning/29_starting_buildings_sweep.md`; state-region resource potentials are intentionally left vanilla and documented in `planning/30_state_resources_policy.md`; the first 1816 building-level rebalance is implemented in `planning/31_building_level_rebalance_plan.md`.
- Still pending: dedicated military building pass, literacy/profession refinement, and any economy changes that require design choices.

## Milestone 6: Technology Pacing

- Decide whether the extra 1816-1835 period is modeled with a new era, added early technologies, or adjusted research pacing. Current status: generic tier 1 now starts with era 1 only; 1836-style tier 1 era 2 techs were removed from the universal bundle.
- Add technology definitions and localization after the structure is approved.
