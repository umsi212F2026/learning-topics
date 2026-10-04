# Rubric: code review

### q-code-review-vs-testing

- **type:** free
- **goal:** w-code-review
- **move:** DISTINGUISH
- **answer:** the tests run the app and check the particular behaviors somebody decided to check,
  so they only ever report on the cases a test exists for. A code review is a second reader going
  through the change itself before it is accepted, and it can judge what no test states: whether
  the change does what was asked, whether it will trip up the next change, whether it breaks
  something nearby, whether the tests themselves check anything worth checking.
- **credit:** full credit for the two distinct things: tests execute the code and check stated
  behaviors, while a review is a second reader looking at the code itself and judging what no
  test asks. "A review can find what nobody wrote a test for" is full credit. Half credit for
  "review is done by a person or another agent, tests run automatically", with nothing about what
  each can find, and half credit for "review is about style and tests are about correctness" as
  the whole difference. No credit for treating a passing test suite as a review.

### q-catch-own-tests-are-review

- **type:** free
- **goal:** w-code-review
- **move:** CATCH
- **answer:** running tests is not a review, and the agent that wrote the change is not a second
  reader. A code review is someone other than the author going over the change before it is
  accepted; a passing suite says only that the checks that already exist came out as expected.
- **credit:** full credit for either half stated clearly: running the tests is not a code review, or
  the author checking its own work is not a second reader. Naming both is stronger and is not
  required. Do not accept a different quibble as the error: that the suite might be small, that the
  agent might have skipped a test, that the agent might be lying, or that the change should also
  have been tried by hand.

### q-review-no-findings

- **type:** mcq
- **goal:** w-code-review
- **move:** INTERPRET
- **answer:** 4
- **credit:** 1 confuses a review with testing: a review is a reader's pass over the change, not a
  run of the suite. 2 claims too much, since a reviewer can miss things and reading a change is not
  running it. 3 misreads a clean review as no review having happened.
