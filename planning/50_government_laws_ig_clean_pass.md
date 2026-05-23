# Government, Laws, and Interest Group Clean Pass

Status: complete for current playable-only pass.

## Scope

This pass starts the government, law, and interest group review after the global population QA.

The first goal is structural safety:

- Validate that law and interest group references resolve against the Victoria 3 1.12.5 base game.
- Find active landholders with missing political/law setup.
- Find duplicate country-history blocks where `?=` load order could silently shadow the intended setup.
- Avoid broad historical law changes until the cleanup policy is approved.

## Validation Results

Current structural results after the first cleanup:

- Active state-owner tags: 412.
- Active owners missing country history: 0.
- Active owners with no politics effect and no direct laws, first-definition-wins check: 0.
- Duplicate active country-history tags: 0.
- Country-history brace failures: 0.
- Bad `activate_law` references: 0.
- Bad `ig:` references: 0.

The earlier `set_interest_group_name` localization warnings are not treated as mod bugs. The names used by the mod are base-game names such as `ig_catholic_church`, `austrian_aristocracy`, `ig_shogunate`, `ig_hindu_priesthood`, and `ig_evangelical_church`.

## Implemented Technical Cleanup

### Malta

`MLT` was an active landholder and British colony subject, but its country history only set `set_country_type = colonial`.

Implemented a minimal crown-colony baseline:

- `set_country_type = colonial`.
- `effect_starting_technology_tier_3_tech = yes`.
- `effect_starting_politics_conservative = yes`.
- `law_colonial_administration`.
- `law_subjecthood`.

No detailed Malta interest-group choice has been made yet.

### Comanche, Lakota, and Kaurna

`COM`, `LKT`, and `KAU` had duplicate country-history blocks, which made their actual start setup dependent on load-order behavior.

Implemented consolidation:

- `COM` canonical file now includes `set_country_type = unrecognized`, tier 6 tech, traditional politics, and native conscription.
- `LKT` canonical file now includes `set_country_type = unrecognized`, tier 6 tech, traditional politics, and native conscription.
- `KAU` canonical file now uses the approved decentralized/local setup instead of the old high-tech parliamentary-republic workaround.
- Removed the duplicate `COM`, `LKT`, and `KAU` blocks from patch files.

## Left Alone For Now

`APC`, `ARP`, and `NVJ` use the vanilla pattern of directly activating `law_elder_council` without also explicitly activating `law_chiefdom`. This pass leaves that alone because it is inherited from base 1.12.5 and has not caused a known start failure.

## First Playable Content Batch

User-approved scope:

- Focus government/law/IG work on playable countries.
- Skip decentralized/local non-playable countries unless a bug forces us to touch them.
- Use conservative-monarchy and crown-colony templates as defaults.
- Prefer a council-style setup for playable Comanche and Lakota if the vanilla Council Republic law is too socialist/modern.

### Native Council Law

`law_council_republic` is not suitable for `COM` and `LKT` in 1816:

- It is unlocked by `socialism`.
- It is heavily tied to socialist/radical-left government behavior.

`law_elder_council` has the right flavor but is only visible for decentralized `law_chiefdom` countries, which would make it a poor fit for the playable unrecognized `COM` and `LKT` starts.

Implemented a narrow custom law:

- File: `common/laws/99_cow_1816_native_council.txt`.
- Law: `law_native_council`.
- Group: `lawgroup_distribution_of_power`.
- Scope: visible/enactable only for `COM` and `LKT`.
- Icon/modifier behavior borrows from vanilla `law_elder_council`.
- Applied to `COM` and `LKT`.

This keeps their governance principle on the safe vanilla `law_monarchy` abstraction while changing their power structure from `law_autocracy` to `law_native_council`.

### Moldavia and Wallachia

Removed two 1830s-era anachronisms from both `MOL` and `WAL`:

- `law_organic_regulation`.
- `law_elected_bureaucrats`.

Both now fall back to the traditional 1816 setup:

- `law_monarchy`.
- `law_autocracy`.
- `law_hereditary_bureaucrats`.
- `law_traditionalism`.
- `law_legacy_slavery`.
- `law_manorialism`.
- `law_migration_controls`.

## Second Playable Content Batch

Implemented obvious ruling-IG consistency for playable custom and colonial starts that had clear ruling elites but no explicit start government.

Custom/new playable tags:

- `V03` Andorra: `ig_devout` ruling, localized as Catholic Church.
- `V04` Saxe-Gotha-Altenburg: `ig_landowners` ruling.
- `V05` Saxe-Hildburghausen: `ig_landowners` ruling.
- `V06` Kuwait: `ig_landowners` ruling.
- `V07` Ryukyu: `ig_landowners` ruling.
- `SUD` Sennar/Funj: `ig_landowners` ruling.
- `ZAN` Zanzibar: `ig_landowners` ruling.

Playable colonial/company tags:

- `MLT`: `ig_armed_forces` ruling; `ig_devout` localized as Catholic Church.
- `NEW`: `ig_landowners` ruling.
- `DOM`: `ig_landowners` ruling; `ig_devout` localized as Catholic Church.
- `JAM`: `ig_landowners` ruling.
- `BAH`: `ig_landowners` ruling.
- `HBC`: `ig_industrialists` and `ig_armed_forces` ruling, matching the chartered-company style used by the British East India Company.

No law model was changed for these countries in this batch.

## Proposed Cleanup Policy

Recommended next step is a focused content pass rather than a global rewrite.

Suggested scope:

1. Review only new or heavily changed start-playable countries first.
2. Then review major vanilla countries whose 1816 situation is meaningfully different from 1836.
3. Leave ordinary decentralized/local tags on vanilla-style traditional politics unless there is a clear bug or approved historical reason.

Suggested law templates:

- European conservative monarchy: monarchy, autocracy or oligarchy depending case, state religion or freedom of conscience, hereditary or appointed bureaucracy, land/per-capita taxation by state capacity, mercantilism, tenant farmers/manorialism/serfdom by region, censorship or right of assembly by constitution.
- Crown colony / colonial administration: colonial administration, subjecthood, conservative economic setup, slavery law only where local slave pops or history require it.
- Playable unrecognized indigenous exception: keep `COM` and `LKT` as unrecognized playable abstractions with custom `law_native_council`.
- Interest groups: add explicit ruling IGs only where the start should be legible and stable; do not force every decentralized/local tag to have custom IG setup.

## Final Playable Review Decisions

Final decisions from the remaining playable-focused review:

- `KRA`: toned down from the more liberal vanilla free-city setup while retaining its republican/free-city identity.
- `ION`: left as-is. Its republic/protectorate abstraction is imperfect for 1816, but better than making it a direct crown colony or monarchy.
- `BCE` and `HBC`: left as-is after ruling-IG consistency work. Their laws are close to vanilla company/colonial templates.

Implemented `KRA` changes:

- `law_laissez_faire` -> `law_interventionism`.
- `law_free_trade` -> `law_mercantilism`.
- `law_total_separation` -> `law_freedom_of_conscience`.

Kept `KRA` laws:

- `law_presidential_republic`.
- `law_wealth_voting`.
- `law_land_based_taxation`.
- `law_private_schools`.
- `law_censorship`.

The government/laws/interest-group pass is now complete for the approved playable-only scope.
