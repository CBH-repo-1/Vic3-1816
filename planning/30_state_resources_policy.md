# State Resources Policy

## Approved Decision

State-region resource potentials should remain the vanilla Victoria 3 values for the 1816 start, including gold, oil, rubber, mines, logging, fishing, whaling, arable land, and arable resource options.

This is intentional. The mod will treat vanilla state resources as physical or ecological potential, while 1816 economic reality is handled through starting buildings, production methods, country technology, laws, and later event/journal content.

## Rationale

- Victoria 3 already gates several sensitive resources through technology and discovery mechanics.
- Oil and rubber use discoverable-resource systems and are locked behind later production technologies.
- Gold fields are discoverable and can create alternate-history early rushes, but the user approved keeping the vanilla physical potential because it is balanced enough for gameplay.
- Most non-discoverable resources represent long-term extractive potential rather than 1816 active output.
- Avoiding state-region overrides keeps the mod lighter and reduces future maintenance risk when the base game changes.

## Implementation Notes

- Do not copy `game/map_data/state_regions` into the mod just to backdate resources.
- If a future pass finds a truly broken resource case, override only the affected state-region file and document the exception here.
- Starting availability and actual economic footprint should be adjusted through:
  - `common/history/buildings`
  - starting production methods
  - country starting technologies
  - laws and institutions
  - later events, journals, or decisions

## Audit Snapshot

Vanilla state-resource audit found:

- 673 state regions across 16 non-sea state-region files.
- No current mod override under `mod/Congress of Vienna 1816/map_data/state_regions`.
- Discoverable resources in vanilla:
  - `building_oil_rig`: 147 states.
  - `building_rubber_plantation`: 123 states.
  - `building_gold_field`: 46 states.

The approved outcome is no game-facing file change for this pass.
