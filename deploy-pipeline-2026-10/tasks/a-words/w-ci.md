# CI

Answer in two or three sentences, in your own words, with nothing open in front of you.

### q-ci-vs-auto-deploy

What is the difference between CI and auto-deploy?

### q-ci-vs-test-suite

What is the difference between CI and a test suite?

### q-catch-ci-blocks-deploys

A team's backend is on Ropewalk, which is linked to `main`. This is how Ropewalk behaves:

- **Ropewalk** runs a long-running backend, such as an Express server.
  - Linked to a GitHub repository, a branch and a folder, it deploys the backend on every push to
    that branch. Its setting "Wait for GitHub checks", off for a new service, makes it deploy a
    commit only once every check on that commit has passed, and skip the commit if one fails. A
    commit with no checks on it is deployed straight away, as if the setting were off.

A GitHub Actions workflow runs the team's tests on every push and shows the result as a check.

A student says:

"We have CI, so code that fails its tests can't go live."

What is wrong with what they said?
