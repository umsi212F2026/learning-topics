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
  version, while a restart starts the same version again. Half for "a redeploy happens on the host
  and a restart on your laptop", with nothing about a new version. Do not accept "a redeploy loses
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

### q-catch-redeploy-crash

- **goal:** `w-redeploy`
- **move:** CATCH
- **answer:** a redeploy puts a new version of the app on the host in place of the running one, and
  the only new version the host can put there is one it has been given. The fix never left the
  laptop, so whatever the host did at noon, it brought back the version it already had: a restart
  of the old code, not a redeploy of the fixed one. Users still have the bug.
- **credit:** full for naming the actual error: bringing the crashed app back runs the version
  already on the host, while getting the fix to users takes a redeploy of a new version the host
  has been given, which hasn't happened. Half for "they need to push first" with nothing about the
  host bringing back the version it already had. Do not accept a different quibble: "the crash may
  have lost their data", or "they should have tested more", neither of which is what the sentence
  gets wrong.
