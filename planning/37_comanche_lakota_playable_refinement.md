# Comanche And Lakota Playability Refinement

Implemented after the user approved making Comancheria and Lakota playable Indigenous powers in North America.

## Scope

Affected files:

- `mod/Congress of Vienna 1816/common/history/pops/05_north_america.txt`
- `mod/Congress of Vienna 1816/common/history/countries/99_cow_1816_north_america_countries.txt`

## Comanche Population Cleanup

The earlier `COM` setup made Comancheria playable in concept but left an anachronistic Oklahoma-heavy population bucket, including a large Cherokee population and enslaved Afro-American pop that fit later Indian Territory more than 1816 Comancheria.

Implemented `STATE_OKLAHOMA` changes under `region_state:COM`:

| Pop | Previous | New |
| --- | ---: | ---: |
| Siouan | 20,000 total across two blocks | 10,000 total across two blocks |
| Afro-American slaves | 1,200 | 0 |
| Caddoan | 8,000 | 10,000 |
| Cherokee | 50,800 | 3,000 |
| Comanche | 0 | 12,000 |
| Apache | 0 | 3,000 |

Oklahoma `COM` population changed from `80,000` to `38,000`.

Overall `COM` population changed from `117,126` to `75,126`.

This keeps Comancheria stronger than small tags such as `PWN`, `APC`, and `NVJ`, but below `LKT`, which remains at `106,000`.

## Lakota Playability

`LKT` now receives a late `set_country_type = unrecognized` override in `99_cow_1816_north_america_countries.txt`.

This mirrors the existing `COM` setup: the base country definition can remain vanilla/decentralized long enough for native setup effects to run, then the late 1816 history file promotes the country into a selectable unrecognized polity.

## Validation

- `COM` now has `75,126` total population and `0` enslaved pops.
- `LKT` remains at `106,000` total population.
- `COM` and `LKT` are both explicitly promoted to `unrecognized` in late North America country history.
- Edited files have balanced brace counts.
- No zero or negative pop sizes were introduced.
- `git diff --check` reports no whitespace errors.
