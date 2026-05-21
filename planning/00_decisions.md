# Design Decisions

This file records decisions that have been explicitly approved.

## Campaign Dates

- Start date: 1816.1.1
- End date: 1936.1.1

## Map Scope

- Use Victoria 3's default state, region, and province geometry.
- Change political ownership and setup data without redrawing provinces or state regions.
- Keep vanilla state-region resource potentials for the 1816 start, including gold, oil, rubber, mines, logging, fishing, whaling, arable land, and arable resource options. Treat these as physical/ecological potential; handle 1816 economic reality through buildings, production methods, technology, laws, and later event/journal content.

## Country/Tag Scope

- Build the first country/tag pass for Europe before expanding region by region.
- Strong reuse candidates are approved by default for all regional inventory passes unless a later historical or technical conflict is found.
- Newly created country tags should use the custom `V**` namespace.
- Allocate new tags as `V00` through `V99` first, then continue as `V0A`, `V0B`, and so on if more are needed.
- Do not use vanilla dynamic tags `D00` through `D99` for fixed mod countries.
- Use a moderately strict interpretation for country tags: reuse vanilla tags when they reasonably represent the 1816 polity, rename/localize vanilla tags when needed, and create/split new tags only when the vanilla abstraction is genuinely misleading and vanilla map geometry can support the split.

## German Confederation

- The Holy Roman Empire will not exist as a start country in 1816.
- The German Confederation will not be a unified playable country at start.
- German Confederation members should be playable as separate countries wherever vanilla state/province geometry can reasonably support them.
- The German Confederation should be represented through diplomacy, legal/political setup, Austrian chairmanship, Austro-Prussian rivalry, and later journal/treaty systems.
- Very small member states will be decided case by case instead of being automatically merged or automatically represented.
- German microstates should be included as playable by default. Only leave one out if it is literally too small to represent with Victoria 3's vanilla map geometry.
- Strong vanilla German Confederation reuse candidates are approved as the initial playable list.
- Use one abstracted playable Anhalt tag, `ANH`, rather than splitting the Anhalt duchies.
- Relocalize `COB` as Saxe-Coburg-Saalfeld for the 1816 start.
- Keep `SCW` as one abstracted playable Schwarzburg Principalities country.
- Keep `HOH` as one abstracted playable Hohenzollern Principalities country.
- Do not place Liechtenstein on the start map under vanilla province geometry; the available one-province compromise is too large. Keep `V00` as an inactive/releasable-or-flavor candidate.
- Preserve Saxe-Gotha-Altenburg as playable with `V04`, using `STATE_SAXONY` province `x31E0C0` as a generous Ernestine compromise.
- Preserve Saxe-Hildburghausen as playable with `V05`, using `STATE_SAXONY` province `x5141A0` as a generous Ernestine compromise.
- Reuss, Lauenburg, and Hesse-Homburg can be abstracted or omitted unless map review gives an unusually clean representation.

## Personal Unions

- If a country or territory was historically under a personal union at the 1816 start date, represent it with Victoria 3's personal union subject type where the game supports it.
- Keep Hanover under Great Britain as a personal union.
- Keep Luxembourg under the Netherlands as a personal union.
- Keep Holstein under Denmark as a personal union.
- Treat Schleswig like Holstein for gameplay: separately playable under Denmark as a personal union, while noting that Schleswig's historical legal status was not identical to Holstein's German Confederation membership.

## Italy

- Display `PAP` as Papal States instead of vanilla "Rome".
- Display `SIC` as Two Sicilies from the 1816 start for simplicity.
- Make Lombardy-Venetia playable under Austria as an Austrian `crown_land`, using `LOM` relocalized to Lombardy-Venetia unless implementation testing shows a better tag arrangement.
- Make Malta playable as a British crown colony, implemented with Victoria 3's `colony` subject type if technically feasible.
- Do not place San Marino on the start map under vanilla province geometry; the available one-province compromise is too large. Keep `V01` as an inactive/releasable-or-flavor candidate.

## Rest Of Europe

- Use the conservative "vanilla-plus" Austrian crown-land setup: playable `HUN`, `TRS`, `CRO`, and already-approved `LOM`; keep `BOH`, `GAL`/`GLI`, and `TRE` Austrian direct or releasable-only unless a later design pass deliberately expands Austrian internal playables.
- Do not place Monaco on the start map under vanilla province geometry; the available one-province compromise is too large. Keep `V02` as an inactive/releasable-or-flavor candidate.
- Preserve Andorra as playable with `V03`, using `STATE_CATALONIA` province `x2914C3` as the approved Pyrenees compromise.
- Represent Krakow as an independent Free City using treaty/guarantee-style protection from Austria, Prussia, and Russia rather than making it the subject of a single overlord.
- Keep Iceland and Greenland Danish direct or releasable-only for the first Europe scripting pass, rather than making them playable Danish subjects at start.
- Defer Georgia, Armenia, Azerbaijan, Dagestan, and Circassia to the Middle East / Russia-Ottoman-Persia frontier pass.
- Use `BRZ` as the Kingdom of Brazil under a Portuguese personal union at start, representing the United Kingdom of Portugal, Brazil and the Algarves without direct Portuguese ownership of Brazil.
- Represent Congress Poland as playable `POL` under a Russian personal union, using Greater Poland, Lesser Poland, and Mazovia as the first-pass vanilla-state approximation.

## Middle East And North Africa

- Use one playable `ALD` for the Regency of Algiers, with `MAS` and `CON` as releasable or administrative abstractions rather than start countries.
- Represent Egypt, Tunis, Tripoli, and Algiers as playable autonomous Ottoman dependents or special diplomatic dependents rather than fully independent states.
- Backdate Egypt from its 1836 setup: Syria, Palestine, Transjordan, Lebanon, and Aleppo return to `TUR`; Sudan and Eritrea should not be Egyptian in 1816.
- Use `NEJ` as the Emirate of Diriyah and `HDJ` as Egyptian-aligned, but delay active war scripting until military/history systems are being implemented.
- Keep `FZN` as a playable Tripolitanian tributary or protectorate instead of folding it directly into `TRI`.
- Make `ABU` and `BHN` playable independent Gulf polities.
- Tentatively reserve `V06` for Kuwait if vanilla map review supports it.
- Use fragmented Yemen with `ZAI`, `LAH`, `MAH`, and `KAT` playable; keep `YEM` as formable or releasable.
- Backdate the Persia/Russia frontier to the post-Gulistan, pre-Turkmenchay situation where map review allows.
- Keep `ARM`, `AZB`, and `GEO` releasable rather than start countries; use `CHC` and `CIR` as playable frontier polities and review `DAG`.
- Defer Afghanistan, Kalat/Makran, Omani East Africa, and detailed Sudan/Horn setup to later regional passes.

## Africa

- Keep vanilla's decentralized-country distinction for most non-centralized African regions, and only make clearly state-like polities playable unrecognized countries.
- Use `SUD` relocalized as Sennar/Funj, use `DFR` for Darfur, use `BJA` and related tags for decentralized areas, and remove 1836 Egyptian conquest results from Sudan and the Horn.
- Replace unified start `ETH` with a fragmented Zemene Mesafint setup using `TGR`, `GJM`, `BGM`, `WLO`, `SHW`, and selected nearby tags; keep `ETH` as a reunification/formable tag.
- Approve strong West African reuse for `SOK`, `BOR`, `WAD`, `BGI`, `OYO`, `DAH`, `BEN`, `ASH`, `KNG`, `FTJ`, `FTR`, `KBU`, `SGU`, and `KRT`; keep `MSN` and `MAL` absent until later emergence or formable content.
- Make `DAH` playable but tributary or protectorate-style under `OYO` at start.
- Use `SAF` as British Cape Colony and `SIL` as British Sierra Leone; represent Portuguese Angola/Mozambique and French Senegal posts as direct colonial ownership rather than new tags.
- Use `ZAN` as an Omani subject or Omani-sphere playable and `MBS` as a playable/autonomous Swahili city-state if map support is clean; keep Witu later or absent.
- Approve Great Lakes and Central Africa vanilla reuse for `BUG`, `BNY`, `ANK`, `RWD`, `BRD`, `KRG`, `KON`, `LBA`, `KZM`, and related tags while keeping most deep-interior tags decentralized unless clearly state-like.
- Use `ZUL` as a small, newly consolidated, playable start country. Keep Boer republics, Natalia, Ndebele, and Gaza absent until later emergence.
- Use `MAD` as Merina/Imerina under Radama I and avoid new Malagasy custom tags in the first pass.

## Central Asia And Afghanistan

- Scope this pass as Afghanistan, Afghan Turkestan, Baluchistan, Central Asian khanates, Kazakh hordes, Turkmen areas, and immediate Russian/Qing frontier effects.
- Defer full Indian subcontinent work for `PAN`, `SIN`, `KAS`, `LAD`, `BIC`, and Indian princely states except where their borders directly affect Afghanistan or Baluchistan.
- Use a fragmented playable Afghan setup with `KAB`, `KAN`, `HER`, `KUN`, `MAI`, and `KAF`; keep `AFG` as a reunification/formable tag rather than a start country.
- Keep `KAF` playable in the first pass rather than converting it to decentralized.
- Backdate later Sikh gains on the Afghan frontier, especially around Peshawar and Kashmir, but leave full Sikh/Sindh/Kashmir design to the India pass.
- Use `KAL` as playable sovereign Kalat and keep `MAK` as a playable or semi-playable Kalat subject if map support is clean.
- Approve strong reuse for `BUK`, `KHI`, and `KOK`, with `BUK` relocalized to a cleaner Bukhara/Emirate of Bukhara display if needed.
- Keep `TRM` decentralized rather than making it a playable centralized country.
- Reuse `KZH`, `OZH`, and `UZH` as playable Kazakh polities, with Russian protectorate-style influence strongest over `KZH`/`OZH` and `UZH` kept more autonomous if technically workable.
- Use vanilla `RUS`, `CHI`, and Central Asian tags for the Russian/Qing frontier rather than adding major custom tags.
- Create no new `V**` tags for this pass unless later map review uncovers a missing polity that is both important and representable.

## Rest Of Asia

- Treat India as a full 1816 backdate rather than copying 1836, because the Third Anglo-Maratha War has not happened yet.
- Keep `BIC` as a playable British chartered company subject under `GBR`, not direct British ownership.
- Keep `MUG` as a tiny playable `BIC` puppet in Delhi if map support remains clean.
- Use `SAT` relocalized for the Peshwa/Maratha core, plus `GWA`, `IND`, `NAG`, and `BER` as playable Maratha powers with mixed British influence rather than all as hard 1836-style puppets.
- Use post-Sugauli borders and treaty setup for Nepal for clean 1816 gameplay.
- Backdate pre-Yandabo Burma by restoring Arakan/Tenasserim-style holdings to `BUR` where the map supports it, while keeping `SHS` as a Burmese vassal.
- Keep `CHI` unified, `TIB` as Qing vassal/protectorate-style subject, and `KOR` as Qing tributary; keep `MGL`, `MCH`, and `XIN` releasable/internal rather than start countries.
- Keep `JAP` unified as Tokugawa Japan; do not split daimyo in the first pass, and keep `EZO` absent or later.
- Add new custom tag `V07` for the playable Ryukyu Kingdom, likely as a Japanese/Satsuma subject with Qing relationship flavor.
- Keep `SIA`, `DAI`, `BUR`, and their vanilla subjects; add/use `VIE` for Vientiane if map support is clean, and keep `LAO` formable/absent.
- Use `DEI` under the Netherlands from the start for gameplay clarity, rather than modeling a temporary British handover period in 1816.
- Approve strong reuse for `ACE`, `BRU`, `LAN`, `YOG`, `SRK`, `PON`, `SMB`, `BNJ`, `TID`, `BAL`, `SUL`, `MGD`, and `PHI`; keep `SLW` decentralized unless map review says otherwise.
- Use `BCE` as British Ceylon after the 1815 Kandyan Convention; keep `CEY` releasable/absent and make `MLD` a playable independent sultanate if the map supports it.

## Oceania

- Use `NSW` as the only playable British Australian colony at start, with Van Diemen's Land/Tasmania represented under `NSW` rather than as separate `TAS`.
- Keep `WAS`, `SAS`, `TAS`, and `AST` absent, releasable, or later rather than start countries.
- Keep Aboriginal Australian polities decentralized/local rather than representing them as playable centralized countries.
- Keep `NTO` and `NTU` as decentralized/local Maori polities; keep `UNT`, `AOT`, and `NZL` absent, later, or formable, with no British protectorate in 1816.
- Use `HAW` as a playable sovereign kingdom under Kamehameha I.
- Use `PLY` as a playable Kingdom of Tahiti / Pomare realm with no French subject status.
- Keep `TNG` decentralized/local rather than starting Tonga as a unified playable country.
- Keep `FJI` decentralized/local rather than starting Fiji as a unified playable country.
- Keep `KNK`, `VNT`, `NRU`, `MCR`, `PPU`, `BLA`, and `HLA` as decentralized/local polities with no European colonial ownership in 1816.
- Create no new `V**` tags for Oceania in this pass.

## North America

- Treat the North America pass as Canada, the United States, Mexico/New Spain, Central America, Alaska, and the Caribbean, while leaving final Panama/New Granada details to the South America pass.
- Start `QUE`, `ONT`, `NVS`, `NBS`, `NEW`, and `HBC` as playable British colonies or chartered company subjects; keep `CAN` formable/absent and `COL` later/absent.
- Use `USA` as a playable recognized republic with 1816 borders, excluding Spanish Florida, Texas, California/New Mexico, and sole Oregon ownership.
- Use `ALK` as a playable Russian-American Company style subject under `RUS`.
- Keep `ORG` and `COL` absent at start and represent Oregon/Columbia through claims, HBC activity, and decentralized/local peoples instead of a start country.
- Use vanilla `SC1` as a playable Spanish colonial subject for New Spain, rather than forcing `MEX` to exist in 1816.
- Use `GUA` relocalized as the Captaincy General of Guatemala as a playable Spanish colonial subject; keep `UCA`, `ELS`, `HON`, `NIC`, and `COS` absent, later, or releasable.
- Keep `MEX` absent, formable, or revolutionary at start, and delay active Mexican War of Independence scripting until the war/journal pass.
- Create no new Florida tag and do not use vanilla `FLA`, because it is Flanders; assign Spanish Florida to direct `SPA`, `SC1`, or `CUB` after map review.
- Make `CUB`, `PCO`, `DOM`, `JAM`, and `BAH` playable colonial subjects where map support is clean; keep `WIN` as later/formable and minor island possessions as direct European ownership.
- Use one playable `HAI` for western Haiti despite the 1816 Christophe/Petion split, and represent the split with flavor/internal instability later rather than another start tag.
- Make `CHE`, `MSC`, `MKT`, and approved special candidate `COM` playable unrecognized or protectorate-style countries; review `IRO` for playable status only if the map can support it cleanly.
- Tentatively reserve `V08` for Choctaw and `V09` for Chickasaw if map review supports them, with fallback to abstraction if the map is poor.
- Keep most Plains, Southwest, Northwest, northern, Pueblo, Maya, and Seminole tags decentralized/local rather than centralized playable countries in the first pass, except approved playable `COM`.
- Promote `COM` as playable Comanche / Comancheria for North American gameplay variety, even though this is an abstraction of band-based Comanche power rather than a strict centralized modern state.

## South America

- Use the South America pass to cover South America plus the Panama/New Granada loose end from Central America.
- Use `SC2` as a playable Spanish New Granada colonial subject covering Colombia, Venezuela, Ecuador, and Panama where map support allows.
- Keep `PNM`, `CLM`, `VNZ`, `ECU`, `GCO`, and `FND` absent, later, or formable at start.
- Use `SC3` as playable Spanish Royalist Peru, including Peru, Upper Peru, and royalist Chile where map support allows.
- Keep `PEU`, `BOL`, and `CHL` absent, later, or revolutionary at start.
- Use `ARG` relocalized as the United Provinces / Rio de la Plata as a playable de facto independent state, despite formal independence falling on July 9, 1816.
- Use `PRG` as playable independent Paraguay under Francia-style dictatorship and isolation.
- Use `URU` relocalized as Banda Oriental / Artigas Federal League as a playable abstraction, with Federal League influence modeled through diplomacy or journals rather than automatically giving it all allied Argentine provinces.
- Keep `SC4` absent or fallback rather than starting a Spanish Rio de la Plata country with land.
- Keep the already-approved `POR` transatlantic monarchy controlling Brazil; keep `BRZ` absent, later, or releasable rather than a separate start country.
- Use direct European ownership for British, Dutch, and French Guianas and create no new Guiana tag.
- Keep `PAT`, `AYM`, `ORN`, `MUI`, `WYU`, `TPI`, `GNI`, and related South American indigenous/local tags decentralized/local or releasable rather than centralized playable start countries in the first pass.
- Create no new `V**` tags for South America in this pass.

## Caribbean

- Use `CUB` and `PCO` as playable Spanish colonial subjects under `SPA`.
- Use one playable `HAI` for western Haiti only, remove 1836-style Haitian ownership of Santo Domingo, and use `DOM` as Spanish Santo Domingo under `SPA`.
- Use `JAM` and `BAH` as playable British colonies under `GBR`.
- Keep Bermuda as direct British ownership, not a playable tag.
- Keep the British enclave in `STATE_GUATEMALA` as direct `GBR` ownership, with no new tag.
- Keep British, French, Dutch, Danish, and possible Swedish island possessions as direct European ownership in `STATE_WEST_INDIES`, rather than creating new playable micro-colony tags.
- Preserve direct Swedish ownership of Saint Barthelemy if the vanilla province split gives a tolerable hook; otherwise abstract it into the closest West Indies owner.
- Move any vanilla `VNZ` island ownership in `STATE_WEST_INDIES` to `SC2` because Venezuela is not a start country.
- Keep `WIN` and `ATL` absent, formable, or alternate-history rather than start countries.
- Create no new `V**` tags for the Caribbean in this pass.

## Global Island And Colonial Leftovers

- Keep Azores, Madeira, Cape Verde, Canary Islands, and Balearic Islands as direct `POR`/`SPA` ownership with no new playable tags.
- Keep `STATE_SOUTH_ATLANTIC_ISLANDS` as direct `GBR` ownership for the first pass, despite the 1816 anachronism, and optionally model Argentine/Spanish-successor claim pressure later.
- Take no action for Saint Helena, Ascension, Tristan da Cunha, Easter Island, Galapagos, and Mascarenes unless a later map audit proves they are normal owned land states.
- Keep Corsica, Sardinia, Balearics, and Cyprus as direct/current planned owners; keep already-approved `ION` and `MLT` plans.
- Move Crete and the West Aegean Islands from their 1836 owners back to `TUR`.
- Treat Ceylon, Maldives, and Ryukyu as already covered by the Asia pass.
- Create no new `V**` tags in this global leftovers pass.

## Pending Decisions

- Whether to add a new pre-1836 technology era or stretch/rework existing Era I pacing.
- Whether to preserve vanilla playable objectives/tutorial assumptions or disable/rewrite them.
- Population and literacy source strategy.
- Starting buildings source strategy beyond the first mechanical cleanup.
