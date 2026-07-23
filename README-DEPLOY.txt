TASKS TRACKER — DEPLOYMENT PACKAGE (R15 mobile build, latest)
=============================================================

R15: Editable Work Records. Each logged entry in Work Records now has
an ✎ Edit button next to the ✕ delete button. Clicking it expands that
row in place into an editable panel — date, work item, category, hours,
status, progress, task description, and notes — with Save changes /
Cancel buttons. No more delete-and-redo to fix a typo or wrong hours.

R14: Auto-reconnect sync. Previously, if the app opened without a solid
connection (common on mobile), Google sign-in would silently fail to
re-authenticate and the app would stay in local-only mode until you
manually signed out and back in. Now it automatically retries getting
a fresh Google session — and syncs with Drive — whenever your phone
reconnects to the network or you switch back into the app. No manual
sign-out needed anymore.

FILES (all six app files go in the TOP LEVEL of your GitHub "Tasks" repo):

  index.html      The entire app. Includes: Excel import with auto-created
                  work items + in-app template link, a choice on import
                  between "Add to existing data" and "Replace all existing
                  data" (R13), success message with counts after import;
                  Install-app button with iOS instructions fallback,
                  full-screen iOS treatment, home-screen shortcuts, hash
                  routing (#plan/#records/#dash); mobile header overflow fix
                  (nav collapses at <=860px, page-level horizontal clip).
  manifest.json   PWA config with app shortcuts (long-press the icon).
  sw.js           Service worker, cache v7 (offline + instant updates).
  icon-192.png / icon-512.png
  Tasks-Tracker-Import-Template.xlsx  (keep this exact filename — the app's
                  "Download the import template" link points to it. R13:
                  Category now lives on Work Records instead of Plan To-Do.)

DEPLOY (2 minutes):
  1. github.com -> your "Tasks" repo -> Add file -> Upload files.
  2. Drag ALL SIX files in -> Commit changes.
  3. Wait up to 10 minutes (CDN), then hard-refresh (Ctrl+Shift+R) or
     open in an incognito window.

INSTALL ON PHONES:
  iPhone: the header shows "Install app" -> tap it for the walkthrough
          (Safari -> Share -> Add to Home Screen -> Add).
  Android: "Install app" appears when not yet installed -> one tap.
          Already installed = button hidden by design; use the installed app.
  Long-press the installed icon for Plan / Log / Dashboard shortcuts.

VERIFY AFTER DEPLOY:
  - View page source -> search "isIOS" (confirms the latest build is live).
  - Signed out: Backup -> template download link works.
  - Signed in: Backup -> Import from Excel with a filled template ->
    a dialog appears with item/plan/record counts and two choices,
    "Add to existing data" or "Replace all existing data" -> after
    either, a message confirms what was imported.
