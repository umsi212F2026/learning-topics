# Rubric: table

### q-define-table

- **type:** free
- **goal:** w-table
- **move:** DEFINE
- **answer:** one kind of thing the database keeps, with a row for each one of that kind of thing
  and the same named columns on every row: a dinners table with a row per dinner, a dishes table
  with a row per dish. Adding another dinner adds a row, not a table.
- **credit:** full credit for saying a table holds one kind of thing, with one row per thing of that
  kind and the same columns across the rows. Full credit for "like a spreadsheet, with rows and
  columns". Do not accept "the database", and do not
  accept "where the data is kept" with no mention of rows or of one kind of thing.

### q-table-vs-database

- **type:** free
- **goal:** w-table
- **move:** DISTINGUISH
- **answer:** the database is the whole store, and a table is one kind of thing inside it. One
  database usually holds several tables, dinners and dishes and comments, each with its own columns
  and a row for each thing of that kind.
- **credit:** full credit for the containment: the database is the whole store and the tables are the
  separate kinds of thing in it, several to a database. Half credit for "a table is part of a
  database" with nothing about a table holding one kind of thing or about there being several. Do not
  accept "a table is a small database", and do not accept a difference in how each is asked, since
  both are reached in SQL.

### q-one-table-per-habit

- **type:** free
- **goal:** w-table
- **move:** CATCH
- **answer:** a table holds one kind of thing, with a row for each. All forty habits are rows in one
  habits table, and adding a habit adds a row. How many tables a database has follows from how many
  kinds of thing the app keeps, not from how many things there are.
- **credit:** full credit for saying each habit is a row in one table, so adding habits adds rows
  rather than tables. Do not accept a different quibble as the error: that forty tables would be
  slow, that the agent should have arranged it differently, or that each one would need a migration.
  What is wrong is what a table is, not how well the database is organized.
