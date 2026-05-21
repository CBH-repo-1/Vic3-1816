# Starting Technology Tier Pass

This pass adjusts the highest generic starting technology tier for the 1816 start.

Implemented:

- Added `common/scripted_effects/99_cow_1816_starting_inventions.txt`.
- Replaced the generic `effect_starting_technology_tier_1_tech` bundle with only `add_era_researched = era_1`.
- This removes the vanilla 1836 tier 1 era 2 bonuses from all generic tier 1 starts:
  - `railways`
  - `intensive_agriculture`
  - `mechanical_tools`
  - `atmospheric_engine`
  - `screw_frigate`
  - `general_staff`
  - `percussion_cap`
  - `power_of_the_purse`
  - `dialectics`
  - `central_archives`
  - `central_banking`
  - `egalitarianism`
  - `corporate_charters`
- Replaced the generic `effect_starting_technology_tier_2_tech` bundle with an advanced partial era 1 package:
  - Starts from the vanilla tier 3 recognized-country package.
  - Adds `napoleonic_warfare`, `banking`, and `empiricism`.
  - Removes all vanilla tier 2 era 2 freebies: `mechanical_tools`, `atmospheric_engine`, `dialectics`, `egalitarianism`, and `corporate_charters`.
  - Leaves edge era 1 techs such as `lathe`, `paddle_steamer`, `stock_exchange`, and `mass_communication` for tier 1 countries.

Design note:

- `atmospheric_engine` should not be part of generic tier 1 in 1816.
- When the country-specific pre-researched technology pass begins, give `atmospheric_engine` to Britain if we want to represent its exceptional steam-engine lead.
- Tier 1 and tier 2 should remain meaningfully different:
  - Tier 1: full era 1 and ready to pursue era 2 immediately.
  - Tier 2: advanced 1816 states, but still missing the highest-edge industrial, naval, commercial, and communications technologies.
