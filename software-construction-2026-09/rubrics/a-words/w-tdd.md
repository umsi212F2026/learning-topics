# Rubric: test-driven development

### q-define-tdd

- **type:** free
- **goal:** w-tdd
- **move:** DEFINE
- **answer:** a rule about the order the work is done in: the test for a piece of behavior is
  written before the code that makes it work. You write a test that says what the app should do,
  watch it fail because nothing does that yet, then write the code until it passes. Whether tests
  exist at all is not the point; which comes first is.
- **credit:** full credit for the order, stated clearly: the test is written before the code it is
  testing. Watching it fail first is a strong addition and is not required. Half credit for "you
  write tests as you go" or "tests and code together", which say nothing about which comes first.
  No credit for "TDD", "test-first development" or "red-green-refactor", which are other names for
  it rather than what it is. No credit for "it means the code is well tested", "it means there are
  lots of tests", or "it means the tests are run automatically".

### q-tdd-vs-writing-tests

- **type:** free
- **goal:** w-tdd
- **move:** DISTINGUISH
- **answer:** both end with a working button and a passing test, so the difference is when the
  test was written. The test-driven one came first and was seen failing before any delete code
  existed, so it is known that it can fail and that the new code is what makes it pass. The other
  test was written after the button already worked and has never been seen failing, so it may pass
  whether or not deleting really works.
- **credit:** full credit for the order together with what it buys: the test-driven test was
  written first and seen failing, so there is evidence it actually checks the thing. Half credit
  for the order alone with no consequence. Do not accept "one of them has tests and the other does
  not": both do. Do not accept differences of amount or quality, such as "test-driven means more
  tests", "test-driven means better code", or "test-driven is slower".

### q-tdd-catch-tests-after

- **type:** free
- **goal:** w-tdd
- **move:** CATCH
- **answer:** the order is backwards. Test-driven development means the test comes before the code
  it tests, and writing all the tests at the end is the opposite of that, so this is not it. The
  second half is wrong for the same reason: a test that has never been seen failing is weak
  evidence, because passing first time is also what a test that checks nothing does.
- **credit:** full credit for naming the order: the tests came after the code, so this is not
  test-driven development. The point about a test never seen failing is a strong addition and is
  not required; an answer that makes only that point, with nothing about the order, gets half
  credit. Do not accept a different quibble as the error: that they should have written more tests,
  that the app should have been built in smaller pieces, or that an agent should not be trusted to
  write tests for its own code.
