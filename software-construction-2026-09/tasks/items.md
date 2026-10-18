# Software construction

**Intended goals:** `c-ask-tested` and `c-judge-manual-test`.

Answer each question in one to three sentences, in your own words. Where a question quotes an AI
coding agent, imagine it is the agent working on your own laptop, running under Superpowers, which
has its agents write the tests, run them and review each other's work between themselves. Several
questions are about a small recipe box your agent built: the page is a Vite React app at
http://localhost:5173, and behind it are a server and a database. Typing a recipe's name in the box
and clicking Save adds it to the list, newest first; the recipes are kept in the database, so they
are still there after a reload; each recipe has a Delete button; and clicking Save with the box
empty saves nothing and shows a message instead.

### q-tested-reply-no-reload

Your recipe box keeps its recipes in a database, so a recipe you save should still be there after
you reload the page. You asked your agent whether that has been tested. It answers: "Yes. The test
named 'Recipe appears after saving' opens the app in a headless browser, types 'Lentil soup',
clicks Save, and checks that 'Lentil soup' is in the list." Would that test fail if a saved recipe
did not survive a reload? Say why, and what you would ask the agent next.

### q-next-question-after-count

In your recipe box, a deleted recipe is meant to be gone for good, reload or not. You asked your
agent whether that has been tested, and it replied: "Yes, all 31 tests are passing." Which of
these is the best question to send next?

1. Which test would fail if a deleted recipe came back after a reload?
2. Are you confident that deleting recipes is working properly?
3. How many of the 31 tests are about deleting recipes?
4. Could you run the test suite again and paste the output for me?

### q-manual-newest-first

Your recipe box shows the newest recipe at the top of the list. Your agent has just changed how
recipes are saved, and asks: "Could you add a few recipes in the browser, reload the page, and tell
me whether they are all still there with the newest one at the top?" Could a program do this check
instead of you? If it could, say how. If it could not, say what the check needs that only you can
supply.

### q-manual-make-sure-notes-work

Your agent finishes a piece of work on the recipe box and asks: "Could you have a click around and
make sure the recipe box is still working properly?" What should you say back to the agent?
