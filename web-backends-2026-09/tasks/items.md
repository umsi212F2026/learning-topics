# The words of web backends

**Intended goals:** `w-backend`, `w-request`, `w-endpoint`, `w-api`, `w-status-code`,
`w-localhost`, `w-server-log`, `w-database`, `w-sql`, `w-table`, `w-schema`, `w-migration` and
`w-fixture`, with six questions on `c-check-persistence`, `c-review-schema` and `c-trace-action`
at the end.

Answer each question in one to three sentences, in your own words, with nothing open. Where a
question quotes an AI coding agent, imagine it is working on an app on your own laptop. Several
questions name a small app your agent built: Shelf, a reading list; Streaks, a habit tracker;
Potluck, an app for planning shared dinners. Every question says what you need to know about the
app it names, so nothing has to be carried from one question to the next.

### q-define-backend

Your agent says: "The backend for Streaks is finished and running. I haven't touched the page
yet." Say what a backend is, in your own words.

### q-backend-vs-dev-server

Your Vite dev server has been running at http://localhost:5173 since before your app had a
backend, and your agent has now added a backend at http://localhost:3001. What is the difference
between the two?

### q-backend-in-the-browser

A classmate says: "My app handles all its buttons in the browser, so it already has a backend: the
backend is the part of the page's code that does the work behind the buttons." What is wrong with
what they said?

### q-request-vs-page-load

Your reading-list app is open in a tab and showing your books. What is the difference between the
page sending a request to the server and the page being loaded?

### q-request-sort-is-request

A classmate says: "I clicked Sort A to Z and my list redrew in alphabetical order, so that was a
request." What is wrong with what they said?

### q-request-nothing-else-reaches

Your agent says: "Shelf's page sends one request when it loads, to get your books, and one more
each time you add a book. Nothing else it does reaches the server." Which of these is true?

1. Ticking a book's Finished box is saved by the server without a request having to be sent.
2. Ticking a book's Finished box never reaches the server, so nothing outside the page is keeping which books are finished.
3. The page has to be reloaded before the server hears about a book you added.
4. The server sends the page a fresh copy of the book list whenever the list changes.

### q-define-endpoint

Your agent says: "I've added an endpoint for deleting a book. The page doesn't use it yet." Say
what an endpoint is, in your own words.

### q-endpoint-vs-page-address

What is the difference between an endpoint and an address you type into the browser to see a page?

### q-endpoint-opened-in-browser

A classmate says: "I typed http://localhost:3001/api/items into my browser and got a screenful of
text in braces instead of my app, so my server is broken." What is wrong with what they said?

### q-define-api

Your agent says: "Before I touch the page, here is the API I'm going to build for Shelf." Say what
an API is, in your own words.

### q-api-vs-backend

Your app has a backend, and your agent keeps talking about its API. What is the difference between
the two?

### q-api-as-a-stop

A classmate says: "When I click Add, the page sends the book to the API, the API passes it to the
server, and the server saves it in the database." What is wrong with what they said?

### q-status-vs-error-message

Your agent says that an Add with an empty box comes back with a 400 and the message "An item needs
some text". What is the difference between the status code and the message?

### q-status-only-on-errors

A classmate says: "My Add worked and the book was saved, so that response had no status code.
Status codes only turn up when something goes wrong." What is wrong with what they said?

### q-status-404-on-delete

Your agent says: "When you delete a book that another tab deleted a moment ago, the server answers
404 and the page shows 'That book no longer exists'." Which of these is true?

1. The server could not be reached, so nothing happened at all.
2. The delete failed because you are not allowed to delete that book.
3. The page worked out on its own that the book was gone, without asking the server.
4. The server was reached and it answered, and its answer was that there was nothing there to delete.

### q-define-localhost

Your agent tells you that Shelf's page is at http://localhost:5173 and its server is at
http://localhost:3001. Say what the localhost part of those addresses means, in your own words.

### q-localhost-sent-to-friend

A classmate says: "I sent my roommate http://localhost:3001 so she could look at my books, and she
says she can't connect. My server must have crashed." What is wrong with what they said?

### q-localhost-tests-passed

Your agent says: "The tests all pass against http://localhost:3001. Putting the app somewhere your
classmates can reach is a separate job, and I haven't done it." Which of these is true?

1. The app has been checked as it runs on your own machine, and nobody else can reach it yet.
2. The app is on the internet already, and the tests confirm your classmates can use it.
3. The tests were run from your classmates' machines against your laptop.
4. The app works when the tests run it, and not when you use it yourself.

### q-define-server-log

Your agent says: "Click Add once more, then send me your server log." Say what a server log is, in
your own words.

### q-server-log-vs-console

Your agent asks you for the browser console one day and the server log the next. What is the
difference between them?

### q-console-empty-so-no-request

A classmate says: "Nothing new showed in the browser console when I clicked Add, so the server
never got my request." What is wrong with what they said?

### q-define-database

Your agent says it is going to add a SQL database to Streaks, which until now has had a page and a
server and nothing else. Say what a database is, in your own words.

### q-database-vs-server

Your app now has a server and a database. What is the difference between them?

### q-server-so-saved

A classmate says: "My habits go to the server now, so they're in a database: the server is where an
app's data lives." What is wrong with what they said?

### q-sql-vs-database

Your agent says Shelf keeps its books in a SQL database. What is the difference between SQL and the
database?

### q-sql-never-typed

A classmate says: "My app doesn't use SQL. My agent wrote everything in JavaScript and I've never
typed a query in my life." What is wrong with what they said?

### q-sql-sqlite-one-file

Your agent says: "Shelf uses SQLite, so the database is a single file on your laptop, and the
server asks it in SQL." Which of these is true?

1. SQLite is the language, and SQL is the file it writes to.
2. Your books are kept on SQLite's own servers, and your laptop holds a copy.
3. Your books are kept in a file on your laptop, and the server is what reads and writes them, in SQL.
4. The page reads the file itself, which is why your books appear so quickly.

### q-define-table

Your agent says Potluck's database will have three tables, and asks you to look at them before it
builds anything. Say what a table is, in your own words.

### q-table-vs-database

What is the difference between a table and the database it is in?

### q-one-table-per-habit

A classmate says: "Every habit I add makes a new table, so after a month my database has about
forty tables in it." What is wrong with what they said?

### q-define-schema

Before building the database, your agent shows you a schema and asks you to approve it. Say what a
schema is, in your own words.

### q-schema-vs-table

What is the difference between a table and the schema?

### q-schema-empty-after-delete

A classmate says: "I deleted all my test dinners, so my schema is empty now." What is wrong with
what they said?

### q-define-migration

Your agent says: "Adding a reminder time to each habit needs a migration. I'll write one and run
it." Say what a migration is, in your own words.

### q-migration-vs-schema

What is the difference between a migration and the schema?

### q-migration-moved-database

A classmate says: "My agent ran a migration last night, so my habits have been moved into a
different database." What is wrong with what they said?

### q-define-fixture

Your agent says: "All of Shelf's tests start from the same fixture." Say what a fixture is, in your
own words.

### q-fixture-vs-sample-data

Your agent put three sample books into Shelf so the app wouldn't look empty when you opened it, and
Shelf also has a fixture its tests run from. What is the difference between the two?

### q-fixture-test-failed

Your agent says: "That test failed because the fixture has two books and the test expected three.
I'll fix the fixture." Which of these is true?

1. Two of the books you added to Shelf have gone missing from the database.
2. The starting state the test sets up doesn't match what the test was written to expect, and the app itself may be perfectly fine.
3. The test is wrong, which is why the agent is about to change the test.
4. The app is showing two books when it should be showing three.

### q-persistence-reload-not-enough

Your agent says: "I've added a server and a SQLite database to your habit tracker. Your habits are
saved now." You add a habit, reload the page, and it is still there. Name two further things you
would do to find out whether it really is kept, and say what each one would catch that the reload
did not.

### q-persistence-agent-already-tested

Your agent says: "Your notes are saved in the database at data/app.db. I checked it myself: I
restarted the server and they came back." What has that not settled, and what would you do about
it?

### q-review-run-club-tables

A running club's app: anyone can post a run with a date, a distance and the name of whoever ran it,
and anyone can leave a comment on a run, each comment showing who wrote it and when. When anyone
opens the app next week, every run and every comment is still there. The agent proposes two tables:
runs, with the columns id, date, distance and runner; and comments, with the columns id, author,
text and created_at. Is anything the app has to remember missing? Say what it is, or say nothing is
missing and where each thing is kept.

### q-review-streak-column

A habit tracker shows, for each habit, how many days in a row you have kept it up. Its agent
proposes two tables: habits, with the columns id, name and created_at; and ticks, with the columns
id, habit_id and day. A classmate says the streak is missing and needs a column of its own on
habits. Are they right?

### q-trace-add-book

A reading-list app on your laptop has three parts: a page in your browser, a server that runs on
your laptop, and a SQL database the server keeps its data in. You type a title and click Add, and
the book appears at the bottom of the list. Say in order which parts the action goes through, from
the click until the book is on screen, and what passes between them.

### q-trace-reload-order

The same reading-list app, with one more thing said about it: while you are developing it, the
page's own files come from a dev server at http://localhost:5173, the app's server is at
http://localhost:3001, and the SQL database is a file on your laptop. You reload the page and your
books appear. Which of these is what happens, in order?

1. The page asks the server for the books, the server asks the database, the answer comes back to the page, and then the browser gets the page's files from the dev server and draws them.
2. The browser asks the dev server for the page's files, the dev server asks the server for the books, and the server answers with the page and the books together.
3. The browser asks the dev server for the page's files; the page starts with no books and asks the server for them; the server asks the database, the database answers the server, the server answers the page, and the page draws them.
4. The browser asks the database for the books directly, since on a reload there is no page yet to send a request.
