TASKS TRACKER — DEPLOYMENT PACKAGE (R12 mobile build, latest)
=============================================================

FILES (all six app files go in the TOP LEVEL of your GitHub "Tasks" repo):

  index.html      The entire app. Includes: Excel import with auto-created
                  work items + in-app template link (R11); Install-app button
                  with iOS instructions fallback, full-screen iOS treatment,
                  home-screen shortcuts, hash routing (#plan/#records/#dash);
                  mobile header overflow fix (nav collapses at <=860px,
                  page-level horizontal clip).
  manifest.json   PWA config with app shortcuts (long-press the icon).
  sw.js           Service worker, cache v4 (offline + instant updates).
  icon-192.png / icon-512.png
  Tasks-Tracker-Import-Template.xlsx  (keep this exact filename — the app's
                  "Download the import template" link points to it)

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
    items auto-created by name, confirmation shows counts.
