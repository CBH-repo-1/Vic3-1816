# MENA, Central Asia, And Asia Map Implementation Notes

This file tracks the first approved ownership/diplomacy backdate after the Africa cleanup.

## Middle East And North Africa

Implemented in `common/history/states/99_cow_1816_mena_states.txt`:

| State | 1836 vanilla setup | 1816 mod setup |
| --- | --- | --- |
| `STATE_ORAN` | `MAS` plus small French ownership | `ALD` |
| `STATE_ALGIERS` | `MAS` plus small French ownership | `ALD` |
| `STATE_CONSTANTINE` | `CON`, small French ownership, and `AIT` | `ALD` plus existing `AIT` |
| `STATE_HAIL` | `JAB` and `NEJ` split | `NEJ` |
| `STATE_TRANSJORDAN` | `EGY` | `TUR` |
| `STATE_PALESTINE` | `EGY` | `TUR` |
| `STATE_LEBANON` | `EGY` | `TUR` |
| `STATE_SYRIA` | `EGY` | `TUR` |
| `STATE_ALEPPO` | `EGY` | `TUR` |
| `STATE_BASRA` | `TUR` | `V06` Kuwait in the vanilla Kuwait port province, rest `TUR` |
| `STATE_ARMENIA` | `RUS` | `PER` |
| `STATE_KARS` | `TUR` and `RUS` split | `TUR` |

Implemented in `common/history/diplomacy/99_cow_1816_mena_subjects.txt`:

- Add `TUR -> ALD` protectorate to represent nominal Ottoman suzerainty over the Regency of Algiers.
- Replace `TUR -> TRI` puppet with `TUR -> TRI` protectorate.
- Add `TRI -> FZN` tributary.
- Remove the premature vanilla `GBR -> ABU` protectorate.

## Central Asia And Afghanistan

Implemented in `common/history/states/99_cow_1816_central_asia_states.txt`:

- `STATE_PASHTUNISTAN`: Peshawar/frontier provinces held by vanilla `PAN` are returned to `KAB`.

Implemented in `common/history/diplomacy/99_cow_1816_central_asia_subjects.txt`:

- Remove `RUS -> UZH` protectorate so Senior Zhuz starts more autonomous.
- Remove `PAN -> KAS` vassal because Kashmir was not yet Sikh-held in 1816.

## Rest Of Asia

Implemented in `common/history/states/99_cow_1816_asia_states.txt`:

| State | 1836 vanilla setup | 1816 mod setup |
| --- | --- | --- |
| `STATE_ARAKAN` | British India and `KKI` | `BUR` and `KKI` |
| `STATE_TENASSERIM` | British India and Siam | Burma and Siam |
| `STATE_PEGU` | Burma, British India, and Denmark | Burma and Denmark |
| `STATE_LAOS` | Luang Prabang, Siam, Champassak, Dai Nam, and `SCT` | Luang Prabang, Vientiane, Champassak, Dai Nam, and `SCT` |
| `STATE_RYUKYU_ISLANDS` | Japan | `V07` Ryukyu |

Implemented in `common/history/diplomacy/99_cow_1816_asia_subjects.txt`:

- Add `JAP -> V07` tributary.
- Add `SIA -> VIE` tributary.

`VIE` now has a basic country history entry in `common/history/countries/00_cow_1816_custom_countries.txt`.

## India First Pass

Implemented in `common/history/states/99_cow_1816_india_states.txt`:

| State | 1836 vanilla setup | 1816 mod setup |
| --- | --- | --- |
| `STATE_PUNJAB` | `PAN` and `BHW` | `PAN`, `BHW`, and playable `V10` Multan |
| `STATE_ASSAM` | Direct `BIC` plus local holders | Direct `BIC` removed; `ASM` and `MNP` restored around their hubs |
| `STATE_GUJARAT` | Direct `BIC` Ahmedabad block; `JUN` owns Surat port province | Ahmedabad block moved to `BER`; Surat port province moved to `BIC` |
| `STATE_RAJPUTANA` | Company-owned Ajmer province | Ajmer returned to `GWA` |
| `STATE_BOMBAY` | Company-owned Poona/Pune province | Poona/Pune returned to `SAT` as the relocalized Peshwa core |
| `STATE_CENTRAL_PROVINCES` | Company Saugor/Nerbudda strip plus `NAG`, `HYD`, and `BAS` | Direct Company ownership removed; western/northern provinces moved to `SAT`, eastern/southern provinces moved to `NAG` |

Implemented in `common/history/diplomacy/99_cow_1816_india_subjects.txt`:

- Remove `BIC -> NAG`, `BIC -> IND`, and `BIC -> GWA` puppet pacts so Nagpur, Indore, and Gwalior start outside hard Company subjection.
- Replace `BIC -> SAT` and `BIC -> BER` puppet pacts with protectorates, representing strong British influence over the Peshwa and Baroda without using the 1836 puppet setup.
- Remove premature `BIC -> BAS` puppet pact and add `NAG -> BAS` tributary.
- Remove premature `BIC` puppet pacts for `BHO`, `MEW`, `JAI`, `JOD`, `BIK`, `JAS`, and `KOT`, while keeping earlier British influence over `ALW` and `PTA`.
- Add `KAB -> KAS` and `KAB -> V10` tributaries.
- Remove premature `BIC -> ASM` and `BIC -> MNP` puppet pacts; add `BIC -> TIP` protectorate.
- Downgrade Gujarat/Kathiawar minors from hard `BIC` puppets to lighter protectorates.

## Deferred

- Dagestan/Caucasus local autonomy remains deferred; Armenia has been restored to Persia, while Azerbaijan/Elizavetpol/Greater Caucasus remain Russian after Gulistan.
- India map ownership is now ready for the later pops/buildings/laws/claims passes, pending in-game visual review.
- Dutch East Indies, China, Korea, Japan, Ceylon, and most Central Asian khanates are mostly acceptable vanilla starts for now, aside from the changes above.
