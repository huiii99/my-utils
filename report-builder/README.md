# 📅 Work Tracker & Report Builder

A pair of work trackers that generate formatted reports ready to paste into an email.

## Features

- Configure your name, email, department, and week range
- Choose the **Daily Work Tracker** to split tasks across Monday–Friday
- Choose the **Weekly Work Tracker** to log tasks in one selectable-week card labeled with the full week range
- Log tasks per day (Monday–Friday) with description and status (Done / In Progress / Blocked)
  - Setting a task to **Blocked** reveals inline fields to record the blocker reason and how to unblock it, which appear in the report's "Blockers & Risks" section
- Log standalone **Blockers & Risks** not tied to any task (reason + how to unblock)
- Record a weekly **Achievement** summary
- Mark days as holidays
- Plan next week's items with priority levels
- **Generate Report** — pick a scope (Weekly / Monthly) then open a review modal with an HTML preview and copy buttons for the email subject and formatted body
  - **Weekly** — the current week's tasks plus a "Next Week Plans" section
  - **Monthly** — rolls up every saved week in the current month; recurring tasks are merged into a date range
- Each week you fill in is snapshotted to `localStorage`, building the history that monthly reports aggregate from
- Weekly tracker data is stored separately from daily tracker data, and its generated report uses the full week range for each task
- Data persists in `localStorage` across sessions
- **Backup / Restore** — since data lives in browser `localStorage` (lost if you clear cache), use **⬇ Backup** to download a `.json` snapshot of everything (tasks, week history, and config), and **⬆ Restore** to load it back on any browser/machine; weekly backup filenames use the selected Monday-Friday date range
- New weekly tasks, blockers, and next-week plans hide their optional **Reference link** field until you click **Link**, unless enabled by your Configuration defaults
- Notes support multiple lines, including in generated reports
- Click a task's **Review** button to mark it as pending review and reveal an optional **Pending review by** field (independent of the reference link). Selected tasks appear in the weekly report's "PR/GH/Work Item Pending Review" section instead of "Completed Tasks" or "In Progress", even without reviewer names. Turning Review off restores their original status placement. Blocked tasks remain in "Blockers & Risks"; monthly and quarterly reports are unchanged.

## Usage

From the main app, select **Weekly Work Tracker**. Its embedded view fills the viewport height; longer content scrolls inside the tracker. Choose the week from the top action bar; the bottom-right settings gear contains **Configuration**, backup, restore, and clear actions.

### Weekly tracker configuration

Enter the required name, email, and department/team in **Configuration**. Under **Defaults for new items**, independently enable **Reference link** (tasks, plans, and blockers) or **Pending review** (tasks only). Both start off on fresh use. Changes save automatically in this browser and apply to newly added items and the blank task seeded when opening an unsaved week. They never change existing items, their individual Link/Review toggles, URLs, or reviewer names.

The weekly defaults persist across page reloads, separately from weekly records and daily tracker data. Backups include them; restoring an older backup without defaults resets both off while preserving the backed-up item settings.

To run the inline regression suite, open `weekly_tracker_v2.html?selftest` in a browser. Success logs `SELFTEST PASS` and sets `document.documentElement.dataset.selftest` to `pass`; preference tests restore the original storage, defaults, and tracker state.

Open `weekly_tracker.html` in your browser:

```
start weekly_tracker.html
```

Or open the weekly-only tracker:

```
start weekly_tracker_v2.html
```
