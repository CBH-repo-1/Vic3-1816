# Continuation Roadmap

Use this file after context compaction or when resuming the project.

## Project

- Mod name: Congress of Vienna 1816
- Workspace: `C:\Users\Blake Gaming\Documents\New project`
- Base game path: `C:\Program Files (x86)\Steam\steamapps\common\Victoria 3`
- Local launcher mod copy: `C:\Users\Blake Gaming\Documents\Paradox Interactive\Victoria 3\mod\Congress of Vienna 1816`
- Detected base game version: `release/1.12.5`

## Current Mod Files

- Game-facing source: `mod/Congress of Vienna 1816`
- Current script changes:
  - `common/defines/00_cow_1816_defines.txt`
  - `common/country_definitions/00_cow_1816_countries.txt`
  - `common/history/countries/00_cow_1816_custom_countries.txt`
  - `common/history/countries/99_cow_1816_caribbean_countries.txt`
  - `common/history/countries/99_cow_1816_north_america_countries.txt`
  - `common/history/countries/99_cow_1816_oceania_countries.txt`
  - `common/history/countries/99_cow_1816_south_america_countries.txt`
  - `common/history/diplomacy/99_cow_1816_africa_subjects.txt`
  - `common/history/diplomacy/99_cow_1816_asia_subjects.txt`
  - `common/history/diplomacy/99_cow_1816_central_asia_subjects.txt`
  - `common/history/diplomacy/99_cow_1816_europe_subjects.txt`
  - `common/history/diplomacy/99_cow_1816_india_subjects.txt`
  - `common/history/military_formations/05_cow_1816_india_formations.txt`
  - `common/history/pops/00_west_europe.txt`
  - `common/history/pops/01_south_europe.txt`
  - `common/history/pops/02_east_europe.txt`
  - `common/history/pops/03_north_africa.txt`
  - `common/history/pops/04_subsaharan_africa.txt`
  - `common/history/pops/05_north_america.txt`
  - `common/history/pops/06_central_america.txt`
  - `common/history/pops/07_south_america.txt`
  - `common/history/pops/08_middle_east.txt`
  - `common/history/pops/09_central_asia.txt`
  - `common/history/pops/10_india.txt`
  - `common/history/pops/11_east_asia.txt`
  - `common/history/pops/12_indonesia.txt`
  - `common/history/pops/13_australasia.txt`
  - `common/history/pops/14_siberia.txt`
  - `common/history/pops/15_russia.txt`
  - `common/history/buildings/00_west_europe.txt`
  - `common/history/buildings/01_south_europe.txt`
  - `common/history/buildings/02_east_europe.txt`
  - `common/history/buildings/03_north_africa.txt`
  - `common/history/buildings/04_subsaharan_africa.txt`
  - `common/history/buildings/05_north_america.txt`
  - `common/history/buildings/06_central_america.txt`
  - `common/history/buildings/07_south_america.txt`
  - `common/history/buildings/08_middle_east.txt`
  - `common/history/buildings/09_central_asia.txt`
  - `common/history/buildings/10_india.txt`
  - `common/history/buildings/11_east_asia.txt`
  - `common/history/buildings/12_indonesia.txt`
  - `common/history/buildings/13_australasia.txt`
  - `common/history/buildings/15_russia.txt`
  - `common/history/diplomacy/99_cow_1816_mena_subjects.txt`
  - `common/history/diplomacy/99_cow_1816_north_america_subjects.txt`
  - `common/history/diplomacy/99_cow_1816_oceania_subjects.txt`
  - `common/history/diplomacy/99_cow_1816_south_america_caribbean_subjects.txt`
  - `common/history/states/00_states.txt`
  - `common/flag_definitions/00_cow_1816_flags.txt`
  - `common/coat_of_arms/coat_of_arms/00_cow_1816_countries.txt`
  - `localization/english/cow_1816_countries_l_english.yml`
- Current approved date override:
  - `START_DATE = "1816.1.1"`
  - `END_DATE = "1936.1.1"`
- Current custom scripted tag layer:
  - `V00` Liechtenstein
  - `V01` San Marino
  - `V02` Monaco
  - `V03` Andorra
  - `V04` Saxe-Gotha-Altenburg
  - `V05` Saxe-Hildburghausen
  - `V06` Kuwait
  - `V07` Ryukyu
  - `V08` Choctaw Nation
  - `V09` Chickasaw Nation
  - `V10` Multan

## Core Working Rules

- Stop and ask before design decisions.
- Use vanilla Victoria 3 state/region/province geometry.
- Europe is the first country/tag pass.
- Strong reuse candidates are approved by default for all regions unless a later historical or technical conflict is found.
- Use moderately strict tags:
  - Reuse vanilla tags when they reasonably fit 1816.
  - Relocalize vanilla tags when names differ.
  - Create new tags only when vanilla abstraction is misleading and map geometry can support it.
- New fixed mod tags use `V**`:
  - `V00` through `V99`, then `V0A`, `V0B`, etc.
  - Do not use `D00-D99`.
- Historical personal unions should use Victoria 3's `personal_union` subject type where supported.

## Approved Germany Decisions

- No Holy Roman Empire start country.
- No unified German Confederation start country.
- German Confederation is a non-country political/diplomatic system.
- German member states are playable by default unless too tiny for the vanilla map.
- Approved personal unions:
  - `GBR -> HAN`
  - `DEN -> HOL`
  - `DEN -> SCH`
  - `NET -> LUX`
- Strong German reuse candidate list is approved in `04_europe_country_inventory.md`.
- `ANH` remains one abstracted playable Anhalt.
- `COB` relocalizes to Saxe-Coburg-Saalfeld.
- `SCW` is one playable Schwarzburg Principalities abstraction.
- `HOH` is one playable Hohenzollern Principalities abstraction.
- `V00` Liechtenstein has no start ownership after in-game map review; keep as inactive/releasable-or-flavor only.
- Reuss, Lauenburg, and Hesse-Homburg may be omitted/abstracted unless map review is unusually generous.

## Approved Italy Decisions

- Strong Italian reuse candidates are approved.
- `PAP` displays as Papal States.
- `SIC` displays as Two Sicilies from the start.
- Lombardy-Venetia is playable under Austria as an Austrian `crown_land`, probably using `LOM` relocalized as Lombardy-Venetia.
- Malta is playable `MLT` as a British crown colony, likely with Victoria 3's `colony` subject type.
- `V01` San Marino has no start ownership after in-game map review; keep as inactive/releasable-or-flavor only.
- `ION` remains a British protectorate.

## Open Europe Work

Europe tag pass status:

- Europe is complete at the country/tag planning level.
- State ownership scripting has begun with the first clear European overrides.
- Remaining Europe ownership work is wider border implementation, not broad tag inventory.
- Tiny-state province choices are recorded in `planning/14_tiny_state_map_review.md`; Monaco, Liechtenstein, and San Marino were removed from the start map after in-game review.

Initial scripted European ownership overrides:

- Carlist Spain removed from the 1816 start by returning Aragon, Basque Country, and most of Catalonia to `SPA`.
- Belgium removed from the 1816 start by returning Flanders, most of Wallonia, and the Belgian Gelre province to `NET`, while preserving Luxembourg's province for `LUX`.
- Independent Greece removed from the 1816 start by returning Peloponnese, Attica, West Aegean Islands, and Crete to `TUR`.
- Lombardy and Venetia moved from direct `AUS` ownership to playable `LOM`, pending the later Austrian crown-land diplomacy/government layer.
- Malta moved from direct `GBR` ownership to playable `MLT`, pending the later British colony diplomacy/government layer.
- Congress Poland is now landholding `POL` in Greater Poland, Lesser Poland, and Mazovia.
- Tiny playable starts now kept on-map: `V03` Andorra, `V04` Saxe-Gotha-Altenburg, and `V05` Saxe-Hildburghausen. `V00` Liechtenstein, `V01` San Marino, and `V02` Monaco remain defined but have no start ownership.

State-history implementation boundary:

- The active map ownership layer is now the merged `common/history/states/00_states.txt` override.
- This file was generated from vanilla `00_states.txt` plus the approved 1816 regional state patches. The old `99_cow_1816_*_states.txt` overlay files were removed because layering `create_state` blocks on top of vanilla created duplicate state objects: old objects received pops, while new province-owning objects had zero pops.
- The merged file includes the earlier Europe, Africa, MENA, Central Asia, Asia, India, Oceania, North America, South America, Caribbean, and follow-up map-review changes. Details are still recorded in the older regional planning notes, but those old `99_cow_1816_*_states.txt` files are no longer active mod files.
- Claims, laws, buildings, and most government setup are intentionally deferred to their own passes.
- Pop ownership alignment is implemented in copied vanilla pop files and documented in `planning/23_pops_ownership_alignment_pass.md`.
- Population scaling is in progress and documented in `planning/24_population_scaling_plan.md`: implemented scopes now include the first America/Portugal batch, the Europe source-backed batch, and the global source-backed batch covering Russia, Prussia, Habsburg non-Italian lands, the Ottoman sphere, Egypt, Persia, Africa, India, China, Japan, Korea, Southeast Asia/Indonesia, Nepal, Spanish America, the Caribbean, Hawaii, and British North America.

Open Africa map work:

- In-game map testing of the conservative local/decentralized reassignments, especially Eritrea, southern Africa, and Mozambique/Zambezia.

Open MENA/Central Asia/Asia map work:

- Dagestan/Caucasus local autonomy review; Armenia is already restored to Persia, while Azerbaijan/Elizavetpol/Greater Caucasus remain Russian after Gulistan.
- India map ownership cleanup is implemented and documented in `planning/22_india_maratha_accuracy_pass.md`; India pop ownership is aligned in `planning/23_pops_ownership_alignment_pass.md`; next India work should be buildings/resources/laws/claims or later demographic scaling unless in-game visual review exposes a map issue.
- Dutch East Indies and Southeast Asian island edge review was audited in `planning/21_remaining_map_cleanup_audit.md`; no ownership change is needed in the current base setup.
- Caribbean ownership and subject cleanup is implemented in `planning/20_south_america_caribbean_map_implementation.md`.
- In-game map testing of the South America and Caribbean ownership pass, especially `SC2`, `SC3`, `DOM`, `JAM`, and `BAH`.
- In-game map testing of the final first-pass ownership map after the Old Southwest and South America follow-up.
- USA frontier cleanup is implemented and follow-up validated: direct `USA` ownership was removed from the approved Plains/upper-frontier states and represented with local/decentralized holders plus `USA` claims; the bad uppercase province-ID prefixes from the first attempt were corrected. A later Old Southwest cleanup removed Cherokee, Choctaw, Chickasaw, and Muscogee start-map ownership and restored Tennessee, Mississippi, Alabama, and Georgia to direct `USA` ownership while preserving the tags/homelands for later release or event work.

Open technology work:

- Generic tier 1 has been backdated for 1816 in `common/scripted_effects/99_cow_1816_starting_inventions.txt`: it now grants only `add_era_researched = era_1`.
- Generic tier 2 has also been backdated: it now uses a partial era 1 package based on vanilla tier 3, plus `napoleonic_warfare`, `banking`, and `empiricism`, with no era 2 freebies.
- Tier 1 and tier 2 are intentionally differentiated:
  - Tier 1 has full era 1.
  - Tier 2 lacks edge era 1 techs such as `lathe`, `paddle_steamer`, `stock_exchange`, and `mass_communication`.
- Later country-specific starting technology pass should consider giving `atmospheric_engine` to Britain only, rather than restoring it to universal tier 1.
- Country-specific starting technology and tier assignment cleanup is implemented and recorded in `planning/28_country_starting_tech_audit.md`.
- Implemented highlights: `GBR` gets `atmospheric_engine` as the only approved era 2 exception; obvious vanilla 1836 tech leftovers were removed from the affected country history overrides; colonial tags `BCE`, `HBC`, `NBS`, `NVS`, `ONT`, `QUE`, `NSW`, and `SAF` were downgraded to tier 3; `V03` Andorra was downgraded to tier 3.
- First starting buildings sweep is implemented and recorded in `planning/29_starting_buildings_sweep.md`.
- Implemented highlights: era 2/anachronistic active PMs and starting railways were removed or downgraded; British Isles atmospheric-engine mine PMs were preserved for `GBR`; 86 stale single-owner building-region blocks were remapped to their 1816 state owners.
- Split-state building allocation is also implemented: all 59 stale split-state building-region blocks were either reassigned, reduced, split by building type, or removed under the approved majority-owner policy.
- State-region resources are intentionally left at vanilla physical potential, including gold, oil, rubber, mines, logging, fishing, whaling, arable land, and arable resource options. This is recorded in `planning/30_state_resources_policy.md`; do not copy `map_data/state_regions` unless a future pass approves a specific exception.
- First broad 1816 civilian building-level rebalance is implemented and recorded in `planning/31_building_level_rebalance_plan.md`. It reduced total starting building levels from 8,212 to 6,718 and removed 13 approved tech-inconsistent building blocks.
- Dedicated military pass is implemented and recorded in `planning/32_military_pass_audit.md`: all vanilla regional formation files are now overridden, unit types are compatible with the 1816 starting tech tiers, Egypt/Algeria/DEI placement issues were cleaned up, oversized barracks-only starts were capped from 1,107 to 892 explicit barracks levels, and `ZUL` received a small named formation.
- Remaining building work: any later targeted economy or military corrections found in-game.

Initial scripted European subject overrides:

- `AUS -> LOM` as `crown_land`.
- `GBR -> MLT` as `colony`.
- `RUS -> POL` as `personal_union`.
- Vanilla `AUS -> KRA` puppet pact removed, preserving Krakow as a free city landholder until joint-protection mechanics are scripted.
- `MLT` is set to `colonial` country type in country history so the colony pact is valid.

Resolved tiny-state map reviews:

- Liechtenstein `V00`: start ownership removed because `STATE_TYROL` province `xD0C0E0` was too large in game.
- San Marino `V01`: start ownership removed because `STATE_ROMAGNA` province `xFE3729` was too large in game.
- Monaco `V02`: start ownership removed because `STATE_PROVENCE` province `x5080E0` was too large in game.
- Andorra playable compromise using `V03`: scripted in `STATE_CATALONIA` province `x2914C3`.
- Saxe-Gotha-Altenburg and Saxe-Hildburghausen: scripted as generous one-province `STATE_SAXONY` abstractions using `V04` and `V05`.

Consolidated rest-of-Europe tag pass:

- Recorded in `planning/04_europe_country_inventory.md`.
- Strong vanilla reuse candidates are approved and mostly ready to script.
- User approved:
  - Conservative Austrian internal crown-land split policy.
  - Monaco and Andorra tiny-state treatment.
  - Krakow free-city protection model.
  - Iceland and Greenland as Danish direct/releasable-only for the first pass.
  - Deferring Caucasus edge cases.
  - Portugal display/global empire handling.

Earlier recommended regional passes, now mostly collapsed into the consolidated inventory:

1. France and Low Countries:
   - France post-1815 borders.
   - United Kingdom of the Netherlands.
   - Belgium not independent at start.
   - Luxembourg already approved as `NET -> LUX` personal union.
2. Iberia:
   - Spain, Portugal, Andorra feasibility.
3. British Isles and British Mediterranean possessions:
   - Great Britain/Ireland setup.
   - Malta implementation detail.
   - Ionian Islands already approved as protectorate.
4. Scandinavia:
   - Denmark, Sweden-Norway personal union, Finland under Russia.
5. Eastern Europe:
   - Russia, Congress Poland, Krakow, Galicia, Prussia/Austria/Russia partitions.
6. Balkans and Ottoman Europe:
   - Serbia, Wallachia, Moldavia, Greece, Ottoman possessions.
7. Switzerland and small neutral states:
   - Swiss confederation setup and Liechtenstein map review.

## Before Scripting

- Custom `V**` country definitions and approved first-pass localization overrides have been started.
- Next script governments, dedicated military building levels, laws/claims, literacy/profession refinement, and later flavor/event systems.
- After each script milestone, copy/sync the mod source into the Paradox launcher mod folder and test boot.

## Current MENA Work

- Middle East and North Africa tag pass is in `planning/05_middle_east_north_africa_inventory.md`.
- MENA is complete at the country/tag planning level.
- Tentative new tag:
  - `V06` Kuwait, pending map review.
- Approved MENA decisions:
  - Algiers as unified `ALD`.
  - Ottoman suzerainty model for Egypt, Tunis, Tripoli, and Algiers.
  - Returning the Levant to `TUR` and removing 1836 Egyptian Sudan/Eritrea holdings.
  - `NEJ` as Emirate of Diriyah and `HDJ` as Egyptian-aligned subject, with active war delayed.
  - `FZN` as Tripolitanian subject.
  - `ABU`, `BHN`, and possible `V06` Kuwait in the Gulf.
  - Yemen fragmentation with `ZAI`, `LAH`, `MAH`, `KAT`.
  - Post-Gulistan/pre-Turkmenchay Persia/Caucasus border review.
  - Defer Afghanistan, Kalat/Makran, Omani East Africa, and detailed Sudan/Horn work.

## Current Africa Work

- Rest-of-Africa tag pass is in `planning/06_africa_inventory.md`.
- Africa is complete at the country/tag planning level.
- No new `V**` tags are proposed for the main Africa pass yet.
- Approved Africa decisions:
  - Keep vanilla decentralized-country distinction for most non-centralized regions.
  - Use `SUD` as Sennar/Funj, `DFR` as Darfur, and remove 1836 Egyptian conquest results.
  - Fragment Ethiopia for the Zemene Mesafint instead of starting unified `ETH`.
  - Approve strong West African reuse candidates, with `MSN` and `MAL` absent until later/formable.
  - Model Dahomey as playable but tributary/protectorate-style under Oyo.
  - Use `SAF` and `SIL` for British colonies; direct ownership for Portuguese/French posts.
  - Use `ZAN`/`MBS` for the Omani/Swahili coast where map support is clean.
  - Approve Great Lakes/Central Africa vanilla reuse while preserving decentralized areas.
  - Use `ZUL` as a small newly consolidated playable start country; keep Boer republics/Natalia/Ndebele/Gaza absent.
  - Use `MAD` as Merina/Imerina under Radama I.

## Current Central Asia And Afghanistan Work

- Central Asia/Afghanistan pass is in `planning/07_central_asia_afghanistan_inventory.md`.
- Central Asia/Afghanistan is complete at the country/tag planning level.
- No new `V**` tags are proposed for this pass yet.
- Approved Central Asia/Afghanistan decisions:
  - Scope this as Afghanistan, Afghan Turkestan, Baluchistan, Central Asian khanates, Kazakh hordes, Turkmen areas, and immediate Russian/Qing frontier effects.
  - Defer full India work for `PAN`, `SIN`, `KAS`, `LAD`, `BIC`, and Indian princely states.
  - Use fragmented playable Afghanistan with `KAB`, `KAN`, `HER`, `KUN`, `MAI`, and `KAF`; keep `AFG` as reunification/formable.
  - Backdate later Sikh frontier gains where they affect Afghanistan, while leaving full Sikh/Sindh/Kashmir setup to India.
  - Use `KAL` and `MAK` for Kalat/Makran.
  - Approve `BUK`, `KHI`, and `KOK` for the main Central Asian khanates.
  - Keep `TRM` decentralized.
  - Reuse `KZH`, `OZH`, and `UZH` as playable Kazakh polities with Russian influence calibrated by horde.
  - Avoid new custom tags unless a later map review finds a necessary and representable missing polity.

## Current Rest Of Asia Work

- Rest-of-Asia tag pass is in `planning/08_asia_inventory.md`.
- Rest of Asia is complete at the country/tag planning level.
- Approved Rest of Asia decisions:
  - Backdate India instead of copying 1836; the Third Anglo-Maratha War has not happened yet.
  - Keep `BIC` as a British chartered company subject.
  - Keep `MUG` as a tiny playable Company puppet if Delhi map support remains clean.
  - Use `SAT` relocalized for the Peshwa/Maratha core, plus `GWA`, `IND`, `NAG`, and `BER` as playable Maratha powers with mixed British influence.
  - Add `V10` Multan as an Afghan-aligned playable frontier state.
  - Use post-Sugauli Nepal setup.
  - Backdate pre-Yandabo Burma and keep `SHS` as Burmese vassal.
  - Keep Qing China unified, with `TIB` and `KOR` as Qing subjects/tributaries; keep `MGL`, `MCH`, and `XIN` internal/releasable.
  - Keep Tokugawa Japan unified; `EZO` absent/later.
  - Add approved custom tag `V07` for the playable Ryukyu Kingdom.
  - Use vanilla mainland Southeast Asia setup with Vientiane review.
  - Use `DEI` under the Netherlands from start for clear gameplay.
  - Approve strong island Southeast Asia and Philippines reuse candidates.
  - Use `BCE` as British Ceylon and `MLD` as independent Maldives if map support is clean.

## Current Oceania Work

- Oceania tag pass is in `planning/09_oceania_inventory.md`.
- First Oceania map implementation is in `planning/18_oceania_north_america_map_implementation.md`.
- Oceania is complete at the country/tag planning level.
- No new `V**` tags are proposed for Oceania at this stage.
- Approved Oceania decisions:
  - Use `NSW` as the only playable British Australian colony at start; represent Van Diemen's Land/Tasmania under `NSW`.
  - Keep `WAS`, `SAS`, `TAS`, and `AST` absent/releasable/later rather than start countries.
  - Keep Aboriginal Australian tags decentralized/local rather than playable centralized countries.
  - Keep New Zealand Maori tags `NTO` and `NTU` decentralized/local; keep `UNT`, `AOT`, and `NZL` absent/later/formable.
  - Use `HAW` as playable sovereign Hawaii.
  - Use `PLY` as playable sovereign Tahiti/Pomare realm.
  - Keep `TNG` decentralized/local rather than a unified playable Tonga.
  - Keep `FJI` decentralized/local rather than a unified playable Fiji.
- Keep wider Melanesia, Micronesia, New Guinea, and Solomon/Bougainville tags decentralized/local with no European colonial ownership in 1816.
- Implemented first-pass map changes: Tasmania under `NSW`; Victoria and Queensland under decentralized `GML`; `WAS` and `SAS` removed from start ownership; New Zealand returned to `NTO`/`NTU`; late British and French protectorates removed.

## Current North America Work

- North America tag pass is in `planning/10_north_america_inventory.md`.
- First North America/Central America map implementation is in `planning/18_oceania_north_america_map_implementation.md`.
- North America is complete at the country/tag planning level.
- Approved North America decisions:
  - British North America split into playable `QUE`, `ONT`, `NVS`, `NBS`, `NEW`, and `HBC`, with `CAN` absent/formable.
  - `USA` starts with 1816 borders; Spanish Florida, Texas, California/New Mexico, and Oregon are not US-owned start areas.
  - `ALK` starts as Russian America / Russian-American Company under `RUS`.
  - `SC1` starts as playable Spanish New Spain; `MEX` is absent/formable/revolutionary.
  - `GUA` represents the Captaincy General of Guatemala under Spain; Central American successor tags are absent/later.
  - Caribbean colonies use `CUB`, `PCO`, `DOM`, `JAM`, and `BAH` where clean; `HAI` is one playable western Haiti despite the 1816 internal split.
  - Promote `COM` as playable Comanche / Comancheria for gameplay variety, even though this abstracts band-based Comanche power into a playable country.
  - Indigenous playable candidate retained on the start map is approved special `COM`; `CHE`, `MSC`, `V08`, and `V09` are no longer start-map owners and are kept for later release/event work.
- Implemented first-pass map changes: `NEW` Newfoundland playable under Britain; `SC1` New Spain restored; `GUA` Captaincy General restored; Florida returned to Spain; `ORG`, `SEQ`, `MEX`, `TEX`, and `UCA` removed from start ownership in the covered regions; the later Baja California/Nevada/Utah `MEX` leftovers were also cleaned to `SC1`; `COM` promoted to playable unrecognized; USA direct frontier ownership was reduced in Iowa, Minnesota, the Dakotas, Nebraska, Kansas, Colorado, Wyoming, and Montana. A later Old Southwest correction removed `CHE`, `MSC`, `V08`, and `V09` start-map ownership.

## Current South America Work

- South America tag pass is in `planning/11_south_america_inventory.md`.
- South America is complete at the country/tag planning level.
- First South America map implementation is in `planning/20_south_america_caribbean_map_implementation.md`.
- Follow-up correction is in `planning/26_americas_followup_date_and_subjects.md`: `BRZ` is now the Kingdom of Brazil under Portuguese personal union, and `CHL` is the Spanish Captaincy General of Chile rather than part of `SC3`.
- No new `V**` tags are proposed for South America at this stage.
- Approved South America decisions:
  - Use `SC2` as playable Spanish New Granada covering Colombia/Venezuela/Ecuador/Panama where map support allows; keep `PNM`, `CLM`, `VNZ`, `ECU`, `GCO`, and `FND` absent/later/formable.
  - Use `SC3` as playable Spanish Royalist Peru, including Peru, Upper Peru, and royalist Chile where map support allows; keep `PEU`, `BOL`, and `CHL` absent/later/revolutionary.
  - Use `ARG` relocalized as United Provinces / Rio de la Plata as playable de facto independent state.
  - Use `PRG` as playable independent Paraguay.
  - Use `URU` relocalized as Banda Oriental / Artigas Federal League as a playable abstraction.
  - Keep `SC4` absent/fallback rather than starting a Spanish Rio de la Plata landholder.
  - Keep approved `POR` transatlantic monarchy controlling Brazil; keep `BRZ` absent/later/releasable.
  - Use direct European ownership for Guianas.
  - Keep South American indigenous/local tags decentralized/local or releasable rather than centralized playable start countries in the first pass.

## Current Caribbean Work

- Detailed Caribbean pass is in `planning/12_caribbean_inventory.md`.
- Caribbean is complete at the country/tag planning level.
- First Caribbean map implementation is in `planning/20_south_america_caribbean_map_implementation.md`.
- No new `V**` tags are proposed for the Caribbean at this stage.
- Approved Caribbean decisions:
  - Use `CUB` and `PCO` as playable Spanish colonial subjects.
  - Use one playable `HAI` for western Haiti only; move Santo Domingo out of Haitian ownership and use `DOM` as Spanish Santo Domingo.
  - Use `JAM` and `BAH` as playable British colonies.
  - Keep Bermuda and Belize/British Honduras as direct British ownership without new tags.
  - Keep Lesser Antilles possessions as direct `GBR`, `FRA`, `NET`, `DEN`, and possibly `SWE` ownership rather than new playable micro-colonies.
  - Move any vanilla `VNZ` island ownership in `STATE_WEST_INDIES` to `SC2`.
  - Keep `WIN` and `ATL` absent/formable/alternate-history.

## Current Global Island And Colonial Leftovers Work

- Cleanup pass is in `planning/13_global_colonial_leftovers_inventory.md`.
- This is not a full region; it catches scattered island state regions and colonial edge cases that cut across regional passes.
- Cleanup pass is complete at the country/tag and broad ownership level.
- Remaining cleanup audit is in `planning/21_remaining_map_cleanup_audit.md`.
- Approved cleanup decisions:
  - Portuguese and Spanish Atlantic islands remain direct `POR`/`SPA`.
  - `STATE_SOUTH_ATLANTIC_ISLANDS` remains direct `GBR` for the first pass.
  - Unrepresented islands and sea-region-only islands get no country-history action.
  - Crete and West Aegean Islands move from 1836 owners back to `TUR`.
  - Ceylon, Maldives, and Ryukyu stay under the Asia pass.
  - No new `V**` tags are created in this cleanup pass.
