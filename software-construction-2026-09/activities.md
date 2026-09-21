# Activities: software construction

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

<!--
  Authored by curation/critique and placed by the orchestrator. Rewritten wholesale each pass,
  so don't edit it — it will be replaced.

  Dated, and short. What the tutor should know about this file as a whole before using it:
  the menu skews toward reading, two capabilities are thinner than they look, the depth
  runs heavier than goals.md asks for. Only things that survived the revision round —
  anything that got fixed doesn't belong here.

  Empty is a legitimate and good outcome. Say "nothing at file level" rather than inventing
  an observation.
-->

## Goals

| id                      | Goal | Criterion — what gets examined, and what counts |
| ----------------------- | ---- | ----------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |
| `c-ask-tested` | ask whether something was tested, and tell a real answer from a hollow one | Given one thing the app should do and the agent's answer to "has this been tested?", says whether the answer names a test that would fail if that one thing broke. If it does not, says what to ask the agent next. An answer about the whole suite, such as "all 24 tests pass", is not an answer about one thing. Nor is a named test that would still pass if that one thing broke, such as one that checks a note was accepted without checking it was saved, or one that runs against a mock instead of the real database. |
| `c-judge-manual-test` | tell when a check really needs a person, and when the agent should automate it | Given an agent's request to test something in the app by hand, says whether a program could do the check instead, for example the agent driving a headless browser. If it could, says what the automated test would do in the app and what it would check, well enough that the agent could write it. If it could not, names what the check needs that only a person can supply. "Automate it", with no account of what the test would check, does not meet it. |

## Coverage

<!--
  Derivation convention, recorded so it does not get re-flagged: an activity carrying `checks`
  is a check, so it appears only in the `checks` cell and never in `study`. Activities whose
  `serves` is `all` sit on the `o-orientation` row, which is the row that carries them; they are
  not repeated on every other goal's row.
-->

| goal                    | study | checks | notes |
| ----------------------- | ----- | ------ | ----- |
| `o-orientation` | `a-read-superpowers-readme`, `a-trace-superpowers-diagram` | `a-dry-run-stepping-in` | |
| `c-ask-tested` | `a-read-name-the-break`, `a-sort-tested-answers`, `a-narrated-hollow-test` | `a-judge-tested-answer`, `a-ask-own-agent-tested` | |
| `c-judge-manual-test` | `a-read-playwright-actions`, `a-sort-manual-requests`, `a-narrated-automate-request` | `a-judge-manual-request`, `a-answer-own-manual-request` | |

---

## Activities

### `a-read-superpowers-readme`

- **serves:** `all`
- **supports:** orient
- **artifact:** Superpowers' own README, in the clone every student has beside course-materials:
  `../superpowers/README.md` from the root of the learning-topics repository, at the commit the
  course pins (v6.3.0, `b36e082`). The same file is at
  https://github.com/obra/superpowers/blob/b36e0829c6d0140e93cfef2ca599b1b07d4a7797/README.md for
  anyone whose clone is missing. Four sections only, about 530 words and 5 minutes of reading
  inside a 25 to 30 minute session: "How it works", "The Basic Workflow" (seven numbered skills),
  "What's Inside" (the Skills Library list) and "Philosophy". Skip the installation sections, which
  are most of the file. There is no code in the four sections. They name five of this topic's nine
  words in place: test-driven development ("true red/green TDD", "RED-GREEN-REFACTOR"), failing
  test ("write failing test, watch it fail"), code review ("requesting-code-review"), spec
  compliance review ("two-stage review (spec compliance, then code quality)") and root cause
  ("4-phase root cause process"). They say "tests" and "clean test baseline" but never test
  suite, and never mention mock, regression or test coverage. In three places the README differs
  from the skill files the course pins (see `tutor does`).
- **verified:** 2026-09-21
- **learner does:** reads the four sections in order, with the Depth section of this topic's
  `goals.md` open beside it. Marks each place the README says the person does something (answers
  questions, signs off on the design, says "go", chooses what happens to the branch at the end).
  Then says which of the four moments in Depth the README mentions at all and which it never does:
  the agent asks you to check something by hand; the run ends and lists the decisions it made for
  you; you try what it built and it is not what you wanted; it hits a failure it could not
  resolve. Stops at each of the five words above as the README reaches it and says what they
  think it names before reading on ("no idea yet" is a fine answer). After the read, asks about
  the four words the README never uses (test suite, mock, regression, test coverage) one at a
  time, and says each back in a sentence of their own after the tutor's reply.
- **tutor role:** explainer
- **tutor does:** stays quiet through the reading except at the stops and when asked. At each
  word stop, takes the learner's guess first and replies with a near-miss question rather than a
  verdict ("you said a failing test means something is broken; what about a test the agent wrote
  a minute ago, before the code it tests exists?"). Anchors the four missing words in this
  course: the test suite is everything that runs when the agent says "all tests pass"; a mock is
  what a test puts where the real database would be, which matters once the lab adds one; a
  regression is something that used to work breaking after a change; test coverage is how much of
  the code the tests reach, which is not the same as how well it is checked. Flags where the
  README differs from the pinned skills, because the course pins the skills: step 2 says the
  worktree is made after design approval, where the skills make it when execution starts; step 4's
  "executes in batches with human checkpoints" is the other executor, which the course's students
  won't be on, since they always have subagents; step 7 lists "discard" among the options at the
  end, where the pinned skill offers three options and discards only when asked in so many words.
  When the learner reaches step 4, says that between "go" and the end the agent is built not to
  stop and ask (the skill's own words: "Do not pause to check in with your human partner between
  tasks"), which is why the moments in Depth are so few. Says that nothing in the README, or in
  the pinned skills, asks the person to check anything by hand: when their agent does ask, that is
  the agent's own habit, not a Superpowers step. Defines nothing unasked beyond the four missing
  words.
- **done when:** each of the four Depth moments is marked as mentioned or not mentioned, each of
  the five words has the learner's first guess and the tutor's near-miss, and each of the four
  missing words has the learner's own sentence. This entry carries no `checks`: the readiness
  indication `o-orientation` is ruled on is taken in `a-dry-run-stepping-in`, which follows.
- **offer as:** the prose route, in Superpowers' own words: the short account of the workflow your
  agent follows, read beside the course's account of where you step in. Quicker than
  `a-trace-superpowers-diagram` (25 to 30 minutes against 30 to 40) and names five of the nine
  words where they belong, but it lists steps without saying who does each, so it never shows you
  how few of them are yours. Take it if you would rather read than look at a diagram. Either
  route is followed by `a-dry-run-stepping-in`.

### `a-trace-superpowers-diagram`

- **serves:** `all`
- **supports:** orient
- **artifact:** the course's own diagram of the pinned Superpowers,
  `workflows/develop/superpowers.bpmn` in the course-materials repository every student has
  cloned, opened in Camunda Modeler (installed in Installation 2, where double-clicking a `.bpmn`
  file was set up to open it). It was drawn from the skill files at v6.3.0, commit `b36e082`, not
  from the README. No code anywhere. At the top level, the lower pool (the one labelled
  "obra/superpowers v6.3.0") has three lanes: HUMAN operator, AI AGENT and PROGRAM. The HUMAN lane
  holds only the start, "Finish the branch" and the end. The PROGRAM lane holds "Run the project's
  full test suite", the diamond "suite green?", and the end "stopped, suite red". The box "Execute
  the plan, task by task" drills down to a plane of its own, whose HUMAN and PROGRAM lanes are both
  empty, each with a note beside it saying why. That plane holds the task reviewer and its diamond
  "spec met and quality approved?", the fix rounds, and the whole-branch reviewer, and it ends
  "branch built, rulings handed over". Selecting an element shows its documentation in the
  properties panel; the documentation of "Finish the branch" describes the "Rulings I made" list.
  The diagram gives a place to five of the nine words: test suite, test-driven development and
  failing test (the note beside the empty PROGRAM lane on the plane below says "the TDD red/green
  cycle, happens inside each implementer"), spec compliance review (the reviewer's diamond) and
  code review (the two reviewers). It gives none to mock, regression, root cause or test coverage.
  30 to 40 minutes.
- **verified:** 2026-09-21
- **learner does:**
  1. Opens the diagram and, before reading any note or clicking anything, looks at the lower
     pool's three lanes and writes down which lane they expect to be busiest and where they expect
     to come in themselves.
  2. Finds everything in the HUMAN lane, selects "Finish the branch", and reads its documentation
     in the properties panel.
  3. Drills into "Execute the plan, task by task" and reads the notes beside the empty HUMAN and
     PROGRAM lanes. Finds the task reviewer, its diamond "spec met and quality approved?", and the
     whole-branch reviewer.
  4. Back at the top level, follows "Run the project's full test suite" to "suite green?" and both
     of its exits.
  5. Draws their own one-line version of a run, left to right, and marks on it the four moments
     from the Depth section of this topic's `goals.md` where they step in: the agent asks for a
     check by hand; the run ends and lists the decisions it made for them; they try what it built
     and it is not what they wanted; it hits a failure it could not resolve. For each, says
     whether the diagram draws it, only mentions it in a note or in documentation, or does not
     show it at all.
  6. Places the topic's nine words on that sketch (test-driven development, failing test,
     regression, mock, code review, spec compliance review, root cause, test suite, test
     coverage), says which ones the diagram gave them nowhere to put, and asks about those.
- **tutor role:** explainer
- **tutor does:** stays quiet until the prediction in step 1 is written, then says which part of it
  the diagram will bear out. Through steps 2 to 4, answers questions and shows where the properties
  panel and the drill-down marker are if the learner cannot find them, and explains BPMN notation
  only as far as a question needs. At step 5, steers by questions toward this reading rather than
  giving it: the rulings list is drawn (at the end of the plane below, and in the documentation of
  "Finish the branch"); a failure it cannot resolve is drawn once ("stopped, suite red") and
  otherwise appears only in the note beside the empty HUMAN lane, as four interrupts that can fire
  anywhere; finding it is not what they wanted comes after the diagram ends; a request to check
  something by hand appears nowhere, because nothing in the pinned skills tells the agent to make
  one, so when their agent asks, that is its own habit. At step 6, supplies a place for each word
  the diagram lacks: a mock sits inside a test, standing where the database would be; a regression
  is what running the whole suite again after a change is there to catch; root cause belongs to a
  Superpowers skill (systematic-debugging) the diagram does not draw, used when a test fails or a
  bug turns up; test coverage measures how much code the tests reach, and no step in the diagram
  looks at it. Corrects a misplaced word by asking what would have to be true for it to live
  there, rather than by moving it.
- **done when:** the sketch shows the four moments, each marked drawn, noted or not shown, and all
  nine words placed where the learner can point at them, and the learner can say what each
  placement means with the diagram still open. This entry carries no `checks`: the readiness
  indication is taken in `a-dry-run-stepping-in`, which follows.
- **offer as:** the picture rather than the prose, and the only route that shows who does each
  step. You see the HUMAN lane almost empty, which is the point of this topic: the few moments you
  step in are the ones left over. Longer than `a-read-superpowers-readme` (30 to 40 minutes against
  25 to 30), and it asks you to read a BPMN diagram in Camunda Modeler, which the workflows session
  prepared you for. Take it if you want to see where you come in before learning what the words
  mean. Either route is followed by `a-dry-run-stepping-in`.

### `a-dry-run-stepping-in`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** no external source. Whatever the learner oriented with, still open beside them:
  the README and their marks from `a-read-superpowers-readme`, or the diagram and their sketch from
  `a-trace-superpowers-diagram`. 10 minutes.
- **verified:** 2026-09-21
- **learner does:** two rehearsals, neither of them judged. First, the tutor, speaking as their
  coding agent at the end of a piece of work, asks them to check one thing by hand, and the learner
  says roughly whether a program could do it and what it would check. Second, the tutor, still as
  the agent, answers "has this been tested?" about one thing the app should do, and the learner
  says whether that answer settles it and what they would ask next. Then answers the question the
  tutor puts.
- **tutor role:** explainer
- **tutor does:** sets both rehearsals from the generator below. Grades neither. If an answer shows
  a misunderstanding (taking "all tests pass" as an answer about one thing, or saying "automate it"
  with nothing about what the test would check), explains it once and moves on. Then puts this
  question, word for word, naming what they oriented with: "With [the README, or your sketch]
  beside you, could you now attempt the two things this topic is for: when your agent asks you to
  check something by hand, telling whether a program could do it instead; and when you ask whether
  something was tested, telling a real answer from a hollow one?" Rules on the answer.
- **done when:** criterion met. The bar for this goal is did it once, and help is expected
  throughout, so the ruling is on the learner's own indication: not on how either rehearsal went,
  and not on whether the tutor thinks they are ready. A yes to one half and a hedge on the other
  is `criterion: unclear`: explain the hedged half again and put the question again. A plain no
  to either half is `criterion: not met`: record it, ask what is missing, and offer the orientation
  route they did not take, or a study activity on the half they named. Do not put the question a
  third time in the same sitting. This goal is not required, so a no blocks nothing else.
- **kind:** generator
- **generator:** vary the request and the answer; hold everything else fixed. The request is one
  Easy instance from `a-judge-manual-request`'s generator: a single item a program could plainly
  check ("Could you add a note, reload the page, and tell me whether it's still there?"). The
  answer is one Easy instance from `a-judge-tested-answer`'s generator: a `suite-count` or
  `by-hand` answer ("Yes, all 24 tests pass."). Both are about a small Notes app with a server and
  a database, described in one sentence. Fixed: two rehearsals in that order, neither graded, then
  the readiness question word for word. Difficulty does not vary: this settles an indication, not
  a capability.
- **worked example:** if the learner freezes on either rehearsal, the tutor answers a different
  instance of the same kind out loud in two or three sentences, then hands the original back.
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. Both
  rehearsals are helped, ungraded and at the easiest level, so it shows nothing about either
  capability, and nothing about the nine words, which have their own supply.
- **offer as:** the short step that closes orientation, after either `a-read-superpowers-readme` or
  `a-trace-superpowers-diagram`. Not an alternative to them: they give you the shape, and this is
  where you say whether you have it. Ten minutes, and nothing new to open.

### `a-read-name-the-break`

- **serves:** `c-ask-tested`
- **supports:** deepen
- **artifact:** "Writing Good Tests", a reference file inside Superpowers' test-driven-development
  skill: `../superpowers/skills/test-driven-development/writing-good-tests.md` from the root of the
  learning-topics repository, at the pinned commit `b36e082`. About 1,300 words in all, with five
  short blocks of code or pseudocode. The skill tells the agent to read it whenever it writes or
  changes a test, so it is the standard the agent's own tests are meant to meet. Read only these
  pieces, about 500 words and 5 minutes of reading inside a 30 to 35 minute session: "Overview"
  (the two principles, "Every test names the break it catches" and "Every test exercises the real
  thing"); the first paragraph of "Principle 1: Name the Break", which asks "what production change
  should make this test fail"; from "Principle 2: Exercise the Real Thing", the paragraph "The mock
  earns no assertions", the line after its example quoting "your human partner" ("Are we testing
  the behavior of a mock?"), the first paragraph of "Mock at the right level", and "Prefer real
  components over complex mocks", which ends with a second such line ("Do we need to be using a
  mock here?"); "The Mutation Check", a list of five kinds of break; and "Warning Signs". Skip every
  code block: nothing here asks the learner to read one.
- **verified:** 2026-09-21
- **learner does:** reads the pieces in order, holding in mind one thing the tutor's app should do
  ("a saved note is still there after a reload"). At "Name the Break", writes the change to the
  app that should make a test of that thing fail, in words about the app ("the server says OK but
  never writes the note to the database"). At "The mock earns no assertions", says in one sentence
  how a test that checks a mock was called could pass while the real database never got the note.
  At "The Mutation Check", writes, for each of the five kinds of break, one way it could happen in
  the Notes app, and beside it the question they would ask the agent to find out whether any test
  would catch it. Takes the two "your human partner" lines and says at what moment in a real run
  they would ask each. From "Warning Signs", picks two they could spot from an agent's plain-words
  description of a test, without seeing its code, and says what in the description would give each
  one away.
- **tutor role:** socratic questioner
- **tutor does:** before the read, says what the file is: instructions Superpowers gives the agent
  itself, so every question the learner writes here is one the agent's own rules say it should be
  able to answer. Describes the app in two sentences: notes typed in and saved, kept in a database
  by a server, still there after a reload. Stays out of the reading until something is written.
  Takes each written break and asks whether a test that looks only at the screen right after Save
  would catch it. Takes each question and asks what answer from the agent would satisfy the
  learner, pressing until the answer they would accept names one test and what it checks. If asked
  what a code block shows, says it in one sentence of words and does not show the code. At the
  end, points at one line in a neighbouring skill,
  `../superpowers/skills/verification-before-completion/SKILL.md`, under "Key Patterns", "Regression
  tests (TDD Red-Green)": "Write → Run (pass) → Revert fix → Run (MUST FAIL) → Restore → Run
  (pass)". It is the request that settles any doubt about one test: undo the change, run the test,
  watch it fail.
- **done when:** the learner has a break and a question for each of the five kinds in the Mutation
  Check, and with the file beside them can say, for any of their questions, what answer from the
  agent would settle it. No `checks`: the learner chose the thing, the tutor pressed on every
  question, and there was no agent's answer to judge.
- **offer as:** the reasons, from the rules your agent is given about its own tests. Short, about
  500 words and 30 to 35 minutes with the writing, and the only candidate that shows you the
  standard the agent already claims to meet, so the questions you learn to ask are ones it has no
  excuse not to answer. It is written for the agent rather than for you, in a developer's
  shorthand, with code you skip. `a-sort-tested-answers` gives you examples before reasons;
  `a-narrated-hollow-test` shows you a green suite with the saving broken.

### `a-sort-tested-answers`

- **serves:** `c-ask-tested`
- **supports:** deepen
- **artifact:** `tasks/sort-tested-answers.md`, written for this topic: a short description of a
  Notes app with a server and a database, ten answers an agent gave to "has [one thing] been
  tested?" about four things the app should do, and a key for the tutor. Three answers name a test
  that would fail if the thing broke. Seven do not, each for a different reason: a count of passing
  tests, a check that the server accepted the note, a test against a mock, a coverage percentage,
  "I tried it in the browser", a real test of a different behavior, and a test that checks half of
  the thing. 20 to 25 minutes. No app, no code, nothing to install.
- **verified:** 2026-09-21
- **learner does:** reads the app description, then answers the file's three questions for each of
  the ten answers: does it name a test that would fail if that one thing broke (yes, no, or can't
  tell from this); what in the answer decided it; and, if not yes, the one question they would send
  the agent next. Then states, in one or two sentences, the rule they sorted by.
- **tutor role:** critic
- **tutor does:** shows the learner everything above the key and nothing in it. Takes all ten
  verdicts and the rule before commenting on any. On each verdict that disagrees with the key, asks
  what the learner would break in the app, and whether that test would still pass, rather than
  giving the answer. When either answer of one of the key's comparison pairs was misjudged (a4 and
  a8; a1, a9 and a6; a10 and a3; a7 and a3), puts them side by side. Reads each next question back
  as a literal agent would answer it, and where the question could be answered with another count,
  a percentage or a plain "yes", answers it that way and lets the learner see why that settles
  nothing.
- **done when:** the learner's rule says, in some words of their own, that the answer has to name
  one test and what it checks, that the check has to be one that would come out differently if the
  thing broke, and that a count, a percentage, a stand-in database or "I tried it" does not count;
  and every next question they wrote would get a test named or a failure shown. No `checks`: the
  pairs are built to be compared, so the contrast does part of the judging, and the set is fixed
  and can be remembered.
- **offer as:** examples before reasons, and the quickest of the three: 20 to 25 minutes, one
  file, no app. All ten answers are about the same small app, so the only thing that varies is the
  difference between an answer that settles it and one that only sounds as if it does. Take
  `a-read-name-the-break` for the reasons first, or `a-narrated-hollow-test` to watch it happen.

### `a-narrated-hollow-test`

- **serves:** `c-ask-tested`
- **supports:** orient, deepen
- **artifact:** no external source. A scratch project the tutor builds before the session, in a
  scratch directory outside any repository the learner commits to, using only Node (the course
  installs version 24) and no packages: a small notes module whose save writes notes to a JSON
  file standing in for the database, and three tests run with Node's built-in test runner
  (`node --test`). All three are about saving a note:
  - A, "save reports success": calls save and checks that it returns success.
  - B, "save asks the store to write": replaces the file store with a stand-in (a mock) and checks
    that the stand-in was asked to write the note.
  - C, "a saved note can be read back": saves into a real JSON file in a temporary folder, reads
    the notes back from that file, and checks the note is there.

  And two planted breaks, each one line the tutor can switch on and off. First break: save returns
  success without calling the store at all. Second break: save calls the store, but the store
  writes nothing to the file. 20 to 25 minutes in the session.
- **verified:** 2026-09-21
- **learner does:** never reads the code, and does not need to. Hears each test described in one
  plain sentence and writes the three sentences down. Then, writing a prediction before every run:
  1. The tutor runs the three tests with nothing broken. The learner predicts pass or fail for each,
     then watches.
  2. The tutor, speaking as a coding agent, answers "has saving been tested?" with "Yes, all 3
     tests pass." The learner says whether that answers it, and writes the question they would send
     next.
  3. The tutor switches on the first break. The learner writes pass or fail for each of A, B and C,
     then watches the run.
  4. The tutor switches to the second break. Predictions again, then the run.
  5. With both runs in front of them, says which one test they would want the agent to name when
     asked about saving, and rewrites their question from step 2 so that only that test, or one
     like it, could satisfy it.
- **tutor role:** explainer
- **tutor does:** builds the project and confirms before the session that all three runs come out
  as intended: nothing broken, all three pass; first break, A passes and B and C fail; second break,
  A and B pass and C fails. If any run comes out differently, fixes the project before showing
  anything. Describes each test in plain words and never shows its code; shows only the runner's
  summary lines (each test's name with pass or fail) and says what each line means. Takes every
  prediction in writing before the run it is about. Narrates the weighing, with one false start
  left in on purpose: after the all-green run in step 1, says "so saving is tested", then stops,
  asks itself which of the three would notice if saving broke, and admits a green run cannot tell
  it. After step 4, says plainly what the learner has just seen: a passing test beside a broken
  save, twice over, and the stand-in in B that catches the first break but not the second. Ties
  the two to the criterion's own examples: A checks the note was accepted without checking it was
  saved, and B runs against a mock instead of the real database. Deletes the scratch project at
  the end.
- **done when:** the learner's predictions and the three runs are written down, and with them in
  front of them the learner can say why A and B stayed green while saving was broken, and what
  question would have got C named. No `checks`: the tutor built the tests, described them and ran
  them.
- **offer as:** watch it happen: a passing test with the saving broken, in a project small enough
  to hold in your head, with your predictions written down before each run. The only candidate
  where you actually see a test pass that should have failed, which the others can only tell you
  about. Needs a live session, 20 to 25 minutes, and a tutor that can run Node on your laptop. Take
  `a-sort-tested-answers` for a quicker route with nothing running.

### `a-judge-tested-answer`

- **serves:** `c-ask-tested`
- **supports:** attempt
- **checks:** `c-ask-tested`
- **artifact:** no external source. An app described in a few sentences, a private inventory of
  its tests that the tutor writes before the attempt, and the tutor playing the learner's coding
  agent. 15 minutes.
- **verified:** 2026-09-21
- **learner does:** is given the app description and one thing the app should do. Asks the
  "agent", in their own words, whether that thing has been tested. When the answer comes, writes
  down, before sending anything else: whether the answer names a test that would fail if that one
  thing broke (yes, no, or can't tell from this), the reason in one sentence, and, if not yes, the
  question they will send next. Sends that question, and when the reply comes, writes the same
  judgment about the reply. Works alone. Never sees test code, and is not asked to.
- **tutor role:** role-play partner
- **tutor does:** before the attempt, builds the instance per the generator and writes the
  inventory into the record: each test the app has, in plain words (what it does in the app, what
  it checks at the end, and whether it uses the real test database or a stand-in), and, for the one
  thing asked about, which tests would fail if it broke, possibly none. Plays a coding agent that
  answers truthfully and literally from the inventory, answering what it was asked and
  volunteering nothing. The first answer is the kind the generator sets, whatever the learner's
  wording. Every later answer is the literal, truthful answer to the question actually asked: if
  the learner's question can be answered with a count, a percentage or a plain "yes", answers it
  that way. Helps only if asked, and writes any help down word for word. Sends the adjudicator the
  app description, the thing asked about, the inventory, both answers, the learner's judgments and
  questions verbatim, and every piece of help. Afterwards, shows the learner what the inventory
  held. Labels the attempt `a-judge-tested-answer/<kind>`, naming the first answer's kind.
- **done when:** criterion met with no help, on a Medium or Hard instance.
- **kind:** generator
- **generator:** fixed for every instance: the app is a small web app with a Vite React front end,
  a server and a database, described in three to five sentences a user could have written; the
  thing asked about is one behavior a user could see, stated in one sentence; the inventory is
  written before the attempt, lists four to seven tests, and describes each in plain words; nobody
  sees test code; the agent never lies.
  What varies:
  - the app: a notes app, a reading list, a club sign-up sheet, a recipe box, a habit tracker, or
    the learner's own lab app as they describe it.
  - the thing: something added is kept after a reload; something deleted stays deleted; an edit is
    kept; an empty or invalid entry is refused with a message and nothing is saved; a list is in
    the right order; a total or count on the page matches; one person's items are not shown to
    another (only for an app that has sign-in).
  - the first answer's kind, which is what sets the difficulty:
    - `suite-count` (Easy): a count of passing tests, or "the suite is green".
    - `by-hand` (Easy): the agent tried it in the browser.
    - `accepted-not-saved` (Medium): names a test that checks the request was accepted (a success
      reply from the server, or the item showing on screen straight away) and not that it was
      kept.
    - `other-behavior` (Medium): names a real test of a neighbouring behavior of the same feature.
    - `coverage` (Medium): a coverage percentage for the code involved.
    - `real` (Medium): names a test that does the thing through the app against the real test
      database and checks what would differ if it broke. The right verdict is yes; a next question
      is optional, and if the learner sends one, the agent answers it.
    - `mock` (Hard): names a test that replaces the database with a stand-in and checks the
      stand-in was called.
    - `half` (Hard): names a test that checks part of the thing (the message appears) and not the
      rest (nothing was saved).
    - `name-only` (Hard): names a test by its file or title and says nothing about what it checks.
      The right verdict is can't tell from this.
  - whether the inventory holds a test that would fail: in about half of the instances whose first
    answer is not `real`, it does, so a good next question gets it named; in the rest, none would,
    so the truthful reply to a good next question is that no test checks it, and the learner has to
    recognize that reply as the answer.
  Difficulty: Easy is `suite-count` or `by-hand`; Medium and Hard are as marked above. An attempt
  meant to count runs at Medium or Hard. Easy is for the worked example and for a retry with help
  after a miss. Across attempts and review visits, serve a first-answer kind the learner has not
  had, until `accepted-not-saved`, `mock`, `half` and `real` have each come up once, reading the
  labels `served.mjs` returns.
- **worked example:** work one Easy instance live, out loud: ask the question, read the answer, say
  why a count of passing tests is not about one thing, write the next question ("which test would
  fail if a saved note weren't there after a reload?"), and say why it cannot be answered with
  another count. At the first level of help on a real attempt, give only the question "if this
  thing broke tomorrow, which test in that answer would go red?".
- **doesn't show:** the tutor's answers are short and tidy. A real agent buries the test in a long
  report and may not say whether its "integration test" used the real database, so a pass here
  does not show the learner would find the one sentence that matters in a real report. The learner
  is told which thing to ask about and knows a check is under way, so a pass does not show they
  would think to ask in the middle of their own work. The truth is a written inventory in plain
  words, so the learner never has to weigh an agent's description against what its test really
  does. A `real` first answer exercises only the verdict half of the criterion: the "what to ask
  next" half is examined only when the first answer is hollow, which is why the rotation above
  requires hollow kinds as well.
- **offer as:** the check you can take now, before your own app has tests. The tutor plays your
  agent while holding a written list of what each of its tests really checks, so whatever you
  missed comes back specific. 15 minutes and a live session. `a-ask-own-agent-tested` is the same
  thing with your real agent, about your real app.

### `a-ask-own-agent-tested`

- **serves:** `c-ask-tested`
- **supports:** attempt
- **checks:** `c-ask-tested`
- **artifact:** no external source. The learner's own app in the in-class lab or in Problem Set 2,
  once their agent has written tests for it, and their own coding agent (Codex, with Superpowers).
  10 minutes on top of the work, and the tutor's reading afterwards.
- **verified:** 2026-09-21
- **learner does:** at a point where the agent says a task, or the whole run, is done, picks one
  thing the app should do that they care about, and writes it down in one sentence in a note
  before asking anything. Asks their agent, in their own words, whether that thing has been
  tested, without adding "which test would fail" to that first question. Before sending anything
  else, writes in the note whether the answer names a test that would fail if that thing broke
  (yes, no, or can't tell from this), the reason, and, if not yes, the next question. Sends that
  question word for word and writes the same judgment about the reply. Keeps the transcript from
  the first question through the agent's reply to the second, and brings it and the note to the
  tutor. No tutor is there while this happens.
- **tutor role:** none
- **tutor does:** when first offering this, tells the learner to keep the note and the transcript,
  and that anything they look at for help while writing gets noted at the top of the note.
  Afterwards, before reading the learner's judgments, establishes the truth: reads each test the
  agent named, in the learner's repository, and writes in plain words what it does, what it checks,
  and whether it uses the real database or a stand-in, then says whether it would fail if the
  thing broke. Where it can, confirms that by copying the project to a scratch directory outside
  the repository, breaking that one thing in the copy, and running the named test there, and says
  in the record whether it did. Never changes the learner's own project. Checks that the first
  question was asked plainly, and that the agent had not already said, earlier in the
  conversation, which test covered the thing. Sends the adjudicator the thing, the note, the
  transcript, the plain-words account of each named test (marked as the tutor's reading), whether
  the break was run, and any help noted. After the ruling, tells the learner what the named test
  really checks. Labels the attempt `a-ask-own-agent-tested`.
- **done when:** criterion met with no help.
- **kind:** generator
- **generator:** the material is the learner's own app and whatever their agent answers, so no two
  instances match and nobody sets the difficulty. Hold fixed: the thing is chosen and written down
  before asking; the first question is asked plainly; the judgment and the next question are
  written before anything else is sent; the transcript runs from the first question to the reply
  to the second; the truth about each named test is written before the learner's judgments are
  read. No instance if the agent had already named the test for that thing earlier in the
  conversation, or if the app has no tests yet (serve `a-judge-tested-answer` instead). An answer
  saying there is no test for the thing is an instance: the right verdict is no, and a good next
  question asks for a test that is shown failing first.
- **worked example:** no tutor is present during the attempt, so nobody offers one. If the learner
  stalls, they may open `writing-good-tests.md` from `a-read-name-the-break`, or their own notes
  from any study activity, and write at the top of the note that they did; the attempt is then
  recorded `unaided: no`.
- **doesn't show:** the truth rests on the tutor's reading of the named test, confirmed by running
  a break only where the tutor could; without that run, whether the test would fail is a reading,
  not an observation. The learner picks the thing and the moment, so a pass says nothing about
  whether they ask at the moments that matter. Which kind of answer comes back is up to the agent:
  a pass may never have met a stand-in database or a test that checks half the thing. And a real
  agent's answer can be long: the transcript shows whether the learner found the sentence that
  mattered, not what they skipped on the way.
- **offer as:** the real thing: your agent, your app, a behavior you care about, judged against
  what the named test really does. Adds ten minutes to real work, and is only possible once your
  lab app or Problem Set 2 has tests, which makes it the natural candidate for review visits later
  in the term. `a-judge-tested-answer` is the one to take now.

### `a-read-playwright-actions`

- **serves:** `c-judge-manual-test`
- **supports:** deepen
- **artifact:** Playwright documentation, "Writing tests", https://playwright.dev/docs/writing-tests
  (free, no account; the page's default JavaScript and TypeScript version). Playwright is one of
  the two tools the react-apps topic named for a headless browser. Read only three pieces: the
  "Introduction", whose first sentence is "Playwright tests are simple: they perform actions and
  assert the state against expectations"; the "Actions" section's "Navigation" and "Interactions"
  paragraphs and its table of basic actions (check, click, uncheck, hover, fill, focus, press,
  pick files to upload, select an option); and the "Assertions" section's paragraph and its table
  of ten common checks (checkbox is checked, control is enabled, element is visible, element
  contains text, element has attribute, a list has a given length, element matches text, an input
  has a value, the page has a title, the page has a URL). Skip "First test", "Test Isolation",
  "Using Test Hooks" and every code block. About 10 minutes of reading inside a 30 to 35 minute
  session. The page never says "headless", and neither table includes a reload; the tutor
  supplies both.
- **verified:** 2026-09-21
- **learner does:** reads the three pieces. Then takes four requests the tutor gives them, worded
  the way a coding agent asks for a check by hand, and for each one writes either: the steps a
  headless browser would take, in plain words drawn from the page's actions (go to the address,
  fill in the box, click Save, reload), and the one check from the Assertions table that would come
  out differently if the thing were broken; or, if nothing in the two tables could do it, what the
  check needs that only a person can supply. For each automated one, marks the detail in its steps
  that an agent would otherwise have had to guess (the exact text typed, which button, whether to
  reload).
- **tutor role:** socratic questioner
- **tutor does:** before the read, says that a program driving a browser can also reload a page,
  though the page's tables do not list it, and that "headless" only means the browser runs without
  a window. Gives four requests from `a-judge-manual-request`'s generator: two from `persist`,
  `remove` or `refuse`, one `taste` or `wording`, and one `mixed`, about the learner's lab app if it
  exists and otherwise a Notes app described in one sentence. Takes each answer and asks what the
  test would see if the thing were broken, pressing until the check named is one that would differ.
  Asks of each "a person has to" answer which check in the table comes closest and why it falls
  short. Explains a table entry in one plain sentence when asked; never writes or shows test code.
- **done when:** each of the four has either steps with a check from the table that would differ if
  the thing broke, or a named thing only a person can supply, and with the page beside them the
  learner can say which is which and why. No `checks`: the learner works with the page open and the
  tutor presses on every answer.
- **offer as:** the palette: a real reference page listing what a program driving a browser can do
  and what it can check, which is the vocabulary you need to tell your agent what its test should
  do. About 30 minutes. It is a developer's page with code you skip, and it says nothing about when
  a person is needed; that half comes from the tutor's four requests. `a-sort-manual-requests` gives
  you worked cases with no page to read.

### `a-sort-manual-requests`

- **serves:** `c-judge-manual-test`
- **supports:** deepen
- **artifact:** `tasks/sort-manual-requests.md`, written for this topic: a short description of a
  Notes app with a server and a database, eight requests its agent made for checks by hand, and a
  key for the tutor. Four could be done by a program (one of them needs no browser at all), two
  need a person, and two are partly each, one of them because it names nothing in particular to
  check. 20 to 25 minutes. No app, no code.
- **verified:** 2026-09-21
- **learner does:** answers the file's three questions for each request: could a program do it
  (yes, no or partly); if so, what the test would do and what it would check, in plain words an
  agent could write it from; if not, what only a person can supply. Then states the rule they used.
- **tutor role:** critic
- **tutor does:** shows everything above the key and nothing in it. Takes all eight answers and the
  rule before commenting on any. Reads each "yes" description back as a literal agent would and
  says where it would have to guess (what text to type, what counts as still there, whether to
  reload). On each "no", asks whether some part of it is a checkable fact. Makes sure m4 is
  discussed whatever the learner answered, because "automate it" is the answer it is built to
  catch, and m5, because the agent can do it itself with no browser and no test file. When either
  request of one of the key's pairs was misjudged (m3 and m8; m1 and m7; m4 and m6), puts the two
  side by side.
- **done when:** the learner's rule separates a check they can describe by what the app does and
  what would be seen if it broke from one that depends on what they wanted, on how something looks
  or reads, or on something only they can reach; and every "yes" description would let an agent
  write the test without asking. No `checks`: the set is fixed and the pairs are built to be
  compared.
- **offer as:** worked cases before any reading: eight requests about one small app, so the only
  thing that changes is what kind of check each one is. The quickest of the three, 20 to 25
  minutes with nothing to open but the file. Take `a-read-playwright-actions` for the list of what
  a program can check, or `a-narrated-automate-request` to watch a description become a test that
  goes red.

### `a-narrated-automate-request`

- **serves:** `c-judge-manual-test`
- **supports:** orient, deepen
- **artifact:** no external source. A scratch copy of the learner's own Vite + React starter
  project from the react-apps topic (or of their lab app, once it exists), running on their laptop,
  and a headless browser the tutor can drive (Playwright, as react-apps named it). 20 to 25
  minutes.
- **verified:** 2026-09-21
- **learner does:** watches, and writes a prediction before each reveal. The tutor, speaking as
  their agent, asks for two checks by hand on the copy: "Could you click the count button three
  times and tell me it shows 3?" and "I changed the heading. Does it look good to you?" Before the
  tutor says anything, the learner says for each whether a program could do it. Then watches the
  tutor turn the first request into a description in plain words, and interrupts wherever the
  description would leave an agent guessing. Predicts, in writing, whether a fresh agent given only
  that description would write a test that passes, and then whether the same test would fail once
  the button is broken so that each click adds 2. Watches both runs. Finally writes, in their own
  words, what they would have sent back to their agent for each of the two requests.
- **tutor role:** explainer
- **tutor does:** beforehand, asks where the starter project is, copies the whole folder (including
  `node_modules`) to a scratch directory outside any repository the learner commits to, starts it,
  and confirms a headless browser can open it; the original is never touched. Composes the
  description out loud with two false starts left in: first "automate it", then asks itself "check
  what?"; then steps that begin from wherever the learner's screen happens to be, then asks "what
  does a freshly opened browser have on screen at step one?" and rewrites them from the address.
  The finished description names the address, the button, three clicks, and the exact text the
  button should show afterwards, read off the running copy. Gives only that description to a fresh
  subagent, with this instruction: "Write and run one Playwright test from this description,
  against this address. Don't read the project's files. Report whether it passed, and every place
  you had to guess." Shows the learner the pass or fail line and the list of guesses, never the
  test's code. Plants the break in the copy (each click adds 2), has the same test run again, and
  shows the fail line. For the heading, says why it stays with a person (only the learner knows
  what "good" means for their app) and what a program could still check about it (that it is on
  the page and says the new words). Stops the copy's server and deletes the copy at the end. If no
  headless browser is available, says so, has the subagent write out the steps and the check it
  would use instead of running anything, and skips the break and the second run; the learner has
  then not seen a test go red, and the tutor says that too.
- **done when:** the learner's predictions and both runs are written down, and with the description
  in front of them they can say which of its details the fresh agent would have had to guess
  without, and what they would send back for each request. No `checks`: the tutor wrote the
  description and ran everything.
- **offer as:** watch a request to check by hand become a test that a fresh agent writes from
  words alone, then watch that test catch a break. The only candidate where your kind of
  description is tried for real. Needs a live session, your starter project, and a tutor that can
  drive a headless browser; without one it shrinks to a description with nothing run. Take
  `a-sort-manual-requests` for a faster route with no app.

### `a-judge-manual-request`

- **serves:** `c-judge-manual-test`
- **supports:** attempt
- **checks:** `c-judge-manual-test`
- **artifact:** no external source. An app described in a few sentences, and the tutor playing the
  learner's coding agent at the end of a piece of work, asking for checks by hand. 15 minutes.
- **verified:** 2026-09-21
- **learner does:** gets one message from the "agent" asking them to check one to three things by
  hand. Replies to it alone, item by item, before doing any check: for each item, either asks the
  agent to automate it and says what the automated test would do in the app and what it would
  check, in plain words the agent could write it from; or says they will do it themselves and
  names what the check needs that only they can supply. Writes no code and is not asked to.
- **tutor role:** role-play partner
- **tutor does:** before the attempt, builds the instance per the generator and writes the truth
  for each item into the record: whether a program could do it; if so, the essential steps and the
  check that would differ if the thing broke; if not, what only a person supplies; if partly,
  which part is which. Sends the message in an agent's voice and waits, helping only if asked and
  writing any help down word for word. When the reply is in, runs the stranger test on each item
  the learner said to automate: a fresh subagent gets only the app description and the learner's
  words for that item, with this instruction: "You have not seen this app's code and must not read
  any files. From this description alone, write out the test you would write: each step, and what
  it checks at the end. List every place you had to guess. Say whether your test would fail if
  [the thing, in the app description's words] broke." Sends the adjudicator the app description,
  the message, the truth for each item, the learner's reply verbatim, every piece of help, and each
  stranger report. Afterwards tells the learner where a stranger had to guess. Labels the attempt
  `a-judge-manual-request/<categories>`, naming the categories of the items served.
- **done when:** criterion met with no help, for every item, on a Medium or Hard instance.
- **kind:** generator
- **generator:** fixed for every instance: the app is a small web app with a Vite React front end,
  a server and a database, described in three to five sentences a user could have written; the
  message comes at the end of a piece of work, in an agent's voice, asks for the checks in a user's
  words, and never says which could be automated; the truth for each item is written before the
  message is sent; nobody writes code.
  What varies:
  - the app: as in `a-judge-tested-answer`'s generator.
  - each item's category:
    - `persist`: something added is still there after a reload.
    - `remove`: something deleted is gone, and still gone after a reload.
    - `refuse`: an empty or invalid entry is refused with a message, and nothing is saved.
    - `order` or `count`: the list order, or a number on the page, is right after some actions.
    - `navigate`: a link, or a pasted address, leads to the right page.
    - `own-run`: something the agent can do itself with no browser, such as starting the server and
      reading what it prints.
    - `taste`: whether a change looks right, or is what the learner wanted.
    - `wording`: whether some text makes sense to a reader.
    - `own-access`: needs something only the learner has: their phone in their hand, their own
      account, their inbox.
    - `mixed`: part checkable, part a person's judgment, such as the layout on a phone-sized screen
      (a program can check the page does not scroll sideways and the buttons are visible; whether
      it looks right needs a person).
    - `vague`: "make sure nothing is broken", which names nothing in particular.
  - the wording: an automatable item phrased in a person's terms ("check the list looks right after
    you delete one"), or a person's item phrased as though it were a checkable fact ("check the new
    message is clear").
  Difficulty: Easy is one item from `persist`, `remove` or `refuse`, plainly phrased. Medium is two
  items, one a program could do (any of the first six categories) and one only a person could
  (`taste`, `wording` or `own-access`), both plainly phrased. Hard is three items including a
  `mixed` or `vague` one, or any item phrased the other way round from its category. An attempt
  meant to count runs at Medium or Hard, because only there do both halves of the criterion come
  up. Easy is for the worked example and for a retry with help after a miss. Across attempts and
  review visits, cover at least once each `refuse`, `own-run`, `mixed` and `vague`, reading the
  labels `served.mjs` returns.
- **worked example:** work one Easy instance live: read the request, say out loud that a headless
  browser could do it, then write the description, naming the address, the exact text typed (text
  no other entry could have), each click, the reload, and what should be on the page afterwards.
  Then say which of those details an agent would have guessed wrong without. At the first level of
  help on a real attempt, give only the question "what would the test see if this were broken?".
- **doesn't show:** the stranger only writes the test out. It is not run against a real app, so
  "well enough that the agent could write it" is shown by a fresh agent's account of what it would
  write and where it guessed, not by a test that ran and went red. The learner knows this is a check
  and that some items may be automatable, so a pass does not show they would question a real
  agent's request in the middle of work instead of simply doing it. The truth for each item is the
  tutor's, and on `mixed` and `own-access` items reasonable people draw the line in slightly
  different places: the adjudicator should rule on whether the learner's line is defensible and
  named, not on whether it matches exactly. And the tutor's requests are short, where a real
  agent's are often buried in a long closing message.
- **offer as:** the check you can take now, on a made-up app, with a fresh agent reading your
  description cold to show where it would have to guess. Every item is either a program's job or
  yours, and some are both. 15 minutes and a live session. `a-answer-own-manual-request` is the
  same thing when your real agent asks.

### `a-answer-own-manual-request`

- **serves:** `c-judge-manual-test`
- **supports:** attempt
- **checks:** `c-judge-manual-test`
- **artifact:** no external source. The learner's own coding agent session during the in-class lab
  or Problem Set 2, at a moment when the agent asks them to check something in the app by hand. 10
  minutes on top of the work.
- **verified:** 2026-09-21
- **learner does:** when the agent asks for a check by hand, does not do it yet. First writes alone,
  in a note, a reply to each item: automate it (with what the test would do in the app and what it
  would check, in words the agent could write it from), or keep it (naming what only they can
  supply). Then sends the "automate" items to their agent word for word, followed by this fixed
  line: "Please write each of these as an automated test, working only from what I wrote. Before
  you write each one, tell me anything my description left you to guess. Then run it." Does the
  items they kept. Keeps the transcript from the agent's request through its reply to that message,
  and brings it and the note to the tutor. No tutor is there while this happens.
- **tutor role:** none
- **tutor does:** when first offering this, gives the learner the fixed line to keep somewhere they
  can copy it from, and says that anything they look at for help gets noted at the top of the note.
  Afterwards, reads the transcript and the note. Checks that the request came from the agent without
  the learner asking to be set one, and that the note was written before anything was sent. Writes
  its own truth for each item, as `a-judge-manual-request` does, before reading the learner's
  answers. Runs that entry's stranger test on each item the learner said to automate (a fresh
  subagent, no files, the app described in a sentence or two), because the working agent knows the
  project, and its list of guesses understates what a stranger would need. Sends the adjudicator
  the request, the note, the truth, the stranger reports, the working agent's reply, and any help
  noted; says so to the adjudicator when every item was one a program could do, since the other
  half of the criterion then went unexamined. After the ruling, tells the learner where a stranger
  had to guess. Labels the attempt `a-answer-own-manual-request`.
- **done when:** criterion met with no help, for every item in the request.
- **kind:** generator
- **generator:** the material is whatever the learner's agent asks for, so no two instances match
  and nobody sets the difficulty. Hold fixed: the request comes from the agent without the learner
  having asked for one; the note is written before anything is sent; the fixed line follows the
  automate items unchanged; the transcript runs from the request to the agent's reply to it; the
  truth and the stranger reports are written before the learner's answers are read. No instance if
  the learner prompted the request, or did the check before writing the note. A request with a
  single, plainly automatable item is an instance, and a fair one here, because the learner also
  had to stop and question a real request instead of just doing it.
- **worked example:** no tutor is present during the attempt, so nobody offers one. If the learner
  stalls, they may open the Playwright page from `a-read-playwright-actions` and write at the top of
  the note that they did; the attempt is then recorded `unaided: no`.
- **doesn't show:** which requests come up is up to the agent, so a pass may never have involved an
  item only a person could do, leaving the "names what only a person can supply" half of the
  criterion unexamined. The learner chooses which requests to bring. The working agent's reply is
  weak evidence, because it already knows the project; the ruling rests on the stranger reports and
  the truth, with the reply as supporting evidence only.
- **offer as:** the real thing: your agent asks you to check something, and you decide what to hand
  back before touching the app. Adds ten minutes to real work, and is only possible once your agent
  is building the lab app or Problem Set 2 and asks you for a check. `a-judge-manual-request` is
  the one to take now.

### `a-w-tdd`

- **origin:** generated
- **serves:** `w-tdd`
- **checks:** `w-tdd`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-failing-test`

- **origin:** generated
- **serves:** `w-failing-test`
- **checks:** `w-failing-test`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-regression`

- **origin:** generated
- **serves:** `w-regression`
- **checks:** `w-regression`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-mock`

- **origin:** generated
- **serves:** `w-mock`
- **checks:** `w-mock`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-code-review`

- **origin:** generated
- **serves:** `w-code-review`
- **checks:** `w-code-review`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-spec-review`

- **origin:** generated
- **serves:** `w-spec-review`
- **checks:** `w-spec-review`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-root-cause`

- **origin:** generated
- **serves:** `w-root-cause`
- **checks:** `w-root-cause`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-test-suite`

- **origin:** generated
- **serves:** `w-test-suite`
- **checks:** `w-test-suite`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-test-coverage`

- **origin:** generated
- **serves:** `w-test-coverage`
- **checks:** `w-test-coverage`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's
