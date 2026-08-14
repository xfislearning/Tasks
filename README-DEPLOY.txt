TASKS TRACKER — DEPLOYMENT PACKAGE (R16, latest)
=============================================================

FILES (all six app files go in the TOP LEVEL of your GitHub "Tasks" repo):

  index.html      The entire app. R16 changes:
                  1) Plan To-Do "Add work item": the inline "Type the new
                     work item name…" box is gone. Choosing "➕ Create new
                     work item…" now prompts for the name directly, shows
                     a small "New item: X · cancel" confirmation, and a
                     static instruction line explains how to add one when
                     you're not mid-creation.
                  2) Work Records: every row now has an ✎ Edit button next
                     to delete. Edit expands the row into editable fields
                     for date, work item, task, category, hours, and notes
                     — Save commits all of it, Cancel discards. Week
                     navigation closes any open edit row.
                  Google Drive sync is UNCHANGED from the previous
                  release — still a single file at the root of the
                  user's Drive (no "Tasks" folder). No work-item rename
                  feature included in this build.
  manifest.json   PWA config with app shortcuts (long-press the icon).
  sw.js           Service worker, cache v8 (offline + instant updates).
  icon-192.png / icon-512.png
  Tasks-Tracker-Import-Template.xlsx  (keep this exact filename — the app's
                  "Download the import template" link points to it.)

DEPLOY (2 minutes):
  1. github.com -> your "Tasks" repo -> Add file -> Upload files.
  2. Drag ALL SIX files in -> Commit changes.
  3. Wait up to 10 minutes (CDN), then hard-refresh (Ctrl+Shift+R) or
     open in an incognito window.

VERIFY AFTER DEPLOY:
  - Plan To-Do: pick "➕ Create new work item…" from the Work item
    dropdown -> a name prompt appears -> confirm -> "New item: ..." hint
    shows above the dropdown -> pick a category -> Add to week.
  - Work Records: click the pencil on any row -> all six fields become
    editable -> Save updates the row -> Cancel discards changes ->
    changing weeks closes any row left open for editing.
  - View page source -> search "edWiTag" (confirms the latest build is
    live).
