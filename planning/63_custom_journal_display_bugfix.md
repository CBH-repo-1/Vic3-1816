# Custom Journal Display Bugfix

Date: 2026-05-23

## Issue

The first custom journal-entry package loaded, but GDP progress displayed as current GDP over a zero target, and some journal-entry UI surfaces showed raw localization keys or irrelevant lobby-preview entries.

## Fix

- Changed all custom GDP journal entries from bare `gdp` scripted values to `root.gdp`, matching base-game GDP journal-entry patterns.
- Removed the custom `progress_desc`; the GDP goal already generates the correct progress line, and the extra descriptor duplicated it.
- Added `_goal` and `_status` localization keys for all 84 custom journal entries.
- Added `is_shown_in_lobby` rules for all 84 custom journal entries, generated from `common/history/global/99_cow_1816_custom_journal_entries.txt`, so country selection previews the entries assigned to that country.
- Moved custom journal-entry assignment out of direct history setup. `common/history/global/99_cow_1816_custom_journal_entries.txt` now schedules a hidden startup event one day later, and `events/cow_1816_journal_startup_events.txt` adds the entries after GDP has initialized.
- Added the `cow_1816_custom_journal_entries_added` country variable guard so the delayed startup event cannot duplicate entries if it fires more than once.

## Timing Note

Custom 1816 journal entries are now added by a hidden event with `days = 1`. In a new game they may not appear while paused on January 1, 1816; unpause to January 2 before checking. This avoids the zero-GDP target bug caused by adding GDP-based journal entries during initial history setup.

## Validation

- 84 custom journal entries found.
- 84 lobby-preview rules found.
- 168 `root.gdp` values found.
- 0 bare `gdp` values remain.
- 0 custom `progress_desc` entries remain.
- 84 `_goal` localization keys found.
- 84 `_status` localization keys found.
- 84 completion event references match 84 event definitions.
- 101 delayed startup triggers found.
- 206 delayed journal-entry assignments found.
- No missing event localization keys detected.
- Braces are balanced in the custom journal-entry, event, and global assignment files.
- Modified files are UTF-8 with BOM.

## Loyalists And Radicals

New Spain (`SC1`) currently has no explicit `add_radicals`, `add_radicals_in_state`, or `add_loyalists` history seeding. The base game also seeds these selectively for specific crisis starts rather than assigning nonzero loyalists/radicals to every country. Seeing `0 / 0` at start is expected unless we later decide to add scenario-specific unrest or support.
