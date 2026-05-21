# Americas Follow-Up: Date, Old Southwest, Brazil, and Chile

This pass responds to the in-game map review after population scaling.

Implemented changes:

- Moved the define override from `00_cow_1816_defines.txt` to `99_cow_1816_defines.txt` so it loads after vanilla `00_defines.txt`.
- Set `START_DATE = "1816.1.1"`, `END_DATE = "1936.1.1"`, and `DEFAULT_LAW_ACTIVATION_DATE = "1816.1.1"`.
- Removed Cherokee, Choctaw, Chickasaw, and Muscogee start-map land ownership from Tennessee, Mississippi, Alabama, and Georgia. These tags remain defined/reusable for later release or event work.
- Restored those Old Southwest provinces to direct `USA` ownership while preserving Native homelands for future release/flavor support.
- Made `BRZ` active as the Kingdom of Brazil, owning the Portuguese Brazil portions previously assigned directly to `POR`.
- Added a `POR -> BRZ` personal union to represent the United Kingdom of Portugal, Brazil and the Algarves.
- Made `CHL` active as the Captaincy General of Chile under Spain instead of folding Chile into `SC3` Royalist Peru.
- Added a `SPA -> CHL` colony pact and light 1816 colonial country history for Chile.

Historical interpretation notes:

- Guayaquil is not free on `1816.1.1`; the Free Province of Guayaquil is a later 1820 development.
- Venezuela is not modeled as a free start country on `1816.1.1`; the stable playable successor/revolutionary setup should be handled later through events, claims, or release mechanics if desired.
- Chile is separate from Peru, but not independent at this date; the implemented compromise is a Spanish colonial subject called the Captaincy General of Chile.

Validation:

- No start ownership or pop buckets remain for `V08`, `V09`, `CHE`, or `MSC`.
- No pop-owner mismatches.
- No zero/negative pop sizes.
- Mod text brace depth is clean.
