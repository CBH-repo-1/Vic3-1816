# Flags and Coat of Arms Pass

## Implemented first batch

- France now sets `legitimist_restoration_var` at start, allowing the base game Bourbon Restoration flag definition to display.
- Custom tag coat-of-arms placeholders were improved for `V00` through `V10` using existing Vic3 emblem assets:
  - `V00` Liechtenstein: cleaner blue/red bicolor.
  - `V01` San Marino: white/light-blue bicolor with three tower approximation.
  - `V02` Monaco: retained red/white bicolor.
  - `V03` Andorra: blue/yellow/red tricolor approximation with centered Iberian shield.
  - `V04` Saxe-Gotha-Altenburg and `V05` Saxe-Hildburghausen: Saxon shield over green/white bases.
  - `V06` Kuwait: retained red field with white hoist element.
  - `V07` Ryukyu: refined white/red roundel with gold frame.
  - `V08` Choctaw and `V09` Chickasaw: simple abstract star treatments; these are gameplay placeholders because no strong 1816 national flag convention is represented by base assets.
  - `V10` Multan: green crescent-and-star treatment.

## Historical notes used

- The base game already includes `FRA_bourbon`, a white Bourbon Restoration flag with gold fleur-de-lis, but it only triggers for a monarchy with `legitimist_restoration_var`.
- The base game already has Portugal / United Kingdom of Portugal, Brazil and the Algarves flag logic through `POR_uk`.
- The base East India Company and Hudson's Bay Company flags already include company-style variants; these should be checked in-game before overriding them.

## Deferred decisions

- United States: the historically correct 1816 flag is the 15-star, 15-stripe flag, but the base dynamic USA flag system starts at 24 stars for state counts below 25. A proper fix likely means overriding or replacing the base `01_flag_definitions_usa.txt`, which is higher-risk than a small COA file.
- Brazil: the base personal-union trigger still points Brazil to the 1822 imperial-style Brazilian COA. A better United Kingdom of Portugal, Brazil and the Algarves treatment probably needs a custom `BRZ_1816` flag definition, which has the same duplicate/override risk as USA.
- Choctaw and Chickasaw: current designs are abstract gameplay placeholders unless we decide to create modern-inspired or non-historical national flags for them.
- More exact arms for the German microstates would require either deeper heraldry scripting or custom image assets.
