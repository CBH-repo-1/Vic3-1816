# Interest Group Flavor Pass

Status: implemented.

## Scope

This pass follows the worldwide structural interest-group sweep. The goal is to improve high-visibility flavor without rewriting every country's politics.

Changes are limited to:

- reusing existing Victoria 3 interest-group display names where they clearly fit the 1816 start;
- adding one small custom display name for council-style Indigenous starts;
- changing German free-city ruling elites from landed aristocrats to urban burgher politics.

## Implemented Changes

### East Asia

- `CHI`: `ig_landowners` now displays as `ig_scholar_officials`.
- `KOR`: `ig_landowners` now displays as `ig_yangban`.

### Romanian Principalities

- `MOL`: `ig_landowners` now displays as `ig_boyars`.
- `WAL`: `ig_landowners` now displays as `ig_boyars`.

### German Free Cities

Changed the ruling IG from `ig_landowners` to `ig_petty_bourgeoisie`, with the existing German display name `ig_kleinburger`:

- `BRE`
- `FRM`
- `HAM`
- `LUB`

This better matches the free-city merchant/burgher political base without touching laws, subjects, or state ownership.

### Native Council Starts

Added `ig_cow_1816_council_elders` and applied it to the rural-folk ruling IG for:

- `COM`
- `LKT`
- `TIP`

This keeps their gameplay on the stable `ig_rural_folk` base while making the visible government flavor fit the council setup.

### India And Company Rule

Applied existing India flavor names to the most visible 1816 India starts:

- `BIC`:
  - `ig_industrialists` displays as `ig_east_india_company`.
  - `ig_armed_forces` displays as `ig_presidency_armies`.
- `AWA`, `BER`, `GWA`, `HYD`, `IND`, `KAS`, `MUG`, `NAG`, `SAT`, `SIN`, and `V10`:
  - `ig_landowners` displays as `ig_zamindars`.

## Validation

After this pass:

- Missing `set_interest_group_name` localization keys: 0.
- Country-history brace failures: 0.
- Malformed country-history start blocks: 0.
- Active non-decentralized countries without a ruling IG: 0.
- Duplicate active country-history tags: 0.
- Bad law references: 0.
- Bad `ig:` references: 0.

## Deferred

Potential later flavor work:

- Custom company names for `HBC`, `ALK`, `DEI`, and selected colonial administrations.
- More precise ruling-IG mixes for major non-European monarchies.
- Wider India minor-prince pass if we want every small state to use regional IG names.
