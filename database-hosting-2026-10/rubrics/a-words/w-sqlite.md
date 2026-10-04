# Rubric: SQLite

What it names: a database that is a single file the backend opens itself. Nearest confusable:
Postgres.

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

### q-define-sqlite

- **goal:** `w-sqlite`
- **move:** DEFINE
- **answer:** a database kept as one ordinary file, which the backend reads and writes itself
  through a library, with no separate database program running. Copy the file and you have copied
  the whole database.
- **credit:** full for a database that is a single file, opened and used by the backend itself
  rather than by a separate database program. Half for "a database stored in a file" with nothing
  about there being no separate program, or for "a small database the backend uses" with nothing
  about its being a file. Do not accept "a SQL database" or "a lightweight database" alone, which
  say what kind of thing it is without saying what it is.
