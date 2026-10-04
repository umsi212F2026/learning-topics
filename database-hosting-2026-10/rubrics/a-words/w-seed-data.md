# Rubric: seed data

What it names: the rows your code puts in when a database is first set up. Nearest confusable:
test data. Synonym: initial data.

### q-seed-vs-test-data

- **goal:** `w-seed-data`
- **move:** DISTINGUISH
- **answer:** what the rows are there for, and what puts them in. Seed data is the rows the code
  itself puts in when a database is first set up, chosen on purpose as what every new database of
  the app should start with, such as a list of categories or a few demo entries. Test data is rows
  put in to try the app out or check that it works, whether typed in by hand or added by a test;
  nothing in setting up a database calls for them.
- **credit:** full for the difference that matters: seed data is put in by the code when a database
  is set up, as the starting content the app is meant to have, while test data is put in to try or
  check the app and is not part of that setup. Half for one side right with the other missing or
  vague. Do not accept "seed data is real and test data is fake", since seed rows may be demo rows,
  or a difference in how many rows there are.

### q-interpret-initial-data

- **goal:** `w-seed-data`
- **move:** INTERPRET
- **answer:** that the code itself puts the four rooms, and nothing else, into the database when it
  is first set up, and that every booking comes later from users. It rules out the database starting
  with any bookings in it, and it rules out the rooms being put in again each time the server starts,
  since this happens on the first run only. Nobody has to add the rooms by hand, either.
- **credit:** full for recovering the claim (the code puts in the rooms, and only the rooms, when
  the database is first set up) and at least one thing it rules out (bookings at the start, the
  rooms being added again on later starts, or someone having to add the rooms by hand). Half for the
  claim with nothing it rules out. Do not accept a reading that "initial data" means bookings made
  while the app was being tried out.
- **tutor note:** this question uses "initial data", a name the readings don't. If the learner
  doesn't recognise it as seed data, record the answer as given; don't tell them.
