# Rubric: connection string

If the learner misses a question here, set a DEFINE or INTERPRET move for connection string live,
as help (it is recorded as helped and doesn't count), then come back to a production question.

A connection string is one line telling the backend where the database is and how to get in. For
a database on a host of its own it looks like `postgres://tally_app:pa55word@db.cellar.cloud:5432/tally`:
the kind of database, a username and password, the machine and port it runs on, and the
database's name. Its other names are database URL and `DATABASE_URL`, and neither of those, given
as an answer, says what it is. The confusables are a database file path, such as
`./data/budgets.sqlite`, which names a file on the same machine that the backend opens itself;
and the database's password, which is only the part of the string that gets the backend in.

### q1

- **goal:** `w-connection-string`
- **move:** DISTINGUISH
- **answer:** A connection string tells the backend how to reach a database running somewhere
  else, as its own server (often on another host), and carries what it needs to get in, such as
  a username and password. A database file path only names a file on the same machine, which the
  backend opens directly, with nothing to log in with and no other machine involved.
- **credit:** full for naming both halves of the difference that matters: the connection string
  reaches a database server elsewhere and carries the login, while the file path points at a file
  on the backend's own machine that needs no login. Half for only one of those halves (for
  example, "one includes a password, the other doesn't" with nothing on where the database is).
  None for an incidental difference alone, such as how they look (one starts with `postgres://`),
  their length, or that one is a URL.
- **tutor note:** if they answer "a connection string is a secret and a file path isn't", ask what
  in the connection string makes it one, and what a file path would need to have for the same to
  be true.

### q4

- **goal:** `w-connection-string`
- **move:** DISTINGUISH
- **answer:** The password is only the part that lets you in. The connection string is one line
  that carries the password together with where the database is (its machine and port), the
  username, and which database to use, so it is everything the backend needs to connect. Both are
  secrets, since both let someone in.
- **credit:** full for naming that the connection string also says where the database is (and as
  whom, and which database), with the password inside it, while the password alone says nothing
  about where to go. Half for saying the connection string "has more in it" or "contains the
  password" without saying what else it carries. None for an incidental difference alone, such
  as length or that one starts with `postgres://`, or for "only one is a secret", which is wrong.
- **tutor note:** if they say the password is the secret and the connection string isn't, ask
  what is inside the connection string.

### q2

- **goal:** `w-connection-string`
- **move:** CATCH
- **answer:** A connection string doesn't only say where the database is; it also says how to get
  in, because it carries the database's username and password. So it is a secret, and anyone who
  reads it in the README could get into the database.
- **credit:** full for naming that the connection string also carries how to get in (the password,
  or the login), so it is not safe to share. Half for saying it is a secret or shouldn't be in the
  README without saying what in it makes it one. None for a different quibble, such as that the
  README is the wrong place for setup details, or that the database's address is also private.
- **tutor note:** a learner who says "it's a secret because it's a setting" has the call right for
  the wrong reason; ask what someone could do with the line if they copied it.

### q3

- **goal:** `w-connection-string`
- **move:** CATCH
- **answer:** `db.cellar.cloud` is only the name of the machine the database runs on. A connection
  string is one line that also says how to get in (a username and password) and which database
  to use, and usually the kind of database and the port, as in
  `postgres://tally_app:pa55word@db.cellar.cloud:5432/tally`.
- **credit:** full for naming that what was copied is only where the database is, and a connection
  string also carries how to get in (the login). Half for saying it is incomplete or "just the
  host" without saying what is missing, or naming only a missing part that isn't the login (the
  port, or the database's name). None for a different quibble, such as that it should have been
  copied into the host's settings rather than the notes.
