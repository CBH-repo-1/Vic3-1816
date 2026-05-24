# Global Relations And Rivalries Pass

This pass rebuilds the 1816 start's basic diplomatic opinion layer after the mod's empty `00_relations.txt` and `00_rivalries.txt` overrides remove vanilla 1836 assumptions.

## Scope

- Add a conservative `99_cow_1816_relations.txt` layer.
- Add a sparse `99_cow_1816_rivalries.txt` layer.
- Keep most tension as relations rather than hard rivalries so later journals, wars, and crises can escalate it deliberately.

## Implemented Relations

- Great power and Congress-era relations:
  - Britain, Austria, Prussia, and Russia start broadly cooperative.
  - France starts moderately cold with the anti-Napoleonic coalition and the Netherlands.
  - Britain keeps strong ties to Portugal, British India, Hanover, and colonial subjects.
  - Austria and Prussia receive positive relations with the major German and Italian settlement states.
- Atlantic and Americas:
  - Spain has positive relations with its remaining colonial subjects and negative relations with de facto independent Spanish-American states.
  - Portugal and Brazil have strong positive relations, while Portugal/Brazil and Banda Oriental remain tense.
  - The United States has border tension with New Spain, Comancheria, Lakota, HBC, and Russian America.
- Ottoman, Persian, and MENA sphere:
  - Russia/Ottoman and Russia/Persia tensions are represented.
  - Ottoman relationships with North African dependents are positive, while Egypt, Serbia, Moldavia, and Wallachia remain strained.
  - Egypt/Hejaz and Egypt/Nejd relations reflect the ongoing anti-Diriyah conflict.
- Asia:
  - Qing relations with Korea and Tibet are positive.
  - Siam/Vietnam/Cambodia and Burma/Shan tensions are represented.
  - British India has positive relations with approved Company protectorates and negative relations with major unresolved Maratha powers.
  - Dutch East Indies relations with Yogyakarta and Surakarta are positive, with Aceh/Brunei/Bali tensions kept moderate.
- Africa and Indian Ocean:
  - Oman/Zanzibar, Oyo/Dahomey, and Cape frontier relations receive basic starting values.

## Implemented Rivalries

Hard rivalries were limited to high-confidence, gameplay-significant tension:

- `RUS` and `TUR`.
- `SIA` and `DAI`.
- `SPA` and `ARG`.
- `EGY` and `NEJ`.

## Deliberately Deferred

- No hard USA/Comanche or USA/Lakota rivalry yet; relations are negative, but hard rivalries may over-punish the playable indigenous setup.
- No hard BIC/Maratha rivalry yet; Nagpur, Indore, and Gwalior have negative relations, but the Third Anglo-Maratha War should probably be event/journal driven.
- No hard Russia/Persia, Russia/Circassia, or Portugal/Banda Oriental rivalry yet; these remain negative-relation clusters because Victoria's rivalry rules are sensitive to rank and recognition.
- No broad German Confederation diplomatic web beyond major Austrian/Prussian affinities.
- No detailed Balkan nationalist or South American independence relation mesh beyond the highest-confidence starts.
- No truce, alliance, guarantee, obligation, or war-start layer in this pass.

## Next Recommendation

In-game check the diplomacy map modes for:

- whether rivalry icons appear only in the intended clusters,
- whether Spain's colonial subjects still look cohesive,
- whether `COM` and `LKT` remain playable despite negative USA relations,
- whether BIC's Indian diplomacy is tense without causing immediate runaway wars.
