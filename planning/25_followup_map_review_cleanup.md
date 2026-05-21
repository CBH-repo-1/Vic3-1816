# Follow-Up Map Review Cleanup

This pass implements the user's post-test feedback about the USA, plus the approved audit cleanup for Dutch East Indies and East India Company ownership.

## Old Southwest

Implemented in `common/history/states/99_cow_1816_z_followup_states.txt` and `common/history/pops/05_north_america.txt`.

| State | Final 1816 setup |
| --- | --- |
| `STATE_TENNESSEE` | `USA`, `CHE`, and `V09` split |
| `STATE_MISSISSIPPI` | Existing `V08`/`V09` split preserved |
| `STATE_ALABAMA` | `MSC`, `V08`, and `V09` split; no direct `USA` ownership |
| `STATE_GEORGIA` | `USA`, `MSC`, and `CHE` split |
| `STATE_FLORIDA` | Existing `SPA`/`SML` split preserved |

Added minimal country and population history for `CHE` and `MSC` in the same style as the existing playable Native starts.

## East India Company

Implemented in `common/history/states/99_cow_1816_z_followup_states.txt` and `common/history/pops/12_indonesia.txt`.

- `STATE_MALAYA`: removed the southern pre-1819 Singapore province from `BIC` and returned it to `JOH`.
- `BIC` keeps a reduced 2-province Malaya hook for the older Penang/Malacca position.
- Removed 1836-style `BIC` claims from:
  - `STATE_ARAKAN`
  - `STATE_ASSAM`
  - `STATE_BALUCHISTAN`
  - `STATE_HILL_PUNJAB`
  - `STATE_KASHMIR`
  - `STATE_PASHTUNISTAN`
  - `STATE_PUNJAB`
  - `STATE_QUETTA`
  - `STATE_SINDH`

## Dutch East Indies

Implemented in `common/history/states/99_cow_1816_z_followup_states.txt` and `common/history/pops/12_indonesia.txt`.

Direct `DEI` ownership is now limited to:

- `STATE_WEST_JAVA`
- `STATE_CENTRAL_JAVA`
- `STATE_EAST_JAVA`
- `STATE_MOLUCCAS`

Outer-island direct ownership was returned to local tags:

- `STATE_ACEH`: `ACE`/`SAK`
- `STATE_NORTH_SUMATRA`: `SAK`/`JMB`
- `STATE_SOUTH_SUMATRA`: `JMB`
- `STATE_WEST_BORNEO`: `LAN`/`STG`/`PON`/`SMB`
- `STATE_EAST_BORNEO`: `BLG`/`BNJ`/`KTI`
- `STATE_CELEBES`: `SLW`/`BTN`/`TID`
- `STATE_SUNDA_ISLANDS`: `BAL`/`POR`

## Validation

- No `MEX` start ownership.
- No unexpected `BIC` or `DEI` claims in the audited states.
- `DEI` effective land ownership only remains in Java and the Moluccas.
- `BIC` Malaya ownership is reduced from 3 provinces to 2.
- No pop-owner mismatches.
- No zero or negative pop sizes.
- Brace depth is clean.
- No uppercase `X` province IDs remain in state history.

## Sources Used

- Mississippi Territory map note from Mississippi State University exhibit.
- Anglo-Dutch Treaty of 1814.
- Britannica summaries for Dutch return in Java/Indonesia and the Straits Settlements.
- Netherlands East Indies 1816 colonial cartography paper.
- World History Encyclopedia summary of the Third Anglo-Maratha War.
