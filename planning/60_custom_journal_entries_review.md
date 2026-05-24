# Custom Journal Entries Review

## Scope

This pass follows the military polish pass. It reviews journal entries that the mod currently starts through copied/edited country and global history files, then tracks the first custom journal-entry package for an 1816 start.

Package A cleanup and the approved first custom journal-entry wave are now implemented.

## Current Mod State

- The mod now defines custom 1816 journal entries in `common/journal_entries/99_cow_1816_custom_journal_entries.txt`.
- The mod does not currently define custom journal-entry events in `events`.
- Existing journal content is being started through history files using vanilla journal entries.
- Several started vanilla entries are designed for Victoria 3's 1836 assumptions or later historical moments, so custom 1816 content should start with a cleanup/delay pass.

## Existing Start-Added Journal Entries

### High-Confidence 1836 Leakage / Delay Candidates

These are likely wrong for an 1816 start and should probably be removed from start history, delayed behind later triggers, or replaced by custom 1816 entries.

| Country / Scope | Current entry | Reason |
| --- | --- | --- |
| `USA` | `je_texas_usa` | Texas is not independent and the 1836 Texas annexation setup does not fit 1816. |
| `USA` | `je_acw_countdown` | The ACW countdown creates 1830s/1850s slavery-crisis pressure immediately. |
| `GBR` | `je_victoria` | This assumes the William IV to Victoria succession setup; 1816 is still George III / Regency era. |
| `HAN` | `je_victoria` | Same succession issue as Britain. |
| `FRA` | `je_conquest_of_algeria` | French conquest of Algeria begins in 1830, not at the 1816 start. |
| `FRA` | `je_divided_monarchists` | Tied to later Bourbon/Orleanist assumptions and needs an 1816 Bourbon Restoration review. |
| `CHI` | `je_warlord_china` | This represents later Qing collapse pressure and should not be active from 1816. |
| `POR` | `je_devorismo` | Post-Liberal-Wars Portuguese politics; too late for 1816. |
| `POR` | `je_second_liberalism` | Same issue; this is not the correct opening Portuguese political crisis. |
| `BIC` | `je_consolidate_colonial_rule` | Targets 1836-era British India expansion toward Punjab, Sindh, Burma, etc.; 1816 needs a Maratha/Company setup instead. |
| `HAI` | `je_haitian_debt` | French indemnity was imposed in 1825, so this should not exist at 1816 start. |
| `HUN` | `je_hungarian_revolution` | 1848 revolution content should not be active at 1816 start. |

Related non-journal item to review with the same package:

- `USA` currently starts with `missouri_compromise`, but the Missouri Compromise was 1820, so this should likely be delayed or replaced by a later Missouri Question chain.

### Plausible To Keep For Now

These look closer to 1816 or at least less harmful as active starts.

| Country / Scope | Current entry | Reason |
| --- | --- | --- |
| `AUS` | `je_metternich` | Metternich is highly relevant to the post-Vienna order; implementation already has custom comments for initialization timing. |
| `AUS` | `je_matter_of_hungary` | May be somewhat early, but fits long-term Habsburg nationality pressure better than most vanilla leaks. |
| `RUS`, `CHC`, `CIR` | Caucasian War entries | The Caucasus conflict is already active in this era. |
| Afghan fragments | `je_unify_afghanistan` | Fragmented Afghanistan and reunification pressure fit the date well enough. |
| `JAP` | `je_terakoya` | Educational/literacy development under Tokugawa Japan is not obviously anachronistic. |
| `MOR` | `je_lands_of_anarchy` | Moroccan internal authority struggles are plausible enough for now. |
| `MUG` | `je_mughal_hindustan` | Fits the alternate-history/playable Mughal remnant concept. |
| `PAN` | `je_sikh_sovereignty` | Sikh state-building is relevant for the period. |
| `MON`, `SER` | Balkan/Montenegrin/Serbian entries | Likely usable, though they should get a later targeted Balkan review. |
| `SAF`, `SWZ`, `PHL`, `WBL`, `ZUL` | Highveld entries | Probably fine as regional flavor unless in-game behavior is odd. |

### Needs Focused Review

These may be usable, but the 1816 start probably changes their timing or framing.

| Country / Scope | Current entry | Question |
| --- | --- | --- |
| Spanish American countries/global | `je_spanish_american_independence` | Vanilla assumes many countries are already independent; 1816 needs an active war/loyalist-colony framework. |
| `CUB` | Cuba Spanish-colony entries | Could be useful, but may be too late or too independent-focused for 1816. |
| `GBR` | `je_aberdeen_act` | British anti-slave-trade policy exists, but the Aberdeen Act itself is later. |
| `PER` | `je_eastern_frontier` | Needs a quick Persia frontier review against the 1816 Russo-Persian border. |
| `PHI` | `je_philippines_development` | Probably harmless, but may assume a later colonial economy. |
| `TUG`, `AIT` | `je_reconquest_of_algeria` | These are tied to the French Algeria system and should be checked if France's Algeria JE is delayed. |

## Recommended First Package

### Package A: Start Cleanup And Delay Layer

Recommended first implementation because it has the lowest risk and fixes the most visible 1836 assumptions before we add new chains.

1. Remove or delay the high-confidence leakage entries listed above.
2. Leave plausible entries active for now.
3. Add planning notes/TODO markers where a delayed vanilla entry should return through a later event or custom JE.
4. Validate that the mod still boots and no journal-entry references break parsing.

Status: approved and implemented.

Implemented cleanup:

- Removed/delayed `USA` start entries `je_texas_usa` and `je_acw_countdown`.
- Removed the premature `USA` `missouri_compromise` start modifier.
- Removed/delayed `GBR` and `HAN` start entry `je_victoria`.
- Removed/delayed `FRA` start entries `je_divided_monarchists` and `je_conquest_of_algeria`.
- Removed the directly related 1836 France flags/modifiers:
  - `modifier_haitian_independence_payments_4`
  - `orleanist_restoration_var`
  - `fra_republic_counter`
- Removed/delayed `POR` start entries `je_devorismo` and `je_second_liberalism`.
- Removed the directly related post-Liberal-Wars Portugal setup:
  - `recent_coup_or_revolution_var`
  - `modifier_legacy_of_the_liberal_wars`
- Removed/delayed `BIC` start entry `je_consolidate_colonial_rule`.
- Removed the directly related `east_indies_revolt_var` start variable.
- Removed/delayed `CHI` start entry `je_warlord_china`.
- Removed the directly related `china_warlord_explosion` start variables from country and global history.
- Removed/delayed `HAI` start entry `je_haitian_debt`.
- Removed/delayed `HUN` start entry `je_hungarian_revolution`.

Post-implementation validation:

- Comment-stripped brace check over `common/history`: 0 problems.
- Targeted search for delayed Package A journal entries in mod history: 0 remaining references.
- Targeted search for delayed Package A support flags/modifiers in mod history: 0 remaining references.

### Package B: First Custom 1816 Anchor Entries

After Package A, add a small set of custom 1816 entries rather than trying to rebuild all historical content at once.

Recommended first custom anchors:

1. `AUS` / Great Power diplomatic order: Congress System / Metternich System.
2. `SPA` and Spanish America: Spanish American Wars of Independence.
3. `POR` and `BRZ`: United Kingdom of Portugal, Brazil and Algarves.
4. `USA`: Era of Good Feelings / Missouri Question / Florida frontier.
5. `BIC` and Maratha/Indian states: Company power after the Second Anglo-Maratha War, before the Third.

Status: approved and implemented as the first custom anchor wave.

Implementation summary:

- Added 84 custom `je_cow_1816_*` journal-entry definitions.
- Added a global-history assignment file giving the approved entries to 101 playable tags and shared regional clusters.
- Added English localization for all titles and reason text.
- Used pinned historical-content entries with GDP-growth objectives as the first low-risk implementation layer.
- Did not add custom event chains, rewards, or branching outcomes yet; those remain a later design decision.

Validation:

- Comment-stripped brace check over `common`: 0 problems.
- Custom JE definitions: 84.
- Custom JE referenced types: 84.
- Missing referenced definitions: 0.
- Missing title/reason localization keys: 0.
- Assigned country-history tags: 101.
- Missing assigned tags: 0.

## Design Decisions Needed Before Implementation

1. Should the first journal-entry implementation be cleanup-only, or should it also include the first new custom entries?
2. Should custom 1816 journal entries be mostly historical guide rails, or should they be stronger mission-style objectives with rewards?
3. For Spanish America, should the first custom system model active wars of independence at game start, or should it model unstable Spanish subject colonies with decisions/events that can become wars?
4. For Portugal/Brazil, should the intended path make Brazilian independence likely, or should preserving the transatlantic monarchy be a viable equal path?
5. For the USA, should the 1816 opening focus on internal slavery compromise, territorial expansion, or both?

## Recommendation

Package A was completed first, then the user approved all listed Package B custom anchor options at once. Future work should build optional event chains and rewards only after a separate design approval.
