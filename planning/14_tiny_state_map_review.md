# Tiny-State Map Review

This file records province-level options for approved tiny playable candidates.

Current status: Andorra and the Ernestine duchies remain scripted. Monaco, Liechtenstein, and San Marino were removed from start ownership after in-game review showed their vanilla-map compromises were too large.

## Rule

- Use the vanilla Victoria 3 state/region/province map.
- Prefer one-province playable compromises only where the vanilla map gives us a visible, clickable shape.
- Do not silently take land from a neighboring country for a microstate without approval.

## High-Confidence Candidates

| Candidate | Tag | Proposed state region | Proposed province | Current vanilla owner | Why this works | Tradeoff | Recommended? |
| --- | --- | --- | --- | --- | --- | --- | --- |
| San Marino | `V01` | `STATE_ROMAGNA` | `xFE3729` | `PAP` | This is the Romagna farm hub, and vanilla names that hub San Marino. | It gives San Marino a larger inland Romagna province rather than the real tiny enclave. | Removed from start map after in-game review |
| Monaco | `V02` | `STATE_PROVENCE` | `x5080E0` | `SAR` | This is the one vanilla Sardinian-owned province in Provence and is the best available Riviera/Monaco compromise. | It effectively gives Monaco the vanilla Nice/Monaco strip and removes Sardinia-Piedmont's one Provence province. | Removed from start map after in-game review |
| Andorra | `V03` | `STATE_CATALONIA` | `x2914C3` | `SPA` after the 1816 Spain override | This is a very small northern Catalonia/Pyrenees province, making it the cleanest one-province Andorra compromise found so far. | It still represents much more than Andorra. | Approved/scripted |

## Liechtenstein Options

| Option | Tag | Proposed state region | Proposed province | Current vanilla owner | Why it works | Tradeoff |
| --- | --- | --- | --- | --- | --- | --- |
| A | `V00` | `STATE_TYROL` | `xD0C0E0` | `AUS` | This province is the Tyrol wood hub, localized as Feldkirch, so it approximates Vorarlberg next to Liechtenstein. | Liechtenstein would include a much larger Austrian Vorarlberg slice. Removed from start map after in-game review. |
| B | `V00` | `STATE_EAST_SWITZERLAND` | `x90C0E0` | `SWI` | This is an eastern Swiss alpine province, near the right neighborhood. | It absorbs a chunk of Swiss Graubunden/Chur into Liechtenstein. |
| C | none | none | none | none | Avoids a distorted playable Liechtenstein. | Loses a user-priority playable microstate. |

Recommended Liechtenstein compromise: Option A, because it is geographically closer to the Liechtenstein/Vorarlberg area and avoids carving up Switzerland.

## Ernestine Duchy Options

The vanilla `STATE_SAXONY` region already has a dense Thuringian split:

- `COB` owns one province.
- `WEI` owns one province.
- `MEI` owns two provinces.
- `SCW` owns one province.
- `SAX` owns the remaining Saxony/Thuringia provinces.

Adding Saxe-Gotha-Altenburg (`V04`) and Saxe-Hildburghausen (`V05`) is possible only by taking one province each from an existing owner.

| Candidate | Tag | Proposed state region | Proposed province | Current vanilla owner | Why it works | Tradeoff | Recommended? |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Saxe-Gotha-Altenburg | `V04` | `STATE_SAXONY` | `x31E0C0` | `SAX` | Gives the duchy a visible province without deleting any existing Thuringian microstate tag. | Not geographically perfect; it is a generous abstraction of Gotha/Altenburg. | Chosen/scripted |
| Saxe-Hildburghausen | `V05` | `STATE_SAXONY` | `x5141A0` | `MEI` | Splits one of vanilla Saxe-Meiningen's two provinces, matching the local Ernestine patchwork better than taking land from Saxony proper. | Weakens `MEI` and still cannot model the full historical patchwork. | Chosen/scripted |

Conservative alternative: do not start `V04` or `V05` as landholders; leave the vanilla Ernestine abstraction in place with `COB`, `MEI`, and `WEI`.

## Approved Choices

Final start-map choices after in-game review:

1. San Marino: no start ownership; keep `V01` inactive/releasable-or-flavor only.
2. Monaco: no start ownership; keep `V02` inactive/releasable-or-flavor only.
3. Andorra: `STATE_CATALONIA` province `x2914C3` to `V03`.
4. Liechtenstein: no start ownership; keep `V00` inactive/releasable-or-flavor only.
5. Ernestine duchies: use the more-playable split, with `STATE_SAXONY` province `x31E0C0` to `V04` and `x5141A0` to `V05`.
