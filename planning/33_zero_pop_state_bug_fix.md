# Zero-Pop State Bug Fix

## Trigger

In-game review after the dedicated military pass showed many deep red states in standard-of-living map mode. The user specifically checked Brazil and Comancheria and found states with 0 pops.

## Root Cause

The mod had been layering regional state-history files like `99_cow_1816_south_america_states.txt` on top of vanilla `00_states.txt`.

That works for ownership colors, but it creates a bad duplicate-state pattern when the same tag already owned the vanilla state:

- the original vanilla state object kept the `region_state:TAG` pop bucket
- the original object lost its provinces after the later ownership/province reassignment
- the new 1816 state object received the provinces
- the new object had no pop bucket, so it appeared as a 0-pop state in game

This showed up clearly in the live save:

- Brazil had pop-bearing but province-empty objects for states like Bahia and Mato Grosso, plus separate province-owning 0-pop objects.
- Comancheria had the same problem in Kansas, Oklahoma, New Mexico, and Texas.
- Spain had the same problem in Aragon and Catalonia.

## Fix

Generated a single active state-history override:

- `common/history/states/00_states.txt`

The generated file starts from vanilla `00_states.txt` and directly replaces the 167 approved 1816 state blocks from the old regional patch files.

Removed the old regional overlay files:

- `99_cow_1816_africa_states.txt`
- `99_cow_1816_asia_states.txt`
- `99_cow_1816_caribbean_states.txt`
- `99_cow_1816_central_asia_states.txt`
- `99_cow_1816_europe_states.txt`
- `99_cow_1816_india_states.txt`
- `99_cow_1816_mena_states.txt`
- `99_cow_1816_north_america_states.txt`
- `99_cow_1816_oceania_states.txt`
- `99_cow_1816_south_america_states.txt`
- `99_cow_1816_z_followup_states.txt`

## Validation

Static validation after the merge:

- active state-history files: 1
- state blocks: 673
- create-state entries: 1,049
- duplicate state/country pairs: 0
- province-owning state/country pairs without matching pop blocks: 0
- brace depth: clean

Focused validation confirms Brazil, Comancheria, Spain, Paraguay's Mato Grosso fragment, and the relevant frontier split states all have pop blocks attached to their province-owning state/country pairs.

## Follow-Up

Needs in-game verification after sync. The previous save still contains the old duplicate objects; a fresh new game is required to test the fix.
