# Central Asia And Afghanistan Country Inventory

This file tracks the country/tag inventory east of the approved Middle East pass and west or north-west of the Indian subcontinent. The batch questions in this file were approved by the user.

## Scope And Rules

- Regional pass: Afghanistan, Afghan Turkestan, Baluchistan, Central Asian khanates, Kazakh hordes, Turkmen areas, and immediate Russian/Qing frontier effects.
- Exclude the main Indian subcontinent pass for now: `PAN`, `SIN`, `KAS`, `LAD`, `BIC`, and Indian princely states are boundary notes unless their 1816 borders directly affect Afghanistan or Baluchistan.
- Persia remains part of the MENA/Persia frontier pass, but eastern Persian border cleanup can be coordinated here if needed.
- Use the same moderately strict tag rule approved for Europe, MENA, and Africa.
- Keep this pass at country/tag and broad start-status level. Detailed population, buildings, resources, and exact province ownership come later.

## Historical Source Notes

- The Durrani state was still a nominal frame in 1816, but Afghan authority had been badly fragmented by succession struggles, regional power-holders, and the decline of central power.
- Bukhara, Khiva, and Kokand were all viable Central Asian khanate/emirate starts before the later Russian conquest.
- Kazakh hordes had varying degrees of Russian protectorate/influence by 1816; direct Russian ownership should be kept to frontier/fort-line areas rather than deep steppe control.
- Kalat existed as a Baloch-Brahui confederacy/khanate; Makran is already modeled by vanilla as a Kalat subject.
- Sikh expansion into Peshawar and Kashmir is mostly later than January 1, 1816, so those frontier gains should be backdated during the Afghanistan/India boundary work.

## Vanilla Tag Baseline

The base game already has strong vanilla support in `common/country_definitions/00_countries.txt` and the Central Asia state history:

- Afghan split/formable set: `KAB`, `KAN`, `HER`, `KUN`, `MAI`, `KAF`, and `AFG`.
- Central Asian khanates: `BUK`, `KHI`, and `KOK`.
- Kazakh hordes and later Kazakh formable: `KZH`, `OZH`, `UZH`, and `KAZ`.
- Turkmen areas and modern releasables/formables: `TRM`, `UZB`, `KYR`, `TJI`, `TRC`.
- Baluchistan edge: `KAL` and `MAK`.
- Indian-subcontinent boundary tags to defer unless needed: `PAN`, `SIN`, `KAS`, `LAD`, `BHW`, and `BIC`.

No new `V**` tags are proposed for this pass at this stage.

## Afghanistan And Afghan Turkestan

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Unified Afghanistan / Durrani restoration goal | `AFG` | Afghanistan | Start absent / reunification or formable tag | Not a normal start country | N/A | Strong | No | Recommended: keep `AFG` as the unification outcome rather than start unified Afghanistan. |
| Kabul | `KAB` | Kabul | Reuse vanilla tag | Playable Afghan principality | Afghan reunification system | Strong | No | Use as the main Kabul-centered successor. Could carry nominal Durrani legitimacy if needed. |
| Kandahar | `KAN` | Kandahar | Reuse vanilla tag | Playable Afghan principality | Afghan reunification system | Strong | No | Vanilla already supports it; useful for the Durrani/Barakzai fragmentation. |
| Herat | `HER` | Herat | Reuse vanilla tag | Playable Afghan principality | Afghan reunification system | Strong | No | Important buffer between Persia and Afghan politics. |
| Kunduz | `KUN` | Kunduz | Reuse vanilla tag | Playable northern Afghan/Uzbek principality | Afghan/Bukhara frontier | Strong | No | Vanilla support exists and fits a fragmented Afghan Turkestan setup. |
| Maimana | `MAI` | Maimana | Reuse vanilla tag | Playable northern Afghan/Uzbek principality | Afghan/Bukhara frontier | Strong | No | Vanilla support exists; keep modest. |
| Kafiristan | `KAF` | Kafiristan | Reuse vanilla tag | Playable isolated local polity, or decentralized if later testing prefers | Afghan reunification edge case | Medium | No | Recommended first pass: keep playable because vanilla already supports it and it adds a distinct mountain start. |
| Sikh-held Afghan frontier gains | `PAN` boundary | Panjab | Backdate later Sikh gains where needed | Boundary adjustment, not full India pass | N/A | Medium | No | Peshawar/Kashmir questions touch India; handle exact ownership with the India pass but avoid 1836 Sikh expansion being present in 1816. |

## Baluchistan And Western India Edge

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Khanate of Kalat | `KAL` | Kalat | Reuse vanilla tag | Playable sovereign/unrecognized khanate | None | Strong | Yes | Strong reuse candidate. |
| Makran | `MAK` | Makran | Reuse vanilla tag | Playable or semi-playable Kalat subject | `KAL` vassal/tributary candidate | Strong | No | Vanilla already has `KAL -> MAK`; likely keep unless map review suggests direct Kalat ownership. |
| Sindh | `SIN` | Sindh | Defer to Indian subcontinent pass | Boundary country | None | Strong | No | Talpur Sindh is important but belongs with the India pass. |
| Sikh Empire / Punjab | `PAN` | Panjab | Defer to Indian subcontinent pass, except Afghan frontier correction | Boundary country | None | Strong | No | Need later backdating of Sikh expansion compared with vanilla 1836. |
| Kashmir and Ladakh | `KAS`, `LAD` | Kashmir, Ladakh | Defer to Indian/Himalayan pass | Boundary countries | Mixed | Strong | No | Kashmir was not yet in the 1836 Sikh position on Jan. 1, 1816. |

## Central Asian Khanates

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Emirate/Khanate of Bukhara | `BUK` | Bukkhara | Reuse vanilla tag, relocalize to Bukhara/Emirate of Bukhara if desired | Playable sovereign/unrecognized | None | Strong | No | Strong reuse candidate; name should probably be cleaned up from vanilla "Bukkhara". |
| Khanate of Khiva | `KHI` | Khiva | Reuse vanilla tag | Playable sovereign/unrecognized | None | Strong | Yes | Strong reuse candidate. |
| Khanate of Kokand | `KOK` | Kokand | Reuse vanilla tag | Playable sovereign/unrecognized | None | Strong | Yes | Strong reuse candidate. |
| Turkmen tribal regions | `TRM` | Turkmenia | Keep decentralized | Decentralized / non-state polity | None | Strong | Yes | Vanilla decentralized treatment is a good first-pass fit. |
| Later modern national tags | `UZB`, `KYR`, `TJI`, `TRC` | Uzbekistan, Kyrgyzstan, Tajikistan, Turkmenistan | Releasable/formable only | Not present | N/A | Strong | Yes | Do not use as 1816 start countries. |

## Kazakh Steppe And Russian Frontier

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Junior/Kishi Zhuz | `KZH` | Kishi Zhuz | Reuse vanilla tag | Playable Russian protectorate or heavily influenced polity | `RUS` protectorate candidate | Strong | No | Russian influence is historically plausible; avoid direct annexation of interior steppe. |
| Middle/Orta Zhuz | `OZH` | Orta Zhuz | Reuse vanilla tag | Playable Russian protectorate or influenced polity | `RUS` protectorate candidate | Strong | No | Similar to `KZH`, but exact liberty/direct-control balance needs approval. |
| Senior/Uly Zhuz | `UZH` | Uly Zhuz | Reuse vanilla tag | Playable more autonomous Kazakh polity | Russian/Qing/Kokand frontier influence | Medium | No | Recommended: do not treat as equally controlled by Russia if we can avoid it. |
| Unified Kazakh state | `KAZ` | Kazakh | Start absent / formable only | Not present | N/A | Strong | Yes | Keep for later unification/formable content. |
| Russian frontier line | `RUS` | Russia | Backdate direct ownership where necessary | Direct ownership only in frontier/fort-line zones | N/A | Medium | No | Keep Russia present on the frontier without swallowing the steppe. |
| Qing Xinjiang frontier | `CHI` boundary | China/Qing | Defer to East Asia pass unless border cleanup is needed | Boundary empire | N/A | Strong | No | Qing control in Xinjiang can remain broadly vanilla until the East Asia pass. |

## Batch Questions For Approval

These design calls were approved as a batch.

1. Scope: treat this as the Afghanistan/Central Asia/Baluchistan pass, while deferring full `PAN`, `SIN`, `KAS`, `LAD`, `BIC`, and Indian princely-state work to the Indian subcontinent pass? Recommended: yes.
2. Afghanistan: use a fragmented playable Afghan setup with `KAB`, `KAN`, `HER`, `KUN`, `MAI`, and `KAF`, while keeping `AFG` as a reunification/formable tag rather than a start country? Recommended: yes, because it matches the political reality better than one clean unified Afghanistan and uses strong vanilla support.
3. Kafiristan: keep `KAF` playable in the first pass rather than converting it to decentralized? Recommended: yes, because vanilla already supports it and it adds a distinct mountain start.
4. Sikh frontier: backdate later Sikh gains on the Afghan frontier, especially around Peshawar/Kashmir, but leave the full Sikh/Sindh/Kashmir design to the India pass? Recommended: yes.
5. Kalat/Makran: use `KAL` as playable sovereign Kalat and keep `MAK` as a playable or semi-playable Kalat subject if map support is clean? Recommended: yes.
6. Central Asian khanates: approve strong reuse for `BUK`, `KHI`, and `KOK`, with `BUK` relocalized to a cleaner Bukhara/Emirate of Bukhara display if needed? Recommended: yes.
7. Turkmen regions: keep `TRM` decentralized rather than making it a playable centralized country? Recommended: yes.
8. Kazakh hordes: reuse `KZH`, `OZH`, and `UZH` as playable Kazakh polities, with Russian protectorate-style influence strongest over `KZH`/`OZH` and `UZH` kept more autonomous if technically workable? Recommended: yes.
9. Russia/Qing frontier: avoid major custom tags and mostly adjust ownership/relationships using vanilla `RUS`, `CHI`, and Central Asian tags? Recommended: yes.
10. New tags: create no new `V**` tags for this pass unless later map review uncovers a missing polity that is both important and representable? Recommended: yes.
