# Rubric: check

What it names: a pass or fail result GitHub shows beside a commit or pull request. Nearest
confusable: a test. Synonym: status check; given as an answer, it names the thing again and says
nothing.

### q-check-vs-test

- **goal:** `w-check`
- **move:** DISTINGUISH
- **answer:** A test is code in the app's test suite that checks one thing the app should do. A
  check is a pass or fail result GitHub shows beside a commit or pull request, from a job that ran
  on it, such as a GitHub Actions run of the whole suite. One check can stand for many tests, a
  check can come from something other than tests, and tests run only on your own machine produce
  no check at all.
- **credit:** full for the difference that matters: a test is code that checks the app, and a check
  is a result GitHub shows on a commit or pull request from a job that ran, which may be many
  tests or none. Half for "a check is what GitHub shows" with nothing on its being a result
  rather than the tests themselves. None for an incidental difference, such as that checks are
  green or red.

### q-catch-check-means-live

- **goal:** `w-check`
- **move:** CATCH
- **answer:** A green tick means a check on that commit passed, for example that its tests ran and
  passed. It says nothing about whether the host has deployed the commit; that is shown in the
  host's list of deploys, or by seeing the change in the live app.
- **credit:** full for naming the actual error: a check is the result of a job run on the commit,
  such as its tests, not a sign that the host deployed it. Half for "that doesn't mean it's
  deployed" with nothing on what the tick does mean. None for a different quibble, such as that
  the browser might be showing an old copy.
- **tutor note:** a learner may say some hosts report their deploys back to GitHub as a check.
  That is true of some hosts and not of Pinecart or Ropewalk in this topic; ask what this tick, on
  its own, could be the result of.

### q-catch-failed-check-rejects-push

- **goal:** `w-check`
- **move:** CATCH
- **answer:** The push succeeded: the commit is on GitHub, on `fix-footer`, and the check is a
  result GitHub shows beside it, from a job that ran on it after it arrived. A failing check
  reports that the job failed, such as the tests; it doesn't undo the push. They fix the code and
  push a new commit, which gets checks of its own.
- **credit:** full for naming the actual error: a check is a result shown beside a commit that is
  already on GitHub, so a failed one leaves the commit there and only reports the failure. Half
  for "the commit is on GitHub" with nothing on the check being a result reported about it. None
  for a different quibble, such as that they should run the tests before pushing, or that the
  check might be flaky.
