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

### q-interpret-postgresql

- **goal:** `w-postgres`
- **move:** INTERPRET
- **answer:** the data would be held by a Postgres database running as its own service, separate
  from the backend, which reaches it over the network rather than opening a file. It rules out the
  data sitting on the backend's own server as a file, so replacing the backend in a redeploy leaves
  the database and its data where they were.
- **credit:** full for recovering both parts: the database runs separately from the backend and the
  backend connects to it, and so a redeploy of the backend does not touch the data (or, equally,
  the data is not a file on the backend's server). Half for one part without the other. Do not
  accept "the data is kept in SQL", or a reading that the database is copied onto the backend's
  server.
- **tutor note:** this question uses PostgreSQL, a name the readings don't. If the learner doesn't
  recognise it as Postgres, record the answer as given; don't tell them.
