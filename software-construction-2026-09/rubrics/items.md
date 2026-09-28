# Rubrics: The words of software construction

Answers for `tasks/items.md`. **Do not read this before attempting the questions.**

### q-define-tdd

- **type:** free
- **goal:** w-tdd
- **move:** DEFINE
- **answer:** a rule about the order the work is done in: the test for a piece of behavior is
  written before the code that makes it work. You write a test that says what the app should do,
  watch it fail because nothing does that yet, then write the code until it passes. Whether tests
  exist at all is not the point; which comes first is.
- **credit:** full credit for the order, stated clearly: the test is written before the code it is
  testing. Watching it fail first is a strong addition and is not required. Half credit for "you
  write tests as you go" or "tests and code together", which say nothing about which comes first.
  No credit for "TDD", "test-first development" or "red-green-refactor", which are other names for
  it rather than what it is. No credit for "it means the code is well tested", "it means there are
  lots of tests", or "it means the tests are run automatically".

### q-tdd-vs-writing-tests

- **type:** free
- **goal:** w-tdd
- **move:** DISTINGUISH
- **answer:** both end with a working button and a passing test, so the difference is when the
  test was written. The test-driven one came first and was seen failing before any delete code
  existed, so it is known that it can fail and that the new code is what makes it pass. The other
  test was written after the button already worked and has never been seen failing, so it may pass
  whether or not deleting really works.
- **credit:** full credit for the order together with what it buys: the test-driven test was
  written first and seen failing, so there is evidence it actually checks the thing. Half credit
  for the order alone with no consequence. Do not accept "one of them has tests and the other does
  not": both do. Do not accept differences of amount or quality, such as "test-driven means more
  tests", "test-driven means better code", or "test-driven is slower".

### q-tdd-catch-tests-after

- **type:** free
- **goal:** w-tdd
- **move:** CATCH
- **answer:** the order is backwards. Test-driven development means the test comes before the code
  it tests, and writing all the tests at the end is the opposite of that, so this is not it. The
  second half is wrong for the same reason: a test that has never been seen failing is weak
  evidence, because passing first time is also what a test that checks nothing does.
- **credit:** full credit for naming the order: the tests came after the code, so this is not
  test-driven development. The point about a test never seen failing is a strong addition and is
  not required; an answer that makes only that point, with nothing about the order, gets half
  credit. Do not accept a different quibble as the error: that they should have written more tests,
  that the app should have been built in smaller pieces, or that an agent should not be trusted to
  write tests for its own code.

### q-define-failing-test

- **type:** free
- **goal:** w-failing-test
- **move:** DEFINE
- **answer:** a test that ran and did not get what it was looking for: the check it makes did not
  hold, so it reports failure. That is a verdict about the code the test is aimed at, saying the
  app does not do that thing, at least not yet. It does not mean the test itself is faulty, and
  when the work is done test-first it is the expected state before the code is written.
- **credit:** full credit for "the test ran and the thing it checked did not come out the way the
  test required", or the plainer "the code did not pass the check that test makes". "It means the
  app is broken" is also full credit, since it puts the verdict on the app rather than the test.
  Half credit for "a test that didn't pass" with nothing about what that says. No credit for "a red
  test", which is another name for the same thing. No credit for defining it as a test that is
  itself wrong or broken.

### q-failing-vs-broken-test

- **type:** free
- **goal:** w-failing-test
- **move:** DISTINGUISH
- **answer:** a failing test is doing its job: it ran, made its check, and the check did not hold,
  which tells you something about the code being tested. A broken test is one where the fault is in
  the test itself, for instance it looks for a button that has been renamed, so its verdict tells
  you nothing about whether the app works. The fix for a failing test is usually in the app; the
  fix for a broken test is in the test.
- **credit:** full credit for locating the fault: a failing test reports on the code under test,
  while a broken test is itself at fault and its result says nothing about the app. "One means the
  app is wrong, the other means the test is wrong" is full credit, as is the fix-the-app versus
  fix-the-test version. Half credit for "a broken test is worse" or "a broken test won't run", with
  nothing about where the fault lies. No credit for treating them as the same thing, and no credit
  for an answer in which a failing test means something has gone wrong in the process, since in
  test-first work the failure is expected.

### q-red-before-code

- **type:** free
- **goal:** w-failing-test
- **move:** INTERPRET
- **answer:** the test it has just written for saving is failing, and that is deliberate: nothing in
  the app saves a note yet, so the test cannot pass. Seeing it fail first is the evidence that the
  test really does check saving, so when it passes later that will be because the saving code made
  it pass. It rules out reading the failure as something having gone wrong.
- **credit:** full credit for both halves: the test is failing right now, and the failure is wanted
  because the code it tests has not been written. The evidence it buys, that the test is known to
  be able to fail, is a strong addition and is not required. Half credit for "the test is failing"
  with nothing about why that is where the agent wants it. No credit for reading "red" as the test being faulty, the agent being stuck, or the agent asking for help.

### q-define-regression

- **type:** free
- **goal:** w-regression
- **move:** DEFINE
- **answer:** something that used to work and does not any more, broken by a change that was just
  made. The app has gone backwards from a state that was good: not a part that was never finished,
  and not a fault that was always there, but working behavior lost.
- **credit:** full credit for both halves: behavior that worked before has stopped working, and a
  change is what caused it. Half credit for "something broke" or "a bug" with no sense of going
  backwards from a working state, and half credit for "the same bug has come back", which is one
  kind of regression and misses the general case. No credit for "any bug in the app", for a problem
  the app always had, or for regression in the statistical sense of a line fitted to data.

### q-regression-vs-new-bug

- **type:** free
- **goal:** w-regression
- **move:** DISTINGUISH
- **answer:** the regression is behavior that used to work and has stopped, so there is a good
  state to go back to and a recent change is the suspect. The new bug is a fault in something new,
  or in something that never worked properly, so nothing has gone backwards: it was just written or
  just found. Only one of the two points at a change to look through.
- **credit:** full credit for the backwards step: a regression is about behavior that worked before
  and does not now, because of a change, while the new bug never worked. Half credit for "one is
  old and one is new" with nothing about having worked before. No credit for a difference of
  severity, of who found it, or of whether a test caught it.

### q-catch-regression-never-worked

- **type:** free
- **goal:** w-regression
- **move:** CATCH
- **answer:** nothing has gone backwards. The ordering never worked, so this is not working
  behavior lost to a change; it is a fault that was there from the first version and has only just
  been noticed. When you noticed it is not what makes something a regression.
- **credit:** full credit for saying a regression needs behavior that worked before and was broken
  by a change, and this behavior never worked. Do not accept a different quibble as the error: that
  they should have tested sooner, that the agent should have caught it, that the word does not
  matter, or that the bug is a small one.

### q-define-mock

- **type:** free
- **goal:** w-mock
- **move:** DEFINE
- **answer:** a stand-in that a test puts in the place of something real the code would otherwise
  use, usually the database or an outside service. The code under test talks to the stand-in
  instead of the real thing, and the test can then check what the code asked the stand-in to do.
  Nothing is really stored, sent or deleted.
- **credit:** full credit for "a stand-in for something real, usually the database or a service,
  that a test puts in its place". No credit for "a stub", "a fake", "a test double" or "something
  that pretends" alone, with no sense of what it stands in for. No credit for "sample data put into the database for the test", which is
  a test dataset, or for a mock-up of what the app will look like.

### q-mock-vs-test-data

- **type:** free
- **goal:** w-mock
- **move:** DISTINGUISH
- **answer:** the three notes are real content in a real database, and the code under test uses the
  database exactly as it normally would. A mock is not content at all: it is a stand-in put in the
  database's place, so the real database is never involved. With the test data, the test can check
  what actually ended up stored; with the mock, it can only check what the code asked the stand-in
  to do.
- **credit:** full credit for the difference that matters: test data is real content and the real
  database is still being used, while a mock replaces the database itself. The consequence version
  is also full credit: with a mock nothing is really stored, so the test can only check the request
  that was made. Half credit for "one is data and one is code" with nothing about whether the real
  database is used. No credit for a difference only of size or speed, and no credit for describing
  a mock as a database full of made-up notes.

### q-mock-earns-no-assertions

- **type:** free
- **goal:** w-mock
- **move:** INTERPRET
- **answer:** it tells you the saving code asked its stand-in to store the note, so the app is
  making the request it should. It leaves open everything after that: whether the real database
  accepted it, whether it was kept where a reload would find it, whether it was kept at all. If
  saving were broken at the database, the stand-in would still be asked and this test would still
  pass, so the answer does not settle your question.
- **credit:** full credit for both halves: the test shows the request was made to the stand-in, and
  it shows nothing about the real database keeping the note. Half credit for either half alone. No
  credit for taking the answer as showing that saving works, and no credit for reading "test
  double" as a second test, a duplicate note, or a backup database.

### q-code-review-vs-testing

- **type:** free
- **goal:** w-code-review
- **move:** DISTINGUISH
- **answer:** the tests run the app and check the particular behaviors somebody decided to check,
  so they only ever report on the cases a test exists for. A code review is a second reader going
  through the change itself before it is accepted, and it can judge what no test states: whether
  the change does what was asked, whether it will trip up the next change, whether it breaks
  something nearby, whether the tests themselves check anything worth checking.
- **credit:** full credit for the two distinct things: tests execute the code and check stated
  behaviors, while a review is a second reader looking at the code itself and judging what no
  test asks. "A review can find what nobody wrote a test for" is full credit. Half credit for
  "review is done by a person or another agent, tests run automatically", with nothing about what
  each can find, and half credit for "review is about style and tests are about correctness" as
  the whole difference. No credit for treating a passing test suite as a review.

### q-catch-own-tests-are-review

- **type:** free
- **goal:** w-code-review
- **move:** CATCH
- **answer:** running tests is not a review, and the agent that wrote the change is not a second
  reader. A code review is someone other than the author going over the change before it is
  accepted; a passing suite says only that the checks that already exist came out as expected.
- **credit:** full credit for either half stated clearly: running the tests is not a code review, or
  the author checking its own work is not a second reader. Naming both is stronger and is not
  required. Do not accept a different quibble as the error: that the suite might be small, that the
  agent might have skipped a test, that the agent might be lying, or that the change should also
  have been tried by hand.

### q-review-no-findings

- **type:** mcq
- **goal:** w-code-review
- **move:** INTERPRET
- **answer:** 4
- **credit:** 1 confuses a review with testing: a review is a reader's pass over the change, not a
  run of the suite. 2 claims too much, since a reviewer can miss things and reading a change is not
  running it. 3 misreads a clean review as no review having happened.

### q-define-spec-review

- **type:** free
- **goal:** w-spec-review
- **move:** DEFINE
- **answer:** the review that holds the finished change up against what was asked for: was
  everything in the request or the plan actually built, does it behave the way the request said,
  and was anything built that nobody asked for. It is about matching the request, not about how
  good the code is.
- **credit:** full credit for "it checks whether the change does what was asked", or "whether it
  matches the plan or the spec". Adding "and nothing extra" is a good addition and is not required.
  Half credit for "it checks the work is correct" with nothing about the request or the plan. No
  credit for "a spec review", which is another name for it. No credit for an account of code
  quality (readable, efficient, well structured), which is the other review.

### q-spec-vs-quality-review

- **type:** free
- **goal:** w-spec-review
- **move:** DISTINGUISH
- **answer:** the code quality review asks whether the code itself is any good: clear, sensibly
  organised, not repeating itself, not leaving a trap for the next change. The spec compliance
  review asks a different question entirely: does this do what was asked, all of it, and nothing
  that was not asked. A change can be beautifully written and answer the wrong request, or do
  exactly what was asked in an awful way, and each review catches one of those.
- **credit:** full credit for both questions: quality is about the code itself, spec compliance is
  about the match with what was requested. Half credit for one side named clearly and the other
  left vague. No credit for treating them as the same review run twice, for "one is stricter than
  the other", or for saying the spec review is the one that runs the tests.

### q-spec-review-passed

- **type:** free
- **goal:** w-spec-review
- **move:** INTERPRET
- **answer:** it tells you the change matches the plan the agent was working from, item by item,
  and that nothing was built beyond it. It leaves open whether that plan was what you actually
  wanted, whether the code is any good, and whether it works at all: matching a plan is not the
  same as behaving correctly, and a plan can faithfully describe the wrong thing.
- **credit:** full credit for both halves: the change matches the plan or request, plus at least one
  thing that leaves open (the plan may not be what you wanted, the quality is unjudged, or it may
  still not work). Half credit for the first half alone. No credit for reading it as "the tests
  pass", "the code is good", or "the app now does what I want" with no caveat.

### q-define-root-cause

- **type:** free
- **goal:** w-root-cause
- **move:** DEFINE
- **answer:** the thing actually responsible for the problem, the one that explains it, as against
  what you first noticed. Fix it and the problem stops for a reason someone can state; what you
  noticed is usually several steps downstream of it.
- **credit:** full credit for "the underlying reason the problem happens", set against what was
  noticed or what the problem looks like from outside. Half credit for "the reason for the bug"
  with nothing separating it from the symptom. No credit for "the bug", "the error message", or
  "the part of the app where the problem shows up", which are the symptom or where it surfaced.

### q-root-cause-vs-symptom

- **type:** free
- **goal:** w-root-cause
- **move:** DISTINGUISH
- **answer:** the symptom is what can be seen from outside: the note does not appear in the list
  after you save it. The root cause is whatever makes that happen, and it could be any of several
  things: the save never reaching the server, the server not storing it, the list being read from
  somewhere the note was never written. The symptom looks the same whichever it is, which is why it
  does not tell you what to fix.
- **credit:** full credit for placing the two: the symptom is the behavior observed, the root cause
  is the underlying reason that produced it, and one symptom can have several possible causes. Half
  credit for "the symptom is the effect and the cause is the cause" with nothing tied to this
  situation. No credit for treating them as the same thing, and no credit for naming one guessed
  cause as though the guess were the definition.

### q-catch-root-cause-workaround

- **type:** free
- **goal:** w-root-cause
- **move:** CATCH
- **answer:** nobody found out why the note was missing from the list. The reload covers the
  symptom up while the cause is still there, so it will show up again anywhere else that path is
  used, and the app now does an extra reload for a reason nobody can state.
- **credit:** full credit for saying the symptom was hidden and the underlying reason was never
  found, so the cause is still there. Naming a consequence, that it will come back elsewhere or
  that nobody can say why the fix works, is a good addition and is not required. Do not accept a
  different quibble as the error: that reloading is slow or ugly, that the agent should have
  written a test, or that they should have asked the agent for more detail.

### q-define-test-suite

- **type:** free
- **goal:** w-test-suite
- **move:** DEFINE
- **answer:** all the tests that exist for the project, taken together as one thing that can be run
  in one go. When an agent says it ran the tests, the suite is what it ran: every test anyone has
  written for this app, and nothing else.
- **credit:** full credit for "all the tests for the project, taken together and run as one", or
  "everything that runs when the tests are run". Half credit for "a group of tests" with no sense
  that it is what runs when the app is tested. No credit for "the tests", which is another name for
  it. No credit for the tool that runs them, for the test results, or for "the tests that are
  passing".

### q-suite-24-passing

- **type:** mcq
- **goal:** w-test-suite
- **move:** INTERPRET
- **answer:** 3
- **credit:** 1 turns a result about the  suite into a statement about the app. The suite is only the tests somebody wrote, and nothing in the answer
  says one of them reloads the page. 2 confuses the number of tests with the number of things the
  app does. 4 would only be true if the note actually disappears after a reload. 

### q-catch-suite-everything

- **type:** free
- **goal:** w-test-suite
- **move:** CATCH
- **answer:** the suite holds only the tests that were written. Anything nobody wrote a test for is
  not in it, so a fully passing suite says nothing about that behavior at all: "everything the app
  does" and "everything somebody tested" are not the same set. Even for the behaviors that do have
  tests, a pass is only as good as the tests: a weak test, or one that checks the wrong thing, can
  pass while the behavior is still wrong.
- **credit:** full credit for saying the suite is only the tests that exist, so a behavior nobody
  tested passes by being absent. An answer that says the tests might be weak or might check the
  wrong thing is also full credit. Do not accept a different
  quibble as the error: that tests can be flaky, that the agent might not have run them, or that
  they should also check the app by hand.

### q-coverage-vs-well-tested

- **type:** free
- **goal:** w-test-coverage
- **move:** DISTINGUISH
- **answer:** coverage measures how much of the code the tests reach: which lines ran at some point
  while the suite was running. Being well tested is about whether the tests check the right things,
  and would fail if a behavior broke. Code can run during a test that looks at nothing afterwards,
  so it can be covered and not tested; a little code with sharp checks can be well tested at a low
  percentage.
- **credit:** full credit for the difference that matters: coverage counts code the tests ran,
  while being well tested is about whether anything was checked and whether the check would fail if
  the behavior broke. An example of high coverage with poor testing is a strong addition and is not
  required. Half credit for "coverage is a number and well tested is a judgment", with nothing
  about what the number counts. No credit for treating them as the same thing, and no credit for
  saying coverage measures how many tests there are.


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
- **answer:** the request names nothing in particular, so as asked there is nothing for you or for
  a program to check. Send back the particular things the app is supposed to do, each with what
  would be seen if it broke, and ask for a test for each: a saved note is still in the list after a
  reload; a deleted note is still gone after a reload; clicking Save with the box empty adds no
  note and shows the message. A headless browser can do every one of those, so none of them needs
  you.
- **credit:** full credit needs both: naming the problem, that the request says nothing particular
  to check, and turning at least one behavior into something a program could check, with what it
  would look at afterwards. Half credit for naming the problem and supplying no particular
  behavior. No credit for "automate it" with nothing more, which is what this item is built to
  catch, and no credit for agreeing to click around and report back. Do not require all three
  behaviors, and do not require them to be the same three.
