# Rubrics: The words of web backends

Answers for `tasks/items.md`. **Do not read this before attempting the questions.**

### q-define-backend

- **type:** free
- **goal:** w-backend
- **move:** DEFINE
- **answer:** the half of an app that doesn't run in the browser: a program of its own, running
  somewhere else (while you are developing, on your own laptop, at its own address), which the page
  sends requests to and which does the work the page can't do, such as reaching the database. The
  page is the other half.
- **credit:** full credit for saying it is the part of the app that runs outside the browser, as its
  own program, and answers what the page asks it. Full credit for "the part that runs on a server
  rather than in the browser, and handles the page's requests". Half credit for "the part the user
  doesn't see", which is also true of plenty of code that runs in the browser. Do not accept "the
  server" or "the server side", which name the thing again rather than saying what it is, and do not
  accept "the database", which is one of the things a backend talks to.

### q-backend-vs-dev-server

- **type:** free
- **goal:** w-backend
- **move:** DISTINGUISH
- **answer:** the dev server's job is to hand your browser the page's own files while you are
  developing, and it is a development tool rather than part of the app: it knows nothing about your
  books or your habits, and it is gone once the app is built and deployed. The backend is part of
  the app itself. It answers the requests the running page sends, does the work the page can't, and
  is the only one of the two that reaches the database.
- **credit:** full credit for the difference that matters: the dev server serves the page's files
  while you develop, and the backend answers the running page's requests as part of the app. Full
  credit for "the dev server is a tool for development that disappears when the app is deployed; the
  backend is the app's own half". Half credit for "they are on different ports" or "one is Vite and
  one is my agent's code", which are true and incidental. Do not accept "they are the same thing
  under two names", and do not accept an answer in which the dev server's job is to pass the page's
  requests on to the backend.

### q-backend-in-the-browser

- **type:** free
- **goal:** w-backend
- **move:** CATCH
- **answer:** a backend is not a part of the page's code. It is a separate program running outside
  the browser, at an address of its own, that the page sends requests to. Code inside the page, even
  the part furthest from the buttons, is still the front half of the app, and an app that does
  everything in the browser has no backend at all.
- **credit:** full credit for saying a backend runs outside the browser as its own program, so code
  inside the page is not a backend however hidden it is. Do not accept a different quibble as the
  error: that they ought to add a backend, that their app is too small to need one, or that a
  browser is a slow place to do work. An answer that says only "you need a database too" has not
  named the error.

### q-request-vs-page-load

- **type:** free
- **goal:** w-request
- **move:** DISTINGUISH
- **answer:** loading the page is the browser fetching the page's own files and starting the app
  over from nothing, so whatever the running app was holding is gone. A request is one trip the
  already-running page makes out to the server and back, asking for something or sending something.
  The page carries on running, and usually only the part of the screen that the answer bears on
  changes.
- **credit:** full credit for the difference that matters: a load starts the page over from its
  files, while a request is one ask-and-answer made by a page that is already running and keeps
  running. Half credit for "a load is the whole page and a request is only part of it", with nothing
  about the page continuing to run. Do not accept a difference of speed or size on its own, and do
  not accept an answer in which every request reloads the page.

### q-request-sort-is-request

- **type:** free
- **goal:** w-request
- **move:** CATCH
- **answer:** something changing on screen does not mean anything left the page. A request is a trip
  out to the server and back, and the page already had every item, so it could put them in a
  different order out of what it was holding without asking anyone. Whether a sort sends a request is
  something you would have to look at, in the Network panel or the server log, rather than something
  the screen tells you.
- **credit:** full credit for saying a change on screen is no evidence that anything went to the
  server, because a request is a trip out to the server and back and the page can reorder what it
  already holds. Half credit for "the page can sort by itself" with nothing about what a request is.
  Do not accept a different quibble as the error: that sorting is slow, that the sort ought to be
  done on the server, or that they should have looked at the Network panel, unless the answer also
  says why the screen alone does not settle it.

### q-request-nothing-else-reaches

- **type:** mcq
- **goal:** w-request
- **move:** INTERPRET
- **answer:** 2
- **credit:** 1 has the server saving something it was never told about. 3 misreads the second
  request: adding a book reaches the server at the moment you add it, which is what the message
  says. 4 has the server starting a trip of its own, when every trip named here starts at the page,
  and the message names only two of them.

### q-define-endpoint

- **type:** free
- **goal:** w-endpoint
- **move:** DEFINE
- **answer:** one of the addresses the server answers at, standing for one thing the page can ask it
  to do: here, an address the page can send a delete to. A server answers at several of them, each
  with its own job, and the page picks the one that matches what it wants.
- **credit:** full credit for saying it is one address the server answers at, tied to one thing the
  page can ask for. Full credit for "one of the addresses the page sends its requests to, each doing
  a different job". Half credit for "a place the page sends requests" with nothing about its being an
  address or about there being several, one per job. Do not accept "an API route", which is another
  name for it, and do not accept "the server's address" on its own, which is where the server is
  rather than one of the things it answers.

### q-endpoint-vs-page-address

- **type:** free
- **goal:** w-endpoint
- **move:** DISTINGUISH
- **answer:** a page's address is meant for a person: you type it in and the browser shows you
  something to look at. An endpoint is meant for the running page: the page sends its requests there
  and gets back data to work with, not a page to look at. Both are addresses, and in an app you are
  developing the page and the endpoints usually sit at two different addresses on your laptop.
- **credit:** full credit for saying an endpoint is an address the page's own code sends requests to
  and gets data back from, while a page's address is one a person opens to see something. Half credit
  for "one is for the server and one is for the browser", which gets the pairing roughly right with
  nothing about who does the asking or what comes back. Do not accept "an endpoint is not a real
  address" or "you can't open an endpoint in a browser": you can, and what comes back is data rather
  than the app.

### q-endpoint-opened-in-browser

- **type:** free
- **goal:** w-endpoint
- **move:** CATCH
- **answer:** that address is one of the server's endpoints, and answering it with data is exactly
  what it is for. The text in braces is the list of items the page normally asks for and draws.
  Nothing is broken, and the app itself is at the page's own address, which is a different one.
- **credit:** full credit for saying an endpoint answers with data rather than with a page, so what
  they saw is the server working as intended. Saying the app is at the page's own address is a good
  addition and is not required. Do not accept a different quibble as the error: that they typed the
  address wrongly, that the server ought to answer with a page, or that they should have used the
  Network panel. An answer that agrees something is broken has not found the error.

### q-define-api

- **type:** free
- **goal:** w-api
- **move:** DEFINE
- **answer:** the set of requests the server has promised to answer, each with what you send it and
  what comes back: give me all the books, save this new book, change whether this one is finished,
  delete this one. It is the agreement the page is written against rather than a piece of the app you
  could point at.
- **credit:** full credit for saying it is the set of requests the server promises to answer, or what
  the page is allowed to ask for and what comes back. Full credit for "the list of things the page
  can ask the server to do". Half credit for "how the page and the server talk to each other", with
  nothing about a set of requests settled in advance. Do not accept "the backend" or "the server",
  which is the thing that answers rather than what has been promised, and do not accept "the code
  that handles the requests".

### q-api-vs-backend

- **type:** free
- **goal:** w-api
- **move:** DISTINGUISH
- **answer:** the backend is the running program: something on your laptop with a process, a
  terminal it prints to, and a database behind it. The API is what that program has promised to
  answer: the set of requests, each with what it takes and what it gives back. One is the machinery
  and the other is the agreement it keeps, so everything inside the backend can be rewritten with the
  API left exactly as it was.
- **credit:** full credit for the difference that matters: the backend is the running thing, the API
  is the set of requests it promises to answer, and the inside can change without the API changing.
  Half credit for "the API is part of the backend" with nothing about what is promised. Do not accept
  "the API is the front end", "the API is a second server", or a difference of size.

### q-api-as-a-stop

- **type:** free
- **goal:** w-api
- **move:** CATCH
- **answer:** the API is not a stop on the way. It is the set of requests the server has promised to
  answer, so the page's request goes to the server, at one of its endpoints. "The page sends a
  request to the server's API" would have been fine; making the API something that takes the book and
  hands it on gives it a part it does not have.
- **credit:** full credit for saying the API is not a part the request passes through but the set of
  requests the server answers, so the page's request goes straight to the server. Half credit for an
  answer that only denies the extra stop without saying what an API is. Do not accept a different
  quibble as the error: that the way back to the page is missing, that the database has to answer the
  server, or that they should have named the endpoint.

### q-status-vs-error-message

- **type:** free
- **goal:** w-status-code
- **move:** DISTINGUISH
- **answer:** the status code is a number that comes back with every response, successful ones
  included, and it says in a standard way how the request went, so the page can act on it without
  reading any words. The message is wording chosen by whoever built the server, for a person to read,
  and a response may not carry one at all.
- **credit:** full credit for the difference that matters: the code is a standard number that comes
  with every response and says how it went, while the message is optional wording meant for a person.
  Full credit for "every response has a code, even a successful one, and only some have a message".
  Half credit for "one is a number and one is words" on its own. Do not accept "the status code only
  appears when something goes wrong", which is the confusion itself, and do not accept "the message
  has more detail" as the whole difference.

### q-status-only-on-errors

- **type:** free
- **goal:** w-status-code
- **move:** CATCH
- **answer:** every response carries a status code, whether things went well or not. A successful
  save comes back with one too, a 200 or a 201, and that is how the page knows it worked. The codes
  in the 400s and 500s are the ones that report trouble, but they are not the only codes there are.
- **credit:** full credit for saying every response has a code, and that a successful one carries a
  code saying it succeeded. Naming 200 or 201 is a good addition and is not required. Do not accept a
  different quibble as the error: that the page might not look at the code, that the agent should log
  it, or that 404 means something else.

### q-status-404-on-delete

- **type:** mcq
- **goal:** w-status-code
- **move:** INTERPRET
- **answer:** 4
- **credit:** 1 confuses a code that came back with never getting an answer at all, when a 404 is
  itself an answer. 2 reads the number as being about permission rather than about the thing not
  being there. 3 leaves the server out, when the number is the server's own answer.

### q-define-localhost

- **type:** free
- **goal:** w-localhost
- **move:** DEFINE
- **answer:** localhost is the name a machine has for itself. An address that starts
  http://localhost reaches whatever is running on the computer the address was typed on, and nothing
  anywhere else, so while the app is at one of those addresses it is running on your own laptop and
  you are the only one who can open it.
- **credit:** full credit for saying localhost means this computer, the one you are on, so the
  address reaches only your own machine. Full credit for "it means the app is running on my laptop
  and is not on the internet". Do not accept "127.0.0.1", which is another name for it rather than a
  definition, do not accept "the port the app is running on", which is the number after the colon,
  and do not accept "the address of a local server" with nothing about whose machine it is.

### q-localhost-sent-to-friend

- **type:** free
- **goal:** w-localhost
- **move:** CATCH
- **answer:** localhost means the machine the address is opened on, so her browser asked her own
  laptop, which is not running their server. The request never reached their machine at all, and what
  she saw says nothing about whether their server is running.
- **credit:** full credit for saying the address points at whoever opens it, so she reached her own
  machine rather than theirs, and it therefore tells them nothing about their own server. Do not
  accept a different quibble as the error: that they sent the wrong port, that she needs to be on the
  same wifi, or that her firewall blocked it. "You would have to deploy it first" names a fix rather
  than the error, and earns credit only with the reason her browser never reached their laptop.

### q-localhost-tests-passed

- **type:** mcq
- **goal:** w-localhost
- **move:** INTERPRET
- **answer:** 1
- **credit:** 2 and 3 both have the app reachable from somewhere other than your own laptop, which is
  the thing an address at localhost rules out. 4 turns "the tests pass" into "it works only under
  test", which the message does not say.

### q-define-server-log

- **type:** free
- **goal:** w-server-log
- **move:** DEFINE
- **answer:** what the server prints as it runs, in the terminal it was started in: a line or so for
  each request that arrives, saying what was asked and how it was answered, along with whatever else
  it reports while working. It is the server's own account of what it did, and it is out of the
  browser's sight.
- **credit:** full credit for saying it is what the server prints while it runs, in its own terminal,
  as a record of the requests it handled and what happened. Half credit for "a record of errors",
  which is only part of what it prints. Do not accept "server output" or "the logs", which name it
  again, and do not accept "what my app prints in the browser", which is the console.

### q-server-log-vs-console

- **type:** free
- **goal:** w-server-log
- **move:** DISTINGUISH
- **answer:** the console shows what the page printed and what went wrong inside the browser. It
  belongs to one tab, and it has no idea what the server did. The server log is what the server
  printed in its own terminal, away from the browser: which requests arrived, how they were answered,
  what it asked the database. Each one sees a half of the app that the other cannot.
- **credit:** full credit for placing both: the console is the browser's side, what the page printed
  in that tab, and the server log is the server's own terminal, the requests it received and what it
  did with them. Half credit for one placed clearly and the other left vague. Do not accept "one is
  for errors and one is for everything", and do not accept an answer in which the console also shows
  what the server printed.

### q-console-empty-so-no-request

- **type:** free
- **goal:** w-server-log
- **move:** CATCH
- **answer:** the console shows what the page printed, not what the server did. A server that
  received the request prints its line in its own terminal, which the console never shows, so an
  empty console is no evidence either way. The server log, or the Network panel, is what would tell
  them.
- **credit:** full credit for saying the server prints where the console cannot see it, so an empty
  console says nothing about whether the request arrived. Naming the server's terminal or the Network
  panel as where to look instead is a good addition and is not required. Do not accept a different
  quibble as the error: that the console was filtered or needed clearing, that they should have
  reloaded first, or that they should just ask the agent.

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
  restart.
- **credit:** full credit for saying the server may be holding them in memory, so reaching the server
  does not mean they are in a database, and they would go when it restarts. Full credit for naming
  the restart as the check that tells the two apart. Do not accept a different quibble as the error:
  that they should look at the database file, that they should ask the agent, or that their app might
  not have a database at all, which is not what the sentence gets wrong.

### q-sql-vs-database

- **type:** free
- **goal:** w-sql
- **move:** DISTINGUISH
- **answer:** the database is the thing that holds the books, a store on your laptop with tables in
  it. SQL is the language it is asked things in: give me every book, add this row, change this one.
  The database is what is asked, and SQL is how you ask it; a different database could be asked in
  the same language.
- **credit:** full credit for the difference that matters: the database is the store, and SQL is the
  language the questions and changes are written in. Half credit for "SQL is used with databases"
  with nothing about its being a language for asking. Do not accept "SQL is a kind of database",
  which is the confusion itself, since SQLite and Postgres are databases and SQL is what they are
  asked in. Do not accept "SQL is the data".

### q-sql-never-typed

- **type:** free
- **goal:** w-sql
- **move:** CATCH
- **answer:** whether they typed it is beside the point. If the app keeps its data in a SQL database,
  then something in the server is asking that database in SQL every time a book is saved or read
  back, whether the agent wrote those queries out or a library wrote them. Their app uses SQL; they
  have just never seen it.
- **credit:** full credit for saying the SQL is being sent by the server, written by the agent or by
  a library, whether or not the learner typed any, so the app does use it. Half credit for "the agent
  wrote the SQL for you" with nothing about its running whenever the app saves or reads. Do not
  accept a different quibble as the error: that they ought to learn SQL, that JavaScript and SQL are
  both languages, or that some databases are not asked in SQL, which is true and is not what this
  sentence gets wrong.

### q-sql-sqlite-one-file

- **type:** mcq
- **goal:** w-sql
- **move:** INTERPRET
- **answer:** 3
- **credit:** 1 swaps the two: SQLite is the database and SQL is the language it is asked in. 2 puts
  the data somewhere else, when the message says it is a file on your own laptop. 4 has the page
  reaching the database itself, when the message says the server is what asks it.

### q-define-table

- **type:** free
- **goal:** w-table
- **move:** DEFINE
- **answer:** one kind of thing the database keeps, with a row for each one of them and the same
  named columns on every row: a dinners table with a row per dinner, a dishes table with a row per
  dish. Adding another dinner adds a row, not a table.
- **credit:** full credit for saying a table holds one kind of thing, with one row per thing of that
  kind and the same columns across the rows. Half credit for "like a spreadsheet, with rows and
  columns" and nothing about its holding one kind of thing. Do not accept "the database", and do not
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

### q-define-fixture

- **type:** free
- **goal:** w-fixture
- **move:** DEFINE
- **answer:** what a test puts in place before it runs, so that it starts from a known state every
  time: three books, say, one of them finished, and nothing else. Each run sets it up afresh, so what
  the test reports depends on the thing being tested rather than on whatever happened to be in the
  database.
- **credit:** full credit for saying it is the known starting state a test sets up before it runs,
  the same every time. Half credit for "data the tests use" with nothing about its being put in place
  beforehand or being identical on each run. Do not accept "test fixture", which names it again, and
  do not accept "the test itself" or "the sample data the app ships with".

### q-fixture-vs-sample-data

- **type:** free
- **goal:** w-fixture
- **move:** DISTINGUISH
- **answer:** the sample books are there for you, in the app you are using, and you can change or
  delete them like any other book; they are ordinary data that happens to have been put there. The
  fixture belongs to the tests: it is set up fresh before a test runs, exactly the same every time,
  so that each run starts from a state nobody has touched. It is not what you see when you open the
  app.
- **credit:** full credit for the difference that matters: sample data sits in the running app for a
  person to see and change, while a fixture is the known state a test sets up for itself, identical
  on every run. Half credit for "one is for the tests and one is for the app" with nothing about the
  fixture being set up fresh and the same each time. Do not accept "they are the same data used in
  two places", and do not accept a difference of amount.

### q-fixture-test-failed

- **type:** mcq
- **goal:** w-fixture
- **move:** INTERPRET
- **answer:** 2
- **credit:** 1 and 4 both read the fixture as the app's own data, when it is the state the test sets
  up for itself before it runs. 3 has the agent changing the test, when it said it would change the
  fixture.

### q-persistence-reload-not-enough

- **type:** free
- **goal:** c-check-persistence
- **answer:** two of these three. Open the app in a browser that has never had it open, or in a
  private window, and look for the habit: that catches an app keeping it in the first browser's own
  storage, which a reload would not disturb. Ask the agent to restart the server, then look again
  from such a window: that catches an app whose server was holding it in memory and never wrote it
  down. Or save a habit, then ask the agent to change the tables, adding a reminder time to each
  habit, say, and afterwards look for that same habit: that catches an app that throws its table away
  and builds it again empty whenever the shape changes. The reload showed only that the habit was not
  being kept in the open page.
- **credit:** full credit for two of the three, each with what it catches: another browser or a
  private window for the browser's own storage; a server restart for the server's memory; something
  saved before a change to the tables and looked for after it, for a table that gets rebuilt. Half
  credit for two steps with no account of what each one catches, or for one step with its account. No
  credit for asking the agent whether it is really saved, and no credit for two forms of the same
  check, such as a reload and a new tab in the same browser, which is a reload with extra steps.

### q-persistence-agent-already-tested

- **type:** free
- **goal:** c-check-persistence
- **answer:** on its own it settles nothing, because the report that they came back is the agent's
  word, which is the thing being checked. Even taking it at face value, a restart says nothing about
  two of the ways an app can look as if it saves: if the agent looked from a page or a browser that
  already had the notes, a copy kept in that browser would have looked exactly like a success, and
  nothing here touches what happens when the tables change. So look for the notes yourself, from a
  browser or a private window that has never seen them, after a restart you asked for; and keep one
  note saved now and look for that same note again after the agent's next change to the tables.
- **credit:** full credit for both halves: that the agent's own report is not evidence, or that a
  restart alone leaves the browser's own storage and the table change untested; and a concrete step
  of their own, looking from a page that has never held the notes. Half credit for either half alone.
  Full credit also for an answer that grants the restart happened but names the browser case and the
  table case as still untouched. No credit for asking the agent to check again, and no credit for
  taking the named file path as proof.

### q-review-run-club-tables

- **type:** free
- **goal:** c-review-schema
- **answer:** one thing is missing: nothing records which run a comment was left on. The comments
  table has no run_id or anything like it, so next week the app could not tell which run's page a
  comment belongs on. Everything else is held: a run's date, distance and runner are columns of runs,
  and who wrote a comment is author, what it says is text, and when it was written is created_at.
- **credit:** full credit for naming the missing link between a comment and its run, and naming
  nothing else as missing. Half credit for naming it alongside something that is in fact held, such
  as a run's date or a comment's author or time, or something the app was never asked to keep. No
  credit for "nothing is missing". No credit for an answer about how the tables are arranged, such as
  wanting a separate table of people: with nobody logging in, a name kept where it is used is not a
  thing the app has failed to remember.

### q-review-streak-column

- **type:** free
- **goal:** c-review-schema
- **answer:** no. The streak can be worked out from what is already kept: the ticks table records
  which habit was ticked on which day, and a run of days in a row follows from those. Something
  counts as missing only when nothing held could produce it, and a streak column would be a second
  copy of what the ticks already say.
- **credit:** full credit for "no", with the reason that the ticks hold which habit was ticked on
  which day and the streak follows from them. Half credit for "no" with a vague reason such as "it
  can be calculated" and nothing about what it would be calculated from. No credit for "yes", and no
  credit for "no" on some other ground, such as streaks not mattering or the app being able to show
  something else instead.

### q-trace-add-book

- **type:** free
- **goal:** c-trace-action
- **answer:** the page hears the click and sends the server a request to save a book with that
  title. The server asks the database to store it. The database stores it and answers the server,
  with the new book's id. The server answers the page that it worked, with the saved book. The page
  adds that book to the list it is holding and redraws, so it appears at the bottom. Five steps
  across three parts, and the way back carries as much as the way there.
- **credit:** full credit for the page, the server, the database, the server and the page again, in
  that order, with roughly what passes at each hop. An answer in which the page shows the new book by
  asking the server for the whole list again after the save is full credit too, as long as every part
  is named in order on the way there and on the way back. Half credit for the way there alone, page
  to server to database, with nothing coming back, since a page that never heard back could not know
  the book was saved. No credit if the page reaches the database itself, if the database answers the
  page, or if a part is named that the action does not go through.

### q-trace-reload-order

- **type:** mcq
- **goal:** c-trace-action
- **answer:** 3
- **credit:** 1 has the page asking for books before the browser has the page at all. 2 gives the dev
  server a job it does not have: it sends the page's files and takes no part in fetching the books. 4
  has the browser reaching the database, which only the server does.
