# Changelog

## 2.4.0 — Grouped Navigation & Storage Insight (2026-08-02)

### Changed
- Reorganized the 18-tab navigation bar into six logical groups with subtle dividers: Studio (Studio, Studio Room, Ignatz), Create (Create, Posts, Calendar, Ideas), Grow (Analytics, Goals, Timeline, Backlog), World (Characters, Art Vault, Garden), Business (Commissions, Business, Artist Row), and Settings — instead of one long, unordered scrolling row.
- On wider screens (desktop/tablet, >820px) the tab bar now wraps onto rows instead of forcing horizontal scrolling through all 18 tabs. Mobile keeps the compact scrolling row since the bottom dock already covers quick navigation there.
- Gave the Ignatz tab an emoji (🤖) to match every other tab's icon + label pattern.

### Added
- A storage usage meter in Settings showing roughly how much of the browser's local storage the app is using, color-coded (calm → amber → red) with a nudge to back up and trim photos once usage gets high.
- A confirmation prompt before importing a backup, since doing so instantly replaces all current data with no way back.

### Fixed
- The v2.3 migration step was writing to local storage on every single app launch, regardless of whether anything changed, and bypassed the quota-safety handling added in 2.3.1. It now only writes when the app version actually changes, and does so safely.

## 2.3.1 — Reliability patch (2026-08-02)

### Fixed
- `save()` no longer fails silently when local storage is full; the person is now warned and told how to free up space instead of losing their latest change with no explanation.
- Character photos are now downscaled and compressed on upload the same way Composer and Inspiration Garden photos already are, instead of being stored at full resolution — this was inflating local storage usage and risking the quota issue above.
- Importing a backup file now runs through the same type-normalization logic used on first load, so an older or hand-edited backup can no longer leave a field with the wrong data type and crash a view after import.
- Service worker cache version bumped so this fix actually reaches people with the app already installed.

## 2.3.0 — Design System & Ignatz (2026-08-01)

### Added
- Original animated CSS avatar for Ignatz with calm, thinking, proud, excited, and sleepy states.
- Living Studio ambience: sunlight, drifting dust, steam, plants, clock, and string lights.
- Shared StudioUI helpers for cards, badges, empty states, and buttons.
- Professional release metadata and automatic v2.3 data migration.
- Release information panel in Settings.

### Improved
- Unified spacing, radii, shadows, typography, buttons, cards, form fields, and focus states.
- Mobile safe-area support, sticky glass header, native-style bottom dock, touch targets, and iOS input sizing.
- Accessibility with visible keyboard focus and reduced-motion support.
- Renamed visible references from Ignacio to Ignatz.

### Compatibility
- Existing local data and v2.2 backups remain supported. Internal legacy keys are retained intentionally.
