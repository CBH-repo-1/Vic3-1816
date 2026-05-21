# Population Scaling Plan

## Approved Method Priority

Use the user's approved hierarchy for 1816 population work:

1. Use an 1816 historical population for the country if the borders are the same.
2. Reconstruct 1816 population by state or map provinces and add them together.
3. Scale down 1836 population on a state-by-state level from a reliable country total.
4. Use a good historical estimate.
5. Use a gameplay-balance estimate.
6. Avoid random guessing unless there is no better option.

## Implementation Rule

Scaling should preserve the existing pop composition inside the affected owner bucket unless a later culture/religion/profession pass explicitly changes it.

For a target owner or region group:

- Compute current total from `common/history/pops`.
- Compute target 1816 total from the best available method above.
- Apply a uniform multiplier to each affected `create_pop` size.
- Preserve exact target totals through integer rounding.
- Document the source/method used for each target.

## First High-Confidence Scaling Batch

Implemented after approval.

| Scope | Current scripted total | Proposed 1816 target | Method | Notes |
| --- | ---: | ---: | --- | --- |
| `USA` direct-owned states after frontier cleanup | 15,235,177 | 8,679,024 | Method 3 | Interpolated between official US 1810 and 1820 census totals, then scaled all remaining `USA` pop buckets. |
| Brazil-facing `POR` state regions | 4,600,097 | 4,396,132 | Method 2/4 | Uses the early Brazil estimate recorded by IBGE. |
| Portugal homeland `POR` state regions | 3,877,892 | 3,000,000 | Method 1/4 | Portugal proper was scaled to the approved rounded early-1800s estimate. |
| `SC1` New Spain | 6,998,585 | 6,122,300 | Method 1/4 | Uses the 1810 New Spain estimate. |

## Design Warning

The user's in-game observation that Portugal has too few pops may conflict with historical scaling. In the current scripts, `POR` has about 10.72 million pops total:

- Brazil-facing `POR` regions: about 4.60 million.
- Portugal homeland and islands: about 3.88 million.
- Other overseas holdings: about 2.24 million.

Following historical 1816 scaling would likely lower Portugal proper and slightly lower Brazil, while leaving overseas colonial population for a later regional pass unless separately researched.

After the first scaling batch, current totals are:

- `USA`: 8,679,024.
- `SC1`: 6,122,300.
- Brazil-facing `POR` regions: 4,396,132.
- Portugal homeland `POR` regions: 3,000,000.
- Total `POR`: 9,638,958, including other overseas holdings not yet scaled.

## Sources Used For First Batch

- United States 1810 and 1820 census totals: US Census Bureau.
- Brazil early estimate: IBGE census history.
- New Spain 1810 estimate: Memoria Politica de Mexico population table.
- Portugal homeland estimate: early-1800s Portugal population table, rounded to the approved target.

## Deferred

- Fine-grained state-by-state corrections where better local census or gazetteer data is later found.
- Culture/religion/profession changes.
- Literacy and wealth changes beyond existing country-population effects.

## Europe Source-Backed Scaling Batch

Implemented after the user's standing approval for all population-scaling targets.

| Scope | Pre-scaling scripted total | Implemented 1816 target | Method | Notes |
| --- | ---: | ---: | --- | --- |
| France homeland `FRA` regions | 30,200,222 | 29,992,333 | Method 1/3 | European France only, including Corsica; colonies left for later colonial pass. |
| England and Wales `GBR` regions | 14,162,200 | 11,082,000 | Method 1/3 | Scaled from British Isles census-era estimates. |
| Scotland `GBR` regions | 2,389,166 | 1,949,000 | Method 1/3 | Scaled separately from England/Wales. |
| Ireland `GBR` regions | 8,024,356 | 6,460,500 | Method 1/3 | Scaled separately because Ireland's growth path differs from Great Britain. |
| Congress Poland `POL` | 4,895,999 | 2,600,000 | Method 1/3 | Uses 1815 Russian Poland estimate; large change because the vanilla-state approximation is broad. |
| Sweden `SWE` | 2,797,184 | 2,489,000 | Method 1/3 | Interpolated from early-19th-century Sweden estimates. |
| Norway `NOR` | 1,236,860 | 901,600 | Method 1/3 | Early-19th-century Norway estimate. |
| Netherlands plus Belgian provinces under `NET` | 6,788,223 | 6,213,000 | Method 1/3 | Combined Netherlands and Belgian provinces under the 1816 United Kingdom of the Netherlands setup. |
| Spain homeland `SPA` regions | 12,572,371 | 12,386,913 | Method 1/3 | Homeland Spain only; excludes Florida and Al Rif. |
| Italian states aggregate (`SIC`, `SAR`, `PAP`, `TUS`, `LOM`, `MOD`, `PAR`, `LUC`) | 20,351,612 | 18,381,000 | Method 1/3 | Aggregate Italian peninsula/islands target, preserving individual existing state composition. |
| Finland `FIN` | 1,444,214 | 1,112,400 | Method 1/3 | Scaled from early-19th-century Finland estimate under Russia. |
| Denmark homeland `DEN` regions | 1,205,704 | 1,052,000 | Method 1/3 | Homeland Jutland and Zealand only. |

Source backbone for this batch: Mitchell's International Historical Statistics as summarized in the Napoleon Series national population estimates table.

Validation after this batch:

- All listed targets match exactly.
- No zero or negative pop sizes were introduced.
- Pop history brace depth is clean.

## Global Source-Backed Scaling Batch

Implemented after the user's standing approval for all population-scaling targets.

This batch copied three previously un-overridden vanilla pop files into the mod so population scaling is now explicit there too:

- `02_east_europe.txt`
- `12_indonesia.txt`
- `14_siberia.txt`

Large regional and country targets:

| Scope | Pre-scaling scripted total | Implemented target | Method | Notes |
| --- | ---: | ---: | --- | --- |
| Direct `RUS` population | 50,758,253 | 45,800,000 | Method 3/4 | Interpolated/estimated between 1810 and 1820 Russian Empire benchmarks while keeping Poland and Finland separate. |
| `PRU` | 14,062,517 | 10,349,031 | Method 1 | Uses the 1816 Prussian census-style total. |
| Habsburg non-Italian crown lands (`AUS`, `HUN`, `TRS`, `CRO`) | 29,190,134 | 27,750,000 | Method 3/4 | Keeps Lombardy-Venetia in the Italian aggregate, then scales the remaining Habsburg lands. |
| Direct `TUR` Ottoman lands | 22,207,742 | 18,500,000 | Method 3/4 | Uses Ottoman Europe, Asia, and Syria benchmark totals; Egypt is scaled separately. |
| `EGY` | 4,633,752 | 2,500,000 | Method 3/4 | Uses the Ottoman Egypt benchmark. |
| `PER` | 6,871,373 | 6,600,000 | Method 1/4 | Uses early Qajar/Iran 1820 benchmark estimates. |
| Africa excluding `EGY` | 68,648,078 | 71,708,000 | Method 4 | Uses Maddison 1820 Africa as the nearest broad benchmark, with Egypt handled separately. |
| Indian subcontinent pop file | 166,746,790 | 209,000,000 | Method 4 | Uses Maddison 1820 India benchmark and preserves the scripted 1816 Indian ownership split. |
| `CHI` | 366,405,602 | 381,000,000 | Method 4 | Uses Maddison 1820 China benchmark. |
| `JAP` | 30,773,123 | 31,000,000 | Method 4 | Uses Maddison 1820 Japan benchmark. |
| `KOR` | 16,201,022 | 13,800,000 | Method 4 | Uses Maddison 1820 Korea benchmark. |
| Southeast Asia and Indonesia remainder | 37,254,150 | 38,000,000 | Method 4 | Scales `11_east_asia.txt` and `12_indonesia.txt` excluding China, Japan, and Korea. |
| `NEP` | 4,242,426 | 3,880,000 | Method 4 | Uses an 1820 Nepal estimate close to the post-war 1816 setup. |

Europe, Americas, and colonial/island target details:

| Scope | Pre-scaling scripted total | Implemented target |
| --- | ---: | ---: |
| `BAV` | 4,175,788 | 3,600,000 |
| `HAN` | 1,846,996 | 1,305,000 |
| `WUR` | 1,719,750 | 1,410,000 |
| `SAX` | 1,392,917 | 1,190,000 |
| `BAD` | 1,301,400 | 1,000,000 |
| `SWI` | 1,966,164 | 2,000,000 |
| `HES` | 729,108 | 650,000 |
| `HEK` | 633,288 | 560,000 |
| `MEC` | 493,998 | 389,000 |
| `NAS` | 402,404 | 300,000 |
| `OLD` | 257,696 | 160,000 |
| `WEI` | 233,840 | 109,000 |
| `V04` Saxe-Gotha-Altenburg | 278,583 | 180,000 |
| `V05` Saxe-Hildburghausen | 67,656 | 33,000 |
| `COB` Saxe-Coburg-Saalfeld | 156,537 | 59,000 |
| `MEI` Saxe-Meiningen | 67,656 | 34,000 |
| `ANH` | 196,008 | 120,000 |
| `SCW` Schwarzburg principalities | 111,832 | 101,000 |
| `LIP` | 77,546 | 91,000 |
| `WLD` | 55,447 | 51,000 |
| `HAM` | 150,404 | 119,000 |
| `BRE` | 106,004 | 50,000 |
| `LUB` | 84,396 | 45,000 |
| `HOH` Hohenzollern principalities | 61,334 | 44,000 |
| `FRM` Frankfurt | 112,872 | 50,000 |
| `SC2` New Granada | 3,592,078 | 3,113,000 |
| `SC3` Royalist Peru and Chile | 3,962,010 | 3,697,000 |
| `ARG` Rio de la Plata | 813,812 | 534,000 |
| `PRG` Paraguay | 280,586 | 384,000 |
| `URU` Banda Oriental | 139,866 | 55,000 |
| `GUA` Captaincy General of Guatemala | 1,681,471 | 2,419,000 |
| `CUB` Cuba | 904,778 | 1,331,000 |
| `HAI` Haiti | 858,270 | 1,150,000 |
| `DOM` Spanish Santo Domingo | 131,530 | 242,000 |
| `PCO` Puerto Rico | 294,668 | 645,000 |
| `JAM` Jamaica | 381,636 | 499,000 |
| `HAW` Hawaii | 192,104 | 145,000 |
| `QUE` Lower Canada | 555,200 | 335,000 |
| `ONT` Upper Canada | 410,796 | 95,000 |
| `NVS` Nova Scotia | 201,572 | 90,000 |
| `NBS` New Brunswick | 120,860 | 55,000 |
| `NEW` Newfoundland | 87,976 | 40,000 |

Source backbone for this batch:

- Napoleon Series / Mitchell-style national estimates for European and Ottoman benchmarks.
- Maddison-style 1820 world, Africa, India, China, Japan, Korea, Southeast Asia, and Latin America benchmarks where exact 1816 values are not practical.
- Statistics Canada / Canadian census-era estimates for Upper Canada, Lower Canada, and maritime colonies.
- Latin America 1820 country table for Spanish America and Caribbean targets.

Validation after this batch:

- All previous and new targets match exactly.
- No zero or negative pop sizes were introduced.
- Pop history brace depth is clean.
- Effective global scripted pop total is 1,036,349,636.
