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

### q-interpret-redeploy

- **goal:** `w-redeploy`
- **move:** INTERPRET
- **answer:** that in about a minute the host will replace the running app with a new version that
  has the fix in it, and the fixed page will then be what users see. It rules out the fix being live
  already: until the redeploy finishes, the old version with the typo is still the one running. It
  also rules out the change being patched into the running app in place.
- **credit:** full for recovering the claim (the host will swap the running app for a new version
  containing the fix) and what it rules out (the fix is not live yet; the old version runs until
  then). Half for the claim without anything it rules out. Do not accept "the host will restart the
  app", which loses the new version.

### q-catch-nightly-restart

- **goal:** `w-redeploy`
- **move:** CATCH
- **answer:** a restart is not a redeploy. A redeploy puts a new version of the app on the host in
  place of the one that was running; a restart stops the running app and starts the same version
  again. So the nightly restart puts no new version anywhere, and the app is redeployed only when a
  new version is put in place.
- **credit:** full for naming the actual error: a redeploy means putting a new version of the app in
  place of the running one, and a restart only starts the same version again, so the nightly restart
  is not a redeploy. Half for "a restart is different from a redeploy" or "a restart doesn't change
  the code" with nothing about a redeploy putting a new version in place. Do not accept a different
  quibble: "restarting every night is unnecessary", or "a restart may lose data", neither of which is
  what the sentence gets wrong.
