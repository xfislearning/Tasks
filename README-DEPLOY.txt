TASKS TRACKER — DEPLOYMENT PACKAGE (R16.1, latest)
=============================================================

FILES (all six app files go in the TOP LEVEL of your GitHub "Tasks" repo):

  index.html      R16.1: fixes a CSS bug from R16 where the "New item:
                  ... cancel" hint under the work-item dropdown was
                  permanently visible (even with no name filled in),
                  regardless of whether you were actually creating a new
                  item. Cause: the hint's CSS set "display:flex" directly,
                  which overrides the browser's built-in rule for hiding
                  elements marked hidden. Fixed by scoping that rule to
                  :not([hidden]). Also tightened the static instruction
                  wording to "To add a new item, choose ➕ Create new work
                  item… from the dropdown above." No other logic changed
                  from R16: Drive sync is still a single file at Drive
                  root (no folder), no rename feature.
  manifest.json   PWA config with app shortcuts (long-press the icon).
  sw.js           Service worker, cache v9 (offline + instant updates).
  icon-192.png / icon-512.png
  Tasks-Tracker-Import-Template.xlsx  (keep this exact filename — the app's
                  "Download the import template" link points to it.)

DEPLOY (2 minutes):
  1. github.com -> your "Tasks" repo -> Add file -> Upload files.
  2. Drag ALL SIX files in -> Commit changes.
  3. Wait up to 10 minutes (CDN), then hard-refresh (Ctrl+Shift+R) or
     open in an incognito window.

VERIFY AFTER DEPLOY:
  - Plan To-Do: with an existing item selected, the "New item..." hint
    should NOT be visible — only the category hint (if applicable) and/or
    the static "To add a new item..." instruction should show.
  - Pick "➕ Create new work item…" -> confirm the name prompt -> now ONLY
    the "New item: <name> · cancel" hint shows, nothing else.
