# Rubric: test suite

### q-define-test-suite

- **type:** free
- **goal:** w-test-suite
- **move:** DEFINE
- **answer:** all the tests that exist for the project, taken together as one thing that can be run
  in one go. When an agent says it ran the tests, the suite is what it ran: every test anyone has
  written for this app, and nothing else.
- **credit:** full credit for "all the tests for the project, taken together and run as one", or
  "everything that runs when the tests are run". Half credit for "a group of tests" with no sense
  that it is what runs when the app is tested. No credit for "the tests", which is another name for
  it. No credit for the tool that runs them, for the test results, or for "the tests that are
  passing".

### q-suite-24-passing

- **type:** mcq
- **goal:** w-test-suite
- **move:** INTERPRET
- **answer:** 3
- **credit:** 1 turns a result about the  suite into a statement about the app. The suite is only the tests somebody wrote, and nothing in the answer
  says one of them reloads the page. 2 confuses the number of tests with the number of things the
  app does. 4 would only be true if the note actually disappears after a reload. 

### q-catch-suite-everything

- **type:** free
- **goal:** w-test-suite
- **move:** CATCH
- **answer:** the suite holds only the tests that were written. Anything nobody wrote a test for is
  not in it, so a fully passing suite says nothing about that behavior at all: "everything the app
  does" and "everything somebody tested" are not the same set. Even for the behaviors that do have
  tests, a pass is only as good as the tests: a weak test, or one that checks the wrong thing, can
  pass while the behavior is still wrong.
- **credit:** full credit for saying the suite is only the tests that exist, so a behavior nobody
  tested passes by being absent. An answer that says the tests might be weak or might check the
  wrong thing is also full credit. Do not accept a different
  quibble as the error: that tests can be flaky, that the agent might not have run them, or that
  they should also check the app by hand.
