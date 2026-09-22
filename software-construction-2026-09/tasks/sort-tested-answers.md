# Sort ten answers to "has this been tested?"

**Used by:** `a-sort-tested-answers`, which serves `c-ask-tested`. A study activity: nothing here
can meet the goal.

## The app

Your agent built a small Notes app. The page is a Vite React app at http://localhost:5173, and
behind it are a server and a database, like the ones the lab adds.

- Typing in the box and clicking Save adds the note to the list.
- Notes are kept in the database, so they are still there after a reload, or when you open the
  app on another computer.
- Each note has a Delete button. A deleted note is gone for good, reload or not.
- Clicking Save with the box empty saves nothing. The app shows "Write something first" instead.
- The list shows the newest note first.

When the agent said it had finished, ten people each asked it about one thing the app should do:
"Has [that thing] been tested?" Below are the answers they got. The agent was not lying in any of
them.

## For each answer, say three things

1. Does the answer name a test that would fail if that one thing broke? Yes, no, or can't tell
   from this.
2. What in the answer decided it for you, in one sentence.
3. If your answer to 1 was not yes, the one question you would send the agent next.

When you have done all ten, say in one or two sentences the rule you used.

---

### a1

**Asked:** Has "a deleted note is gone for good" been tested?

> Yes. There's a test called "delete removes the note". It replaces the database with a mock,
> clicks Delete, and checks that the mock's delete function was called with that note's id.

### a2

**Asked:** Has "a saved note is still there after a reload" been tested?

> Yes. I ran the full test suite just now: 24 tests, all passing, none failing.

### a3

**Asked:** Has "an empty note can't be saved" been tested?

> Yes. "Empty note is refused" opens the app in a headless browser, counts the notes, clicks Save
> with the box empty, and checks two things: that "Write something first" appears on the page, and
> that after a reload the list has the same number of notes as before.

### a4

**Asked:** Has "a saved note is still there after a reload" been tested?

> Yes. "POST /notes returns 201" sends a new note to the server and checks that the server answers
> 201 Created.

### a5

**Asked:** Has "the newest note is shown first" been tested?

> Yes, I checked it myself in the browser. I added three notes and the newest one was at the top.

### a6

**Asked:** Has "a deleted note is gone for good" been tested?

> Yes. "Deleted note stays deleted" runs against the test database. It saves a note, deletes it
> through the server, then asks the server for the list again and checks the note isn't in it.

### a7

**Asked:** Has "an empty note can't be saved" been tested?

> Yes. Test coverage for the notes code is 96%, and the function that checks for empty notes has
> 100% line coverage.

### a8

**Asked:** Has "a saved note is still there after a reload" been tested?

> Yes. "Saved note survives a reload" opens the app in a headless browser, types "Buy bread",
> clicks Save, reloads the page, and checks that "Buy bread" is in the list. I watched it fail
> before I wrote the saving code.

### a9

**Asked:** Has "a deleted note is gone for good" been tested?

> Yes. "Saves and lists notes" runs against the test database. It saves two notes and checks that
> both come back in the list.

### a10

**Asked:** Has "an empty note can't be saved" been tested?

> Yes. "Shows empty-note message" clicks Save with the box empty and checks that "Write something
> first" appears.

---

## Key, for the tutor

Show the learner everything above this section and nothing in it. Take all ten answers and the
stated rule before saying anything about any of them.

| answer | asked about | names a test that would fail? | what decides it | a next question that works |
| ------ | ----------- | ----------------------------- | --------------- | -------------------------- |
| a1 | deleting | no | A mock. The test checks that a stand-in was asked to delete. If the real database never lost the note (the delete went to the wrong place, or never took effect), the stand-in is still called and the test still passes. Superpowers' own rules for the agent say it: "The mock earns no assertions." | "Which test deletes a note in the real test database and then checks the list no longer has it?" |
| a2 | reload | no | A count. Twenty-four passing tests is a fact about the whole suite. It says nothing about whether any one of them would fail if saving broke. | "Which of those tests would fail if a saved note were not there after a reload, and what does it check?" |
| a3 | empty note | yes | Does the thing through the app and checks both halves of it: the message appears, and after a reload nothing was added. If an empty note got saved, the reloaded list would have one more and the test would fail. The reload is what makes the second check about saving: a count taken straight after Save can match while the server stored the empty note. | none needed; "show me it failing if empty notes get through" is a fine extra |
| a4 | reload | no | Accepted, not saved. The server can answer 201 and store nothing, or store it somewhere a reload never reads. The test checks the note was accepted, not that it was kept. | "Which test saves a note and then reloads, or reads the list back from the database, and finds it there?" |
| a5 | newest first | no | Tried by hand. Trying it once is not a test. Nothing reruns it, so nothing would fail if a later change reversed the order. | "Which test checks that the newest note is shown first, and how?" If the honest answer is that none does: "Please write one that adds three notes and checks the newest is at the top, and show me it failing when the order is reversed." |
| a6 | deleting | yes | Real test database, deletes through the server, then checks the list. A broken delete leaves the note in the list, and the test fails. | none needed |
| a7 | empty note | no | A percentage. Coverage says the code ran during some test, not that any test checked what it did. A test could run the empty-note check and look at nothing afterwards. | "Which test tries to save an empty note, and checks both that the message appears and that nothing was saved?" |
| a8 | reload | yes | Does exactly the thing and checks exactly what would differ if it broke. It was also seen failing first, which is the evidence that it can fail. | none needed |
| a9 | deleting | no | The wrong behavior. A real test, on the real test database, but about saving. Nothing in it deletes anything, so a broken delete leaves it passing. | same as a1 |
| a10 | empty note | no | Half the thing. It checks the message appears, not that nothing was saved. If the app showed the message and saved the empty note anyway, this test passes. | "Which test checks that no note was saved when Save is clicked with the box empty, and how does it check?" |

**Pairs built to be compared.** a4 and a8: the same thing, accepted versus kept. a1, a9 and a6:
three answers about deleting, a mock, a different behavior, and a real one. a10 and a3: the
message alone, versus the message and the list after a reload. a7 and a3: a percentage, versus a
check. If the learner misjudged either one of a pair, put the two side by side and ask what they
would break in the app to make each test fail.

**Verdicts are judged on what each answer says**, since there is no test code to look at. For a2,
a5 and a7, which name no test at all, "can't tell from this" is as good as no: what matters is
that none of them is taken as yes, and the question sent next.

**The rule the learner should arrive at**, in words of their own: an answer settles it only when it
names one test, says what that test does in the app, and checks the thing that would come out
differently if that one thing broke, against the real database rather than a stand-in. A count, a
percentage or "I tried it" is not a test of one thing. The question that works after any hollow
answer has the same shape every time: which test would fail if this broke, and what does it check?
Or: break it on purpose, and show me which test fails. Either way its honest answer has to name one
test, or say there is none; a question that could be answered with a count, a percentage or a
plain yes settles nothing.
