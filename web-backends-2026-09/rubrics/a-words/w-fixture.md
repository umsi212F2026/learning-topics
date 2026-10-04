# Rubric: fixture

### q-define-fixture

- **type:** free
- **goal:** w-fixture
- **move:** DEFINE
- **answer:** what a test puts in place before it runs, so that it starts from a known state every
  time: three books, say, one of them finished, and nothing else. Each run sets it up afresh, so what
  the test reports depends on the thing being tested rather than on whatever happened to be in the
  database.
- **credit:** full credit for saying it is a known starting state, put in place the same way every
  time. Mentioning tests is natural here but not required: "what gets loaded to start a fresh
  database, the same every time" also earns full credit. Half credit for "sample data" or "data the
  tests use" with nothing about its being put in place the same way every time. Do not accept "test
  fixture", which names it again, and do not accept "the test itself".

### q-fixture-vs-sample-data

- **type:** free
- **goal:** w-fixture
- **move:** DISTINGUISH
- **answer:** the fixture is put in place identically before every test run, so each run starts
  from exactly that state, however many times it runs. The books in your Shelf started from the
  samples but have changed with a week of use, and nothing puts them back. One is a known state that
  gets restored; the other is wherever use has taken the data.
- **credit:** full credit for the difference that matters: the fixture is reset to the same state
  every time, while the books in the app have drifted from where they started. Full credit whether or
  not the answer says the samples might themselves have been loaded from a fixture. Half credit for
  "one is for the tests and one is for the app" with nothing about the fixture being reset the same
  each time. Do not accept "the fixture is fake data and yours is real", and do not accept a
  difference of amount.

### q-fixture-test-failed

- **type:** mcq
- **goal:** w-fixture
- **move:** INTERPRET
- **answer:** 2
- **credit:** 1 reads the fixture as your own books in the app. 3 has the agent changing the test,
  when it said it would change the fixture. 4 reads the failure as a bug in the app, when the agent
  has said the fault is in the fixture.
