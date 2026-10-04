# Rubric: Postgres

What it names: a database that runs as a program of its own, which the backend connects to.
Nearest confusable: SQL. Synonym: PostgreSQL.

### q-postgres-vs-sql

- **goal:** `w-postgres`
- **move:** DISTINGUISH
- **answer:** SQL is a language, the one queries and changes are written in. Postgres is a
  database: a program that runs on its own, holds the data, and is asked things in SQL by the
  backend, which connects to it. SQLite is asked in SQL too, which is why the queries mostly carry
  over; what changes is the thing being asked.
- **credit:** full for the difference that matters: SQL is the language, and Postgres is a database,
  a running program that is asked in that language. Half for "Postgres uses SQL" with nothing about
  Postgres being the database that holds the data. Do not accept "Postgres is a kind of SQL" or
  "Postgres is a newer version of SQL", which are the confusion itself, and do not accept a
  difference of size or speed.

### q-catch-postgres-file

- **goal:** `w-postgres`
- **move:** CATCH
- **answer:** Postgres is not a file the backend opens. It is a database that runs as a program of
  its own, often as a separate service, and the backend connects to it and sends it queries. The
  package they install only lets the backend connect; a Postgres database has to be running
  somewhere for it to connect to.
- **credit:** full for naming the actual error: there is no Postgres file for the backend to open,
  since Postgres runs as its own program and the backend connects to it. Half for "Postgres needs
  more setting up than a library" with nothing about its running apart from the backend, which
  connects to it. Do not accept a different quibble: "some queries will need changing", "SQLite is
  fine for this app", or a remark about connection strings or passwords alone, none of which is what
  the sentence gets wrong.
