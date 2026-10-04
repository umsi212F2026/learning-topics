# The words of web backends

**Intended goals:** `w-backend`, `w-request`, `w-endpoint`, `w-api`, `w-status-code`,
`w-localhost`, `w-server-log`, `w-database`, `w-sql`, `w-table`, `w-schema`, `w-migration` and
`w-fixture`, with five questions on `c-check-persistence`, `c-review-schema` and `c-trace-action`
at the end.

Answer each question in one to three sentences, in your own words, with nothing open. Where a
question quotes an AI coding agent, imagine it is working on an app on your own laptop. Several
questions name a small app your agent built: Shelf, a reading list; Streaks, a habit tracker;
Potluck, an app for planning shared dinners. Every question says what you need to know about the
app it names, so nothing has to be carried from one question to the next.

### q-persistence-reload-not-enough

Your agent says: "I've added a server and a SQLite database to your habit tracker. Your habits will be
saved now." You add a habit, reload the page, and it is still there. Name two further things you
would do to find out whether it really is kept, and say what each one would catch that the reload
did not.

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

While developing a reading-list app, a page's own files come from a dev server at
http://localhost:5173, the app's server is at http://localhost:3001, and the SQL database is a file
on your laptop. You reload the page and your books appear. Which of these is what happens, in order?

1. The page asks the server for the books and gets them back, then the browser gets the page's files from the dev server and draws them.
2. The browser asks the dev server for the page's files, the dev server asks the server for the books, and the server answers with the page and the books together.
3. The browser gets the page's files from the dev server, then the page asks the server for the books, and the server asks the database and answers the page.
4. The browser asks the database for the books directly, since on a reload there is no page yet to send a request.
