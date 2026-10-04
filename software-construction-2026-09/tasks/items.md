# The words of software construction

**Intended goals:** `w-tdd`, `w-failing-test`, `w-regression`, `w-mock`, `w-code-review`,
`w-spec-review`, `w-root-cause`, `w-test-suite` and `w-test-coverage`, with four questions on
`c-ask-tested` and `c-judge-manual-test` at the end.

Answer each question in one to three sentences, in your own words, with nothing open. Where a
question quotes an AI coding agent, imagine it is the agent working on your own laptop, running
under Superpowers, which has its agents write the tests, run them and review each other's work
between themselves. Several questions are about a small Notes app your agent built: the page is a
Vite React app at http://localhost:5173, and behind it are a server and a database. Typing in the
box and clicking Save adds a note to the list, newest first; the notes are kept in the database,
so they are still there after a reload; each note has a Delete button; and clicking Save with the
box empty saves nothing and shows a message instead.

### q-tested-reply-no-reload

Your Notes app keeps its notes in a database, so a note you save should still be there after you reload
the page. You asked your agent whether that has been tested. It answers: "Yes. The test named 'Note appears after
saving' opens the app in a headless browser, types 'Buy bread', clicks Save, and checks that 'Buy
bread' is in the list." Would that test fail if a saved note did not
survive a reload? Say why, and what you would ask the agent next.

### q-next-question-after-count

In your Notes app, a deleted note is meant to be gone for good, reload or not. You asked your
agent whether that has been tested, and it replied: "Yes, all 31 tests are passing." Which of
these is the best question to send next?

1. Which test would fail if a deleted note came back after a reload?
2. Are you confident that deleting notes is working properly?
3. How many of the 31 tests are about deleting notes?
4. Could you run the test suite again and paste the output for me?

### q-manual-newest-first

Your Notes app shows the newest note at the top of the list. Your agent has just changed how notes
are saved, and asks: "Could you add a few notes in the browser, reload the page, and tell me whether
they are all still there with the newest one at the top?" Could a program do this check instead of
you? If it could, say how. If it could not, say what the check needs that only you can supply.

### q-manual-make-sure-notes-work

Your agent finishes a piece of work on the Notes app and asks: "Could you have a click around and
make sure the notes feature is still working properly?" What are two ways you should push back against the agent's request?
