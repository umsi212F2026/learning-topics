# Rubric: test coverage

### q-catch-coverage-is-checked

- **type:** free
- **goal:** w-test-coverage
- **move:** CATCH
- **answer:** coverage says only how much of the code ran while the tests were running, not that
  anything was checked. A line can run during a test that never looks at what it did, so 95%
  coverage can sit beside behaviors no test would notice breaking.
- **credit:** full credit for saying coverage counts code the tests ran, not code whose behavior
  they checked, so a high number doesn't show the app works. Half credit for "coverage isn't
  everything" or "the tests could be bad" with nothing about what the number counts. Do not accept
  a different quibble as the error: that 95% is not 100%, that the remaining 5% might hold a bug,
  or that they should run the tests again.

### q-catch-coverage-report

- **type:** mcq
- **goal:** w-test-coverage
- **move:** CATCH
- **answer:** 2
- **credit:** coverage counts how much of the code ran during the tests. 1 is the tempting one: it
  reads coverage as how well tested the app is, but a line can run in a test that checks nothing
  about it. 3 confuses coverage with the pass rate. 4 has the tests finding bugs, which coverage
  says nothing about.

### q-coverage-vs-well-tested

- **type:** free
- **goal:** w-test-coverage
- **move:** DISTINGUISH
- **answer:** coverage measures how much of the code the tests reach: which lines ran at some point
  while the suite was running. Being well tested is about whether the tests check the right things,
  and would fail if a behavior broke. Code can run during a test that looks at nothing afterwards,
  so it can be covered and not tested; a little code with sharp checks can be well tested at a low
  percentage.
- **credit:** full credit for the difference that matters: coverage counts code the tests ran,
  while being well tested is about whether anything was checked and whether the check would fail if
  the behavior broke. An example of high coverage with poor testing is a strong addition and is not
  required. Half credit for "coverage is a number and well tested is a judgment", with nothing
  about what the number counts. No credit for treating them as the same thing, and no credit for
  saying coverage measures how many tests there are.
