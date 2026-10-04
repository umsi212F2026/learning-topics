# Rubric: migration

### q-define-migration

- **type:** free
- **goal:** w-migration
- **move:** DEFINE
- **answer:** a change to the shape of the database, made when there is already data in it: adding a
  column, adding a table, changing what a column holds. The rows that are already there are the whole
  difficulty, since they have to come through the change still holding what they held.
- **credit:** full credit for saying it is a change to the schema, the tables and columns, carried
  out on a database that already has data in it. Half credit for "a change to the database" with
  nothing about the shape, since adding a habit changes the database too. Do not accept "schema
  migration" or "database migration", which are other names for it, and do not accept "moving the
  data to a different database".

### q-migration-vs-schema

- **type:** free
- **goal:** w-migration
- **move:** DISTINGUISH
- **answer:** the schema is the shape the data has at a given moment. A migration is the step from
  one shape to the next: the thing that gets carried out, once, to take a database that already holds
  rows from the old schema to the new one.
- **credit:** full credit for the difference that matters: the schema is a state, the shape as it now
  is, and a migration is the change from one such state to another, run against a database that
  already holds data. Half credit for "a migration changes the schema" with nothing about the schema
  being the shape itself. Do not accept "they are the same thing at different times", and do not
  accept an answer in which a migration is a kind of schema.

### q-migration-moved-database

- **type:** free
- **goal:** w-migration
- **move:** CATCH
- **answer:** a migration is a change to the shape of the database they already have, a column added
  or a table added, not a move to a different one. The habits are where they always were, and what
  changed is what the tables can hold.
- **credit:** full credit for saying a migration changes the schema of the same database rather than
  moving anything anywhere. Do not accept a different quibble as the error: that the agent should have
  asked first, that a badly done migration can lose data, which is true and is not what the sentence
  claims, or that they should have a backup of the file.
