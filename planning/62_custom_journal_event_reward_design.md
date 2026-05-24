# Custom Journal Event And Reward Design

## Scope

This began as a design-only pass for the custom 1816 journal entries added in `common/journal_entries/99_cow_1816_custom_journal_entries.txt`.

Status: approved and implemented for Package B1. Future follow-up entries, map changes, law changes, subject changes, or country-specific branching still require separate user approval.

## Current State

- 84 custom `je_cow_1816_*` journal entries exist.
- 101 journal-entry assignments exist across 101 playable tags.
- Entries are pinned historical-content objectives.
- Each playable tag receives one active custom GDP-growth entry at start, using the original Option A anchor for that country or regional cluster.
- Every custom entry currently completes by reaching its GDP-growth target; active start entries require 20% GDP growth.
- Entries now have localized completion events and very light completion rewards.
- Unassigned approved entries are retained for later use but hidden from the lobby preview.
- Entries still have no failures, timeouts, follow-up chains, map changes, law changes, subject changes, or war/release effects.

## Design Principles

- The first reward layer should be stable and easy to debug.
- Completion should feel like historical momentum, not the total solution to a country's 19th-century problems.
- Rewards should be modest because the entries are broad GDP-growth objectives rather than full historical crisis chains.
- Early rewards should avoid direct law changes, subject changes, annexations, releases, or war starts unless separately approved.
- Events should use base-game event syntax, base-game event images/icons, and custom static modifiers.
- Cluster-specific branching should come after the safe universal layer unless the user explicitly wants a deeper first implementation.

## Recommended Architecture

### Package B1: Universal Completion Events

Add a completion event to every custom 1816 journal entry.

Implementation shape:

- `events/cow_1816_journal_events.txt`
- `common/static_modifiers/99_cow_1816_journal_modifiers.txt`
- `localization/english/cow_1816_journal_events_l_english.yml`
- Add `on_complete = { trigger_event = { id = cow_1816_journal.X popup = yes } }` to each custom JE.

Event style:

- One completion event per custom journal entry.
- Most events have one default option.
- A small number of headline countries or clusters can have two flavor options, but both options should remain modest and not alter the map.

Reward style:

- Custom country or interest-group static modifiers.
- Duration: 5 years for most rewards.
- Duration: 7 to 10 years only for harder 10% GDP objectives if approved.
- Rewards should be small enough that completing both starting entries is nice, not overpowering.

Recommended first implementation: Package B1 only.

Status: implemented.

Implemented files:

- `events/cow_1816_journal_events.txt`
- `common/static_modifiers/99_cow_1816_journal_modifiers.txt`
- `localization/english/cow_1816_journal_events_l_english.yml`
- `common/journal_entries/99_cow_1816_custom_journal_entries.txt` was updated with `on_complete` hooks.

Implemented shape:

- 84 completion events, one for every custom 1816 journal entry.
- 12 reusable very light reward modifiers.
- 18 headline entries have a second modest option; all others have one default option.
- All rewards last 1095 days, approximately 3 years.
- Rewards are limited to very mild country, economy, diplomacy, military, and interest-group modifier effects.
- No event starts a war, changes a law, changes a subject relationship, changes ownership, releases a country, or adds a follow-up journal entry.

GDP consolidation update:

- Active start assignments were reduced from 206 to 101, so every assigned country starts with exactly one custom GDP-growth journal entry.
- All custom GDP targets were standardized to 20% growth.
- Unassigned approved entries remain defined for future chain work, but their `is_shown_in_lobby` triggers are disabled.
- Reward modifiers were reduced and shortened from 5 years to 3 years.

Validation:

- Comment-stripped brace check over `common` and `events`: 0 problems.
- Journal-entry `on_complete` event hooks: 84.
- Active custom JE assignments: 101.
- Countries with exactly one active custom JE assignment: 101.
- Active/lobby assignment mismatch: 0.
- 20% GDP goals: 84.
- 20% GDP goal localization strings: 84.
- Old 5%/10% GDP goals: 0.
- Event definitions: 84.
- Missing event definitions: 0.
- Static reward modifiers: 12.
- Missing reward modifiers: 0.
- Event localization references: 354.
- Missing event localization keys: 0.
- Modifier effect types checked against base 1.12.5 modifier definitions: 24 checked, 0 missing.
- Event video references checked against base event usage: 12 checked, 0 missing.
- Icon paths checked against base/mod files: 15 checked, 0 missing.
- New/rewritten event, modifier, JE, and localization files have a single UTF-8 BOM.

### Package B2: Headline Branching Chains

After the universal completion layer works in game, add deeper branching only for the countries and clusters that most need it.

Recommended clusters:

1. Iberian world: `SPA`, `POR`, `BRZ`, Spanish America.
2. German and Italian systems: `AUS`, `PRU`, German Confederation, Italian Restoration.
3. British India and Maratha India: `BIC`, `SAT`, `GWA`, `IND`, `NAG`, `PAN`.
4. Ottoman world: `TUR`, `EGY`, `SER`, `MOL`, `WAL`, `MON`.
5. East Asia: `CHI`, `JAP`, `KOR`.
6. North American frontier: `USA`, `SC1`, `COM`, `LKT`, `HBC`.

Branching should mostly create follow-up journal entries, diplomatic modifiers, prestige, interest-group approval, or short-term economic bonuses. Direct wars, independence, annexation, and law swaps should be separate design approvals.

### Package B3: Dynamic Historical Crises

This is the most powerful layer and should wait.

Possible later systems:

- Missouri Question / slavery compromise chain.
- Spanish American independence and recognition framework.
- Portugal-Brazil separation or continued transatlantic monarchy.
- Third Anglo-Maratha War pressure.
- Greek independence / Eastern Question escalation.
- Belgian Revolution timing pressure.
- French Algeria crisis after 1830.
- Opium War pressure after the late 1830s.

These should not be bundled into the first reward implementation.

## Reward Archetypes

These archetypes keep the first implementation readable and reusable.

| Archetype | Use For | Example Modifier Direction |
| --- | --- | --- |
| Diplomatic settlement | Congress System, Holy Alliance, Eastern Question, Recognition | prestige, influence, diplomatic reputation |
| State capacity | Restoration, reform state, crownlands, court reform | bureaucracy, authority, legitimacy |
| Industrial momentum | Workshop, company foundations, colonial commercial revival | construction efficiency, throughput, tech spread |
| Military reform | Prussian reform, Punjab, Egypt, frontier states | army/navy power projection, barracks/naval base throughput, military tech spread |
| Commercial networks | Netherlands, DEI, HBC, Hawaii, Barbary commerce | convoys, trade center throughput, minting, diplomatic reputation |
| Internal cohesion | Bourbon Restoration, Two Haitis, Habsburg Crownlands | loyalists/radicals pressure, legitimacy, IG approval |
| Frontier administration | Russia, USA, Qing, Persia, Afghanistan | authority, infrastructure, bureaucracy, tension decay |
| Colonial governance | BIC, DEI, Brazil/Portugal, Spain | bureaucracy, subject management, tax or trade efficiency |
| Reform pressure | Portugal liberalism, Japan Rangaku, Korea Court Reform | education/research spread, intelligentsia approval, enactment support |
| Conservative order | Austria, Russia, Ottoman recovery, Tokugawa order | authority, legitimacy, devout/landowner approval |
| Local polity coherence | Comanche, Lakota, Zulu, Sokoto, Madagascar | authority, legitimacy, army throughput, prestige |
| Regional leadership | German/Italian/Maratha/Balkan/Central Asian shared entries | prestige, influence, diplomatic reputation |

## Country And Cluster Reward Direction

### Core Great And Major Powers

| Tag | Entry Theme | Suggested Reward Direction |
| --- | --- | --- |
| `GBR` | Postwar Settlement | prestige/influence or lower interest burden style modifier |
| `GBR` | Workshop of the World | industrial throughput or construction cost bonus |
| `FRA` | Bourbon Restoration | legitimacy, loyalists, landowner/devout approval |
| `FRA` | Return to Great Power | prestige, army/navy projection, diplomatic reputation |
| `AUS` | Congress System | influence, diplomatic reputation, authority |
| `AUS` | Habsburg Crownlands | bureaucracy, legitimacy, reduced internal instability |
| `PRU` | Reform State | bureaucracy, education/research, army reform |
| `PRU` | German Dualism | prestige/influence, German leadership setup |
| `RUS` | Holy Alliance | prestige, legitimacy, diplomatic reputation |
| `RUS` | Imperial Borderlands | authority, infrastructure, frontier administration |
| `TUR` | Ottoman Recovery | bureaucracy, authority, legitimacy |
| `TUR` | Eastern Question | influence, army reform, subject/autonomy management flavor |
| `CHI` | Canton System | trade, authority, coastal stability |
| `CHI` | Inner Frontiers | authority, bureaucracy, legitimacy |
| `USA` | Era of Good Feelings | legitimacy, loyalists, modest authority |
| `USA` | Continental Frontier | authority, infrastructure, diplomatic maneuvering |
| `SPA` | Crisis of the Indies | prestige/influence, colonial governance |
| `SPA` | Postwar Restoration | legitimacy, bureaucracy, army recovery |
| `POR` | Atlantic United Kingdom | trade, legitimacy, subject/liberty-desire flavor |
| `POR` | Liberal Revolution | reform pressure, intelligentsia approval, enactment support |
| `BRZ` | Kingdom in the Tropics | construction/plantation/trade momentum |
| `BRZ` | Road to Independence | prestige, legitimacy, liberty-desire flavor |
| `BIC` | Maratha War | army reform, diplomacy with Indian states |
| `BIC` | Company Raj | bureaucracy, revenue, princely relations flavor |

### Regional Powers

| Tags | Suggested Reward Direction |
| --- | --- |
| `PER` | authority, military reform, frontier administration |
| `EGY` | army reform, bureaucracy, construction/industry |
| `NET` | trade, bureaucracy, colonial commerce |
| `SWE`, `DEN` | legitimacy, naval/trade recovery, diplomacy |
| `JAP`, `KOR` | authority, reform pressure, education/tech spread |
| `SIA`, `DAI`, `BUR` | authority, regional diplomacy, army/state capacity |
| `DEI` | bureaucracy, plantations/trade, colonial administration |
| `PAN` | army reform, prestige, frontier diplomacy |

### Shared Systems

| Cluster | Suggested Reward Direction |
| --- | --- |
| Maratha Confederacy | prestige/influence and military cohesion without forcing reunification |
| Spanish America | legitimacy, prestige, diplomatic recognition flavor |
| Italian Restoration | legitimacy/authority or reform pressure depending on entry |
| German Confederation | influence/prestige for political entry; trade/construction for economic entry |
| Balkans | legitimacy/autonomy flavor; army/prestige for uprising path |
| Afghanistan | authority, prestige, military reform |
| Central Asia | prestige, authority, trade/diplomacy |

### Distinctive Starts

| Tags | Suggested Reward Direction |
| --- | --- |
| `HAI` | legitimacy, loyalists, recognition/diplomatic reputation |
| `ALD`, `MOR`, `TUN`, `TRI` | trade/naval/diplomatic reputation, authority |
| `SOK` | authority, legitimacy, devout approval |
| `MAD` | authority, military reform, trade/education |
| `ZUL` | army throughput, authority, prestige |
| `COM`, `LKT` | authority, prestige, army throughput, trade/network flavor |
| `HAW` | trade, diplomacy, legitimacy |
| `HBC` | trade center/convoy flavor, diplomacy, frontier administration |

## Design Decisions Needed

### 1. Reward Strength

Recommended: Light.

- Light: 5-year modest modifiers, no direct map/law/subject changes.
- Medium: stronger 7-10 year modifiers and occasional two-option political tradeoffs.
- Strong: meaningful long-term bonuses, follow-up JEs, and some direct political/diplomatic effects.

### 2. Event Style

Recommended: Mixed simple flavor.

- Simple: one option per completion event.
- Mixed simple flavor: one option for most entries, two options for major powers and shared regional systems.
- Branch-heavy: two or more options for nearly every entry.

### 3. Follow-Up Chains

Recommended: Not in the first implementation.

- None first: completion events only.
- Headline only: follow-up JEs for the six headline clusters listed in Package B2.
- Broad: follow-up JEs for most entries.

### 4. Political Effects

Recommended: Mild.

- Mild: legitimacy, authority, prestige, influence, bureaucracy, and small IG approval modifiers.
- Moderate: law-enactment bonuses and larger IG approval tradeoffs.
- Direct: actual law changes, government changes, releases, annexations, or forced wars.

### 5. Failure And Timeouts

Recommended: No failure/timeouts in the first implementation.

- None: entries simply wait until completed.
- Long timeout: 20-25 year timeout with small failure event.
- Crisis timeout: missed goals create regional crises or instability.

### 6. Implementation Order

Recommended: Universal completion layer first.

- Universal completion layer first: implement all safe completion events and rewards.
- One deep cluster first: choose one cluster such as Iberian world or India and make it more detailed before touching the rest.
- Hybrid: implement universal events for great powers only, then one deep cluster.

## Recommendation To User

Approved and implemented recommended first package:

- Light reward strength.
- Mixed simple flavor event style.
- No follow-up chains yet.
- Mild political effects only.
- No failure/timeouts yet.
- Universal completion layer first.

This gives every custom JE a satisfying completion event while keeping the mod easy to debug and avoiding accidental alternate-history railroading. After this is stable in game, move to Package B2 cluster chains one at a time.
