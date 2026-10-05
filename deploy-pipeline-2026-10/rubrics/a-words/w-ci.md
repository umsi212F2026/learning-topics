# Rubric: CI

What it names: running the tests automatically on every push, before anything goes further.
Nearest confusables: auto-deploy; a test suite. Synonym: continuous integration; given as an
answer, it names the thing again and says nothing.

### q-ci-vs-auto-deploy

- **goal:** `w-ci`
- **move:** DISTINGUISH
- **answer:** CI runs the tests on every push and reports whether they passed; it puts nothing
  live. Auto-deploy is the host putting each change live by itself. They are separate: auto-deploy
  with no CI puts untested changes live, and CI alongside an auto-deploy that doesn't wait for it
  still lets a change with failing tests go live.
- **credit:** full for the difference that matters: CI tests each push, and auto-deploy puts each
  change live, so having one doesn't make the other happen or wait. Half for "CI tests and
  auto-deploy deploys" with nothing on the two being separate. None for an incidental difference,
  such as that CI runs on GitHub and auto-deploy on the host, with nothing on what each does.

### q-ci-vs-test-suite

- **goal:** `w-ci`
- **move:** DISTINGUISH
- **answer:** A test suite is the tests themselves, code that checks the app behaves as it should.
  CI is running that suite automatically on every push. An app can have a test suite that only
  runs when someone types the command, which is not CI, and CI has nothing to run without a suite.
- **credit:** full for the difference that matters: the test suite is the tests, and CI is running
  them automatically on every push. Half for "CI runs the tests" with nothing on its happening by
  itself on every push. None for an incidental difference, such as that a test suite is written in
  the app's language.

### q-catch-ci-by-hand

- **goal:** `w-ci`
- **move:** CATCH
- **answer:** CI runs the tests automatically on every push, without anyone remembering to.
  Running `npm test` by hand before committing is running the test suite, which is worth doing,
  but it depends on the student remembering, happens on their machine only, and nothing records
  it on the push.
- **credit:** full for naming the actual error: CI is the tests running automatically on every
  push, not someone running them by hand. Half for "that isn't automatic" with nothing on what CI
  is. None for a different quibble, such as that they should run the tests before pushing rather
  than before committing.
