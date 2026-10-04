# Rubric: schema

### q-define-schema

- **type:** free
- **goal:** w-schema
- **move:** DEFINE
- **answer:** the shape the data is promised to have: which tables there will be, and what columns
  each of them has. It says what can be written down rather than what has been, which is why it can
  be read and approved before a single row exists.
- **credit:** full credit for saying it is the shape or structure of the data, which tables and which
  columns, as against the data itself. Half credit for "the design of the database" with nothing
  about tables and columns and nothing about its not being the data. Do not accept "data model",
  which is another name for it, and do not accept "the tables" or "what is in the database".

### q-schema-vs-table

- **type:** free
- **goal:** w-schema
- **move:** DISTINGUISH
- **answer:** a table is one of the things in the database, holding actual rows. The schema is the
  stated shape: that there is a dinners table and what columns it has, that there is a dishes table
  and what columns that has. The schema covers every table at once and holds no data of its own; a
  table is one of the things the schema describes, with the data in it.
- **credit:** full credit for the difference that matters: a table holds rows of data, while the
  schema is the stated shape, which tables and which columns, and holds no data. Half credit for "the
  schema is all the tables together", which gets the scope right and misses the shape-rather-than-data
  point. Do not accept "the schema is a table listing the other tables", and do not accept an answer
  in which the schema is the data as it currently stands.

### q-schema-empty-after-delete

- **type:** free
- **goal:** w-schema
- **move:** CATCH
- **answer:** deleting rows empties the tables, not the schema. The schema is the shape, which tables
  there are and what columns each one has, and that is exactly as it was before: the dinners table is
  still there, with all its columns, holding nothing.
- **credit:** full credit for saying the schema is the shape rather than the data, so removing rows
  leaves it unchanged. Do not accept a different quibble as the error: that they should not have
  deleted the data, that the ids will carry on from where they left off, or that emptying a table
  needs a migration.
