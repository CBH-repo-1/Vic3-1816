# Europe Country Inventory

This file tracks the Europe-first country/tag inventory for the 1816 start. Rows here are planning candidates unless marked approved and ready to script.

## Scope And Rules

- First regional pass: Europe.
- Current sub-pass: German Confederation and adjacent personal-union cases.
- Default interpretation: moderately strict.
- Strong reuse candidates are approved by default for all regional passes unless a later historical or technical conflict is found.
- Reuse vanilla tags when they reasonably fit.
- Relocalize vanilla tags when the tag is usable but the 1816 name differs from vanilla.
- Create new `V**` tags only when vanilla abstraction is genuinely misleading and the vanilla map can support it.
- German microstates are playable by default unless literally too small to represent on the vanilla map.
- Historical personal unions should use Victoria 3's `personal_union` subject type where supported.

## Historical Source Notes

- The German Confederation was established in 1815 as a loose association of German states, not a unified country.
- The Confederation had no central executive or judiciary; Austria dominated the federal assembly.
- Some vanilla tags use later names or consolidated entities, so exact 1816 naming may need relocalization.

## German Confederation: Strong Reuse Candidates

These rows are approved as the initial German Confederation playable list. They are ready for later scripting once the broader Europe inventory reaches implementation.

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Austrian Empire, German Confederation lands | `AUS` | Austria | Reuse vanilla tag | Sovereign great power | German Confederation presiding power | Strong | Yes | Only Austria's confederation lands should count for the German Confederation system. |
| Kingdom of Prussia, German Confederation lands | `PRU` | Prussia | Reuse vanilla tag | Sovereign great power | German Confederation member | Strong | Yes | Prussian non-confederation lands should remain Prussian but outside the confederation concept. |
| Kingdom of Bavaria | `BAV` | Bavaria | Reuse vanilla tag | Sovereign | German Confederation member | Strong | Yes | Includes Palatinate/Rhenish Bavaria if represented by vanilla split state. |
| Kingdom of Saxony | `SAX` | Saxony | Reuse vanilla tag | Sovereign | German Confederation member | Strong | Yes | Reuse. |
| Kingdom of Hanover | `HAN` | Hanover | Reuse vanilla tag | Personal union junior | `GBR` personal union | Strong | Yes | Approved principle: historical personal union with Great Britain. |
| Kingdom of Wurttemberg | `WUR` | Wurttemberg | Reuse vanilla tag | Sovereign | German Confederation member | Strong | Yes | Reuse. |
| Grand Duchy of Baden | `BAD` | Baden | Reuse vanilla tag | Sovereign | German Confederation member | Strong | Yes | Reuse. |
| Electorate of Hesse / Hesse-Kassel | `HEK` | Hesse-Kassel | Reuse vanilla tag | Sovereign | German Confederation member | Strong | Yes | Vanilla tag matches the needed polity well. |
| Grand Duchy of Hesse / Hesse-Darmstadt | `HES` | Hesse | Reuse vanilla tag, relocalize | Sovereign | German Confederation member | Strong | Yes | Display as Hesse-Darmstadt to distinguish from `HEK`. |
| Duchy of Holstein | `HOL` | Holstein | Reuse vanilla tag | Personal union junior | `DEN` personal union | Strong | Yes | Approved principle: personal union under Denmark. |
| Duchy of Schleswig | `SCH` | Schleswig | Reuse vanilla tag | Personal union junior | `DEN` personal union | Strong | Yes | Approved gameplay simplification: treat like Holstein, while noting legal status differed. |
| Grand Duchy of Luxembourg | `LUX` | Luxembourg | Reuse vanilla tag | Personal union junior | `NET` personal union | Strong | Yes | Approved principle: personal union under the Netherlands. |
| Saxe-Weimar-Eisenach | `WEI` | Saxe-Weimar | Reuse vanilla tag, relocalize | Sovereign | German Confederation member | Strong | Yes | Display as Saxe-Weimar-Eisenach. |
| Saxe-Meiningen | `MEI` | Saxe-Meiningen | Reuse vanilla tag | Sovereign | German Confederation member | Strong | Yes | Reuse, but borders may need 1816 review. |
| Brunswick | `BRA` | Brunswick | Reuse vanilla tag | Sovereign | German Confederation member | Strong | Yes | Reuse. |
| Nassau | `NAS` | Nassau | Reuse vanilla tag | Sovereign | German Confederation member | Strong | Yes | Exact January 1, 1816 succession/union details need review before final scripting. |
| Mecklenburg-Schwerin | `MEC` | Mecklenburg | Reuse vanilla tag, relocalize | Sovereign | German Confederation member | Strong | Yes | Display as Mecklenburg-Schwerin. |
| Mecklenburg-Strelitz | `MST` | Mecklenburg-Strelitz | Reuse vanilla tag | Sovereign | German Confederation member | Strong | Yes | Reuse. |
| Oldenburg | `OLD` | Oldenburg | Reuse vanilla tag | Sovereign | German Confederation member | Strong | Yes | Reuse. |
| Lippe | `LIP` | Lippe | Reuse vanilla tag | Sovereign microstate | German Confederation member | Strong | Yes | One-province vanilla fragment. |
| Schaumburg-Lippe | `SCM` | Schaumburg-Lippe | Reuse vanilla tag | Sovereign microstate | German Confederation member | Strong | Yes | One-province vanilla fragment. |
| Waldeck and Pyrmont | `WLD` | Waldeck | Reuse vanilla tag, relocalize | Sovereign microstate | German Confederation member | Strong | Yes | Display as Waldeck and Pyrmont. |
| Frankfurt | `FRM` | Frankfurt | Reuse vanilla tag | Free city | German Confederation member | Strong | Yes | Free city. |
| Hamburg | `HAM` | Hamburg | Reuse vanilla tag | Free city | German Confederation member | Strong | Yes | Free city. |
| Bremen | `BRE` | Bremen | Reuse vanilla tag | Free city | German Confederation member | Strong | Yes | Free city. |
| Lubeck | `LUB` | Lubeck | Reuse vanilla tag | Free city | German Confederation member | Strong | Yes | Free city. |

## German Confederation: Abstraction Or Relocalization Cases

These should be reviewed as a batch before we script anything. Under the approved "moderately strict" rule, the likely answer for many is relocalization or abstraction rather than splitting.

| 1816 polity/problem | Current vanilla support | Proposed handling | Needs new `V**` tag? | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- |
| Anhalt-Dessau, Anhalt-Bernburg, Anhalt-Kothen | `ANH` owns 2 vanilla provinces in `STATE_ANHALT` | Approved: keep one abstracted playable `ANH` | No | Yes | Three historical Anhalt duchies cannot be cleanly represented with only two vanilla-owned Anhalt provinces. |
| Saxe-Coburg-Saalfeld vs vanilla Saxe-Coburg-Gotha | `COB` exists as Saxe-Coburg-Gotha | Approved: relocalize `COB` to Saxe-Coburg-Saalfeld for 1816 | No | Yes | Saxe-Coburg-Gotha is a later post-1826 name. |
| Saxe-Gotha-Altenburg | No obvious vanilla tag | Approved/scripted as `V04` with a one-province `STATE_SAXONY` compromise | Yes | Yes | Uses province `x31E0C0`; chosen to maximize playable German microstates. |
| Saxe-Hildburghausen | No obvious vanilla tag | Approved/scripted as `V05` with a one-province `STATE_SAXONY` compromise | Yes | Yes | Uses province `x5141A0`, split from vanilla `MEI`; chosen to maximize playable German microstates. |
| Schwarzburg-Sondershausen and Schwarzburg-Rudolstadt | `SCW` abstracts Schwarzburg | Approved: keep one abstracted playable Schwarzburg Principalities country | No | Yes | Vanilla has one Schwarzburg fragment; splitting is not required. |
| Hohenzollern-Hechingen and Hohenzollern-Sigmaringen | `HOH` abstracts Hohenzollern | Approved: keep one abstracted playable Hohenzollern Principalities country | No | Yes | Vanilla has one Hohenzollern fragment; splitting is not required. |
| Reuss principalities | No obvious vanilla tags or state ownership | Approved fallback: handwave/omit unless map review is unusually generous | Maybe, but unlikely | No | Reuss Elder/Younger line states may be too small for vanilla geometry. |
| Liechtenstein | No vanilla tag or split-state ownership found; nearby candidate regions include `STATE_EAST_SWITZERLAND` and `STATE_TYROL` | Start ownership removed; keep `V00` inactive/releasable-or-flavor only | Maybe later | No | In-game map review showed the one-province compromise was too large. |
| Lauenburg | No obvious separate vanilla tag | Approved fallback: abstract into Denmark/Holstein handling unless map review is unusually generous | Probably no | No | Historically tied to Danish monarchy; vanilla Schleswig-Holstein region does not expose an obvious Lauenburg tag. |
| Hesse-Homburg | No obvious vanilla tag; joined German Confederation in 1817, not start | Approved fallback: omit/releasable only unless map review is unusually generous | Maybe, but unlikely | No | Important exact-date note: not a German Confederation member on Jan. 1, 1816. |

## Approval Questions For This Batch

Resolved:

1. Strong reuse candidates are approved as the initial German Confederation playable list.
2. Anhalt remains one abstracted playable `ANH`.
3. `COB` should be relocalized to Saxe-Coburg-Saalfeld for 1816.
4. `SCW` and `HOH` remain one abstracted playable country each.
5. Liechtenstein gets a priority map review; Reuss, Lauenburg, and Hesse-Homburg may be omitted/abstracted unless map review is unusually generous.

Additional resolved map-review decisions:

1. Saxe-Gotha-Altenburg and Saxe-Hildburghausen are scripted as `V04` and `V05` with generous one-province compromises in `STATE_SAXONY`.
2. Liechtenstein was tested as `V00` using `STATE_TYROL` province `xD0C0E0`, then removed from start ownership because the map footprint was too large.

## Italy: Vanilla Tag Baseline

Victoria 3 already defines most Italian Restoration-era tags. These rows are planning candidates only until approved.

Historical frame:

- The Congress of Vienna made Francis I of Austria king of Lombardy-Venetia and incorporated it into the Habsburg state.
- Sardinia-Piedmont was restored and gained Genoa/Liguria.
- Parma went to Marie Louise of Austria for her lifetime, with Bourbon-Parma compensated with Lucca.
- Modena and Tuscany returned to Habsburg-related dynasties.
- The Papal States were restored.
- The Bourbon monarchy in the south was restored; the unified Kingdom of the Two Sicilies was formally proclaimed in December 1816, after our January 1, 1816 start date.

### Italy: Strong Reuse Candidates

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Kingdom of Sardinia / Piedmont-Sardinia | `SAR` | Sardinia-Piedmont | Reuse vanilla tag | Sovereign | None | Strong | Yes | Should include Piedmont, Savoy, Nice where represented, Sardinia, and Genoa/Liguria if vanilla state setup supports it. |
| Papal States | `PAP` | Rome / Papal States file | Reuse vanilla tag, relocalize display | Sovereign | None | Strong | Yes | Approved display name: Papal States. |
| Kingdom of Naples and Sicily / Two Sicilies transition | `SIC` | Two Sicilies | Reuse vanilla tag | Sovereign | None | Strong | Yes | Approved display name: Two Sicilies from start for simplicity. |
| Grand Duchy of Tuscany | `TUS` | Tuscany | Reuse vanilla tag | Sovereign | Habsburg-Lorraine dynasty influence | Strong | Yes | Tuscany also gains the State of the Garrisons; vanilla map may abstract this. |
| Duchy of Parma, Piacenza and Guastalla | `PAR` | Parma | Reuse vanilla tag | Sovereign/Restoration duchy | Marie Louise / Austrian dynastic influence | Strong | Yes | Should not be a Bourbon-Parma state at the start if modeling strict 1816. |
| Duchy of Modena and Reggio | `MOD` | Modena | Reuse vanilla tag | Sovereign/Restoration duchy | Habsburg-Este dynasty influence | Strong | Yes | May include Massa/Carrara handling by abstraction. |
| Duchy of Lucca | `LUC` | Lucca | Reuse vanilla tag | Sovereign/Restoration duchy | Bourbon-Parma compensation | Strong | Yes | Temporary duchy; vanilla has a one-province Lucca fragment. |
| Ionian Islands | `ION` | Ionian Islands | Reuse vanilla tag | British protectorate | `GBR` protectorate | Strong | Yes | Vanilla already models `GBR` -> `ION` as protectorate. |
| Malta | `MLT` | Malta | Reuse vanilla tag; make playable British colony | British crown colony | `GBR` colony | Strong | Yes | Implementation may require changing `MLT` country type to `colonial` because Victoria 3's `colony` subject type requires colonial subjects. |

### Italy: Austrian / Releasable Cases

| 1816 polity/problem | Current vanilla support | Proposed handling | Needs new `V**` tag? | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- |
| Kingdom of Lombardy-Venetia | `LOM` and `VEN` tags exist; Lombardy/Venetia are direct `AUS` in vanilla state history; dynamic loc exists for Lombardy-Venetia | Approved: playable Austrian `crown_land` using `LOM` relocalized as Lombardy-Venetia | No | Yes | `crown_land` fits Habsburg crown-land status better than `protectorate`, while preserving playability. |
| Venice / San Marco | `VEN` and `RSM` exist but no vanilla start ownership | Keep as releasable/revolt unless Lombardy-Venetia design needs them | No | No | `RSM` is San Marco, not San Marino. `VEN` remains useful for future Venetian revolts/releasables. |
| Lombardy | `LOM` exists but no vanilla start ownership | Keep as releasable unless Lombardy-Venetia design uses it | No | No | Could be useful for future revolts. |
| San Marino | No obvious vanilla San Marino tag found; `RSM` is San Marco | Start ownership removed; keep `V01` inactive/releasable-or-flavor only | Maybe later | No | In-game map review showed the one-province compromise was too large. |
| Genoa / Liguria | Sardinia-Piedmont owns Piedmont/Sardinia in vanilla; Congress of Vienna grants Genoa to Sardinia | Likely represent inside `SAR`, not as independent Genoa | No | No | Need confirm exact vanilla province/state support when scripting ownership. |
| Nice and Savoy | `SAR` owns Savoy in vanilla; Nice appears abstracted in nearby state setup | Likely represent inside `SAR` | No | No | Need exact state/province ownership review later. |
| Trento / South Tyrol | Direct `AUS` in vanilla | Keep Austrian | No | No | Congress settlement formally annexed Trento to Austria. |

### Italy Approval Questions

Resolved:

1. Strong reuse candidates are approved by default for all regions unless a later conflict is found.
2. `PAP` should display as Papal States.
3. Lombardy-Venetia should be playable under Austria as a `crown_land`, using `LOM` relocalized as Lombardy-Venetia.
4. Malta should be playable as a British crown colony, using `MLT`.
5. San Marino gets a Liechtenstein-style priority map review with tentative tag `V01`.
6. `SIC` should display as Two Sicilies from start for simplicity.

## Rest Of Europe: Consolidated Tag Pass

This section completes the first-pass tag plan for European 1816 polities outside the already-detailed German and Italian sections. Strong vanilla reuse candidates are treated as approved by the standing rule unless a later map or scripting conflict appears. Rows with a real design choice remain "No" until the user approves the batch questions below.

### France And Low Countries

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Kingdom of France | `FRA` | France | Reuse vanilla tag | Sovereign great power | None | Strong | Yes | Bourbon Restoration government setup comes later; tag is clear. |
| United Kingdom of the Netherlands | `NET` | Netherlands | Reuse vanilla tag, relocalize display | Sovereign kingdom | `LUX` personal union already approved | Strong | Yes | Should own the Belgian provinces at start; Belgium is not independent in 1816. |
| Belgium | `BEL` | Belgium | Start absent / releasable only | Not present | Inside `NET` at start | Strong | Yes | Useful for later 1830 revolution content. |
| Flanders | `FLA` | Flanders | Start absent / releasable only | Not present | Inside `NET` at start | Strong | Yes | Releasable/cultural tag only. |
| Wallonia | `WLL` | Wallonia | Start absent / releasable only | Not present | Inside `NET` at start | Strong | Yes | Releasable/cultural tag only. |
| Limburg | `LIM` | Limburg | Start absent / releasable only | Not present | Inside `NET` at start | Medium | Yes | Relevant to later Dutch/Belgian/German border issues, but not a separate 1816 start country. |
| Monaco | `V02` | No usable vanilla tag | Start ownership removed; keep inactive/releasable-or-flavor only | Sardinian-protected microstate, not on start map | Sardinian protection influence | One-province compromise too large | No | In-game map review showed the Nice-strip abstraction was too large. |

### Iberia

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Kingdom of Spain | `SPA` | Spain | Reuse vanilla tag | Sovereign kingdom | None | Strong | Yes | Restored Bourbon Spain. American empire handling belongs to the global pass. |
| United Kingdom of Portugal, Brazil and the Algarves | `POR` | Portugal | Reuse vanilla tag, possible relocalization | Sovereign kingdom/empire | None | Strong | Yes | European tag is clear; Brazil/global possessions need a later Americas pass. |
| Andorra | `V03` | No vanilla tag found | Approved/scripted custom tag | Co-principality microstate | French/Spanish ecclesiastical co-principality | One-province compromise | Yes | Uses `STATE_CATALONIA` province `x2914C3`. |
| Catalonia | `CAT` | Catalonia | Start absent / releasable only | Not present | Inside `SPA` at start | Strong | Yes | Not an 1816 state. |
| Navarre | `NAV` | Navarre | Start absent / releasable only | Not present | Inside `SPA` at start | Strong | Yes | Not an 1816 state. |
| Carlist Spain | `SPC` | Carlist Spain | Start absent / later revolt only | Not present | Inside `SPA` at start | Strong | Yes | Useful for later Carlist content, not a start tag. |

### British Isles And North Atlantic

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| United Kingdom of Great Britain and Ireland | `GBR` | Great Britain | Reuse vanilla tag, relocalize display to United Kingdom if needed | Sovereign great power | Hanover personal union already approved | Strong | Yes | The 1816 state is the post-1801 United Kingdom. |
| Ireland | `IRE` | Ireland | Start absent / releasable only | Not present | Inside `GBR` at start | Strong | Yes | Ireland is not independent in 1816. |
| Scotland | `SCO` | Scotland | Start absent / releasable only | Not present | Inside `GBR` at start | Strong | Yes | Releasable/formable content only. |
| England | `ENG` | England | Start absent / releasable only | Not present | Inside `GBR` at start | Strong | Yes | Releasable/formable content only. |
| Wales | `WLS` | Wales | Start absent / releasable only | Not present | Inside `GBR` at start | Strong | Yes | Releasable content only. |
| Ulster | `ULS` | Ulster | Start absent / releasable only | Not present | Inside `GBR` at start | Medium | Yes | Later releasable only. |
| Iceland | `ICL` | Iceland | Approved: Danish direct/releasable only for first pass | Danish dependency | `DEN` | Strong island support | Yes | Historically under the Danish crown; not a playable subject in the first Europe scripting pass. |
| Greenland | `GRN` | Greenland | Approved: Danish direct/releasable only for first pass | Danish dependency | `DEN` | Strong island support | Yes | More North Atlantic than Europe, but it uses a vanilla tag and is tied to Denmark. |
| Faroe Islands | None proposed | No vanilla tag found | No start tag | Danish dependency | `DEN` | Tiny/poor | Yes | Too small for a first-pass custom tag unless user later wants exhaustive North Atlantic microtags. |
| Gibraltar | None proposed | No vanilla tag found | No start tag | British fortress/colony | `GBR` | Tiny/poor | Yes | Represent through British ownership rather than a playable country. |
| Channel Islands / Isle of Man | None proposed | No vanilla tag found | No start tag | British crown dependencies | `GBR` | Tiny/poor | Yes | Represent through British ownership/claims only. |

### Scandinavia And Finland

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Kingdom of Sweden | `SWE` | Sweden | Reuse vanilla tag | Sovereign kingdom | Norway personal union senior | Strong | Yes | Reuse. |
| Kingdom of Norway | `NOR` | Norway | Reuse vanilla tag | Personal union junior | `SWE` personal union | Strong | Yes | Vanilla already supports `SWE` -> `NOR` personal union. |
| Kingdom of Denmark | `DEN` | Denmark | Reuse vanilla tag | Sovereign kingdom | Holstein/Schleswig personal unions already approved | Strong | Yes | Reuse. |
| Grand Duchy of Finland | `FIN` | Finland | Reuse vanilla tag, dynamic/relocalized display | Personal union junior | `RUS` personal union | Strong | Yes | Vanilla already has `dyn_c_grand_duchy_of_finland` localization. |
| Sapmi | `SMI` | Sapmi | Start absent / cultural releasable only | Not present | Mostly inside Sweden/Norway/Russia | Medium | Yes | Not a state polity in 1816 for this first pass. |

### Eastern Europe, Poland, And Russia

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Russian Empire | `RUS` | Russia | Reuse vanilla tag | Sovereign great power | Finland and Congress Poland personal unions | Strong | Yes | Reuse; western border ownership must be backdated to the Vienna settlement. |
| Congress Poland / Kingdom of Poland | `POL` | Poland | Reuse vanilla tag, relocalize/dynamic display | Personal union junior | `RUS` personal union | Strong | Yes | The Tsar was king of Poland; historical personal-union rule points to `personal_union`. |
| Free City of Krakow | `KRA` | Krakow | Approved: reuse vanilla tag | Free city / jointly protected republic | Austria, Prussia, and Russia guarantee/protection system | Strong | Yes | Represent protection through treaty/guarantee-style diplomacy rather than one overlord. |
| Danzig | `DZG` | Danzig | Start absent / releasable only | Not present | Inside `PRU` at start | Strong | Yes | The Napoleonic Free City was ended before 1816. |
| Baltic Governorates | `UBD` | Baltic | Start absent or releasable-only abstraction | Not present as unified country | Inside `RUS` at start | Strong | Yes | No unified Baltic state in 1816. |
| Estonia | `EST` | Estonia | Start absent / releasable only | Not present | Inside `RUS` at start | Strong | Yes | Releasable content only. |
| Latvia | `LAT` | Latvia | Start absent / releasable only | Not present | Inside `RUS` at start | Strong | Yes | Releasable content only. |
| Lithuania | `LIT` | Lithuania | Start absent / releasable only | Not present | Partitioned among empires | Strong | Yes | Releasable content only. |
| Belarus | `BYE` | Belarus | Start absent / releasable only | Not present | Inside `RUS` at start | Strong | Yes | Releasable content only. |
| Ukraine | `UKR` | Ukraine | Start absent / releasable only | Not present | Split mostly between `RUS` and `AUS` | Strong | Yes | Releasable content only. |
| Crimea | `CRI` | Crimea | Start absent / releasable only | Not present | Inside `RUS` at start | Strong | Yes | The Crimean Khanate no longer exists in 1816. |

### Austrian Non-German Crown Lands

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Kingdom of Hungary | `HUN` | Hungary | Reuse vanilla tag | Austrian crown land | `AUS` crown_land | Strong | Yes | Vanilla already supports an Austrian `crown_land` setup. |
| Grand Principality of Transylvania | `TRS` | Transylvania | Reuse vanilla tag | Austrian crown land | `AUS` crown_land | Strong | Yes | Vanilla already supports an Austrian `crown_land` setup. |
| Kingdom of Croatia | `CRO` | Croatia | Reuse vanilla tag | Austrian crown land | `AUS` crown_land | Strong | Yes | Vanilla already supports an Austrian `crown_land` setup. |
| Kingdom of Bohemia | `BOH` | Bohemia | Approved: Austrian direct/releasable only for first pass | Not playable at start | `AUS` | Strong | Yes | Conservative Austrian internal split keeps Bohemia inside direct Austria unless later expanded. |
| Galicia and Lodomeria | `GAL` | Galicia-Lodomeria | Approved: Austrian direct/releasable only for first pass | Not playable at start | `AUS` | Strong | Yes | Conservative Austrian internal split keeps Galicia inside direct Austria unless later expanded. |
| Galicia / alternate tag | `GLI` | Galicia | Approved: releasable/alternate only unless needed | Not present separately if `GAL` is used | `AUS` | Strong | Yes | Avoid using both `GAL` and `GLI` for the same start polity. |
| Kingdom of Illyria / Austrian Adriatic lands | `TRE` | Trieste | Approved: Austrian direct/releasable only for first pass | Not playable at start | `AUS` | Medium | Yes | Conservative Austrian internal split keeps this inside direct Austria unless later expanded. |
| Slovenia | `SLO` | Slovenia | Start absent / releasable only | Not present | Inside `AUS` at start | Medium | Yes | Not an 1816 polity. |
| Slovakia | `SLV` | Slovakia | Start absent / releasable only | Not present | Mostly inside `HUN`/`AUS` setup | Medium | Yes | Not an 1816 polity. |
| Czechia | `CZH` | Czechia | Start absent / releasable only | Not present | Inside `AUS` at start | Strong | Yes | Use `BOH` for the historical crownland if needed. |

### Switzerland And Tiny Neutral States

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Swiss Confederation | `SWI` | Switzerland | Reuse vanilla tag | Sovereign confederation | Perpetual neutrality settlement | Strong | Yes | Reuse tag; government/law setup comes later. |
| Liechtenstein | `V00` | No vanilla tag found | Start ownership removed; keep inactive/releasable-or-flavor only | Sovereign microstate, not on start map | German Confederation member | One-province compromise too large | No | Removed after in-game map review. |

### Balkans And Ottoman Europe

| 1816 polity | Proposed tag | Vanilla tag/name | Proposed action | Start status | Overlord/system | Map support | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Ottoman Empire | `TUR` | Turkey / Ottoman Empire dynamic loc | Reuse vanilla tag, display as Ottoman Empire | Sovereign empire | Senior power over Balkan principalities | Strong | Yes | Use Ottoman Empire display rather than "Turkey" for the 1816 start. |
| Wallachia | `WAL` | Wallachia | Reuse vanilla tag | Ottoman protectorate/autonomous principality | `TUR` protectorate | Strong | Yes | Vanilla already supports `TUR` -> `WAL` protectorate. |
| Moldavia | `MOL` | Moldavia | Reuse vanilla tag | Ottoman protectorate/autonomous principality | `TUR` protectorate | Strong | Yes | Vanilla already supports `TUR` -> `MOL` protectorate. |
| Serbia | `SER` | Serbia | Reuse vanilla tag | Ottoman protectorate/autonomous principality | `TUR` protectorate | Strong | Yes | 1815/1816 autonomy is close enough for playable subject treatment. |
| Montenegro | `MON` | Montenegro | Reuse vanilla tag | De facto sovereign principality | Ottoman contested claims/influence | Strong | Yes | Make playable; exact Ottoman relation can be tuned later. |
| Greece | `GRE` | Greece | Start absent / revolt and releasable only | Not present | Inside `TUR` at start | Strong | Yes | Greek independence war begins later. |
| Crete | `CRE` | Crete | Start absent / releasable only | Not present | Inside `TUR` at start | Strong | Yes | Not separate in 1816. |
| Cyprus | `CYP` | Cyprus | Start absent / releasable only | Not present | Inside `TUR` at start | Strong | Yes | Ottoman direct possession in 1816. |
| Albania | `ALB` | Albania | Start absent / releasable only | Not present | Inside `TUR` at start | Strong | Yes | Not a start country. |
| Bosnia | `BOS` | Bosnia | Start absent / releasable only | Not present | Inside `TUR` at start | Strong | Yes | Not a start country. |
| Bulgaria | `BUL` | Bulgaria | Start absent / releasable only | Not present | Inside `TUR` at start | Strong | Yes | Not a start country. |
| Romania | `ROM` | Romania | Start absent / formable only | Not present | Moldavia/Wallachia separate at start | Strong | Yes | Later formable or unification result. |
| Yugoslavia | `YUG` | Yugoslavia | Start absent / formable only | Not present | N/A | Strong | Yes | Later formable only. |

### Caucasus Edge Cases

The Caucasus has several vanilla tags, but it sits at the edge of the Europe pass and depends on Russian, Ottoman, and Persian frontier design. Recommended handling: do not script these as part of the Vienna-Europe pass unless the user wants the Caucasus included now.

| 1816 polity/problem | Candidate vanilla tags | Proposed handling | Needs new `V**` tag? | Ready to script | Notes |
| --- | --- | --- | --- | --- | --- |
| Georgia and Georgian kingdoms | `GEO` | Approved: defer to Russia/Ottoman/Persia frontier pass | No | Yes | Much of Georgia had been annexed by Russia by 1816, but exact frontier setup needs separate review. |
| Armenia | `ARM` | Approved: defer to Caucasus/frontier pass | No | Yes | Split across empires; not a simple Vienna-Europe decision. |
| Azerbaijan / khanates | `AZB` | Approved: defer to Caucasus/frontier pass | No | Yes | Requires Persian/Russian treaty context. |
| Dagestan / North Caucasus | `DAG`, `CHC`, `CIR` | Approved: defer to Caucasus/frontier pass | No | Yes | Could become decentralized or playable frontier polities later. |

### Consolidated Batch Questions

Resolved by user approval:

1. Conservative Austrian internal split is approved.
2. Monaco `V02` and Andorra `V03` get the Liechtenstein treatment.
3. Krakow uses an independent Free City plus treaty/guarantee-style protection model.
4. Iceland `ICL` and Greenland `GRN` stay Danish direct/releasable-only for the first Europe scripting pass.
5. Caucasus edge cases defer to the Russia-Ottoman-Persia frontier pass.
6. Portugal uses `POR` for the United Kingdom of Portugal, Brazil and the Algarves; Brazil and overseas ownership wait for the Americas/global pass.
