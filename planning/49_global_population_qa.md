# Global Population QA Pass

Status: QA complete; no immediate population data fix required.

## Scope

This pass reviewed the complete start-population layer after the regional refinement passes.

Files reviewed:

- All 16 files in `common/history/pops`.
- `common/history/states/00_states.txt`.
- `common/history/countries`.
- `common/country_definitions`.
- Base-game culture, religion, pop type, and scripted-effect definitions for reference validation.

## Structural Checks

Results:

- Pop files checked: 16.
- Pop files without UTF-8 BOM: 0.
- Pop file brace-depth failures: 0.
- `create_pop` blocks checked: 4,443.
- `create_pop` blocks missing culture: 0.
- `create_pop` blocks missing size: 0.
- Nonpositive pop sizes: 0.
- Undefined pop owner tags: 0.
- Undefined state owner tags: 0.
- Undefined cultures: 0.
- Undefined religions: 0.
- Undefined pop types: 0.

Owner/state alignment:

- State owners: 412.
- Pop owners: 412.
- State-owner pairs: 1,069.
- Pop state-owner pairs: 1,069.
- Owned state-region pairs missing pops: 0.
- Pop state-region pairs without matching ownership: 0.
- State owners without any pops: 0.

Country history coverage:

- Start-land country owners missing country history: 0.
- Country-history tags without start land: 1, `UBD`.
- `UBD` is intentionally inactive after the Baltic Governorates were folded into `RUS`.

## Global Population Snapshot

Global scripted start population:

- 1,027,957,737.

Pop file totals:

- `00_west_europe.txt`: 90,258,035.
- `01_south_europe.txt`: 46,366,855.
- `02_east_europe.txt`: 34,760,532.
- `03_north_africa.txt`: 18,177,955.
- `04_subsaharan_africa.txt`: 55,968,777.
- `05_north_america.txt`: 16,837,394.
- `06_central_america.txt`: 4,646,297.
- `07_south_america.txt`: 12,440,465.
- `08_middle_east.txt`: 19,130,216.
- `09_central_asia.txt`: 26,654,154.
- `10_india.txt`: 207,019,914.
- `11_east_asia.txt`: 442,359,659.
- `12_indonesia.txt`: 19,248,988.
- `13_australasia.txt`: 536,229.
- `14_siberia.txt`: 1,855,759.
- `15_russia.txt`: 31,696,508.

Largest owner totals:

- `CHI`: 379,982,929.
- `BIC`: 132,123,571.
- `RUS`: 45,800,000.
- `JAP`: 31,000,000.
- `FRA`: 30,819,174.
- `GBR`: 20,060,980.
- `TUR`: 18,500,000.
- `AUS`: 15,699,013.
- `KOR`: 13,800,000.
- `HYD`: 13,606,199.

Smallest owner totals:

- `NRU`: 1,276.
- `SML`: 10,000.
- `MRN`: 10,000.
- `MZB`: 11,481.
- `SLK`: 12,000.
- `TUA`: 12,535.
- `NTU`: 13,000.
- `BRK`: 13,068.
- `ALK`: 14,028.
- `V03`: 14,902.

These small owner totals are not zero-pop bugs. They are either island/frontier abstractions, tiny playable/local tags, or split-state remnants.

## Slave Pop And Law Consistency

Results:

- Countries with enslaved pops: 202.
- Total enslaved pops: 14,565,383.
- Slave owners missing an effective slavery law: 0.
- Slave owners with `law_slavery_banned`: 0.

The first shallow pass showed six apparent missing-law cases:

- `ASM`, `BAS`, `BHW`, `COO`, `HYD`, and `MLD`.

These are false positives because their country history uses `effect_starting_politics_princely_state`, and that scripted effect activates `law_debt_slavery`.

Largest enslaved-pop owner totals:

- `BIC`: 3,347,703.
- `USA`: 1,277,942.
- `BRZ`: 1,064,708.
- `SOK`: 777,454.
- `HYD`: 585,390.
- `JAM`: 338,000.
- `SUD`: 327,996.
- `GBR`: 292,000.
- `KHI`: 255,444.
- `SC2`: 208,005.

No immediate law/pop consistency edit is recommended.

## Profession Checks

Pop-type totals:

- Default pops: 1,012,709,225.
- Slaves: 14,565,383.
- Aristocrats: 213,308.
- Soldiers: 205,405.
- Laborers: 71,419.
- Bureaucrats: 56,521.
- Shopkeepers: 51,174.
- Clerks: 49,379.
- Officers: 16,084.
- Farmers: 12,077.
- Clergymen: 4,600.
- Capitalists: 3,162.

Specialist-pop sanity result:

- Decentralized countries with non-slave specialist pops: 0.

No immediate profession cleanup is recommended.

## Low-Pop State Scan

Lowest state totals:

- `STATE_WISCONSIN`: 866.
- `STATE_NAURU`: 1,276.
- `STATE_OB`: 5,162.
- `STATE_KAMCHATKA`: 5,234.
- `STATE_KOLA`: 5,474.
- `STATE_TASMANIA`: 7,000.
- `STATE_MICHIGAN`: 7,242.
- `STATE_ARKANSAS`: 8,989.
- `STATE_OKHOTSK`: 10,354.
- `STATE_SURGUT`: 10,518.

No state has 0 population.

These low-pop states are mostly frontier, island, or remote-state abstractions. `STATE_WISCONSIN`, `STATE_MICHIGAN`, and `STATE_ARKANSAS` may deserve later gameplay/map polish, but they are not structural QA failures.

## Non-Pop Structural Note

One state-history oddity was found:

- `STATE_RIGA` has two `create_state` blocks for `RUS`.
- One block is marked as Dvinsk and `unincorporated`.
- The other block is marked as Governorate of Livonia and `incorporated`.

This is not a population alignment bug because the state-owner pair has matching pops. It may still be a map/government representation issue because the same country owns two split chunks inside one state region with different state types.

Recommended later decision:

- Decide whether to merge the two `RUS` create-state blocks into one `STATE_RIGA` block, and if so whether the combined state should be `incorporated` or `unincorporated`.

No change was made during this QA pass because that is a map/government design decision.

## Conclusion

The global population layer is structurally clean after the regional refinements.

No immediate pop data fix is recommended before moving on to the next gameplay layer.
