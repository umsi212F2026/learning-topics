# Rubric: auto-deploy

What it names: a host redeploying the app by itself whenever the repository changes. Nearest
confusable: redeploy. Synonyms: continuous deployment, CD; given as an answer, either one names the
thing again and says nothing.

### q-auto-deploy-vs-redeploy

- **goal:** `w-auto-deploy`
- **move:** DISTINGUISH
- **answer:** A redeploy is one event: a new version of the app put on the host in place of the
  running one. Auto-deploy is the standing arrangement that makes the host do those redeploys by
  itself, each time the repository changes, with nobody asking. So auto-deploy is what triggers
  redeploys; a redeploy can also happen without it, when someone starts one by hand.
- **credit:** full for the difference that matters: a redeploy is a single replacement of the
  running app, and auto-deploy is the host starting redeploys on its own whenever the repository
  changes. Half for "auto-deploy happens by itself on each push and a redeploy is one you do
  yourself", which gets the trigger but misses that what auto-deploy does is redeploy. None for an
  incidental difference, such as that auto-deploy is a setting and a redeploy is a button, with
  nothing on one being the event and the other what sets it off.

### q-catch-auto-deploy-on-save

- **goal:** `w-auto-deploy`
- **move:** CATCH
- **answer:** Auto-deploy reacts to the repository changing on GitHub, a push to the branch the
  host is linked to. The host cannot see files on the student's machine, so a saved file that is
  not committed and pushed never reaches it, and nothing redeploys. They still have to commit and
  push.
- **credit:** full for naming the actual error: auto-deploy fires when the repository on GitHub
  changes, not when a file is saved on their own machine, so they still have to commit and push.
  Half for "you still have to push" with nothing on what auto-deploy responds to. None for a
  different quibble, such as that redeploying on every save would be too often, or that the tests
  should run first.
