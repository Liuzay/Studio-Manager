# Studio Manager 3.0.0 — UI Refresh + Reliable Twitch Studio

This release repairs the Twitch generation workflow and improves the app-wide interface. The generator now initializes after the Twitch module is available, provides visible progress, supports selectable generated titles, and lets you copy the full plan. A guarded renderer prevents one unfinished module from disabling the rest of Studio Manager.


## 3.0.1 Twitch reliability hotfix
- Moved Twitch controls into an isolated self-contained module.
- Rebound every Twitch button with fresh event listeners.
- Added visible module status and local Twitch-specific persistence.
- Fixed plan generation, checklist, schedule, clip package, overlay accent, and session logging controls.
