TASKS TRACKER — DEPLOYMENT PACKAGE (mobile-app build)
=====================================================

FILES (all go in the TOP LEVEL of your GitHub "Tasks" repo):
  index.html      App (R12: Install-app button, iOS full-screen + safe areas,
                  home-screen shortcuts, hash routing; plus Excel import R11
                  and everything before)
  manifest.json   PWA config with app shortcuts (long-press the icon ->
                  jump straight to Plan / Log / Dashboard)
  sw.js           Service worker (cache bumped to v4)
  icon-192.png / icon-512.png
  Tasks-Tracker-Import-Template.xlsx   (keep this exact filename)

DEPLOY: upload all six files -> Commit -> wait <=10 min -> hard refresh.

INSTALLING AS A MOBILE APP:
  Android (Chrome): an "Install app" button appears in the app header ->
    one tap installs it. (Or menu -> Install app.)
  iPhone (Safari): Share -> Add to Home Screen. Opens full-screen with the
    status bar blending into the navy header.
  Desktop (Chrome/Edge): the same Install button, or the install icon in
    the address bar.

After installing, long-press the app icon to see the Plan To-Do /
Work Records / Dashboard shortcuts.
