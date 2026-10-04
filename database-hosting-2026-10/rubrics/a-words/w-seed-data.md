# Rubric: seed data

What it names: the rows your code puts in when a database is first set up. Nearest confusable:
test data; schema. Synonym: initial data.

### q-seed-vs-test-data

- **goal:** `w-seed-data`
- **move:** DISTINGUISH
- **answer:** what the rows are there for, and what puts them in. Seed data is the rows the code
  itself puts in when a database is first set up, chosen on purpose as what every new database of
  the app should start with, such as a list of categories or the first real listings. Test data is rows
  put in to try the app out or check that it works, whether typed in by hand or added by a test;
  nothing in setting up a database calls for them.
- **credit:** full for the difference that matters: seed data is put in by the code when a database
  is set up, as the starting content the app is meant to have, while test data is put in to try or
  check the app and is not part of that setup. Half for one side right with the other missing or
  vague. Do not accept "seed data is real and test data is fake" as the whole answer, with nothing
  about what puts the rows in or what they are for; alongside either of those it is fine. Do not
  accept a difference in how many rows there are.

### q-seed-vs-schema

- **goal:** `w-seed-data`
- **move:** DISTINGUISH
- **answer:** a schema is the shape of the database: which tables there are, which columns each
  has, and what kind of value goes in each. It holds no rows. Seed data is rows: the starting rows
  the code puts into those tables when a database is first set up, such as a list of categories.
  A database can have its schema and no seed rows at all, but seed rows need the schema's tables
  to go into.
- **credit:** full for the difference that matters: the schema is the structure (tables and their
  columns) and seed data is the starting rows the code puts into it when a database is first set
  up. Half for one side right with the other missing or vague. Do not accept "the schema is
  written in SQL and seed data isn't" (both may be), "seed data is test data", or a difference of
  size.

### q-catch-seed-rebuild

- **goal:** `w-seed-data`
- **move:** CATCH
- **answer:** seed data is only the starting rows the code puts in when a database is first set up,
  here the list of categories. It holds nothing users added afterwards, so running it again on an
  empty database gives back the categories and none of the recipes people saved. It is not a copy
  of the database as it stands, and putting the app back the way it was would need such a copy.
- **credit:** full for naming the actual error: seed data is the fixed starting rows the code puts
  in at setup, so it does not include what users added since, and running it again brings back only
  the starting categories, not the saved recipes. Half for "seed data isn't a backup" or "you'd
  lose the recipes" with nothing about seed data being only the starting rows. Do not accept a
  different quibble: "keep the database on a persistent volume", "use Postgres instead", or a
  remark about when or where the seed step should run, none of which is what the sentence gets
  wrong.
- **tutor note:** a learner who says the seed rows might be inserted twice has found a different
  problem; ask what the app would hold after running the seed data on a database that was lost.
