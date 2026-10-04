# Rubric: database host

If the learner misses a question here, set a DEFINE or INTERPRET move for database host live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

A database host is where the app's data is kept once it leaves your laptop. The confusable is a
server host, which keeps the backend program running; the backend reads and writes the data the
database host keeps. "Managed database" means the same as database host and is not a confusable.
Which database host to pick, and keeping its data safe, belong to the database-hosting topic, not
to these questions.

### q1

- **goal:** `w-database-host`
- **move:** DISTINGUISH
- **answer:** A server host keeps your backend program running so it can answer requests. A
  database host keeps the app's data, so it is there whenever the backend asks for it. The backend
  runs on one and connects to the other, even when one vendor offers both.
- **credit:** full for the difference that matters: one runs the backend program, the other keeps
  the data the backend reads and writes. Half for "one holds the data" with nothing on what the
  server host does, or the reverse. None for an incidental difference alone, such as that they have
  different limits or prices, or that one uses SQL.

### q2

- **goal:** `w-database-host`
- **move:** CATCH
- **answer:** The deployed backend runs on the host's machines and can't reach a file on the
  student's laptop, so it won't see that data. A database host is where the data is kept once it
  leaves the laptop, somewhere the hosted backend can reach; the laptop is the opposite of that.
- **credit:** full for naming that the hosted backend can't reach a file on the laptop, so the
  laptop can't be its database host. Half for "the data has to be moved off the laptop" without
  saying why. None for a different quibble alone, such as that SQLite is not a good choice or that
  the laptop might be switched off.
- **tutor note:** a learner who says "the laptop might be off" is near; ask whether the hosted
  backend could open `groups.db` even with the laptop on.
