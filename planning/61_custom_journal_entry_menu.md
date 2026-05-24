# Custom Journal Entry Menu

## Scope

This began as the proposal menu for the first wave of custom 1816 journal-entry content after Package A cleanup.

Status: approved and implemented. The user approved all listed options, so every Option A and Option B entry below has been scripted.

Implementation files:

- `common/journal_entries/99_cow_1816_custom_journal_entries.txt`
- `common/history/global/99_cow_1816_custom_journal_entries.txt`
- `localization/english/cow_1816_journal_entries_l_english.yml`

Implemented shape:

- 84 custom journal-entry definitions.
- 101 assigned playable tags.
- Each entry has a localized title and reason text.
- Each entry is a pinned historical-content journal entry with a GDP-growth objective, giving players a visible 1816 story spine without adding unapproved event rewards yet.
- Later GDP consolidation kept the approved definitions but assigns only one active custom GDP entry per playable tag. The active starts now use the original Option A anchor for each country or regional cluster, with unassigned entries hidden from the lobby preview.

Original approval format requested from the user:

- `both`
- `A only`
- `B only`
- `neither`

## Selection Rules

Countries and clusters are included when they meet at least one of these standards:

- plausible great-power or major-power gameplay path
- already a great power or major regional power in the 1816 start
- especially important to the mod's changed 1816 map
- distinctive playable start that benefits from a custom story spine
- necessary to make another country's journal chain work

Small German/Italian/Indian/etc. states are not all given bespoke entries in this first wave. Many should instead be covered by shared regional systems such as German Confederation, Italian Restoration/Risorgimento, Maratha Confederacy, and British India.

## Core Great And Major Power Menu

| Tag | Country | Option A | Option B | Recommendation |
| --- | --- | --- | --- | --- |
| `GBR` | Great Britain | Postwar Settlement: manage debt, demobilization, anti-slave-trade diplomacy, and the Concert order. | Workshop of the World: coal, textiles, iron, ports, and naval-industrial dominance. | both |
| `FRA` | France | Bourbon Restoration: stabilize restored Bourbon rule against liberal, Bonapartist, and ultra-royalist pressure. | Return to Great Power: rebuild prestige and armed forces, with Algeria/colonial ambitions delayed into a later phase. | both |
| `AUS` | Austria | Congress System: preserve the Vienna settlement, German order, and anti-revolutionary diplomacy. | Habsburg Crownlands: manage Hungary, Bohemia, Lombardy-Venetia, Croatia, and Transylvania. | both |
| `PRU` | Prussia | Reform State: modernize army, administration, education, and the Rhineland/Westphalian acquisitions. | German Dualism: build influence against Austria and prepare a Zollverein/German leadership path. | both |
| `RUS` | Russia | Holy Alliance: defend the restoration order and project influence in Europe/Balkans. | Imperial Borderlands: Poland, Finland, the Caucasus, Siberia, and Alaska. | both |
| `TUR` | Ottoman Empire | Ottoman Recovery: stabilize the empire after war and provincial decentralization. | Eastern Question: manage Serbia, the Danubian Principalities, Egypt, Greece, and European pressure. | both |
| `CHI` | Qing China | Canton System: control foreign trade, opium pressure, and coastal access. | Qing Inner Frontiers: manage Tibet, Mongolia, Xinjiang, Korea, and frontier stability. | both |
| `USA` | United States | Era of Good Feelings / Missouri Question: nationalism, party decline, slavery balance, and sectional compromise. | Continental Frontier: Florida, New Spain border pressure, Indigenous diplomacy, and western settlement. | both |
| `SPA` | Spain | Crisis of the Indies: hold, negotiate with, or fight to recover Spanish America. | Postwar Restoration: debt, army collapse, liberal officers, and absolutist restoration. | both |
| `POR` | Portugal | United Kingdom Across the Atlantic: preserve or rebalance the Portugal-Brazil monarchy. | Liberal Revolution: delayed pressure toward constitutionalism and the return of the court. | both |
| `BRZ` | Kingdom of Brazil | Kingdom in the Tropics: develop Brazil as the imperial center of the Portuguese monarchy. | Road to Independence: autonomy, elite support, and the 1822-style break with Portugal. | both |
| `BIC` | East India Company | Before the Third Anglo-Maratha War: contain, confront, or bargain with the Maratha powers. | Company Raj Foundations: revenue, sepoy army, and princely-state loyalty. | both |

## High-Interest Regional Power Menu

| Tag | Country | Option A | Option B | Recommendation |
| --- | --- | --- | --- | --- |
| `PER` | Persia | Qajar Restoration: recover from Gulistan and decide how hard to press the Caucasus question. | Centralize the Realm: tribal autonomy, taxation, army reform, and frontier governors. | both |
| `EGY` | Egypt | Muhammad Ali's State: build the army, bureaucracy, industry, and schools. | Ambition of Egypt: expansion toward Sudan, Arabia, Crete, and the Levant while balancing the Ottomans. | both |
| `NET` | Netherlands | United Kingdom of the Netherlands: integrate north, south, Luxembourg, and the Belgian provinces. | Colonial Commercial Revival: rebuild trade and the Dutch East Indies after the Napoleonic era. | both |
| `SWE` | Sweden-Norway | New Scandinavian Balance: manage Norway and recover from the loss of Finland. | Baltic Ambition: rebuild military and diplomatic influence without overcommitting. | both |
| `DEN` | Denmark | Postwar Denmark: recover from bankruptcy, fleet loss, and Norway's loss. | Schleswig-Holstein Question: hold the composite monarchy together. | both |
| `JAP` | Japan | Late Tokugawa Order: preserve shogunate authority, domain hierarchy, and sakoku. | Rangaku and Reform: selective modernization before forced opening. | both |
| `KOR` | Korea | Hermit Kingdom: preserve Joseon isolation and tributary order. | Court Reform: manage yangban power, corruption, and state capacity. | both |
| `SIA` | Siam | Chakri Consolidation: centralize tributary networks and Bangkok authority. | Between Empires: balance Dai Nam, Burma, Britain, and Malay frontier pressure. | both |
| `DAI` | Dai Nam | Nguyen State-Building: consolidate Vietnam under the Nguyen dynasty. | Mekong Rivalry: compete with Siam over Cambodia, Laos, and regional prestige. | both |
| `BUR` | Burma | Konbaung Ascendancy: rebuild and project power in mainland Southeast Asia. | Company Frontier: tension with British India and frontier states before the Anglo-Burmese wars. | both |
| `DEI` | Dutch East Indies | Restore Dutch Rule: reassert control after the British interregnum. | Java Revenue State: plantations, taxation, local resistance, and colonial bureaucracy. | both |
| `PAN` | Punjab / Sikh Empire | Sikh Empire Consolidation: army reform, administration, and Lahore authority. | Frontier Between Empires: manage Afghanistan, Kashmir, Sindh, and British India. | both |

## Regional Systems Covering Multiple Playables

| Tags | Cluster | Option A | Option B | Recommendation |
| --- | --- | --- | --- | --- |
| `SAT`, `GWA`, `IND`, `NAG` | Maratha Confederacy | Confederacy Restored: rebuild Maratha cohesion and decide the Peshwa's role. | Subsidiary Alliance: resist, accept, or manipulate Company influence. | both |
| `SC1`, `SC2`, `SC3`, `CHL`, `ARG`, `PRG`, `URU` | Spanish American Independence | Wars of Independence: active revolutionary/royalist struggle across Spanish America. | Recognition and Fragmentation: diplomacy, debt, legitimacy, and successor-state formation after independence. | both |
| `SIC`, `SAR`, `PAP`, `TUS`, `MOD`, `PAR`, `LOM` | Italian Restoration | Restoration Italy: Austrian influence, Bourbon/Papal/Savoyard legitimacy, and post-Napoleonic order. | Seeds of the Risorgimento: liberal nationalism, reform, and future unification paths. | both |
| `BAV`, `SAX`, `HAN`, `WUR`, `BAD`, `HES`, `HEK`, free cities, and German minors | German Confederation | Confederation Politics: federal defense, Austrian presidency, Prussian influence, and minor-state sovereignty. | German Economic Union: customs integration, rail/market development, and future Zollverein leadership. | both |
| `SER`, `MOL`, `WAL`, `MON`, possible later `GRE` content | Balkan Autonomy | Ottoman Vassals: autonomy, tribute, reforms, and nationalist pressure. | Balkan Uprisings: delayed revolt/independence paths and great-power intervention. | both |
| `KAB`, `KAN`, `HER`, `KUN`, `MAI`, `KAF`, `V10` | Afghanistan / Frontier | Afghan Fragmentation: reunify or preserve the Durrani successor states. | Between Empires: Persia, Punjab, Bukhara, and Company pressure. | both |
| `BUK`, `KOK`, `KHI`, `KZH`, `OZH`, `UZH` | Central Asian Khanates | Khanate Rivalries: trade, raids, legitimacy, and oasis politics. | Russian Shadow: diplomacy, border forts, and later imperial pressure. | both |

## Distinctive Playable Starts

| Tag | Country | Option A | Option B | Recommendation |
| --- | --- | --- | --- | --- |
| `HAI` | Haiti | Two Haitis: stabilize or reunify the split Haitian political world. | French Recognition: delayed French indemnity/recognition crisis after the 1820s. | both |
| `ALD` | Regency of Algiers | Regency and Corsairs: naval commerce, tribute, Ottoman ties, and European tension. | Road to Algiers: delayed diplomatic crisis leading toward possible French invasion. | both |
| `MOR` | Morocco | Makhzen and the Tribes: state authority over autonomous regions. | Atlantic/Maghreb Pressure: trade, border pressure, and European diplomacy. | both |
| `TUN`, `TRI` | Tunis / Tripolitania | Barbary Autonomy: Ottoman connection, local dynasties, and European pressure. | Mediterranean Commerce: corsair decline, trade, and naval diplomacy. | both |
| `SOK` | Sokoto | Caliphate Consolidation: administration, scholarship, and subject emirates. | West African Jihad Legacy: expansion, legitimacy, and neighboring states. | both |
| `MAD` | Imerina | Radama's Kingdom: unify Madagascar and build the army/state. | Foreign Mission and Trade: British/French ties, education, and coastal diplomacy. | both |
| `ZUL` | Zulu | State Formation: Shaka-era consolidation and military institutions. | Highveld Upheaval: regional warfare, migration, and competition with neighbors. | both |
| `COM` | Comancheria | Lords of the Southern Plains: horse trade, raiding, and diplomacy with New Spain/USA. | Band Confederacy: keep a playable polity coherent without turning it into a conventional state. | both |
| `LKT` | Lakota | Western Expansion: move into and dominate the northern plains. | Plains Trade Network: horses, bison, diplomacy, and intertribal relations. | both |
| `HAW` | Hawaii | Kamehameha's Kingdom: consolidate the islands and royal authority. | Pacific Crossroads: trade, missionaries, whalers, and foreign influence. | both |
| `HBC` | Hudson's Bay Company | Fur Trade Empire: posts, trade routes, and relations with Indigenous powers. | Red River and British North America: settlement pressure and colonial integration. | both |

## Lower Priority / Deferred

These countries are playable or interesting, but probably do not need bespoke first-wave custom journal entries unless the user wants wider coverage immediately:

- most German microstates individually, because the German Confederation system should cover them
- most Italian minors individually, because the Italian Restoration/Risorgimento system should cover them
- most Indian princely states individually, because Maratha/BIC/shared India systems should cover them first
- most decentralized/local tags, unless already promoted for gameplay variety
- small colonial tags such as `MLT`, `BCE`, `NEW`, `NBS`, `NVS`, `ONT`, `QUE`, `JAM`, and `BAH`, unless a later colonial flavor pass is requested

## Implementation Recommendation

Implemented in one approved wave:

1. Great/major powers with no current custom start spine: `GBR`, `FRA`, `PRU`, `RUS`, `TUR`, `CHI`, `USA`, `SPA`, `POR`, `BRZ`, `BIC`.
2. Regional power anchors: `PER`, `EGY`, `NET`, `SWE`, `DEN`, `JAP`, `SIA`, `DAI`, `BUR`, `DEI`, `PAN`.
3. Shared systems: Spanish America, Maratha Confederacy, German Confederation, Italian Restoration, Balkans, Afghanistan, Central Asia.
4. Distinctive starts: `HAI`, `ALD`, `MOR`, `TUN`, `TRI`, `SOK`, `MAD`, `ZUL`, `COM`, `LKT`, `HAW`, `HBC`.

This order gets the most visible map starts covered first while letting shared systems do the heavy lifting for many playable minors.
