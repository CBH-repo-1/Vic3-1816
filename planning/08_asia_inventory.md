# Rest Of Asia Country Inventory

This file tracks the country/tag inventory for the rest of Asia after the Europe, MENA, Africa, and Central Asia/Afghanistan passes. The batch questions in this file were approved by the user.

## Scope And Rules

- Regional pass: Indian subcontinent, Himalayas, Tibet, China, Korea, Japan, mainland Southeast Asia, island Southeast Asia, the Philippines, Ceylon/Sri Lanka, Maldives, and remaining Asian colonial/company possessions.
- Russia-in-Asia and Persia are already covered by Europe/MENA/Central Asia unless a border cleanup is needed.
- Oceania and Australia are not part of this pass except where island Southeast Asia touches the Pacific map.
- Use the same moderately strict tag rule approved for earlier regions.
- Reuse vanilla tags wherever possible. Create `V**` tags only where a historically important polity has no usable vanilla tag and the map can plausibly show it.
- Keep this pass at country/tag and broad start-status level. Detailed population, buildings, resources, and exact province ownership come later.

## Historical Source Notes

- The British East India Company was already the dominant power in India, but the Third Anglo-Maratha War had not yet happened on January 1, 1816, so India should not simply copy the 1836 post-Maratha setup.
- Nepal's Sugauli settlement belongs to the immediate 1816 moment; using the post-Sugauli border is cleaner even though ratification details sit close to the start date.
- The Konbaung kingdom of Burma still held important western/southern territories before the First Anglo-Burmese War and the 1826 Treaty of Yandabo.
- Qing China, Tokugawa Japan, Joseon Korea, and Nguyen Vietnam are strong vanilla starts with relatively straightforward backdating.
- The Dutch East Indies were in the handover moment from British occupation back to Dutch rule in 1816; for clean gameplay, the first pass should use Dutch colonial control rather than a temporary British interregnum.
- Ryukyu is historically important and map-visible, but vanilla has no Ryukyu country tag.

## Vanilla Tag Baseline

Useful vanilla support includes:

- India and Himalayas: `BIC`, `MUG`, `PAN`, `SIN`, `KAS`, `LAD`, `NEP`, `BHU`, `SIK`, `AWA`, `HYD`, `MYS`, `TRA`, `COC`, `GWA`, `IND`, `NAG`, `BER`, `SAT`, `BHO`, `JAI`, `MEW`, `BIK`, `JAS`, `KUT`, `BHW`, `PTA`, `GAR`, `ASM`, `MNP`, `TIP`, `NGA`, `MGH`, and many smaller princely tags.
- Ceylon and Indian Ocean: `BCE`, `CEY`, and `MLD`.
- China and East Asia: `CHI`, `TIB`, `KOR`, `JAP`, `AIN`, `EZO`, `MGL`, `MCH`, `XIN`, and `YUZ`.
- Mainland Southeast Asia: `SIA`, `BUR`, `DAI`, `CAM`, `CMI`, `LUA`, `CHP`, `VIE`, `LAO`, `SHS`, and `JOH`.
- Island Southeast Asia and Philippines: `DEI`, `PHI`, `ACE`, `BAL`, `BRU`, `LAN`, `SAK`, `JMB`, `PON`, `SMB`, `STG`, `BNJ`, `YOG`, `SRK`, `TID`, `BTN`, `SUL`, `MGD`, `SLW`, `SEL`, and `PRK`.

Approved new tag:

- `V07` Ryukyu Kingdom. Vanilla has `STATE_RYUKYU_ISLANDS` but no usable country tag found.

## Indian Subcontinent And Himalayas

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| British East India Company | `BIC` | British East India Company | Reuse vanilla tag | British chartered company / colonial subject | `GBR` chartered company | Strong | Yes | Strong reuse candidate; should be the main British Indian power, not direct Britain. |
| Mughal emperor in Delhi | `MUG` | Mughals | Reuse vanilla tag | Tiny playable Company puppet if map support stays clean | `BIC` puppet | Strong | No | Historically weak but politically real; vanilla already gives a Delhi micro-subject. |
| Sikh Empire / Punjab | `PAN` | Panjab | Reuse vanilla tag | Playable sovereign/unrecognized kingdom | None | Strong | Yes | Later Peshawar gains are already backdated; Multan is split out for 1816. |
| Multan | `V10` | No clean vanilla tag | Add custom tag | Playable Afghan-aligned frontier state | `KAB` tributary | Medium | Yes | Approved because Multan was not yet absorbed by the Sikh Empire in 1816. |
| Sindh / Talpur Amirs | `SIN` | Sind | Reuse vanilla tag | Playable sovereign/unrecognized principality | None | Strong | Yes | Strong reuse candidate. |
| Kashmir | `KAS` | Kashmir | Reuse vanilla tag | Playable Afghan-aligned boundary polity | `KAB` tributary | Strong | Yes | Not Sikh-held yet in 1816; `PAN -> KAS` is removed and `KAB -> KAS` added. |
| Ladakh | `LAD` | Ladakh | Reuse vanilla tag | Playable independent frontier polity | Himalaya frontier | Strong | Yes | Kept independent in the first deeper India pass. |
| Nepal | `NEP` | Nepal | Reuse vanilla tag | Playable sovereign/unrecognized kingdom | None, with British treaty relation | Strong | No | Recommended: use post-Sugauli border for cleaner 1816 setup. |
| Bhutan | `BHU` | Bhutan | Reuse vanilla tag | Playable sovereign/unrecognized principality | None | Strong | Yes | Strong reuse candidate. |
| Sikkim | `SIK` | Sikkim | Reuse vanilla tag | Playable Himalayan principality | British/Nepal/Tibet frontier | Medium | No | Backdate against Nepal/British frontier settlement if needed. |
| Awadh | `AWA` | Awadh | Reuse vanilla tag | Playable Company protectorate/puppet | `BIC` subject | Strong | No | Strong reuse; subject type can be tuned lighter than hard puppet. |
| Hyderabad | `HYD` | Hyderabad | Reuse vanilla tag | Playable Company subsidiary ally/subject | `BIC` subject | Strong | No | Strong reuse candidate. |
| Mysore | `MYS` | Mysore | Reuse vanilla tag | Playable Company subject | `BIC` subject | Strong | No | Strong reuse candidate. |
| Travancore and Cochin | `TRA`, `COC` | Travancore, Cochin | Reuse vanilla tags | Playable Company subjects | `BIC` subject | Strong | No | Strong reuse candidates. |
| Maratha Peshwa / Pune core | `SAT` | Satara | Reuse/relocalize to Peshwa's State or Maratha core | Playable, not yet annexed | Maratha/BIC conflict setup | Medium | No | Vanilla lacks a Peshwa tag; using `SAT` is the least-code first pass. |
| Maratha powers | `GWA`, `IND`, `NAG`, `BER` | Gwalior, Indore, Nagpur, Baroda | Reuse vanilla tags | Playable Maratha states with mixed British influence | Mixed BIC subject/protectorate/independent | Strong | No | Do not blindly copy 1836 puppetry; 1816 is pre-final Maratha defeat. |
| Rajput and central Indian princely states | `JAI`, `MEW`, `BIK`, `JAS`, `BHO`, `KUT`, `JOD`, `ALW`, others | Multiple vanilla tags | Reuse vanilla tags | Playable or BIC subject/protectorate depending treaty status | `BIC` influence | Strong | No | Keep vanilla playable granularity unless exact map/history creates clutter. |
| Assam, Manipur, Tripura, Khasi/Naga frontier | `ASM`, `MNP`, `TIP`, `MGH`, `NGA`, others | Multiple vanilla tags | Reuse vanilla tags | Playable/local polities; not all British | Burma/BIC frontier | Strong | Yes | Company ownership removed from Assam; Tripura kept under lighter British protectorate treatment. |
| British Ceylon | `BCE` | British Ceylon | Reuse vanilla tag | British colony | `GBR` colony | Strong | Yes | Kandy was annexed in 1815; `CEY` should be releasable/absent at start. |
| Maldives | `MLD` | Maldives | Reuse vanilla tag | Playable sovereign/unrecognized sultanate | None | Strong | No | Not yet a British protectorate. |

## China, Korea, Tibet, And Japan

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Qing China | `CHI` | China | Reuse vanilla tag, display/Qing flavor if needed | Sovereign unrecognized empire | None | Strong | Yes | Strong reuse candidate. |
| Tibet | `TIB` | Tibet | Reuse vanilla tag | Playable Qing vassal/protectorate-style subject | `CHI` vassal | Strong | No | Vanilla already uses Qing vassal. |
| Korea / Joseon | `KOR` | Korea | Reuse vanilla tag | Playable Qing tributary | `CHI` tributary | Strong | Yes | Strong reuse candidate. |
| Mongolia, Manchuria, Xinjiang | `MGL`, `MCH`, `XIN` | Mongolia, Manchuria, Xinjiang | Start absent / releasable only | Qing internal/frontier regions | `CHI` | Strong | Yes | Do not split Qing start unless later design deliberately expands Qing internal playables. |
| Taiwan/Formosa indigenous areas | `YUZ` | Yuanzhumin | Keep decentralized/local if map supports | Decentralized / frontier polity | Qing frontier | Medium | No | Use carefully; not a centralized island state. |
| Tokugawa Japan | `JAP` | Japan | Reuse vanilla tag | Sovereign unrecognized shogunate | None | Strong | Yes | Strong reuse; no need to split domains in first pass. |
| Ainu / Hokkaido frontier | `AIN` | Ainu Mosir | Reuse vanilla tag if map needs frontier separation | Decentralized/local or playable edge case | Japanese frontier | Medium | No | Recommended: not a full centralized playable state unless map/testing makes it worthwhile. |
| Ezo Republic | `EZO` | Ezo | Start absent / later event only | Not present | N/A | Strong | Yes | Ezo Republic is a later 1868-69 event, not an 1816 start. |
| Ryukyu Kingdom | `V07` proposed | No vanilla tag | Add new tag if approved | Playable dual-subordination kingdom | Japanese/Satsuma subject, Qing relation flavor | Strong | No | Recommended: add `V07`; vanilla has Ryukyu islands but no country tag. |

## Mainland Southeast Asia

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Siam / Rattanakosin Kingdom | `SIA` | Siam | Reuse vanilla tag | Playable sovereign/unrecognized kingdom | None | Strong | Yes | Strong reuse candidate. |
| Chiang Mai / Lanna | `CMI` | Chiang Mai | Reuse vanilla tag | Playable Siamese vassal | `SIA` vassal | Strong | Yes | Vanilla already supports it. |
| Luang Prabang | `LUA` | Luang Prabang | Reuse vanilla tag | Playable Siamese tributary | `SIA` tributary | Strong | Yes | Vanilla already supports it. |
| Champassak | `CHP` | Champassak | Reuse vanilla tag | Playable Siamese vassal | `SIA` vassal | Strong | Yes | Vanilla already supports it. |
| Vientiane | `VIE` | Vientiane-style Laos tag | Reuse vanilla tag if map supports | Playable Siamese tributary | `SIA` tributary | Medium | No | Important because Vientiane still exists before its 1828 destruction. |
| Unified Laos | `LAO` | Laos | Start absent / formable only | Not present | N/A | Strong | Yes | Do not use as start country. |
| Vietnam / Nguyen dynasty | `DAI` | Dai Viet | Reuse vanilla tag, relocalize if needed | Playable sovereign/unrecognized kingdom | None | Strong | Yes | Gia Long's Vietnam is unified by 1816. |
| Cambodia | `CAM` | Cambodia | Reuse vanilla tag | Playable Vietnamese-aligned vassal/tributary with Siam pressure | `DAI` vassal candidate | Strong | No | Vanilla `DAI -> CAM` is acceptable first pass, with Siam relations. |
| Konbaung Burma | `BUR` | Burma | Reuse vanilla tag | Playable sovereign/unrecognized kingdom | None | Strong | No | Backdate pre-Yandabo holdings, especially Arakan/Tenasserim. |
| Shan States | `SHS` | Shan | Reuse vanilla tag | Playable Burmese vassal | `BUR` vassal | Strong | Yes | Vanilla already supports it. |
| Malaya states | `JOH`, `PRK`, `SEL` | Johor, Perak, Selangor | Reuse vanilla tags | Playable Malay states | None / local relations | Medium | No | No Singapore start; Penang/British/Dutch coastal details need map review. |

## Island Southeast Asia And Philippines

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Dutch East Indies | `DEI` | Dutch East Indies Company | Reuse/relocalize as Dutch East Indies | Dutch colonial subject | `NET` colony/chartered company | Strong | No | Recommended: use Dutch control from start for clean gameplay, despite 1816 handover timing. |
| Javanese princely states | `YOG`, `SRK` | Yogyakarta, Surakarta | Reuse vanilla tags | Playable Dutch subjects | `DEI` puppets | Strong | Yes | Vanilla already supports them. |
| West Borneo kongsis/sultanates | `LAN`, `PON`, `SMB`, `STG` | Lanfang, Pontianak, Sambas, Sintang | Reuse vanilla tags | Playable local states | Qing/Dutch/local relationships | Strong | No | `LAN` can keep Qing tributary flavor if workable. |
| Sumatra states | `ACE`, `SAK`, `JMB` | Aceh, Siak, Jambi | Reuse vanilla tags | Playable local states | Mixed Dutch/local | Strong | No | Aceh should remain independent. |
| Borneo and eastern islands | `BRU`, `BNJ`, `TID`, `BTN`, `BAL`, `SLW` | Brunei, Banjar, Tidore, Buton, Bali, Sulawesi | Reuse vanilla tags | Playable or decentralized local polities | Mixed Dutch/local | Strong | No | Keep vanilla decentralized status for `SLW` unless map review suggests state-like play. |
| Spanish Philippines | `PHI` | Philippines | Reuse vanilla tag | Spanish colony | `SPA` colony | Strong | Yes | Strong reuse candidate. |
| Sulu Sultanate | `SUL` | Sulu | Reuse vanilla tag | Playable sovereign/unrecognized sultanate | None / Spanish frontier | Strong | Yes | Strong reuse candidate. |
| Maguindanao | `MGD` | Maguindanao | Reuse vanilla tag | Playable sovereign/unrecognized sultanate | None / Spanish frontier | Strong | Yes | Strong reuse candidate. |

## Batch Questions For Approval

These design calls were approved as a batch.

1. India scope: treat India as a full 1816 backdate rather than a light 1836 copy, because the Third Anglo-Maratha War has not happened yet? Recommended: yes.
2. British India: keep `BIC` as a playable British chartered company subject under `GBR`, not direct British ownership? Recommended: yes.
3. Mughal emperor: keep `MUG` as a tiny playable `BIC` puppet in Delhi if map support remains clean? Recommended: yes for flavor and playability.
4. Maratha setup: use `SAT` relocalized for the Peshwa/Maratha core, plus `GWA`, `IND`, `NAG`, and `BER` as playable Maratha powers with mixed British influence rather than all as hard 1836-style puppets? Recommended: yes.
5. Nepal: use post-Sugauli borders/treaty setup for clean 1816 gameplay? Recommended: yes.
6. Burma: backdate pre-Yandabo Burma by restoring Arakan/Tenasserim-style holdings to `BUR` where the map supports it, while keeping `SHS` as Burmese vassal? Recommended: yes.
7. China/Korea/Tibet: keep `CHI` unified, `TIB` as Qing vassal/protectorate-style subject, and `KOR` as Qing tributary; keep `MGL`, `MCH`, and `XIN` releasable/internal rather than start countries? Recommended: yes.
8. Japan: keep `JAP` unified as Tokugawa Japan; do not split daimyo in the first pass, and keep `EZO` absent/later. Recommended: yes.
9. Ryukyu: add new custom tag `V07` for the playable Ryukyu Kingdom, likely as a Japanese/Satsuma subject with Qing relationship flavor? Recommended: yes, because vanilla has the islands but no country tag.
10. Mainland Southeast Asia: keep `SIA`, `DAI`, `BUR`, and their vanilla subjects, add/use `VIE` for Vientiane if map support is clean, and keep `LAO` formable/absent? Recommended: yes.
11. Dutch East Indies: use `DEI` under the Netherlands from the start for gameplay clarity, rather than modeling a temporary British handover period in 1816? Recommended: yes.
12. Island Southeast Asia/Philippines: approve strong reuse for `ACE`, `BRU`, `LAN`, `YOG`, `SRK`, `PON`, `SMB`, `BNJ`, `TID`, `BAL`, `SUL`, `MGD`, and `PHI`; keep `SLW` decentralized unless map review says otherwise? Recommended: yes.
13. Ceylon/Maldives: use `BCE` as British Ceylon after the 1815 Kandyan Convention; keep `CEY` releasable/absent and make `MLD` a playable independent sultanate if the map supports it? Recommended: yes.
