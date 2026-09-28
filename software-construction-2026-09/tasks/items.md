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

### q-define-tdd

Your agent tells you it built the Notes app's Delete button using test-driven development. Say
what test-driven development is, in your own words.

### q-tdd-vs-writing-tests

Two agents each finish a working Delete button for your Notes app, and each hands back a test for
it that passes. One of them worked test-driven and the other did not. What is the difference
between the two?

### q-tdd-catch-tests-after

A classmate says: "My agent built the whole Notes app first, and then at the end wrote tests for
all of it. Every test passed the first time it ran. That is test-driven development, and the tests
passing first time shows it worked." What is wrong with what they said?

### q-define-failing-test

Your agent stops partway through a task and tells you it has a failing test. Say what a failing
test is, in your own words.

### q-failing-vs-broken-test

Your agent reports that one test is failing. A few minutes later it says a different test is
broken. What is the difference?

### q-red-before-code

Your agent says: "The new test for saving a note is red, and that is exactly where I want it
before I touch the saving code." What is it telling you?

### q-define-regression

Superpowers tells your agent to stop and report any regression it finds. Say what a regression is,
in your own words.

### q-regression-vs-new-bug

Your Notes app has two problems this afternoon that you did not know about this morning. Your
agent calls one of them a regression and the other just a new bug. What is the difference?

### q-catch-regression-never-worked

A classmate says: "The newest note has been going to the bottom of the list ever since the first
version of my app, and I only noticed it today. That is a regression." What is wrong with what
they said?

### q-define-mock

Your agent says the test for deleting a note runs against a mock. Say what a mock is, in your own
words.

### q-mock-vs-test-data

Before one test runs, three notes are put into a real test database so the test has something to
work with. A different test replaces the database with a mock. What is the difference between a
mock and those three notes?

### q-mock-earns-no-assertions

You asked your agent whether saving a note works. It answers: "The save test never touches the
real database. It stands a test double in for it, and checks that the double was asked to store
the note." What does that confirm is working if the test passes, and what still not be working?

### q-code-review-vs-testing

After your agent finishes the Delete button, Superpowers runs the tests and also sends the change
to a second agent for code review. What does the code review do that running the tests does not?

### q-catch-own-tests-are-review

A classmate says: "My agent ran the test suite on its own change and everything passed, so that
change has been code reviewed." What is wrong with what they said?

### q-review-no-findings

Your agent says: "I sent the Delete change for code review. The reviewer came back with no
findings, so I merged it." Which of these does that tell you?

1. The Delete button has been tested, since a code review runs the tests over the change.
2. Delete works, because someone read the code change and found nothing wrong with it.
3. Nothing was looked at: "no findings" means the review never ran.
4. Someone read the code change and found nothing wrong with it. Delete may or may not work.

### q-define-spec-review

When your agent finishes a piece of work, Superpowers has a separate agent do a spec compliance
review of it. Say what a spec compliance review is, in your own words.

### q-spec-vs-quality-review

Two reviewer agents read the same finished change to your Notes app. One does a code quality
review and the other a spec compliance review. What is each one asking?

### q-spec-review-passed

Your agent says: "Spec compliance review passed: every item in the plan is implemented, and
nothing extra was added." What does that tell you, and what does it leave open?

### q-define-root-cause

Your agent says it will not change any code until it has found the root cause. Say what a root
cause is, in your own words.

### q-root-cause-vs-symptom

You save a note in your Notes app and it does not appear in the list. What is the difference
between the symptom here and the root cause?

### q-catch-root-cause-workaround

A classmate says: "Notes I saved were not appearing in the list. My agent made the page reload
itself after every save, and now they appear, so it found the root cause." What is wrong with what
they said?

### q-define-test-suite

Your agent says it ran the test suite before handing the work back to you. Say what a test suite
is, in your own words.

### q-suite-24-passing

You asked your agent whether a note you save is still there after a reload. It answers: "Yes. I
ran the full test suite just now: 24 tests, all passing, none failing." Which of these does that
answer tell you?

1. A saved note does survive a reload, because a test would have caught it if it did not.
2. There are 24 things the app does, and all 24 of them work.
3. Every test that exists for this app came out as expected.
4. More tests are needed.

### q-catch-suite-everything

A classmate says: "My whole test suite passes, so everything my Notes app does has been tested."
What is wrong with what they said?

### q-coverage-vs-well-tested

What is the difference between how much test coverage the Notes app's code has and how well tested
it is?


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
make sure the notes feature is still working properly?" Could you push back and ask the agent to do that clicking around itself, or does it really need you?
