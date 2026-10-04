# Rubric: seed data

What it names: the rows your code puts in when a database is first set up. Nearest confusable:
fixture (a word from web-backends). Synonym: initial data.

### q-seed-vs-fixture

- **goal:** `w-seed-data`
- **move:** DISTINGUISH
- **answer:** seed data goes in once, when a database is first set up, production's included, and
  from then on real use changes it and nothing puts it back. A fixture is put in place before every
  test run, in a test database, so that each run starts from the same known state. The rows may be
  identical; what differs is when they go in and what they are for.
- **credit:** full for the difference that matters: seed data is put in once when a database is set
  up and then left to change, while a fixture is restored before every test run. Half for "one is
  for the app and one is for the tests" with nothing about once against every run. Do not accept
  "seed data is real and the fixture is fake", or a difference of amount, since the question gives
  both three events.

### q-catch-seed-tables

- **goal:** `w-seed-data`
- **move:** CATCH
- **answer:** seed data is rows, not tables. Having none means production starts with empty tables,
  not with no tables: the tables come from the code that sets up the database, such as the backend
  creating them at startup. So the first sign-up can be saved into an empty table.
- **credit:** full for naming the actual error: the teammate has mixed up seed data, which is rows,
  with the tables, which the code creates whether or not any rows are put in. Half for "you don't
  need seed data" with nothing about tables being made separately. Do not accept a different
  quibble: "they should add seed data", or "they should copy their laptop's database up", which is
  not a fix and is not what the sentence gets wrong.
- **tutor note:** if the learner's own app doesn't create its tables at startup, they may say the
  teammate could be right. Ask what makes the tables, as against what fills them.
