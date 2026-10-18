# Rubrics: The words of software construction

Answers for `tasks/items.md`. **Do not read this before attempting the questions.**

### q-tested-reply-no-reload

- **type:** free
- **goal:** c-ask-tested
- **answer:** no. The test stops before the reload, so all it shows is that the note appears on
  screen straight after Save. The app could be holding the note in the page and never keeping it in
  the database, or keeping it somewhere a reload never reads, and this test would still pass. What
  to ask next: "Which test saves a note, reloads the page or reads the list back from the database,
  and then checks the note is there?"
- **credit:** full credit needs both: (a) no, with the reason that the test never reloads, so it
  checks the note appearing rather than the note being kept; and (b) a next question asking for one
  test that reloads or reads the note back, and what that test checks. Half credit for either half
  alone. No credit for "yes". No credit for a next question that could be answered with a count, a
  percentage or a plain yes, such as "are you sure?", "how many tests cover saving?" or "could you
  run the tests again?". An answer that says "can't tell from this" for the right reason and sends
  a question that works earns full credit.

### q-next-question-after-count

- **type:** mcq
- **goal:** c-ask-tested
- **answer:** 1
- **credit:** 1 is the only one whose honest answer has to name one test and say what it checks, or
  admit there is none. 2 can be answered yes with nothing behind it. 3 asks for another count,
  which is the same kind of answer that settled nothing the first time. 4 runs the whole suite
  again and says nothing about this one behavior.

### q-manual-newest-first

- **type:** free
- **goal:** c-judge-manual-test
- **answer:** yes. The agent can write a test that works the page itself, for example in a headless
  browser, a real browser with no window that a program controls. The test types and saves a few
  notes, reloads the page, and checks that every one of them is in the list with the last one saved
  at the top.
- **credit:** full credit for "yes" plus a test that goes through the page and says what it checks:
  it adds notes, reloads, and checks that they are all still listed with the newest first. Naming a
  headless browser, or any other way for a program to work the page, is welcome and is not
  required. Half credit for "yes" with a test that leaves out the reload or the order, and half
  credit for "yes, in a headless browser" with nothing about what the test does or checks. No
  credit for "no, someone has to look at the list", for "yes, automate it" with no account of the
  test, or for a test that calls the server or the database directly, since that skips the page the
  request is about.

### q-manual-make-sure-notes-work

- **type:** free
- **goal:** c-judge-manual-test
- **answer:** that the agent can do this check itself, with a test that works the page the way a
  person would, for example in a headless browser, a real browser with no window that a program
  controls. And that "working properly" names nothing in particular, so the test should say what it
  does and what it expects, for instance: save a note, reload, and the note is still in the list;
  delete a note, reload, and it is still gone; click Save with the box empty, and no note is added
  and a message shows.
- **credit:** full credit needs both: (a) that a program can do the check instead of you, by working
  the page itself or by tests that already do; and (b) at least one thing the check should do in
  the Notes app and what it should expect to see, well enough that the agent could write it.
  Naming a headless browser is welcome and is not required. Half credit for either alone: "do it
  yourself" or "automate it" with nothing about what to check, or a list of things to check that
  still leaves you to click through them. A plain "be more specific" with no example counts toward
  neither. Other sound replies, such as asking what changed or which tests already cover saving
  and deleting, are welcome and do not stand in for (a) or (b) unless they amount to them. No
  credit for agreeing to click around and report back.
