# Country and Tag Inventory

This file is for approved country/tag decisions. It should stay readable: design decisions go here first, game script follows after approval.

## Vanilla Tag Audit

Base game version audited: Victoria 3 `release/1.12.5`.

Country definition files:

| File | Defined tags |
| --- | ---: |
| `common/country_definitions/00_countries.txt` | 460 |
| `common/country_definitions/01_africa.txt` | 190 |
| `common/country_definitions/01_pacific_and_australasia.txt` | 49 |
| `common/country_definitions/99_dynamic.txt` | 100 |
| Total | 799 |

Starting setup files:

| Source | Count | Notes |
| --- | ---: | --- |
| `common/history/countries` files | 423 | Country laws, tech, politics, and startup effects. |
| Land-owning tags in `common/history/states/00_states.txt` | 422 | Tags that own at least one state at vanilla start. |
| Defined tags without vanilla land ownership | 377 | Includes releasables, formables, dynamic tags, and unused definitions. |

Notable audit detail:

- `SAH` has a country history file but does not appear as a land-owning tag in vanilla `00_states.txt`.

## Decision Table

Use this table for approved country/tag choices. No row should move to "Ready to Script" until the tag, name, and start status are approved.

| 1816 polity | Region | Approved action | Tag | Existing vanilla tag/name | Start status | Notes | Ready to script |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TBD | TBD | TBD | TBD | TBD | TBD | TBD | No |

## New Tag Namespace

Approved convention for newly created fixed mod countries:

- Use 3-character tags beginning with `V`.
- Allocate `V00` through `V99` first.
- After `V99`, continue with `V0A`, `V0B`, `V0C`, and so on.
- Do not use `D00` through `D99`; vanilla reserves those for dynamic country definitions.

Allocation table:

| Tag | Country/polity | Region | Status | Notes |
| --- | --- | --- | --- | --- |
| `V00` | Liechtenstein | Europe | Definition scripted; start ownership removed | Removed from the start map after in-game review showed the vanilla province compromise was too large. Keep as inactive/releasable-or-flavor candidate. |
| `V01` | San Marino | Europe | Definition scripted; start ownership removed | Removed from the start map after in-game review showed the vanilla province compromise was too large. Keep as inactive/releasable-or-flavor candidate. |
| `V02` | Monaco | Europe | Definition scripted; start ownership removed | Removed from the start map after in-game review showed the vanilla province compromise was too large. Keep as inactive/releasable-or-flavor candidate. |
| `V03` | Andorra | Europe | Definition and ownership scripted | Uses `STATE_CATALONIA` province `x2914C3` as the approved Pyrenees compromise. |
| `V04` | Saxe-Gotha-Altenburg | Europe | Definition and ownership scripted | Uses `STATE_SAXONY` province `x31E0C0` as a generous playable Ernestine abstraction. |
| `V05` | Saxe-Hildburghausen | Europe | Definition and ownership scripted | Uses `STATE_SAXONY` province `x5141A0`, split from vanilla `MEI`, as a generous playable Ernestine abstraction. |
| `V06` | Kuwait | Middle East | Definition and ownership scripted | Uses the vanilla Kuwait/Basra port province as the approved Gulf microstate compromise. |
| `V07` | Ryukyu Kingdom | Asia | Definition and ownership scripted | Uses `STATE_RYUKYU_ISLANDS` as the approved playable island kingdom setup. |
| `V08` | Choctaw Nation | North America | Definition scripted; start ownership removed | Removed from the start map after in-game review; keep for later release/event work. |
| `V09` | Chickasaw Nation | North America | Definition scripted; start ownership removed | Removed from the start map after in-game review; keep for later release/event work. |
| `V10` | Multan | India | Definition and ownership scripted | Uses the Multan hub area in `STATE_PUNJAB` as an approved Afghan-aligned playable frontier tag. |

## Tag Interpretation Rule

Approved default: moderately strict.

- Reuse vanilla tags when they reasonably represent the 1816 polity.
- Rename or relocalize vanilla tags when the underlying tag is usable but the vanilla name is not ideal for 1816.
- Create or split new `V**` tags only when the vanilla abstraction is genuinely misleading and vanilla map geometry can support the distinction.
- Do not create extra tags purely for perfection if the result would be awkward or invisible on the vanilla map.

Approved action values:

- Reuse vanilla tag
- Add new tag
- Start absent / releasable only
- Replace vanilla tag meaning
- Needs research
- Undecided

Start status values:

- Sovereign
- Subject
- Personal union / dynastic arrangement
- Unincorporated colony
- Decentralized / non-state polity
- Releasable only
- Not present
- Undecided

## Open Design Questions

- Rest-of-Europe batch questions are now consolidated in `planning/04_europe_country_inventory.md`.
- Remaining Europe tag issues are mostly small-state map reviews, Austrian internal crown-land policy, Krakow's joint protection model, and whether to defer Caucasus edge cases.
- Outside Europe, composite overseas structures still need later regional passes, especially the Portuguese empire, Spanish colonies, and British colonial/company possessions.

## Approved Scope

- First country/tag pass: Europe.

## Approved German Confederation Principle

- No Holy Roman Empire start country.
- No unified German Confederation start country.
- Maximize playable German member states where vanilla state/province geometry can reasonably support them.
- Represent the German Confederation as a non-country political/diplomatic system.
- Decide very small member states case by case.
- German microstates are playable by default; exclude only if literally too small to represent on the vanilla Victoria 3 map.

## German Confederation Vanilla Tag Baseline

Vanilla already defines and localizes many useful German Confederation member-state tags. These are initial candidates for reuse, not final approved 1816 setup.

| Tag | Vanilla name | Vanilla start ownership found | Initial note |
| --- | --- | --- | --- |
| `AUS` | Austria | Yes | Confederation presiding power; only German Confederation lands should count for the confederation system. |
| `PRU` | Prussia | Yes | Major internal rival to Austria; Prussian non-German lands remain outside the confederation idea. |
| `BAV` | Bavaria | Yes | Reuse candidate. |
| `WUR` | Wurttemberg | Yes | Reuse candidate. |
| `BAD` | Baden | Yes | Reuse candidate. |
| `SAX` | Saxony | Yes | Reuse candidate. |
| `HAN` | Hanover | Yes | Reuse candidate; 1816 personal union with Great Britain needs separate diplomacy decision. |
| `HES` | Hesse | Yes | Vanilla Hesse-Darmstadt; reuse candidate. |
| `HEK` | Hesse-Kassel | Yes | Reuse candidate. |
| `NAS` | Nassau | Yes | Reuse candidate. |
| `BRA` | Brunswick | Yes | Reuse candidate. |
| `MEC` | Mecklenburg | Yes | Reuse candidate. |
| `MST` | Mecklenburg-Strelitz | Yes | Reuse candidate. |
| `OLD` | Oldenburg | Yes | Reuse candidate. |
| `ANH` | Anhalt | Yes | Reuse candidate. |
| `WEI` | Saxe-Weimar | Yes | Reuse candidate. |
| `COB` | Saxe-Coburg-Gotha | Yes | Reuse candidate, but name may be historically awkward for 1816 and needs review. |
| `MEI` | Saxe-Meiningen | Yes | Reuse candidate. |
| `SCW` | Schwarzburg | Yes | Reuse candidate, likely abstracts multiple Schwarzburg lines. |
| `LIP` | Lippe | Yes | Reuse candidate. |
| `SCM` | Schaumburg-Lippe | Yes | Reuse candidate. |
| `WLD` | Waldeck | Yes | Reuse candidate. |
| `HOH` | Hohenzollern | Yes | Reuse candidate. |
| `FRM` | Frankfurt | Yes | Free city; reuse candidate. |
| `HAM` | Hamburg | Yes | Free city; reuse candidate. |
| `BRE` | Bremen | Yes | Free city; reuse candidate. |
| `LUB` | Lubeck | Yes | Free city; reuse candidate. |
| `HOL` | Holstein | Yes | German Confederation member; approved as separately playable under Denmark as a personal union. |
| `SCH` | Schleswig | Yes | Approved as separately playable under Denmark like Holstein for gameplay, with legal-status caveat. |
| `LUX` | Luxembourg | Yes | German Confederation member; approved as separately playable under the Netherlands as a personal union. |

Open German-specific decisions:

- Which vanilla abstraction tags, such as `SCW` and `COB`, need only 1816 relocalization versus a real split.
- Which historical German Confederation members are too tiny to represent individually with vanilla Victoria 3 map geometry.

Useful vanilla support:

- Vanilla already supports one-province and two-province playable German tags in state history, so German microstate playability is technically feasible.
- Vanilla already has `personal_union` subject support and uses it for `GBR` -> `HAN`, `DEN` -> `HOL`, `DEN` -> `SCH`, and `NET` -> `LUX`.

Approved personal-union rule:

- Historical personal unions at the 1816 start date should be represented as personal unions where Victoria 3 supports them.
- Approved German-region examples: `GBR` -> `HAN`, `DEN` -> `HOL`, `DEN` -> `SCH`, `NET` -> `LUX`.
