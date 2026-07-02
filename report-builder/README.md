# 📅 Work Tracker & Report Builder

A work tracker that lets you log daily tasks and generate a formatted **weekly, monthly** report ready to paste into an email.

## Features

- Configure your name, email, department, and week range
- Log tasks per day (Monday–Friday) with description and status (Done / In Progress / Blocked)
- Mark days as holidays
- Plan next week's items with priority levels
- **Generate Report** — pick a scope (Weekly / Monthly) then open a review modal with an HTML preview and copy buttons for the email subject and formatted body
  - **Weekly** — the current week's tasks plus a "Next Week Plans" section
  - **Monthly** — rolls up every saved week in the current month; recurring tasks are merged into a date range
- Each week you fill in is snapshotted to `localStorage`, building the history that monthly reports aggregate from
- Data persists in `localStorage` across sessions
- **Backup / Restore** — since data lives in browser `localStorage` (lost if you clear cache), use **⬇ Backup** to download a `.json` snapshot of everything (tasks, week history, and config), and **⬆ Restore** to load it back on any browser/machine

## Usage

Open `weekly_tracker.html` in your browser:

```
start weekly_tracker.html
```
