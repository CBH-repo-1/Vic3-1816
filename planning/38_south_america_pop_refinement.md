# South America Population Refinement

This pass implements the approved South America population-composition refinement after the broader 1816 scaling pass.

## Implemented Changes

- Kept the existing approved owner totals unchanged.
- Added `law_colonial_slavery` to `SC2` and `SC3`, since both Spanish colonial subjects already contained enslaved pops.
- Added `law_legacy_slavery` to `CHL`, matching the 1816-1823 transitional Chilean slavery setup.
- Added `law_colonial_slavery` to `GBR`, since Britain still had colonial slavery in 1816 despite the earlier abolition of the British slave trade.
- Converted the Guiana plantation-colony Afro-Caribbean/Afro-Antillean populations into enslaved/free splits:
  - British Guiana: 92,000 enslaved Afro-Caribbean pops.
  - Dutch Guiana/Suriname: 48,000 enslaved Afro-Caribbean pops.
  - French Guiana: 12,251 enslaved and 2,149 free Afro-Antillean pops.
- Adjusted Santiago so Chile has 3,500 enslaved Afro-Chilean pops while preserving the total `CHL` population.

## Validation Targets

- `BRZ`, `ARG`, `PRG`, `URU`, `SC2`, and combined `SC3 + CHL` should remain on their approved 1816 targets.
- `STATE_GUAYANA` and `STATE_SANTIAGO` totals should be unchanged from the pre-refinement file.
- No owner/pop alignment changes were made.

## Source Backbone

- UK National Archives guidance on British slave registers and the continued existence of slavery before 1833 abolition.
- British Guiana slave-register scholarship citing Demerara/Essequibo enslaved population figures around 1817.
- Dutch National Archives Suriname slave-register documentation.
- Chilean National Archive summary of the 1811 free-womb law and 1823 abolition, including the estimated enslaved population at abolition.
