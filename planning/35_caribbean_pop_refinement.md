# Caribbean Pop Refinement

Implemented after the user approved the first pop-refinement batch.

## Scope

This pass focuses on the Caribbean because the earlier global population scaling pass left several plantation colonies with obviously 1836-ish totals or with large Afro-Caribbean populations represented entirely as free pops.

Affected pop history file:

- `mod/Congress of Vienna 1816/common/history/pops/06_central_america.txt`

Affected country history file:

- `mod/Congress of Vienna 1816/common/history/countries/99_cow_1816_caribbean_countries.txt`

## Implemented Targets

| Country/scope | Previous total | New total | New enslaved pops | Notes |
| --- | ---: | ---: | ---: | --- |
| `CUB` Cuba | 1,331,000 | 553,033 | 199,145 | Uses the 1817 Cuba breakdown: 239,830 white, 114,058 free people of color, 199,145 enslaved. Existing three-state distribution and minor European/Chinese diversity were preserved proportionally. |
| `PCO` Puerto Rico | 645,000 | 230,622 | 21,730 | Uses the 1820 Puerto Rico breakdown: 102,432 white, 106,460 free people of color, 21,730 enslaved. |
| `JAM` Jamaica | 499,000 | 397,000 | 338,000 | Converts Jamaica from all-free Afro-Caribbean population to an 1816 plantation-colony split. |
| `BAH` Bahamas | 119,600 | 16,000 | 10,000 | Reduces the overlarge Bahamas population and gives it a majority enslaved population. |
| `STATE_WEST_INDIES` French share | 238,304 | 238,304 | 180,000 | Keeps total but splits Afro-Antillean population into free and enslaved. |
| `STATE_WEST_INDIES` Danish share | 43,988 | 43,988 | 34,000 | Keeps total but splits Afro-Caribbean population into free and enslaved. |
| `STATE_WEST_INDIES` British share | 269,868 | 269,868 | 200,000 | Keeps total but splits Afro-Caribbean population into free and enslaved. |
| `STATE_WEST_INDIES` Dutch share | 20,838 | 20,838 | 10,212 | Restores the existing commented-out Papiamento-speaker slave pop. |

## Law Cleanup

`JAM` and `BAH` now activate `law_legacy_slavery`, matching the new enslaved populations without giving them an independent open slave-trade setup.

Parent countries already had the needed broader colonial slavery laws for their direct West Indies holdings:

- `FRA`
- `DEN`
- `GBR`
- `NET`

## Validation

Post-patch totals:

- `CUB`: 553,033 total, 199,145 enslaved.
- `PCO`: 230,622 total, 21,730 enslaved.
- `JAM`: 397,000 total, 338,000 enslaved.
- `BAH`: 16,000 total, 10,000 enslaved.

`git diff --check` reports no whitespace errors. Brace counts are balanced in both edited files.

## Source Backbone

- Cuba 1817 population table: 553,033 total, 199,145 enslaved.
- Puerto Rico 1820 population table: 230,622 total, 21,730 enslaved.
- British Caribbean slave-register summaries and early-19th-century Bahamas figures for Jamaica, Bahamas, and the West Indies split.
