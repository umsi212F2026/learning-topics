# Rubric: seed data

What it names: the rows your code puts in when a database is first set up. Nearest confusable:
test data; schema. Synonym: initial data.

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

### q-catch-seed-schema

- **goal:** `w-seed-data`
- **move:** CATCH
- **answer:** seed data is rows, not tables. It is the starting rows the code puts into the tables
  when a database is first set up, such as the list of categories. Making the tables and their
  columns is a different job, and the tables have to exist before any seed rows can go into them.
- **credit:** full for naming the actual error: seed data is the rows the code puts in when a
  database is first set up, while what the teammate describes is making the tables those rows go
  into. Half for "that isn't seed data" or "that's the tables' definition" with nothing about seed
  data being rows. Do not accept a different quibble: "they should have more seed data", or "they
  should copy their laptop's database instead", neither of which is what the sentence gets wrong.

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
