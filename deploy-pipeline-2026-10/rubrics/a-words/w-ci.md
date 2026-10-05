# Rubric: CI

What it names: running the tests automatically on every push and reporting whether they passed.
Nearest confusables: auto-deploy; a test suite. Synonym: continuous integration; given as an
answer, it names the thing again and says nothing.

### q-ci-vs-auto-deploy

- **goal:** `w-ci`
- **move:** DISTINGUISH
- **answer:** CI runs the tests on every push and reports whether they passed; it deploys nothing.
  Auto-deploy is the host redeploying the app whenever the repository changes; it tests nothing.
  Both are set off by a push, but one produces a test result and the other a new version of the
  live app, and neither waits for the other unless the host is set to.
- **credit:** full for the difference that matters: CI tests each push and reports the result,
  while auto-deploy puts each push live, so one checks the code and the other ships it. Half for
  naming what one of them does with nothing on the other. None for an incidental difference, such
  as that CI runs on GitHub and auto-deploy on the host, with nothing on what each does.

### q-ci-vs-test-suite

- **goal:** `w-ci`
- **move:** DISTINGUISH
- **answer:** A test suite is the tests themselves: code in the repository that checks what the app
  does, which anyone can run by hand. CI is the arrangement that runs that suite automatically on
  every push and reports whether it passed. A suite can exist with no CI, run only by hand, and CI
  with no suite has nothing to run.
- **credit:** full for the difference that matters: the suite is the tests, and CI is running them
  automatically on every push and reporting the result. Half for "CI runs the tests" with nothing
  on its doing so on every push, by itself. None for an incidental difference, such as that the
  suite is in a folder of its own.

### q-catch-ci-blocks-deploys

- **goal:** `w-ci`
- **move:** CATCH
- **answer:** CI runs the tests and reports whether they passed; it holds nothing back. Whether a
  deploy waits for that result is a separate setting on the host. Ropewalk deploys every push to
  `main` unless it is set to wait for GitHub checks, so having CI says nothing about whether a
  commit whose tests fail goes live.
- **credit:** full for naming the actual error: CI only reports whether the tests passed, and
  failing code is kept from going live only if the host is set to wait for that result. Half for
  "the host deploys anyway" with nothing on CI only reporting, or on the wait being the host's
  setting. None for a different quibble, such as that the tests might not cover everything, or
  that the tests take time to run.
- **tutor note:** a learner may name Ropewalk's "Wait for GitHub checks" setting. That is the
  right setting, and the setup does not say whether it is on; ask what CI alone does with a
  failing result.
