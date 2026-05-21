# Africa Country Inventory

This file tracks the Africa country/tag inventory outside the already-approved Middle East and North Africa pass. The Africa-wide batch was approved by the user, including an explicit confirmation that `ZUL` should be playable.

## Scope And Rules

- Regional pass: Africa outside the MENA inventory.
- Use the same moderately strict tag rule approved for Europe and MENA.
- Reuse vanilla tags when they reasonably fit the 1816 polity.
- Relocalize vanilla tags when the tag is usable but the 1816 name differs from vanilla.
- Create new `V**` tags only where vanilla has no usable tag and vanilla map geometry can plausibly support the polity.
- Keep this pass at country/tag and broad start-status level. Detailed population, buildings, resources, and exact province ownership come later.

## Historical Source Notes

- The Sokoto Caliphate already existed in 1816 after the Fulani jihad and the fall of much of Hausaland.
- Dahomey existed in 1816 under Adandozan and remained tributary to Oyo until the later Ghezo-era break.
- Ethiopia was in the Zemene Mesafint, with imperial authority fragmented among regional princes.
- The Merina kingdom under Radama I was expanding in Madagascar, but not all Madagascar was unified in 1816.
- Southern Africa was at the opening edge of the Shaka/Mfecane era; later Boer republics, the Ndebele state, and the Gaza Empire should not be start countries.

## Vanilla Tag Baseline

The base game has extensive African support in `common/country_definitions/01_africa.txt`. The useful tags for this pass are mostly vanilla tags, not new custom tags.

No new `V**` tags are proposed for the main rest-of-Africa pass at this stage. The approved direction is to choose which vanilla tags become playable unrecognized states and which remain decentralized.

## Nile Valley, Sudan, And The Horn

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Sultanate of Sennar / Funj remnant | `SUD` | Sudan | Reuse vanilla tag, relocalize display | Sovereign/unrecognized | None | Medium | No | Recommended: use `SUD` for Sennar/Funj in the Blue Nile after removing improper 1816 Egyptian ownership. |
| Sultanate of Darfur | `DFR` | Darfur | Reuse vanilla tag | Sovereign/unrecognized | None | Strong | Yes | Strong reuse candidate. |
| Beja areas | `BJA` | Beja | Reuse vanilla tag | Decentralized / non-state polity | None | Medium | No | Use to help replace 1836 Egyptian/Eritrean ownership where map review supports it. |
| Ethiopian Empire as unified state | `ETH` | Ethiopia | Start absent / formable or reunification tag | Not unified in practice | N/A | Strong | No | Recommended: do not use unified `ETH` as a start country because of the Zemene Mesafint. |
| Tigray | `TGR` | Tigray | Reuse vanilla tag | Playable regional prince | Ethiopian imperial system | Strong | No | Candidate for fragmented Ethiopian setup. |
| Gojjam | `GJM` | Gojjam | Reuse vanilla tag | Playable regional prince | Ethiopian imperial system | Strong | No | Candidate for fragmented Ethiopian setup. |
| Begemder / Gondar core | `BGM` | Begemder | Reuse vanilla tag | Playable regional prince / imperial core | Ethiopian imperial system | Strong | No | Could carry the nominal emperor if we need one central tag. |
| Wello | `WLO` | Wello | Reuse vanilla tag | Playable regional prince | Ethiopian imperial system | Medium | No | Candidate for fragmented Ethiopian setup. |
| Shewa | `SHW` | Shewa | Reuse vanilla tag | Playable regional prince | Ethiopian imperial system | Strong | No | Important Ethiopian regional polity. |
| Qwara | `QWR` | Qwara | Reuse vanilla tag if needed | Playable or releasable regional polity | Ethiopian imperial system | Medium | No | Useful if map review supports a cleaner Gondar/Qwara split. |
| Aussa | `AWS` | Aussa | Reuse vanilla tag | Playable Afar polity | None | Medium | Yes | Vanilla support exists. |
| Harar | `HAR` | Harar | Reuse vanilla tag | Playable local polity | None | Medium | Yes | Vanilla support exists. |
| Kaffa | `KFA` | Kaffa | Reuse vanilla tag | Playable local kingdom | None | Medium | Yes | Vanilla support exists. |
| Welega / Oromo polities | `WLG`, `SDM`, `WLT`, `HDY`, `ARS` | Multiple vanilla tags | Reuse where map supports; otherwise decentralized/releasable | Local polities | None | Medium | No | Needs map review to avoid over-fragmenting Ethiopia. |
| Somali polities | `WSG`, `GLD`, `MJT`, `ISQ`, `OGD` | Warsangali, Geledi, Majerteen, Isaaq, Ogaden | Reuse vanilla tags | Playable or decentralized local polities | None | Strong | No | Strong tag support, but start statuses need batch approval. |
| Hobyo | `HOB` | Hobyo | Start absent / later releasable only | Not present | N/A | Strong | Yes | Hobyo is a later 19th-century state, not an 1816 start country. |

## West Africa And The Sahel

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Sokoto Caliphate | `SOK` | Sokoto | Reuse vanilla tag | Sovereign/unrecognized | None | Strong | Yes | Strong reuse candidate for the post-1804 Caliphate. |
| Gobir / Hausa remnants | `HAU` | Gobir | Start absent or small releasable | Mostly absorbed/contested | Sokoto/Bornu frontier | Medium | No | Vanilla `HAU` localizes as Gobir; use carefully so it does not undo Sokoto. |
| Bornu | `BOR` | Bornu | Reuse vanilla tag | Sovereign/unrecognized | None | Strong | Yes | Strong reuse candidate. |
| Wadai | `WAD` | Wadai | Reuse vanilla tag | Sovereign/unrecognized | None | Strong | Yes | Strong reuse candidate. |
| Bagirmi | `BGI` | Bagirmi | Reuse vanilla tag | Sovereign/unrecognized | None | Medium | Yes | Strong enough vanilla support. |
| Air / Tuareg polities | `AIR`, `TUA`, `AHG`, `ADG`, `ATR`, `DIN` | Multiple Tuareg tags | Keep mostly decentralized | Decentralized / non-state polity | None | Strong | Yes | Keep vanilla decentralized treatment unless a later Sahara pass asks otherwise. |
| Oyo Empire | `OYO` | Oyo | Reuse vanilla tag | Sovereign/unrecognized, weakened | Dahomey tributary senior | Strong | No | Oyo exists but is declining; recommended to model Dahomey tribute without overstrengthening Oyo. |
| Dahomey | `DAH` | Dahomey | Reuse vanilla tag | Oyo tributary / playable state | `OYO` tributary or protectorate-style relationship | Strong | No | In 1816 this is pre-Ghezo and still under Oyo tribute. |
| Benin Kingdom | `BEN` | Benin | Reuse vanilla tag | Sovereign/unrecognized | None | Strong | Yes | Strong reuse candidate. |
| Ashanti / Asante Empire | `ASH` | Ashanti | Reuse vanilla tag, possible relocalization to Asante | Sovereign/unrecognized | None | Strong | Yes | Strong reuse candidate. |
| Kong Empire | `KNG` | Kong | Reuse vanilla tag | Sovereign/unrecognized | None | Strong | Yes | Strong reuse candidate. |
| Futa Jallon | `FTJ` | Futa Jallon | Reuse vanilla tag | Sovereign/unrecognized | None | Strong | Yes | Strong reuse candidate. |
| Futa Toro | `FTR` | Futa Toro | Reuse vanilla tag | Sovereign/unrecognized | None | Medium | Yes | Strong enough vanilla support. |
| Kaabu | `KBU` | Kaabu | Reuse vanilla tag | Sovereign/unrecognized | None | Medium | Yes | Strong enough vanilla support. |
| Bambara states | `SGU`, `KRT` | Segou, Kaarta | Reuse vanilla tags | Sovereign/unrecognized | None | Strong | Yes | Strong reuse candidates. |
| Massina | `MSN` | Massina | Start absent / later event country | Not present on Jan. 1, 1816 | N/A | Medium | Yes | Founded shortly after the start date; keep for later emergence. |
| Mali | `MAL` | Mali | Start absent / formable only | Not present | N/A | Medium | Yes | Not an 1816 state. |
| Jolof / Cayor / Senegambia polities | `JLF`, `CAY`, `MDK`, `BND`, `SRR`, `SSU`, `TMN`, `DIO` | Multiple vanilla tags | Reuse mostly as decentralized or local polities | Mixed local polities | None | Medium | No | Needs a Senegambia mini-review if we want a fine-grained setup. |
| Mossi states | `MOS` | Mossi | Reuse vanilla tag, likely decentralized | Decentralized/local kingdoms | None | Medium | No | Could be upgraded to unrecognized if we decide to make more African states playable. |
| Igbo and Niger Delta polities | `IBO`, `IBL`, `TIV` | Multiple vanilla tags | Keep mostly decentralized | Decentralized / local polities | None | Strong | Yes | Keep vanilla decentralized treatment for first pass. |
| Sierra Leone Colony | `SIL` | Sierra Leone | Reuse vanilla tag | British colony | `GBR` colony | Strong | Yes | Existing British colony in 1816. |
| Liberia | `LIB` | Liberia | Start absent / later colony | Not present | N/A | Strong | Yes | Liberia is later than 1816. |
| French Senegal posts | None new | French enclaves | Represent as direct `FRA` ownership where map supports | Colonial posts | `FRA` | Small | No | No custom tag recommended. |

## Central Africa And The Congo Basin

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Kingdom of Kongo | `KON` | Kongo | Reuse vanilla tag | Sovereign/unrecognized, weakened | None | Strong | Yes | Strong reuse candidate. |
| Loango | `LNG` | Loango | Reuse vanilla tag | Local polity | None | Medium | No | Vanilla marks decentralized; review if playable. |
| Yaka | `YKA` | Yaka | Reuse vanilla tag | Local polity | None | Medium | No | Vanilla support exists. |
| Kuba | `KBA` | Kuba | Reuse vanilla tag | Local kingdom/polity | None | Medium | No | Vanilla marks decentralized; review if playable. |
| Luba | `LBA` | Luba | Reuse vanilla tag | Local kingdom/polity | None | Medium | No | Vanilla marks decentralized; review if playable. |
| Lunda / Kazembe zone | `LND`, `KZM`, `KSN`, `CHK` | Lunda, Kazembe, Kasanje, Chokwe | Reuse vanilla tags | Local polities | None | Strong | No | Need map review to distinguish central/southern Lunda states cleanly. |
| Equatorial/Congo decentralized regions | `BNG`, `BOB`, `MNB`, `LGA`, `HMB`, `ZND`, `DAK`, `DFT` | Multiple vanilla tags | Keep mostly decentralized | Decentralized / local polities | None | Strong | Yes | Keep vanilla decentralized treatment unless later design wants more playable states. |
| Portuguese Angola coast | None new | Portuguese colonial holdings | Represent as direct `POR` ownership where map supports | Colonial holdings | `POR` | Medium | No | No new Angola tag recommended for colonial holdings. |

## East Africa, Great Lakes, And Omani Coast

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Zanzibar / Omani East Africa | `ZAN` | Zanzibar | Reuse vanilla tag | Omani subject or direct Omani sphere | `OMA` subject candidate | Strong | No | Recommended: playable Omani subject for the Swahili coast where map supports it. |
| Mombasa | `MBS` | Mombasa | Reuse vanilla tag | Swahili city-state / Omani rival or subject | `OMA` influence | Strong | No | Mazrui autonomy can justify playability; exact relationship needs approval. |
| Witu | `WTU` | Witu | Start absent / later releasable only | Not present as start country | N/A | Medium | Yes | Later polity. |
| Buganda | `BUG` | Buganda | Reuse vanilla tag | Sovereign/unrecognized | None | Strong | Yes | Strong reuse candidate. |
| Bunyoro | `BNY` | Bunyoro | Reuse vanilla tag | Sovereign/unrecognized | None | Strong | Yes | Strong reuse candidate. |
| Ankole | `ANK` | Ankole | Reuse vanilla tag | Sovereign/unrecognized | None | Strong | Yes | Strong reuse candidate. |
| Rwanda | `RWD` | Rwanda | Reuse vanilla tag | Sovereign/unrecognized | None | Strong | Yes | Strong reuse candidate. |
| Burundi | `BRD` | Burundi | Reuse vanilla tag | Sovereign/unrecognized | None | Strong | Yes | Strong reuse candidate. |
| Karagwe | `KRG` | Karagwe | Reuse vanilla tag | Sovereign/unrecognized | None | Medium | Yes | Strong enough vanilla support. |
| Interior East African decentralized regions | `MSI`, `TRK`, `LUO`, `KKY`, `GGO`, `SNG`, `NYM`, `SKM`, `HHE` | Multiple vanilla tags | Keep mostly decentralized | Decentralized / local polities | None | Strong | Yes | Keep vanilla decentralized treatment for first pass. |
| Coastal Mozambique polities | `AGC`, `TGI`, `UYA`, `MKU`, `LMW`, `SNA`, `BTG` | Multiple vanilla tags | Reuse/keep local or decentralized | Local polities and Portuguese frontier | `POR` influence in coastal holdings | Medium | No | Needs Mozambique coast map review alongside Portuguese ownership. |
| Portuguese Mozambique coast | None new | Portuguese colonial holdings | Represent as direct `POR` ownership where map supports | Colonial holdings | `POR` | Medium | No | No custom Mozambique tag recommended for colonial holdings. |

## Southern Africa

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Cape Colony | `SAF` | South Africa | Reuse vanilla tag, relocalize/display as Cape Colony if needed | British colony | `GBR` colony | Strong | Yes | Strong reuse candidate; should not represent later Union/South Africa at start. |
| Zulu Kingdom | `ZUL` | Zulu | Reuse vanilla tag | Newly consolidated playable kingdom | None | Strong | No | Approved playable. Shaka's reign begins in 1816; map size/strength should be conservative. |
| Xhosa polities | `XHO` | Xhosa | Reuse vanilla tag | Decentralized/local polity | None | Strong | No | Could stay decentralized or become playable depending Africa-wide policy. |
| Swazi polity | `SWZ` | Swaziland | Reuse vanilla tag | Playable/local kingdom candidate | None | Medium | No | Vanilla tag exists. |
| Tswana polities | `TSW` | Tswana | Reuse vanilla tag | Decentralized/local polity | None | Strong | No | Vanilla decentralized treatment likely sufficient. |
| Griqua polities | `WBL`, `PHL` | Griqualand, Philippolis | Reuse vanilla tags if date/map support | Local frontier polities | None | Medium | No | Need exact-date review; may be easier to keep as later/frontier tags. |
| Basutoland | `BST` | Basutoland | Start absent / later emergence | Not present as 1836-style polity | N/A | Strong | Yes | Moshoeshoe's consolidation is later than Jan. 1, 1816. |
| Oranje / Boer republics | `ORA`, `TRN`, `NAL` | Oranje, Transvaal, Natalia | Start absent / later emergence | Not present | N/A | Strong | Yes | Boer republics and Natalia are later than 1816. |
| Ndebele / Matabele | `MTB` | Ndebele | Start absent / later emergence | Not present in later location | N/A | Medium | Yes | Later Mfecane-era movement; not a start country. |
| Gaza Empire | `GZA` | Gaza | Start absent / later emergence | Not present | N/A | Medium | Yes | Later 19th-century state. |
| Mutapa / Shona polities | `MTP`, `MSH`, `ZIM` | Mutapa, Mashona, Zimbabwe | Keep mostly decentralized/releasable | Local polities | None | Medium | No | `ZIM` should not be a unified start country. |
| Herero, Ovambo, Nama, San, Venda, Pedi | `HRO`, `OVB`, `NAM`, `SAN`, `VND`, `PDI` | Multiple vanilla tags | Keep mostly decentralized | Decentralized / local polities | None | Strong | Yes | Keep vanilla decentralized treatment for first pass. |

## Madagascar And Indian Ocean

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Merina / Kingdom of Imerina under Radama I | `MAD` | Madagascar | Reuse vanilla tag, relocalize display if needed | Sovereign/unrecognized kingdom | None | Strong | No | Recommended: use `MAD` for Merina/Imerina rather than creating multiple Malagasy custom tags. |
| Coastal Malagasy kingdoms | None new | No obvious vanilla split tags | Abstract as decentralized/local control within Madagascar setup | Local polities | None | Medium | No | Only split if a later map review finds clean vanilla province support. |
| Mauritius / Reunion / Seychelles | None new | No local country tags needed | European colonial ownership | British/French colonial possessions | `GBR`/`FRA` | Strong islands | No | Handle through colonial state ownership rather than new tags. |

## Africa-Wide Policy Questions

These design calls were approved as a batch.

1. Decentralized-country policy: keep vanilla's decentralized distinction for most non-centralized African regions, and only make clearly state-like polities playable unrecognized countries? Recommended: yes, because this keeps the workload sane and preserves Victoria 3's Africa mechanics.
2. Sudan/Nile Valley: use `SUD` relocalized as Sennar/Funj, use `DFR` for Darfur, use `BJA`/other tags for decentralized areas, and remove 1836 Egyptian conquest results? Recommended: yes.
3. Ethiopia: replace unified start `ETH` with a fragmented Zemene Mesafint setup using `TGR`, `GJM`, `BGM`, `WLO`, `SHW`, and selected nearby tags; keep `ETH` as reunification/formable. Recommended: yes.
4. West Africa: approve strong reuse for `SOK`, `BOR`, `WAD`, `BGI`, `OYO`, `DAH`, `BEN`, `ASH`, `KNG`, `FTJ`, `FTR`, `KBU`, `SGU`, and `KRT`; keep `MSN` and `MAL` absent until later emergence/formable content. Recommended: yes.
5. Dahomey/Oyo relationship: make `DAH` playable but tributary/protectorate-style under `OYO` at start, reflecting pre-1823 tribute. Recommended: yes if the subject type can be made to feel light enough.
6. European colonial posts: use `SAF` as British Cape Colony and `SIL` as British Sierra Leone; represent Portuguese Angola/Mozambique and French Senegal posts as direct colonial ownership rather than new tags. Recommended: yes.
7. East African coast: use `ZAN` as an Omani subject or Omani-sphere playable, and `MBS` as a playable/autonomous Swahili city-state if map support is clean; keep Witu later/absent. Recommended: yes.
8. Great Lakes and Central Africa: approve strong reuse for `BUG`, `BNY`, `ANK`, `RWD`, `BRD`, `KRG`, `KON`, `LBA`, `KZM`, and related vanilla tags, while keeping most deep-interior tags decentralized unless clearly state-like. Recommended: yes.
9. Southern Africa: use `ZUL` as a small newly consolidated start country, keep Boer republics/Natalia/Ndebele/Gaza absent until later, and leave many surrounding groups decentralized. Recommended: yes.
10. Madagascar: use `MAD` as Merina/Imerina under Radama I and avoid new Malagasy custom tags in the first pass. Recommended: yes.
