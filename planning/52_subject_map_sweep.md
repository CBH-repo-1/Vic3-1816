# Subject Map Sweep

This pass checks whether the scripted 1816 subject map can actually resolve in Victoria 3's subject system.

## Scope

- Every `create_diplomatic_pact` in `common/history/diplomacy`.
- Active start-map landholders from `common/history/states/00_states.txt`.
- Subject type country-type rules from base `common/subject_types/00_subject_types.txt`.
- Country types from base-plus-mod `common/country_definitions`, with start-history `set_country_type` overrides applied.

## Result

The sweep found one technical mismatch:

- `BIC -> TIP` was scripted as a `protectorate`.
- `TIP` was still defined as `decentralized`.
- Base `subject_type_protectorate` allows subject country types `recognized` and `unrecognized`, but not `decentralized`.

This was a technical bug because the earlier India pass had already approved the `BIC -> TIP` protectorate.

## Implemented Fix

Changed `TIP` / Tipperah in `common/country_definitions/00_countries.txt`:

- From `country_type = decentralized`
- To `country_type = unrecognized`

This keeps Tipperah as a small local landholder while allowing the approved Company protectorate relationship to appear correctly on the subject map.

## Validation

After the fix:

- Created pact count: 82.
- Diplomacy brace failures: 0.
- Bad subject-map pacts: 0.
- Duplicate created pacts: 0.
- Country-history brace failures: 0.
- Bad law references: 0.
- Bad interest-group references: 0.
- `git diff --check`: no whitespace errors, only existing CRLF normalization warnings.

## Deferred

The sweep did not make new historical subject design choices. These still need approval in later passes:

- Whether `MBS` should be under Oman.
- Whether additional DEI outer-island subjects should be explicitly restored.
- Whether remaining Indian princely minors should receive softer BIC relationships.
- How to model Krakow's joint protection without a single overlord.
