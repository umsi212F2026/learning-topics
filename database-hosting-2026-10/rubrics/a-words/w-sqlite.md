# Rubric: SQLite

What it names: a database that is a single file the backend opens itself. Nearest confusable:
Postgres; SQL.

### q-sqlite-vs-postgres

- **goal:** `w-sqlite`
- **move:** DISTINGUISH
- **answer:** SQLite is a single file that the backend opens and works on itself, through a
  library, with no other program involved. Postgres runs as a program of its own, often on another
  machine or service, and the backend connects to it and sends it requests. So with SQLite the data
  is wherever that file sits on the backend's own disk; with Postgres it is wherever the Postgres
  program keeps it.
- **credit:** full for the difference that matters: SQLite is a file the backend opens directly,
  while Postgres is a separate running program the backend connects to. Half for getting one side
  right (say, "SQLite is just a file") with nothing said about how Postgres differs. Do not accept
  a difference of size, speed or popularity, "one uses SQL and the other doesn't" (the question says
  both do), or "SQLite can't be used in production", which is not true: SQLite on storage that lasts
  is sound.
- **tutor note:** the readings' MDN passage leaves some learners thinking SQLite itself is unsafe on
  a host. If the answer says so, ask what would happen to the file if it sat on storage that
  survives a redeploy.

### q-catch-sqlite-server

- **goal:** `w-sqlite`
- **move:** CATCH
- **answer:** SQLite has no server. The database is a single file, and the backend opens and works
  on it itself, through a library; there is no separate program to start first or to connect to.
  Starting a database program for the backend to connect to is what Postgres needs, not SQLite.
- **credit:** full for naming the actual error: SQLite is not a separate running program, since the
  backend opens the file itself, so there is no SQLite server to start or connect to. Half for
  "SQLite doesn't need starting" with nothing about the backend opening the file itself. Do not
  accept a different quibble: "SQLite isn't meant for production", "use Postgres instead", or a
  remark about the order of the startup steps.

### q-sqlite-vs-sql

- **goal:** `w-sqlite`
- **move:** DISTINGUISH
- **answer:** SQL is a language: the one those lines are written in, for asking a database for
  rows and changing them. SQLite is a database: a single file holding the app's tables and rows,
  which the backend opens and works on itself, through a library, and asks things in SQL. Postgres
  is asked in SQL too, so SQL is not what makes the app a SQLite app; the file is.
- **credit:** full for the difference that matters: SQL is the language queries are written in,
  and SQLite is a database, the file holding the data that the backend opens itself and asks in
  that language. Half for "SQL is a language" with nothing said about what SQLite is, or for
  "SQLite is a database" with nothing about SQL being the language it is asked in. Do not accept
  "SQLite is a small or lite version of SQL" or "SQLite is a kind of SQL", which are the confusion
  itself, and do not accept a difference of size or speed.
