# Southeast Asia And Indonesia Population Refinement Audit

Status: approved cleanup implemented.

## Scope

This pass reviewed mainland Southeast Asia, Malaya, island Southeast Asia, Java, Borneo, the Philippines, and related colonial edge cases in `11_east_asia.txt` and `12_indonesia.txt`.

Files reviewed:

- `common/history/pops/11_east_asia.txt`.
- `common/history/pops/12_indonesia.txt`.
- `common/history/states/00_states.txt`.
- Asia planning notes `08_asia_inventory.md`, `17_mena_central_asia_asia_map_implementation.md`, `21_remaining_map_cleanup_audit.md`, and `24_population_scaling_plan.md`.

## Current Snapshot

Selected Southeast Asia and Indonesia state total:

- 33,326,567 across the selected mainland Southeast Asia, Malaya, Indonesia, and Philippine state regions.

Largest current owner totals in the selected states:

- `DEI`: 8,464,860.
- `DAI`: 6,702,463.
- `PHI`: 2,617,666 in the Philippine state regions, plus 9,174 in West Micronesia.
- `SIA`: 2,583,956.
- `BUR`: 2,382,058.
- `BAL`: 1,573,968.
- `CMI`: 942,704.
- `SAK`: 787,306.
- `CAM`: 728,715.
- `SHS`: 640,369.

Philippines current setup:

- `STATE_LUZON`, `PHI`: 1,463,176.
- `STATE_VISAYAS`, `PHI`: 1,054,440.
- `STATE_MINDANAO`, `PHI`: 100,050.
- Spanish-subject Philippine state-region total: 2,617,666.
- Local independent Philippine-state total, using `SUL`, `MGD`, and `MND` in Luzon/Mindanao: 955,046.
- Total Luzon/Visayas/Mindanao population: 3,572,712.
- `STATE_WEST_MICRONESIA`, `PHI`: 9,174, treated separately as Guam/Palau rather than part of the Philippine-islands target.
- `STATE_NORTH_BORNEO`, `SUL`: 41,648, treated separately because it is North Borneo-facing.

Java current setup:

- `STATE_WEST_JAVA`: 3,938,516.
- `STATE_CENTRAL_JAVA`: 2,248,694.
- `STATE_EAST_JAVA`: 2,122,046.
- Java total: 8,309,256.

## Implemented Correction

### 1. Philippines Spanish-Subject Population Is A Bit High

Current setup:

- `PHI` in Luzon, Visayas, and Mindanao totals 2,617,666.

Nearby historical estimate:

- An 1817-18 Philippine census cited in *The Philippine Islands, 1493-1898*, volume LI, gives 2,236,000 people subject to Spanish laws.

Implemented correction:

- Scale only `PHI` buckets in `STATE_LUZON`, `STATE_VISAYAS`, and `STATE_MINDANAO` from 2,617,666 to 2,236,000.
- Preserve each state bucket's internal culture, religion, profession, and enslaved/free composition proportionally.
- Leave `PHI` in `STATE_WEST_MICRONESIA` unchanged because that bucket represents Guam/Palau rather than the main Philippine Islands.

Implemented state-bucket targets:

- `STATE_LUZON`, `PHI`: 1,463,176 -> 1,249,839.
- `STATE_MINDANAO`, `PHI`: 100,050 -> 85,462.
- `STATE_VISAYAS`, `PHI`: 1,054,440 -> 900,699.

### 2. Independent Philippine Local Populations Are Also High

Current setup:

- `SUL`, `MGD`, and `MND` in Luzon and Mindanao total 955,046.

Nearby historical estimate:

- The same 1817-18 Philippine description adds roughly three quarters of a million people in independent tribes/polities outside Spanish law, especially the interior and Mindanao/Sulu-facing areas.

Implemented correction:

- Scale `SUL`, `MGD`, and `MND` only inside `STATE_LUZON` and `STATE_MINDANAO` from 955,046 to 750,000.
- Preserve internal composition proportionally.
- Leave `SUL` in `STATE_NORTH_BORNEO` unchanged because that bucket belongs to the North Borneo side of Sulu's map abstraction.

Implemented state-bucket targets:

- `STATE_LUZON`, `SUL`: 44,096 -> 34,629.
- `STATE_MINDANAO`, `MGD`: 297,984 -> 234,008.
- `STATE_MINDANAO`, `MND`: 516,371 -> 405,507.
- `STATE_MINDANAO`, `SUL`: 96,595 -> 75,856.

Aggregate impact:

- Luzon/Visayas/Mindanao total falls from 3,572,712 to 2,986,000.
- Global `PHI` becomes 2,245,174 after retaining 9,174 in West Micronesia.
- The selected Southeast Asia/Indonesia total falls from 33,326,567 to 32,739,855.

## Leave Alone For Now

- Java should stay as-is for this pass. The current 8.31 million Java total is high versus Raffles' contemporary 1815 census, but modern scholarship often treats that census as too low and places Java near 7.5-8.4 million around 1800-1815. The current total is therefore defensible, especially because the vanilla map gives only tiny one-province buckets to `YOG` and `SRK`.
- `YOG` and `SRK` are underpopulated relative to their historical importance, but correcting that properly would require a map/design decision about how much of Central Java should be assigned to each court. Leave this for a later Java-specific political/border review.
- Mainland Southeast Asia should stay as-is for now. The broad `SIA`, `BUR`, `DAI`, `CAM`, `CMI`, `LUA`, `CHP`, `VIE`, and `SHS` totals do not show an obvious game-breaking 1816 artifact in this quick pass.
- Malaya, Portuguese Timor, Danish Pegu, British Penang/Singapore-area abstractions, and North Borneo should stay as-is unless an in-game review exposes a specific problem.

## Sources Checked

- *The Philippine Islands, 1493-1898*, volume LI, lines around the 1817-18 population description: https://www.gutenberg.org/cache/epub/57304/pg57304-images.html
- Feenstra, "Dutch Coins for Asian Growth", table of Java population estimates around 1800/1815: https://tseg.nl/article/download/7418/8048/11160

## Validation Snapshot

- `common/history/pops/12_indonesia.txt`: brace depth 0, minimum depth 0, UTF-8 BOM present.
- `PHI` in Luzon/Visayas/Mindanao now totals exactly 2,236,000.
- Local independent `SUL`/`MGD`/`MND` in Luzon/Mindanao now totals exactly 750,000.
- Luzon/Visayas/Mindanao now totals exactly 2,986,000.
- `PHI` in West Micronesia remains unchanged at 9,174.
- `SUL` in North Borneo remains unchanged at 41,648.
- Global nonpositive pop-size check remains clean: 0 nonpositive pop sizes.

## Approved And Implemented

The user approved this focused Philippines cleanup:

- Scale Spanish-subject `PHI` in Luzon/Visayas/Mindanao to 2,236,000.
- Scale local independent `SUL`/`MGD`/`MND` in Philippine state regions to 750,000.
- Leave West Micronesia `PHI` and North Borneo `SUL` unchanged.
- Leave Java and the rest of Southeast Asia unchanged for this pass.
