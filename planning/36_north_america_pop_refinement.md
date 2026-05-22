# North America Pop Refinement

Implemented after the user approved the rest-of-North-America pop batch.

## Scope

This pass deliberately touched only direct `USA` population buckets in:

- `mod/Congress of Vienna 1816/common/history/pops/05_north_america.txt`

British North America, Hudson's Bay Company lands, Russian America, New Spain, Guatemala, Miskitia, and Indigenous/local polities were left unchanged in this batch because their totals looked more intentional and less visibly 1830s/frontier-heavy.

## Method

Each `region_state:USA` bucket was scaled to an approximate 1816 state target interpolated 60 percent of the way between the 1810 and 1820 census totals. This matches the earlier USA whole-country scaling convention already used in `planning/24_population_scaling_plan.md`.

The pass preserves each state bucket's internal culture, religion, and enslaved/free composition. This keeps the edit narrowly focused on redistributing population eastward and away from overinflated frontier states.

## Implemented Results

| State region | Previous total | New total |
| --- | ---: | ---: |
| `STATE_NEW_YORK` | 1,265,237 | 1,207,307 |
| `STATE_PENNSYLVANIA` | 854,675 | 953,711 |
| `STATE_VIRGINIA` | 466,443 | 904,796 |
| `STATE_NORTH_CAROLINA` | 421,638 | 605,497 |
| `STATE_MASSACHUSETTS` | 482,671 | 502,788 |
| `STATE_KENTUCKY` | 424,049 | 501,195 |
| `STATE_SOUTH_CAROLINA` | 335,302 | 467,691 |
| `STATE_OHIO` | 765,758 | 441,164 |
| `STATE_MARYLAND` | 204,514 | 396,628 |
| `STATE_TENNESSEE` | 439,858 | 358,379 |
| `STATE_GEORGIA` | 340,990 | 305,567 |
| `STATE_MAINE` | 226,289 | 270,483 |
| `STATE_CONNECTICUT` | 113,494 | 269,926 |
| `STATE_NEW_JERSEY` | 197,784 | 264,770 |
| `STATE_NEW_HAMPSHIRE` | 159,108 | 232,281 |
| `STATE_VERMONT` | 161,130 | 228,616 |
| `STATE_WEST_VIRGINIA` | 118,950 | 124,272 |
| `STATE_LOUISIANA` | 167,873 | 122,667 |
| `STATE_INDIANA` | 377,980 | 98,115 |
| `STATE_ALABAMA` | 342,075 | 89,341 |
| `STATE_RHODE_ISLAND` | 59,713 | 80,608 |
| `STATE_DELAWARE` | 54,987 | 72,719 |
| `STATE_DISTRICT_OF_COLUMBIA` | 69,286 | 69,286 |
| `STATE_MISSISSIPPI` | 260,804 | 57,791 |
| `STATE_MISSOURI` | 209,358 | 47,865 |
| `STATE_ILLINOIS` | 259,998 | 38,039 |
| `STATE_ARKANSAS` | 52,764 | 8,989 |
| `STATE_MICHIGAN` | 86,590 | 7,242 |
| `STATE_WISCONSIN` | 20,510 | 866 |

Total direct `USA` population in the North America pop file changed from `8,939,828` to `8,728,599`.

## Validation

- Edited file brace count is balanced.
- No zero or negative pop sizes were introduced.
- `git diff --check` reports no whitespace errors.

## Source Backbone

- 1810 and 1820 United States census state and territory population totals.
- The 1816 target is an interpolation rather than a separate census.
