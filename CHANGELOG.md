# Changelog

All notable changes to this project are documented here.
Format loosely follows [Keep a Changelog](https://keepachangelog.com/).

## 2026-07-02

### Added
- **Report Builder — Achievement section**: a weekly free-text field to record what
  you achieved; appears above "Next Week Plans" in the report (weekly scope).
- **Report Builder — task blocker details**: setting a task's status to "! Blocker"
  reveals inline **🔒 Blocker reason** and **🔑 How to unblock** fields, which render
  under the task in the report's "Blockers & Risks" section.
- **Report Builder — standalone blockers**: a "Blockers & Risks (not tied to a task)"
  list (add/delete) for blockers unrelated to any task, each with reason + how to
  unblock; rendered in the report's Blockers section (weekly scope).

## 2026-07-01

### Added
- **Report Builder — Monthly report**: pick a scope (Weekly / Monthly) when
  generating; Monthly rolls up every saved week in the current month, merging
  recurring tasks into a date range. (Quarterly Review logic is in place but the
  dropdown option is hidden for now.)
- **Report Builder — per-week history**: each week you edit is snapshotted to
  `localStorage`, so switching weeks loads that week's own tasks/plans/holidays
  (empty week if none). This history is what monthly reports aggregate from.
- **Report Builder — Backup / Restore**: export all data (tasks, week history,
  config) to a timestamped JSON file and restore it later on any browser.
- **Report Builder — week range stepper**: replaced the year-long dropdown with a
  compact `‹ label ›` prev/next stepper plus a **Today** button; you can now step
  to any week, not just the current year's remaining weeks.
- **Report Builder — settings menu**: moved Backup, Restore, and Clear into a ⚙️
  gear menu to declutter the action bar.
- **Home (`index.html`) — collapsible sidebar**: a ☰ button (shown when hidden)
  opens the sidebar and a ✕ in the header closes it; the sidebar is hidden by
  default and the choice is remembered in `localStorage`.

### Changed
- **Report Builder — config field widths**: the User Configuration row is now a
  12-column grid — Department is narrower and Week Range is wider; fields stack
  full-width on screens ≤720px.

### Notes
- Open `report-builder/weekly_tracker.html?selftest` to run the built-in
  aggregation / backup self-checks.
