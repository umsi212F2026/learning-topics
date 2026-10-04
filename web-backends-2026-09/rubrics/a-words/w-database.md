# Rubric: database

### q-define-database

- **type:** free
- **goal:** w-database
- **move:** DEFINE
- **answer:** the place an app writes things down so that they are still there afterwards: after the
  page is closed, after the server is restarted, after the laptop is switched off. What is in it sits
  outside any running program, so the app can read it back the next time it starts.
- **credit:** full credit for saying it is where the app's data is kept so that it outlives the
  running app, still there after a reload, a restart, or the machine being switched off. Half credit
  for "where the app stores its data" with nothing about lasting past the app running, since that is
  what separates it from what the page or the server is holding at the time. Do not accept "DB", and
  do not accept "the backend" or "the server", which is the program that talks to it.

### q-database-vs-server

- **type:** free
- **goal:** w-database
- **move:** DISTINGUISH
- **answer:** the server is a running program: it answers the page's requests and does the app's
  work, and whatever it is holding in its own memory goes when it restarts. The database is where
  things are written down so that they survive that. The server asks it to store something or to hand
  something back, and what it holds is still there after everything has been switched off and started
  again.
- **credit:** full credit for the difference that matters: the server is the running program that
  handles requests and loses what it is holding when it restarts, while the database keeps what is
  written to it past any restart. Half credit for "one does the work and one stores the data" with
  nothing about what survives a restart. Do not accept "the database is inside the server" as the
  whole answer, and do not accept a difference of speed or size.

### q-server-so-saved

- **type:** free
- **goal:** w-database
- **move:** CATCH
- **answer:** a server can hold things in its own memory without writing them down anywhere. Then
  they survive a reload, and another browser sees them, and they go the moment the server restarts.
  Reaching the server is not the same as being in a database, and only the database keeps them past a
  restart of the server.
- **credit:** full credit for saying the server may be holding them in memory, so reaching the server
  does not mean they are in a database, and they would go when it restarts. Full credit for naming
  the restart as the check that tells the two apart. Do not accept a different quibble as the error:
  that they should look at the database file, that they should ask the agent, or that their app might
  not have a database at all, which is not what the sentence gets wrong.
