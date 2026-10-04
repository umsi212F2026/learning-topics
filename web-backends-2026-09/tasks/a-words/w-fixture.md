# fixture

### q-define-fixture

Your agent says: "All of Shelf's tests start from the same fixture." Say what a fixture is, in your
own words.

### q-fixture-vs-sample-data

When your agent set up Shelf, it put three sample books in the database so the app wouldn't look
empty. You've been adding and deleting books for a week since. Shelf's tests also start from a
fixture of three books. What is the difference between the books in your Shelf now and the fixture?

### q-fixture-test-failed

Your agent says: "That test failed because the fixture has two books and the test expected three.
I'll fix the fixture." Which of these is true?

1. Two of the books you added to Shelf have gone missing from the database.
2. The test's starting state doesn't match what it expected; the app may be fine.
3. The test is wrong, which is why the agent is about to change the test.
4. The app has a bug that loses a book, and the agent is about to fix it.
