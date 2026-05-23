# Worldwide Focused Claims Pass

This pass reviews the active claim layer after the subject-map sweep.

## Scope

- Current effective claims in `common/history/states/00_states.txt`.
- Comparison against vanilla claim inheritance and earlier 1816 ownership decisions.
- Focused cleanup only. Broad political claim policy is left for approval.

## Starting Audit

Before this pass:

- Effective claim entries: 79.
- Claims on states where the claimant already owns part or all of the state: 50.
- Claims on states where the claimant owns no starting province: 29.

Most active claims are either inherited vanilla pressure claims, owner/split-state claims, or claims intentionally introduced by earlier 1816 map decisions.

## Implemented Cleanup

Removed six high-confidence stale claims:

- Removed Sweden's five inherited Finland claims:
  - `STATE_UUSIMAA`
  - `STATE_ALAND`
  - `STATE_WEST_KARELIA`
  - `STATE_OSTROBOTHNIA`
  - `STATE_OULU`
- Removed Chile's inherited `STATE_ANTOFAGASTA` claim.

## Rationale

- Sweden ceded Finland to Russia in 1809. By the 1816 start, a blanket Swedish claim over Finland is a 1836 gameplay/revanchist inheritance rather than a clean Congress-era claim.
- Chile is a Spanish colonial subject in this start, not the later independent Chilean state contesting Antofagasta. The Antofagasta claim is therefore better saved for later Chile/Bolivia/Peru event or journal content.

## Approved Design-Cluster Cleanup

After review, the following broader political claims were also removed:

- Removed `ARG` and `CHL` claims from `STATE_PATAGONIA`.
- Removed `ARG` claim from `STATE_ARAUCANIA`, while keeping the remaining Chilean claim.
- Removed `GRE` claims from `STATE_IONIAN_ISLANDS` and `STATE_THESSALIA`.
- Removed `SER` claim from `STATE_DELVIDEK`.
- Removed `MOR` claim from `STATE_WEST_SAHARA`.

These claims are better handled by later unification, independence, or frontier content than by giving every future nationalist ambition a start-date claim in 1816.

## Result

After the first cleanup:

- Effective claim entries: 73.
- Claims on states where the claimant already owns part or all of the state: 50.
- Claims on states where the claimant owns no starting province: 23.
- `SWE` effective claims: 0.
- `CHL` claim on `STATE_ANTOFAGASTA`: 0.
- State-history brace depth: 0.

After the approved design-cluster cleanup:

- Effective claim entries: 66.
- `ARG` effective claims remain on `STATE_BUENOS_AIRES`, `STATE_RIO_NEGRO`, and `STATE_JUJUY`.
- `CHL` effective claims remain on `STATE_ARAUCANIA`.
- `SER` effective claims remain on `STATE_WESTERN_SERBIA` and `STATE_EASTERN_SERBIA`.
- `MOR` effective claims remain on `STATE_INNER_MOROCCO`.
- `GRE` effective claims: 0.
- State-history brace depth: 0.

## Remaining Deferred Claims

These were not changed because they shape the intended politics of the start:

- USA western/frontier claims on the Plains and upper frontier:
  - Previously approved when the USA was pulled back from direct ownership.
  - Keep unless we decide playable `COM`/`LKT` need more protection from early American pressure.
- Moldavian claims:
  - Useful for Balkan nationalist pressure, but should be tuned with future Ottoman/Balkan event design.
- Persia/Russia/Caucasus claims:
  - Historically plausible tension after Gulistan, but should be handled in a focused Caucasus pass.
- Morocco, Tripoli/Fezzan, South Africa, HBC, ALK, and company/colonial claims:
  - Mostly represent frontier or charter pressure; leave until the matching colonial/frontier journal work.
- Mindanao claims by `PHI`, `MGD`, and `SUL`:
  - Leave until a Philippines/Sulu/Maguindanao-specific pass.

## Next Recommendation

If the claims map looks sane in-game, the next gameplay layer should be either:

- targeted claim-policy decisions for the deferred clusters above, or
- institutions/literacy/education/administration cleanup for playable countries.
