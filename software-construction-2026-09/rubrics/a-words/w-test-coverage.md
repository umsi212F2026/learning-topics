# Rubric: test coverage

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
