# Rubric: redeploy

What it names: putting a new version of the app on its hosts in place of the running one. Nearest
confusable: restart.
### q-redeploy-vs-restart

- **goal:** `w-redeploy`
- **move:** DISTINGUISH
- **answer:** a restart stops the running app and starts the same version of it again. A redeploy
  puts a new version of the app on the host in place of the one that was running, and the host may
  set it up on a fresh server to do it. One runs the same code again; the other swaps in different
  code.
- **credit:** full for the difference that matters: a redeploy replaces the running app with a new
  version, while a restart starts the same version again. No credit for "a redeploy happens on the
  host and a restart on your laptop", an incidental difference with nothing about a new version.
  Do not accept "a redeploy loses
  your data and a restart doesn't": on some hosts a restart wipes an ephemeral disk too, and data on
  a volume survives both.
