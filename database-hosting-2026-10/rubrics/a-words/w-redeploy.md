# Rubric: redeploy

What it names: putting a new version of the app on its hosts in place of the running one. Nearest
confusable: restart; deploy.

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

### q-redeploy-vs-first-deploy

- **goal:** `w-redeploy`
- **move:** DISTINGUISH
- **answer:** the first deploy puts the app on the host where none of it was running, so there is
  nothing for it to replace. A redeploy puts a version of the app in place of one that is already
  running there, which users are already using and which may already have data. That is why a
  redeploy raises a question the first deploy can't: what, from the running copy, is still there
  after it has been replaced.
- **credit:** full for the difference that matters: a redeploy replaces a copy of the app that is
  already running on the host, while the first deploy has nothing running to replace. Half for "a
  redeploy puts up a newer version" with nothing about its replacing a copy that is already
  running. No credit for "the first deploy happens once and redeploys happen many times" or "a
  redeploy happens on every push", incidental differences with nothing about replacing what is
  running. Do not accept a claim about what either one does to the database (that the first deploy
  creates it, or that a redeploy keeps or loses it), which turns on the plan and the host, not on
  the words.

### q-catch-redeploy-trial

- **goal:** `w-redeploy`
- **move:** CATCH
- **answer:** a redeploy puts the new version in place of the running one, the copy users are
  using. So once the app is redeployed, the new sign-up page is what users get; there is no later
  step of switching them over, and "trying it out on the host first" is not something a redeploy
  does. Trying it first happens before the redeploy, somewhere that is not the running app.
- **credit:** full for naming the actual error: redeploying replaces the running app, the one users
  reach, so the new page reaches users as soon as the redeploy is done, not after a separate
  switch. Half for "that's not what a redeploy is" or "test it before redeploying" with nothing
  about a redeploy replacing what users are using. Do not accept a different quibble: "the redeploy
  might lose their data", "they should push first", or "they should test more", none of which is
  what the sentence gets wrong.
- **tutor note:** a learner may say some hosts offer preview deployments. That is right, and a
  preview is a separate copy alongside the running app, not a redeploy of it; ask what happens to
  the running app when it is redeployed.
