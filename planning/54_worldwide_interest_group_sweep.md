# Worldwide Interest Group Sweep

Status: implemented.

## Scope

This pass extends the earlier playable-focused government/law/interest-group cleanup to the full active start map.

The goal is structural stability, not a full flavor rewrite:

- Every active landholder should have country history.
- Every active non-decentralized landholder should have an explicit ruling interest group.
- Country-history law and interest-group references should resolve against Victoria 3 1.12.5 plus the mod's custom laws.
- Decentralized/local countries are left alone unless a technical issue requires a change.

## Starting Audit

Before this sweep:

- Active landholders: 412.
- Active landholders missing country history: 0.
- Active non-decentralized landholders without an explicit ruling interest group: 125.
- Active decentralized landholders: 138.
- Active non-decentralized landholders:
  - Colonial: 25.
  - Recognized: 69.
  - Unrecognized: 180.

## Implemented Cleanup

Added explicit ruling interest groups to the 125 active non-decentralized countries that lacked one.

Assignment policy:

- `ig_landowners` for ordinary conservative/traditional monarchies, princely states, and most unrecognized states.
- `ig_armed_forces` for colonial-garrison/company administration cases without another clear ruling group:
  - `ALK`
  - `SIL`
- `ig_devout` for theocratic starts without another ruling group:
  - `CHC`
  - `ZAI`
- `ig_rural_folk` for council-style starts:
  - `COM`
  - `LKT`
  - `TIP`

No new interest-group names or localization keys were added in this pass. That keeps the edit structural and avoids turning this into a flavor/name-design pass.

## Validation

After cleanup:

- Active landholders: 412.
- Active landholders missing country history: 0.
- Active non-decentralized landholders without explicit ruling interest group: 0.
- Duplicate active country-history tags: 0.
- Country-history brace failures: 0.
- Malformed country-history start blocks: 0.
- Bad `activate_law` references: 0.
- Bad `ig:` references: 0.

## Deferred Flavor

A later flavor pass could improve display names for country-specific elites without changing the structural setup:

- Qing `ig_landowners` could use the existing `ig_scholar_officials` name.
- Moldavia and Wallachia could use the existing `ig_boyars` name.
- `COM`, `LKT`, and possibly `TIP` could get a custom elder/council-style display name if we want the Native Council setup to read better in-game.

Those are presentation/design choices, so they were intentionally deferred.

Follow-up: the first focused flavor layer is now implemented in `planning/55_interest_group_flavor_pass.md`.
