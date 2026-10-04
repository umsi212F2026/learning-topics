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
- **answer:** yes. The agent can run the check in a headless browser, a real browser with no window
  that a program controls. The test adds the notes through the page, reloads, and reads the order
  off the list.
- **credit:** full credit for "yes" plus a headless browser or a browser a program controls. A
  description of the test is welcome and is not required. No credit for "no, someone has to look at
  the list", no credit for "yes, automate it" with no browser, and no credit for a test that calls
  the server or the database directly, since that skips the page the request is about.

### q-manual-make-sure-notes-work

- **type:** free
- **goal:** c-judge-manual-test
- **answer:** first, the agent does not need you to click around: it can drive a headless browser,
  a real browser with no window that a program controls, and do the clicking itself. Second,
  "working properly" names nothing in particular, so the agent should say what it will click on
  and what it expects to happen, for instance: save a note, reload, and the note is still in the
  list; delete a note, reload, and it is still gone; click Save with the box empty, and no note is
  added and a message shows.
- **credit:** full credit needs both pushbacks: that the agent can do the checks itself in a
  headless browser or a browser a program controls, and that it should spell out what gets clicked
  and what effect it expects. A plain "be more specific" counts as the second pushback; naming the
  action and the expected effect, or giving an example, is welcome and is not required. Half credit
  for either pushback alone, so "be more specific" by itself gets half credit. No credit for
  "automate it" with no browser, or for agreeing to click around and report back.
