# Visible Polish Pass

## Approved ruler policy

- Use the de facto active ruler for the visible country ruler when the legal sovereign was incapacitated, absent, or only a formal overlord.
- Do not create heirs who were not born by 1816.1.1.
- Colonial company tags should show the active governor or administrator rather than a later 1836 placeholder.

## Implemented ruler batch

- Great Britain: replaced William IV and unborn Victoria with George, Prince Regent.
- France: replaced Louis-Philippe and Ferdinand-Philippe with Louis XVIII and Louis Antoine.
- United States: replaced Andrew Jackson as ruler with James Madison.
- Russia: replaced Nicholas I and unborn Alexander II with Alexander I and Nicholas as heir.
- Austria: replaced Ferdinand I ruler and unborn Franz Joseph with Francis I and Ferdinand as heir.
- China: replaced Daoguang ruler and unborn Xianfeng with Jiaqing and Daoguang as heir.
- Spain: replaced Maria Cristina regency and unborn Isabella II with Ferdinand VII and Infante Carlos as heir.
- Portugal: replaced Miguel/Maria II setup with Joao VI and Pedro as heir.
- Brazil: replaced Pedro II/regency setup with Joao VI and Pedro as heir.
- East India Company: replaced Lord Auckland with Francis Rawdon-Hastings.
- Ottoman Empire: removed unborn Abdulmejid as heir; Mahmud II remains ruler.
- Yogyakarta: replaced unborn Hamengkubuwono V with Hamengkubuwono IV and removed the unborn Hamengkubuwono VI heir.
- Removed direct heir blocks with explicit post-1816 birth dates or vanilla-style child ages under 21.
- Removed one non-ruler historical leader born after 1816: Mori Takachika in Japan.
- Removed template-created unborn heirs and one unborn commander after resolving character templates against the base game.

## Validation notes

- Removed the audited 1836 ruler/heir template references from the edited character files.
- Checked edited files for balanced braces.
- Checked edited visible ruler/heir blocks for birth years after 1816; none found.
- Checked direct and template-created character blocks for post-1816 birth dates; none remain in loaded start characters.
- Added a localization entry for Jiaqing; other new first and last name keys were already covered by base localization after key cleanup.

## Remaining character audit buckets

- Minor and medium tags still need a lower-priority pass for missing birth dates, generic age guesses, and 1830s interest group leaders.
- Several commander and industrialist characters are probably still vanilla 1836 flavor. They are less visible than rulers, so handle them after flags unless they create absurd ages.
- Some tags may need alternate de facto rulers or administrators where the map uses a gameplay tag for a subordinate political unit.

## Flag and coat of arms audit

- The custom `V00` through `V10` tags currently use simple generated coat-of-arms placeholders.
- No flag art changes were made in this batch because flags are more subjective and should be done as a focused visual batch.
- High-value candidates for the flag batch:
  - Bourbon France / Restoration white flag variant.
  - United States 1816 flag variant.
  - United Kingdom of Portugal, Brazil and the Algarves / Brazil 1816 royal symbolism.
  - Spanish monarchy and Spanish American loyalist/rebel variants.
  - East India Company and Hudson's Bay Company company flags.
  - German microstate arms, especially the Saxon duchies.
  - Ryukyu, Kuwait, Multan, and any custom tags still using placeholder arms.
