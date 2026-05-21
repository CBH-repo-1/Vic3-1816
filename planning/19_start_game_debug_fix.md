# Start Game Debug Fix

## Trigger

The mod loaded to the Victoria 3 main menu, but failed when starting a new game after the 1816 map passes.

## Log Signature

The active log showed one stale province list plus vanilla 1836 history trying to create invalid armies, navies, characters, and declared interests for tags or regions that no longer match the 1816 setup.

Key stale references included:

- Armenia used obsolete province IDs that no longer exist in the current base-game map.
- France's vanilla North Africa army before France owns a North Africa HQ.
- Great Britain's vanilla Italy/Mediterranean formations before Britain owns an Italy HQ.
- Russia's vanilla Poland formation after Poland-region ownership was changed.
- Greece, Belgium, Carlist Spain, Texas, and Mexico vanilla start formations after those tags were removed from the 1816 start map.
- Belgium, Mexico, Greece, and the USA vanilla declared interests that no longer validate in the 1816 start.

## Implemented Fix

Added mod-side history overrides:

- `common/history/military_formations/00_military_formations_europe.txt`
- `common/history/military_formations/01_military_formations_north_america.txt`
- `common/history/interests/00_interests.txt`

These are adapted copies of the vanilla files with only the stale 1836 references removed.

Corrected `STATE_ARMENIA` in `common/history/states/99_cow_1816_mena_states.txt` to use the current vanilla province IDs, and removed Russia's two vanilla combat-unit entries that were still placed in Armenia after the 1816 setup assigns that state to Persia.

Added blank character-history overrides for removed 1836 start tags:

- `common/history/characters/bel - belgium.txt`
- `common/history/characters/gre - greece.txt`
- `common/history/characters/mex - mexico.txt`
- `common/history/characters/spc - carlist spain.txt`
- `common/history/characters/tex - texas.txt`

## Next Verification

Launch the mod and try starting a new game again. If it still fails, inspect the fresh `error.log` first; any remaining failures should now be a smaller list of stale vanilla start-history references.
