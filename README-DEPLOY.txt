TASKS TRACKER — DEPLOYMENT PACKAGE (R17, latest)
=============================================================

WHAT'S NEW IN R17
  - Removed "Work Plan Ahead" and "Random To-Do" (menu, Home cards,
    Dashboard card, Excel export sheets, app shortcut). Plan for the Week,
    Work Records and Dashboard are unchanged.
    Anything you had entered in those two features stays inside your
    tasks-tracker-data.json file on Drive (hidden, not deleted).
  - Google Calendar permission removed: Work Plan Ahead was the only
    feature that used it. Sign-in now asks for Google Drive only.
    Calendar events it created earlier stay in your Google Calendar.
  - Edit categories: in the Category dropdown on Plan for the Week or
    Log Work, choose "✎ Edit categories…". Click ✎ to rename (fix typos).
    The new name is applied to all work items and ALL past records, so
    past weeks/months and the Dashboard update too. Renaming a category
    to a name that already exists merges the two (you'll be asked first).
    ✕ still removes a category from the list (items keep the old label).

FILES (all six app files go in the TOP LEVEL of your GitHub "Tasks" repo):
  index.html      the app (R17)
  manifest.json   PWA config with app shortcuts (Work Plan Ahead removed)
  sw.js           Service worker, cache v11 (forces the update to load)
  icon-192.png / icon-512.png
  Tasks-Tracker-Import-Template.xlsx  (keep this exact filename)

DEPLOY (2 minutes):
  1. github.com -> your "Tasks" repo -> Add file -> Upload files.
  2. Drag ALL SIX files in -> Commit changes.
  3. !! CHECK THE CUSTOM DOMAIN: Repo -> Settings -> Pages -> make sure
     "Custom domain" still says tasks.qentrotech.com (re-enter + Save if
     blank). The CNAME file is not in this zip, so don't delete the one
     already in your repo.
  4. Wait up to 10 minutes, then hard-refresh (Ctrl+Shift+R) or open in
     an incognito window.

VERIFY AFTER DEPLOY:
  - Menu shows: Home · Plan for the Week · Work Records · Dashboard.
  - Plan for the Week -> Category dropdown -> "✎ Edit categories…" ->
    rename a category -> close -> its records show the new name.
