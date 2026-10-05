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

### q-catch-auto-deploy-runs-tests

- **goal:** `w-auto-deploy`
- **move:** CATCH
- **answer:** Auto-deploy runs no tests. It redeploys the app whenever the repository changes, on
  every push to the linked branch, broken or not. Holding a deploy back until the tests pass is a
  separate arrangement, such as a host setting that waits for GitHub checks, or a workflow that
  runs the tests and then deploys; without one, a broken commit goes live like any other.
- **credit:** full for naming the actual error: auto-deploy redeploys on every change without
  testing anything, so waiting for the tests has to be set up separately. Half for "it deploys
  broken commits too" with nothing on waiting for tests being a separate arrangement, or the
  reverse. None for a different quibble, such as that the tests might not catch every bug, or
  that a deploy can fail for other reasons.
- **tutor note:** a learner may say some hosts can wait for GitHub checks. That is right, and it
  is a setting beside auto-deploy, not what auto-deploy is; ask what such a host does with a
  failing commit while that setting is off.
