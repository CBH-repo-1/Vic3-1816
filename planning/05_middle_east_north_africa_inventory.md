# Middle East And North Africa Country Inventory

This file tracks the Middle East and North Africa country/tag inventory for the 1816 start. Rows are planning candidates unless marked approved and ready to script.

## Scope And Rules

- Regional pass: Middle East and North Africa.
- Use the same moderately strict tag rule approved for Europe.
- Strong vanilla reuse candidates are approved by default unless a historical or technical conflict appears.
- Reuse vanilla tags when they reasonably fit the 1816 polity.
- Relocalize vanilla tags when the tag is usable but the 1816 name differs from vanilla.
- Create new `V**` tags only where vanilla has no usable tag and vanilla map geometry can plausibly support the polity.
- This pass separates tag/start-status decisions from later population, building, and detailed state-ownership work.

## Historical Source Notes

- Egypt under Muhammad Ali was formally Ottoman but highly autonomous by 1816.
- The First Saudi State / Emirate of Diriyah still existed on January 1, 1816, and was destroyed in 1818.
- The Regency of Algiers, Tunis, and Tripoli were autonomous North African powers with varying degrees of Ottoman suzerainty.
- Qajar Persia had ceded major Caucasus territories to Russia by the 1813 Treaty of Gulistan, but the 1828 Turkmenchay border had not happened yet.

## Vanilla Tag Baseline

Useful vanilla tags found for this pass:

- Ottoman and Levant: `TUR`, `EGY`, `HDJ`, `SYR`, `LEB`, `PAL`, `EOT`, `IRQ`, `CYP`, `KUR`, `ASS`, `ISR`
- Maghreb and Libya: `MOR`, `ALD`, `MAS`, `CON`, `TUN`, `TRI`, `FZN`, `CYR`, `LBY`, `SAH`
- Arabia and Gulf: `NEJ`, `JAB`, `OMA`, `ABU`, `BHN`, `YEM`, `ZAI`, `LAH`, `MAH`, `KAT`
- Persia and Caucasus: `PER`, `ARB`, `ARM`, `AZB`, `GEO`, `DAG`, `CHC`, `CIR`
- Nile Valley edge cases: `SUD`, `DFR`, `BJA`

No vanilla Kuwait tag was found. `V06` is tentatively held for Kuwait if the vanilla Basra/Gulf map can support it.

## North Africa And Egypt

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Sultanate of Morocco | `MOR` | Morocco | Reuse vanilla tag | Sovereign | None | Strong | Yes | Retain Spanish enclaves as `SPA` ownership where represented; no separate enclave tags. |
| Regency of Algiers | `ALD` | Algeria | Approved: reuse vanilla tag, relocalize display | Autonomous Ottoman regency | `TUR` nominal suzerainty or loose diplomacy | Strong, but vanilla ownership is split | Yes | One playable `ALD`; use `MAS` and `CON` as releasable/admin abstractions rather than start countries. |
| Beylik of Mascara / Oran | `MAS` | Mascara | Approved: start absent / releasable or admin abstraction | Not sovereign at start if `ALD` is unified | Inside `ALD` | Strong | Yes | Vanilla owns Oran/Algiers in 1836; fold into `ALD` for 1816. |
| Beylik of Constantine | `CON` | Constantine | Approved: start absent / releasable or admin abstraction | Not sovereign at start if `ALD` is unified | Inside `ALD` | Strong | Yes | Vanilla owns Constantine in 1836; fold into `ALD` for 1816. |
| Regency of Tunis | `TUN` | Tunis | Approved: reuse vanilla tag | Autonomous Ottoman regency | `TUR` protectorate-style subject | Strong | Yes | Vanilla already models `TUR` -> `TUN` as protectorate. |
| Regency of Tripoli / Tripolitania | `TRI` | Tripolitania | Approved: reuse vanilla tag | Autonomous Ottoman regency | `TUR` protectorate or puppet-style subject | Strong | Yes | Vanilla uses `TUR` -> `TRI` puppet; protectorate may better fit autonomy. |
| Fezzan | `FZN` | Fezzan | Approved: reuse vanilla tag as playable | Tripolitanian interior subject | `TRI` tributary/protectorate candidate | Medium | Yes | Playable `FZN` under Tripoli. |
| Cyrenaica | `CYR` | Cyrenaica | Start absent / releasable only | Not present as a separate 1816 country | Inside Tripoli/Ottoman sphere | Medium | Yes | Useful later, but not a start country. |
| Libya | `LBY` | Libya | Start absent / formable or releasable only | Not present | N/A | Strong | Yes | Not an 1816 polity. |
| Egypt under Muhammad Ali | `EGY` | Egypt | Approved: reuse vanilla tag | Autonomous Ottoman province / protectorate | `TUR` protectorate plus own market | Strong | Yes | Should not own Syria/Palestine/Transjordan/Lebanon/Aleppo in 1816. |
| Egyptian Levant holdings | N/A | Vanilla has `EGY` owning them in 1836 | Approved: return to Ottoman ownership | Not Egyptian in 1816 | `TUR` direct | Strong | Yes | Syria, Palestine, Transjordan, Lebanon, and Aleppo return to `TUR`. |
| Egyptian Sudan / Eritrea holdings | `SUD`, `DFR`, `BJA` candidates | Vanilla has `EGY` owning parts in 1836 | Approved: remove from Egypt and defer detailed setup | Not Egyptian in 1816 | Africa/Nile Valley pass | Medium | No | Muhammad Ali's Sudan conquest begins after our start. Detailed setup moves to Africa. |
| Saharan decentralized polities | Various vanilla tags | Keep vanilla/defer | Decentralized / non-state polity | N/A | Strong | Yes | Handle detailed Sahara in the Africa pass unless it directly affects Morocco/Algeria/Tripoli. |

## Ottoman Core, Levant, And Iraq

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Ottoman Empire | `TUR` | Turkey / Ottoman Empire dynamic loc | Reuse vanilla tag, display as Ottoman Empire | Sovereign empire | Senior power | Strong | Yes | Should directly hold Anatolia, Iraq, Cyprus, and the Levant outside autonomous subjects. |
| Syria | `SYR` | Syria | Start absent / releasable only | Not present | Inside `TUR` at start | Strong | Yes | Not a separate 1816 country. |
| Lebanon / Mount Lebanon | `LEB` | Lebanon | Start absent / releasable only | Not present as a full country | Inside `TUR` at start | Strong | Yes | Local autonomy can be represented later without a start country. |
| Palestine | `PAL` | Palestine | Start absent / releasable only | Not present | Inside `TUR` at start | Strong | Yes | Not a separate 1816 country. |
| Transjordan | `EOT` | Emirate of Transjordan | Start absent / releasable only | Not present | Inside `TUR` at start | Strong | Yes | Not a separate 1816 country. |
| Iraq / Mesopotamian eyalets | `IRQ` | Iraq | Start absent / releasable only | Not present as unified Iraq | Inside `TUR` at start | Strong | Yes | Baghdad, Basra, and Mosul should be Ottoman direct unless local autonomy is later modeled. |
| Cyprus | `CYP` | Cyprus | Start absent / releasable only | Not present | Inside `TUR` at start | Strong | Yes | Ottoman direct possession in 1816. |
| Kurdistan | `KUR` | Kurdistan | Start absent / releasable only | Not present as one state | Split among empires/local authorities | Strong | Yes | Keep for later revolts/releasables. |
| Assyria | `ASS` | Assyria | Start absent / releasable only | Not present | Inside Ottoman/Persian borderlands | Medium | Yes | Releasable/cultural tag only. |
| Israel | `ISR` | Israel | Start absent / later releasable only | Not present | N/A | Strong | Yes | Not an 1816 country. |

## Arabia And The Persian Gulf

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| First Saudi State / Emirate of Diriyah | `NEJ` | Nejd | Approved: reuse vanilla tag, relocalize display | Sovereign unrecognized emirate | Hostile with Egypt/Ottoman sphere | Strong | Yes | Use `NEJ` for Diriyah; active-war scripting delayed to military/history systems. |
| Jabal Shammar / Ha'il | `JAB` | Jabal Shammar | Approved: start absent / later releasable only | Not present as 1836-style polity | Likely inside `NEJ` or local abstraction | Strong | Yes | Jabal Shammar as a major independent emirate is later than 1816. |
| Hedjaz | `HDJ` | Hedjaz | Approved: reuse vanilla tag | Egyptian/Ottoman-aligned subject | `EGY` tributary/protectorate candidate | Strong | Yes | Vanilla already models `EGY` -> `HDJ` tributary. |
| Oman / Omani Empire | `OMA` | Oman | Reuse vanilla tag | Sovereign unrecognized kingdom | None | Strong | Yes | East African and overseas Omani possessions should be handled in the East Africa/global pass. |
| Trucial Coast / Abu Dhabi | `ABU` | Trucial States | Approved: reuse vanilla tag | Playable unrecognized Gulf polity | No British subject status in 1816 | Strong | Yes | Vanilla has `ABU`; British protectorate relationship should not exist yet. |
| Bahrain | `BHN` | Bahrain | Approved: reuse vanilla tag | Playable unrecognized Gulf polity | Independent or disputed Gulf influence | Strong | Yes | Vanilla has map support in `STATE_ABU_DHABI` and `STATE_LARISTAN`. |
| Kuwait | `V06` | No vanilla tag found | Approved: add new tag if map review allows | Playable Gulf microstate candidate | Ottoman/Persian Gulf diplomacy | Tiny/needs review | No | Preserve if the Basra/Gulf map can support one province. |
| Qatar | None proposed | No vanilla tag found | No start tag | Local/tribal polity | Abstract into Gulf setup | Tiny/poor | Yes | Not recommended as a first-pass custom tag. |
| Zaidi Imamate / Yemen highlands | `ZAI` | Azal | Approved: reuse vanilla tag, relocalize if needed | Sovereign/local Yemeni polity | None | Strong | Yes | Main north Yemen start tag. |
| Lahej | `LAH` | Lahej | Approved: reuse vanilla tag | Playable local polity | None or loose regional diplomacy | Strong | Yes | Vanilla has support in `STATE_YEMEN`. |
| Mahra | `MAH` | Mahra | Approved: reuse vanilla tag | Playable local polity | None or loose regional diplomacy | Strong | Yes | Vanilla has support in `STATE_YEMEN`. |
| Kathiri | `KAT` | Kathiri | Approved: reuse vanilla tag | Playable local polity | None or loose regional diplomacy | Strong | Yes | Vanilla has support in `STATE_YEMEN`. |
| Yemen | `YEM` | Yemen | Start absent / formable only | Not unified | N/A | Strong | Yes | Use as later unification/releasable tag rather than a start country. |

## Persia And Caucasus Frontier

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Qajar Persia | `PER` | Persia | Reuse vanilla tag | Sovereign unrecognized empire | None | Strong | Yes | Needs 1816 border review against Russia and Ottoman Empire. |
| Arabistan / Muhammara | `ARB` | Arabistan | Reuse vanilla tag | Persian subject | `PER` vassal/protectorate | Strong | Yes | Vanilla already models `PER` -> `ARB` as vassal. |
| Armenia / Erivan frontier | `ARM` | Armenia | Approved: start absent / releasable only | Not present as start country | Split `PER`/`RUS` borderlands | Strong | No | 1816 border should be pre-Turkmenchay; ownership needs map review. |
| Azerbaijan / khanates | `AZB` | Azerbaijan | Approved: start absent / releasable only | Not present as unified start country | Split `PER`/`RUS` borderlands | Strong | No | 1816 border should be post-Gulistan but pre-Turkmenchay. |
| Georgia | `GEO` | Georgia | Start absent / releasable only | Mostly Russian-controlled/annexed | `RUS` direct | Strong | Yes | Use as releasable only for now. |
| Circassia | `CIR` | Circassia | Approved: reuse vanilla tag | Playable frontier polity | Russian/Ottoman frontier pressure | Strong | Yes | Vanilla has map support. |
| Chechnya | `CHC` | Chechnya | Approved: reuse vanilla tag | Playable frontier polity | Russian frontier pressure | Strong | Yes | Vanilla has map support. |
| Dagestan | `DAG` | Dagestan | Approved: reuse vanilla tag if map review allows | Playable or releasable frontier polity | Russian/Persian/Ottoman frontier | Medium | No | Vanilla tag exists, but vanilla start ownership is not clean. |

## Edge Cases Deferred From This Pass

| Area/problem | Candidate tags | Proposed handling | Ready to script | Notes |
| --- | --- | --- | --- | --- |
| Afghanistan and Central Asia | `AFG`, `KHI`, `KOK`, `BUK`, others | Defer to Central/South Asia pass | Yes | Not part of the MENA pass unless Persia border work demands it. |
| Kalat, Makran, and Baluchistan | `KAL`, `MAK`, others | Defer to South/Central Asia or Persia-border pass | Yes | Useful later, but not needed to finish MENA tag layout. |
| Omani East Africa / Zanzibar | `ZAN`, `MBS`, others | Defer to East Africa/global pass | Yes | Oman should exist now; overseas possessions need their own regional pass. |
| Detailed Sudan / Horn of Africa setup | `SUD`, `DFR`, `BJA`, others | Approved: defer to Africa pass after removing improper 1816 Egyptian ownership | No | We need avoid 1836 Egyptian conquest results in 1816. |

## Consolidated Batch Questions

Resolved by user approval:

1. One playable `ALD` Regency of Algiers; `MAS` and `CON` are releasable/admin abstractions.
2. Egypt, Tunis, Tripoli, and Algiers use autonomous Ottoman-dependent modeling.
3. Syria, Palestine, Transjordan, Lebanon, and Aleppo return to `TUR`; Sudan/Eritrea are removed from `EGY`.
4. `NEJ` is the Emirate of Diriyah and `HDJ` is Egyptian-aligned; active war scripting is delayed.
5. `FZN` remains a playable Tripolitanian subject.
6. `ABU` and `BHN` are playable independent Gulf polities; `V06` is tentatively reserved for Kuwait.
7. Yemen uses `ZAI`, `LAH`, `MAH`, and `KAT`; `YEM` is formable/releasable.
8. Persia/Caucasus border review uses post-Gulistan, pre-Turkmenchay logic; `CHC` and `CIR` are playable and `DAG` gets review.
9. Afghanistan, Kalat/Makran, Omani East Africa, and detailed Sudan/Horn setup are deferred.
