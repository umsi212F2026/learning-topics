# Rubrics: The words of web backends

Answers for `tasks/items.md`. **Do not read this before attempting the questions.**

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
- **answer:** the page notices the click and sends the server a request to save a book with that
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
