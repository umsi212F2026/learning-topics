# Activities: workflow design

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

The minimum route, the orientation, one passed question for the one word and enough questions to
meet both capabilities and both cases of `c-divide-into-steps`, comes to about 32 minutes: about
14 for `a-read-workflow-design` (the reading is now about 8 minutes on its own), about 3 for the
word, one scenario's two questions of `a-split-a-lumped-step` at about 5 minutes each (the two
carry both cases), and one question of `a-defend-a-lane-choice` at about 5 minutes. With the two
pick-one checks instead (`a-contrast-step-splits` at about 3 minutes a question and
`a-pick-sound-defense` at about 2) it is about 25.
Both capabilities carry `taught elsewhere` (the session 18 class), so their four activities are
offered after that class, as practice and review.

In this topic's banks and live questions, every workflow is a made-up one described in words:
never the learner's own app, repo or project, never the reading's grading example or any other
homework or grading workflow, and never a document pipeline (downloading files, turning PDFs into
text, extracting from them, processing what was extracted), which is reserved for the session 18
class. No question needs reading code, a command or a query. Learner-facing text states the task,
never the scoring.

## Check notes


## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |
| `c-divide-into-steps` | divide a workflow into steps that can each be checked on their own | given a step in a described workflow that does too much, says where a step boundary belongs inside it and why: because the kind of check changes there, or because the executor does. Says what intermediate result is saved at that boundary, so the step before it can be checked on its own. A boundary with no reason, or with no saved result, does not meet it. Cases: `same-executor`, `executor-changes`. |
| `c-assign-a-lane` | choose who should do a step, and defend the choice by its trade-offs | given a step in a described workflow, says who should do it (a person, an AI agent or a program) and compares that choice with one alternative. Names one goal the choice helps and one it hurts, compared with that alternative, such as correctness, cost, timeliness or privacy, and ties each to something about this step: what its input is, what a mistake there would cost, or what data it handles. A reason that would hold for any step given to that executor does not meet it. |

## Coverage

| goal | checks | notes |
| ---- | ------ | ----- |
| `o-orientation` | `a-read-workflow-design` | |
| `c-divide-into-steps` | `a-split-a-lumped-step`, `a-contrast-step-splits` | |
| `c-assign-a-lane` | `a-defend-a-lane-choice`, `a-pick-sound-defense` | |

---

## Activities

### `a-read-workflow-design`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** a reading the course wrote for this topic, `tasks/read-workflow-design.md` in this
  folder, "Designing a workflow" (about 1,890 words, about 8 minutes). No external reading is
  used: the instructor wanted a course-written one. It follows one made-up example throughout, a
  teaching assistant who grades about 200 homework submissions a week with a workflow run partly
  by programs and partly by an AI agent. Sections: What people want from a workflow (eight final
  goals: correctness, cost, timeliness, security, privacy, maintainability, access, scale, each
  statable as value produced or value lost); Design decisions, and their options (seven decisions,
  of which this topic covers the first two, the second being who does each step: a person, an AI
  agent or a program); Intermediate goals (steps that can be checked, inspectable intermediate
  results, steps that are safe to rerun, a single source of truth, least privilege, failing
  loudly, and a note that intermediate goals serve each other); Trade-offs (a good reason points
  at something particular to the step: its input, what a mistake there would cost, what data it
  handles); Design patterns (three named ones: Checkpoints, where each step saves its output and
  the next reads it from there; Propose-apply, where an agent writes down what should change and
  a program makes the change; Maker-checker, where a separate step, usually a different executor,
  checks an unreliable step's output; then patterns as shorthand for telling an agent what you
  want, and a pattern is not a rule); Dividing a workflow into steps (the TA's one-step design, a
  five-step division with who does each step, the two rules of thumb, a boundary where the kind of
  check changes and a boundary where the executor changes, then "More steps are not always
  better": every boundary adds something to save, name and keep in sync); Who does each step (a
  paragraph each on what a program, an agent and a person are good and bad at; step 3 argued from
  its input, the cost of a mistake and its data; step 5 compared; steps 3 and 4 as maker-checker
  and steps 3 and 5 as propose-apply; then a closing paragraph on checking a step while building
  the workflow versus checking it on every run); Putting it to use. About 8 minutes of reading,
  12 with the two stops, 14 with the close. Words in place: the topic's one word, design pattern,
  in bold where it is introduced and defined in the words goals.md uses, with its synonym,
  pattern, used unbolded in the same section. Also in bold, though none is a word of this topic:
  final goals, design decisions, options, intermediate goals, trade-off, and each named final
  goal, intermediate goal, pattern and rule of thumb. The reading names no real workflow tool; it
  names three real AI providers (OpenAI, Anthropic, Google) once, as examples of where an agent's
  transcripts may be kept.
- **learner does:** reads the page once, top to bottom, and stops twice, answering before reading
  on; "I don't know yet" is an honest answer.
  1. After Trade-offs: names one final goal from the first section and one intermediate goal that
     would help it in the TA's workflow, and says how.
  2. After Design patterns: names one thing the Checkpoints pattern costs, compared with passing
     results straight from one step to the next.
  Then the close, about 2 minutes (up to 5 if a section is gone over again), with the reading still
  beside them: answers the question the tutor puts: with this page beside you, could you now take
  a short description of a workflow and say where a step boundary belongs and what would be saved
  there; and, for one of its steps, say who should do it and argue the choice from something about
  that step?
- **tutor role:** explainer
- **tutor does:** puts the reading in front of the learner by opening the file
  `tasks/read-workflow-design.md` from the topic folder on the local filesystem, so the learner's
  agent shows it formatted in a sidebar; does not paste it into the chat. Stays quiet through the
  reading except at the stops and when asked. At each stop, takes the learner's answer first and
  replies with one near-miss question rather than a verdict. Stop 1's intended answer is any
  sensible pairing with a how: steps that can be checked helping correctness (a program can
  confirm every submission has a pass or fail for every test), inspectable intermediate results
  helping correctness (the TA can see whether the tests or the feedback went wrong), failing loudly helping timeliness (a crashed
  test run is noticed before grades are due), least privilege helping security (the feedback step
  can't touch the gradebook), a single source of truth helping correctness (two copies of a grade
  can't disagree), steps safe to rerun helping correctness (running the posting twice doesn't post
  a grade twice). A pairing with no how gets one near-miss question ("if the test results were
  saved, what could the TA do when a student complains that they couldn't do now?"). Stop 2's
  intended answer is anything saving each step's output costs: more to save, name and keep in sync
  (the reading says so in the next section, under "More steps are not always better"), room to
  store it, a slower run, or a next step reading an old saved result by mistake. A learner who says
  it costs nothing gets one near-miss question ("if the step before changes what it writes, what
  happens to the step that reads it?"). Does not set or rehearse any word question from `a-words`:
  does not ask the learner to define design pattern, does not ask for an example of one, and does
  not offer a misused sentence to correct. Does not set or rehearse a question from this topic's
  capability activities either: does not ask the learner to divide a workflow or choose who does a
  step beyond what the reading itself works through; if the learner asks how to do that for a new
  workflow, says that is what the session 18 class and the practice after it are for. Says that
  building a workflow is Problem Set 5's work, not this topic's; that the other five decisions
  (triggers, state, failures, what each part may touch, where it runs) come in later topics and
  are checked nowhere here; and that the lists of final and intermediate goals, and the three
  named patterns, are there for the shape of the area and are not checked by name, though the lane questions ask for one goal a
  choice helps and one it hurts. At the close, puts the readiness question as written above and
  rules on the answer.
- **done when:** criterion met. The bar for this goal is did it once and help is expected
  throughout, so the ruling is on the learner's answer to the readiness question, not on the stops
  or on whether the tutor thinks they are ready. A plain yes to both parts is `criterion: met`. A
  hedge on either part, with no plain no, is `criterion: unclear`: for the first part go over
  Dividing a workflow into steps once more, for the second Trade-offs and Who does each step, and
  put the question again. A second hedge stays `unclear`: the tutor says both decisions are taught
  in the session 18 class and offers this topic's practice activities after it. Before session 18,
  an answer that waits on the class ("not until we've done it in class") is a hedge, not a no: it
  is `criterion: unclear` with no rereading, the tutor says the class teaches both decisions, and
  puts the question again at the learner's first study after it. A plain no to either part is
  `criterion: not met`: record it, ask what is missing, and offer to go back over the stop or the
  section that bears on it; don't put the question again in the same sitting. This goal isn't
  required, so a no never blocks anything else the learner wants to try.
- **worked example:** n/a
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. It
  shows nothing about design pattern, which has its own supply in `a-words`, and nothing about
  either capability: the reading works one example of each decision, the readiness question asks
  only whether the learner thinks they could do the same, and the stops are helped, ungraded and
  about other things. The reading is one course-written page built on one made-up grading
  workflow, so it shows nothing of a workflow in a different domain, or of the case worked in the
  session 18 class. The other five design decisions are in the reading and checked nowhere, by
  design, and so is its closing choice between checking a step while building and checking it on
  every run.
- **offer as:** this topic's orientation: one short page the course wrote, following one made-up
  grading workflow from what people want from it, through design decisions, trade-offs and
  patterns, to where its steps divide and who does each, with two short stops and a one-question
  close. About 14 minutes.

### `a-split-a-lumped-step`

- **serves:** `c-divide-into-steps`
- **supports:** attempt
- **checks:** `c-divide-into-steps`
- **artifact:** no external source. A described workflow with two steps that each do too much, from
  this activity's bank or written live per the generator below. About 5 minutes a question, 10 a
  scenario.
- **learner does:** reads the scenario's setup, a workflow laid out as numbered steps with who does
  each, and the one question served, which names one step that does too much; says in a few
  sentences where inside that step a boundary should go, why there, and what would be saved at it.
- **tutor role:** examiner
- **tutor does:** dividing a workflow is taught in the session 18 class (`taught elsewhere`), and
  this is practice for after it: before session 18 the tutor says so and offers to wait, and goes
  ahead if the learner wants. Sets the question as served, without rewording it or hinting; never
  names the cases, the two rules of thumb or the kind of reason wanted. Gives help whenever it is
  asked for, and records the attempt as helped. When the generator is run live, writes the key and
  the case into the record before showing the question. Labels the attempt with the question's
  path, or `a-split-a-lumped-step/<shape>` when run live, and records the case with `--cases`.
- **done when:** the criterion met with no help, case by case: a full-credit answer passes the case
  its question carries.
- **generator:** **A scenario** is one made-up workflow that someone runs on a regular cycle, set
  out in a setup of six to nine sentences. One or two sentences say who runs it, what it is for and
  roughly how much passes through it ("about 60 orders a week"). Then come four or five numbered
  steps, one sentence each, with the executor in parentheses after it as the reading lays out the
  TA's steps: a person named by role ("the shop owner"), an AI agent, or a program. Every step's
  sentence says in plain words what it takes in and what it produces; none is described with code,
  a command, a file format or a query. Two of the steps are lumped, each doing work that belongs in
  separate steps; the others are single acts, one executor doing one thing checked one way. The
  setup ends: "Some of these steps do more than one step's work."

  **Every lumped step has three parts, and so two joins.** At one join the shape's change happens;
  the other join has no change at all: the same executor on both sides, both results checked the
  same way. The boundary belongs only at the join with the change, so where it goes is never given
  away by the step having just one join. Which of the two joins comes first varies across the
  bank.

  **A question** names one lumped step and asks: "Step <n> does too much for one step. Where inside
  it should a step boundary go, and why there? What would be saved at that boundary?" Free response,
  `type: free`.

  **Shapes**, each with the case it carries, which its rubric `cases:` line lists. The examples are
  illustrations of the shape, not bank items, and their domains (a youth orchestra, a running club)
  are used by no bank in this topic.
  - `check-split` (`same-executor`): the lumped step is done by one executor throughout, named alone
    in its parentheses, and its sentence mentions no other. At the change join, the parts on either
    side produce different kinds of thing checked in different ways, and the later part uses the
    earlier one's result. One side's result can be checked against something fixed (the requests
    it came from, a count, a total, a rule such as no double bookings) and the other's needs a
    person's judgment (is it clear, polite, fair, well chosen), in either order. "3. Read the
    week's practice-room requests, settle who gets which room at which hour, list the bookings by
    day, and write each player a short friendly note with their slot. (an AI agent)" Key: no
    boundary between settling the rooms and listing them by day, since the same agent does both and
    both are checked the same way, against the requests and for clashes; the boundary goes before
    the notes, which are checked by a person reading them for tone and clarity; save the bookings
    list, one line per player with day, room and hour, so it can be checked before any note is
    written.
  - `handoff-split` (`executor-changes`): the lumped step names two executors in its parentheses,
    the second taking over from the first ("(an AI agent, then the club captain)"). The change join
    is the handoff; the join with no change lies inside one executor's two parts, before or after
    the handoff. At the handoff the
    kind of check changes too, as it naturally does when the work passes to a different executor
    (the first's result checked against something fixed, the second's needing a person's judgment,
    or the other way round), so the scenario never has to hold the check constant across a handoff
    and either reason is there to be named. "2. Sort the runners by their recent times, draft pace
    groups of similar speed, then move runners between groups by hand so that friends who carpool
    run together and nobody new is left in a group of strangers. (an AI agent, then the club
    captain)" Key: no boundary between sorting and drafting, since the agent does both and both
    are checked against the recent times; the boundary goes at the handoff from the agent to the
    captain, where the executor changes and the check changes with it (the draft is checked
    against the times, the captain's moves by someone who knows the members); save the agent's
    draft groups before the captain's changes, so a runner in the wrong group can be traced to the
    draft or to the hand changes.

  **How hard** depends on the join with no change:
  - Medium: the parts on either side of it are plainly one kind of act (settling the rooms and then
    listing them by day; sorting runners by time and then grouping them by time).
  - Hard: the parts on either side of it produce things that look different, though both are
    checked the same way by the same executor (looking up each member's address and then printing
    it on a label, both checked against the member list), so that join looks like a place for a
    boundary and isn't. The question's wording is unchanged.

  **A scenario holds two questions**, one on a `check-split` step and one on a `handoff-split`
  step, so one scenario carries both cases. Which comes first is chosen at random, and the second
  question's text gives nothing away about the first's answer. At most one of the two is Hard.

  **Domains** vary by scenario, none repeating within the bank: a food bank's volunteer shifts, a
  community garden's plot waitlist, a neighborhood association's yearly dues, a bakery's custom cake
  orders, a youth soccer league's referee assignments, a public library's overdue notices, a
  podcast's weekly episode release, a hiking club's trip sign-ups. No domain from the other three
  question activities' lists, no homework or grading workflow, and no step that downloads files or
  turns documents into text.

  **Spread across the bank.** A bank is six scenarios, 12 questions: each shape six times, three of
  them Hard, and `check-split` first in three scenarios. When the generator is run live, the tutor
  picks each next shape to carry a case the learner hasn't passed.

  Credit: full when the answer does all three: puts the boundary at the join where the shape's
  change happens; gives a reason naming what changes there; and names as the saved result the
  output just before that boundary, concretely enough to say what it is ("the bookings list"), not
  "save everything" or the step's final output. In a `check-split` step the reason must name the
  two kinds of check, each said even briefly, such as "compare with the requests" and "read for
  tone"; an executor change there is not in the step, so a reason resting only on one (proposing
  that a person check the notes) is not enough. In a `handoff-split` step either reason earns
  credit: the two executors, or the two kinds of check, or both. Half when the boundary is at the
  right join with only one of the other two: a reason that is missing, generic ("smaller steps are
  easier") or, in a `check-split` step, only an executor change the answer proposes; or a saved
  result that is missing or is not the output just before the boundary. An answer that also puts a boundary at the join with no change gets at most
  half. None when the boundary is only at the join with no change, or no boundary is placed.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works one of the two illustrations above aloud, the one of the same shape as the question:
  says what comes out of each part, how each would be checked and by whom, where those differ, and
  what to keep at the boundary so the first part can be looked at on its own. It may point to
  Dividing a workflow into steps in `tasks/read-workflow-design.md`.
- **doesn't show:** the question names the step that does too much, as the criterion allows, so a
  pass doesn't show the learner would find it in a described workflow, or in a workflow of their
  own, as planning for Problem Set 5 asks. At every handoff in these scenarios the kind of check
  changes too, and either reason earns credit there, so no question requires the executor reason
  on its own: a pass on `executor-changes` may rest on the check alone, and doesn't show the
  learner would put a boundary at a handoff where the check stays the same. It shows nothing about when a boundary costs more than it earns, which the reading
  mentions and nothing here checks.
- **offer as:** the write-it-yourself check, after session 18: a short workflow and one step that
  does too much, and you say where to split it, why, and what to keep at the split. About 5
  minutes a question. Harder than `a-contrast-step-splits`, since nothing is proposed for you.

### `a-contrast-step-splits`

- **serves:** `c-divide-into-steps`
- **supports:** attempt
- **checks:** `c-divide-into-steps`
- **artifact:** no external source. A described workflow and three people's proposals for splitting
  one of its steps, from this activity's bank or written live per the generator below. About 3
  minutes a question, 7 a scenario.
- **learner does:** reads the scenario's setup and the one question served, three proposals for
  splitting the same step, and picks the best division.
- **tutor role:** examiner
- **tutor does:** as `a-split-a-lumped-step`'s, including the offer to wait for session 18, except
  that it labels a live run `a-contrast-step-splits/<shape>`. Never says what a weaker proposal
  gets wrong before the learner has chosen.
- **done when:** as `a-split-a-lumped-step`'s: the criterion met with no help, case by case. Each
  question gets one ruling: the sound proposal passes the case the question carries, and the other
  two pass none. There is no half credit. Since every question sets the sound proposal beside both
  a split at the wrong join and a split that saves the wrong thing, one pick bears on both where
  the boundary goes and what is saved there.
- **generator:** **A scenario** is set up as in `a-split-a-lumped-step` (a made-up workflow of four
  or five numbered steps with executors in parentheses, two of them lumped, each lumped step with
  three parts and so two joins, one where the shape's change happens and one with no change at all,
  nothing described with code, a command, a file format or a query). The shapes are the same two,
  `check-split` carrying `same-executor` (one executor throughout, a boundary where only the kind
  of check changes) and `handoff-split` carrying `executor-changes` (a boundary at the handoff
  between two executors, where the kind of check changes too), with the same illustrations. A
  scenario holds two questions, one per shape, in random order.

  **A question** reads: "<Name1>, <Name2> and <Name3> each propose splitting step <n> into two
  steps." Then three numbered proposals, each one or two sentences in the same frame: where the
  split goes (after which part) and what, if anything, is kept between the two new steps. No
  proposal gives a reason. Then "Which proposal is the best division of step <n>?" with the choices
  "1. <Name1>'s", "2. <Name2>'s" and "3. <Name3>'s", `type: mcq`. The three proposals are within
  ten words of each other in length. Every question has all three of these:
  - the sound proposal: splits at the join where the shape's change happens and keeps the output
    just before that join, named concretely;
  - a `wrong-join` near-miss: splits at the join with no change, and keeps that join's output,
    named just as concretely, so it sounds as careful as the sound one;
  - a `nothing-saved` near-miss: splits at the right join, but keeps nothing the boundary needed.
    Here this near-miss alone sets how hard a question is; the join with no change may be of
    either kind `a-split-a-lumped-step` describes. Medium says so plainly ("hands the list straight on to the next step"). Hard keeps only the
    step's final output ("and keeps the finished notes"), so something is saved, but not the
    result the boundary needed.

  **Spread across the bank.** A bank is six scenarios, 12 questions: each shape six times, three of
  each shape's questions Hard, and the sound proposal in each of the three positions four times.
  Names vary and are never reused within a scenario.

  **Domains** are this activity's own, none repeating within the bank: a landlord's repair requests,
  a student club's event-room requests, a dental office's appointment reminders, a used-bike shop's
  online listings, a city's pothole reports, a choir's concert ticket sales, a pet shelter's adoption
  visits, a farmers market's stall assignments. No domain from the other three question activities'
  lists, no homework or grading workflow, and no step that downloads files or turns documents into
  text.

  Credit: full for the sound proposal, whose position is the rubric's `answer`; none for either
  other.
- **worked example:** shown only as help when asked for, which records the attempt as helped. As
  `a-split-a-lumped-step`'s, and then the tutor sets the two weaker splits of the same illustration
  beside the worked one (the split at the join with no change, and the right split with nothing
  kept) and says what the worked one lets someone check that each weaker one doesn't.
- **doesn't show:** the proposals are given and the learner picks, so a pass doesn't show they
  would place a boundary, give its reason or name what to save on their own; with three choices a
  guess is right a third of the time. The proposals give no reasons, so the learner's reason for a
  boundary is never seen, and the criterion's "and why" is not checked here. The rest of
  `a-split-a-lumped-step`'s `doesn't show` applies, including that every handoff here also
  changes the check, so no question asks for a boundary at a handoff where the check stays the
  same.
  `a-split-a-lumped-step` checks the same goal with nothing proposed.
- **offer as:** the quick check, after session 18: a short workflow and three people's ways of
  splitting one of its steps, and you pick the best one. About 3 minutes a question. Easier than
  `a-split-a-lumped-step`, since the splits are in front of you.

### `a-defend-a-lane-choice`

- **serves:** `c-assign-a-lane`
- **supports:** attempt
- **checks:** `c-assign-a-lane`
- **artifact:** no external source. A described workflow with two steps whose executor is left
  open, and three facts about each told in running prose, from this activity's bank or written live
  per the generator below. About 5 minutes a question, 10 a scenario.
- **learner does:** reads the scenario's setup and the one question served, which names one open
  step; says who should do it, compares that with one other choice, and names one goal the choice
  helps and one it hurts, saying what about the step makes it so.
- **tutor role:** examiner
- **tutor does:** choosing who does a step is taught in the session 18 class (`taught elsewhere`),
  and this is practice for after it: before session 18 the tutor says so and offers to wait, and
  goes ahead if the learner wants. Sets the question as served, without rewording it or hinting;
  never says which fact matters or which executor the key expects, and never says a reason must
  avoid being generic. Gives help whenever it is asked for, and records the attempt as helped.
  When the generator is run live, writes the key into the record before showing the question.
  Labels the attempt with the question's path, or `a-defend-a-lane-choice/<shape>` when run live.
  Rules on the reasons, never on the choice: any executor defended by reasons tied to the step
  passes.
- **done when:** the criterion met with no help.
- **generator:** **A scenario** is one made-up workflow that someone runs on a regular cycle, set
  out in a setup of who runs it, what it is for and roughly how much passes through it (one or two
  sentences), then four or five numbered steps, one sentence each, with the executor in parentheses
  as the reading lays them out: a person named by role, an AI agent, or a program. Two steps are open:
  their parentheses read "(who?)". Each open step has three facts (a fourth where the shape below
  adds one):
  - its input: what comes in, in what form (typed free text, a list someone has already approved,
    short form answers, photos) and how many a week;
  - what a mistake there would cost: who is hurt and how much, and whether a later step would catch
    it or it goes out unchecked;
  - what data it handles: whose, and whether any of it is private (health details, home addresses,
    payment details, children's names) or none is.
  These facts are not set out under a heading or one to a line. Below the steps comes one paragraph
  of running prose, six to nine sentences, in the voice of the person who runs the workflow, that
  tells both open steps' facts in no fixed order, mixed with each other: a sentence may carry two
  facts, and a fact is tied to its step by what it is about ("the refund requests", "the
  receipts"), not by a step number or a label naming the kind of fact. The paragraph also carries
  one irrelevant detail for each open step, said as plainly as the facts but bearing on no goal
  (how long the workflow has run, which day the team meets, what the form's heading says). The
  facts are stated plainly, never as a hint about who should do the step, and never using the words
  person, agent or program. Nothing is described with code, a command, a file format or a query.

  **A question** reads: "Who should do step <n>: a person, an AI agent or a program? Compare your
  choice with one of the other two: name one goal your choice helps and one it hurts, and say what
  about step <n> makes it so." Free response, `type: free`.

  **Shapes**, by the executor the facts favor (the key's natural choice) and the alternative the
  key compares it with. In every shape the facts give the natural choice one goal it helps and one
  it hurts against that alternative, each traceable to a fact, and give the alternative the same,
  so a learner who picks the alternative can also pass. All are Medium.
  - `structured-irreversible`: natural choice a program, alternative an AI agent. The input is a list
    someone has already approved, in a fixed form; a mistake moves money, changes a booking or
    changes a record, and nothing later catches it; and one more fact gives the program a cost, such
    as a few entries a week arriving with a note typed where a number should be. Helped: correctness,
    tied to applying exactly the approved list every time. Hurt: timeliness, or someone's time, tied
    to the odd entries the program will stop on.
  - `messy-volume-checked`: natural choice an AI agent, alternative a person. The input is typed
    free text in volume (a hundred or more a week, in mixed styles); a mistake is caught at a later
    step where a person reviews; the data includes something private. Helped: timeliness or cost,
    tied to the volume and messiness of the input. Hurt: privacy, tied to the private detail going
    to the agent's provider, or correctness, tied to the particular misreading this input invites.
  - `judgment-few-costly`: natural choice a person, alternative an AI agent. A handful of cases a
    week, each needing judgment on something the form doesn't settle; a mistake costs one person a
    lot and goes out unchecked; the data is private. One more fact says when the person can do it
    ("the manager does these on Friday mornings"). Helped: correctness or privacy, tied to the
    judgment or the data. Hurt: timeliness, tied to when the person is available, or the person's
    time, tied to how long each case takes.

  **A scenario holds two questions**, one per open step, of two different shapes, in step order.
  The second question gives nothing away about the first's answer.

  **Reasons differ across the bank.** No two open steps in a bank have the same pair of facts behind
  the key's helped and hurt goals: vary the kind of input, the volume, the private data (health
  details in one, a home address in another, a child's name in a third), what a mistake costs and
  to whom, the odd entries a program stops on, and when the person is free. A learner who memorizes
  one key's reasons has nothing to reuse on the next step.

  **Domains** are this activity's own, none repeating within the bank: a veterinary clinic's
  follow-up calls, a nonprofit's donation receipts, a theater's ticket refunds, a coffee shop's
  supplier orders, a tutoring center's tutor matching, a bike-share's damage reports, a town
  newsletter's event listings, a moving company's quote requests. No domain from the other three
  question activities' lists, no homework or grading workflow, and no step that downloads files or
  turns documents into text.

  **Spread across the bank.** A bank is six scenarios, 12 questions, each shape four times. When the
  generator is run live, the tutor picks a shape the learner hasn't seen yet.

  The facts are chosen so that each of the three pairings of executors (the natural choice against
  the alternative, the natural choice against the third executor, and the alternative against the
  third) has a goal each side helps and one it hurts, traceable to a fact; the third pairing may
  rest on the same facts as the other two. The key gives the natural choice and alternative; for
  each of the three pairings, the helped and hurt goals each fact supports for each side; which
  sentences of the paragraph carry each open step's facts; the irrelevant detail for each open
  step; and two or three generic reasons that would fail because they hold for any step given that
  executor ("programs don't make mistakes", "an agent is cheaper", "a person has better judgment",
  "agents can be wrong in ways that look right"). A reason resting on the irrelevant detail is not
  tied. Credit: full when the answer chooses an
  executor, names one alternative, and names a goal the choice helps and a goal it hurts compared
  with that alternative, each with a reason tied to a fact about this step (its input, what a
  mistake would cost, or its data). A reason is tied when it would not hold for that executor on a
  step with different facts; a generic reason that mentions the step's nouns ("a program is cheaper
  for these refunds because programs cost almost nothing to run") is still generic. Half when one
  of the two is tied and the other is generic or missing, or when both are tied but no alternative
  is named. None when neither is tied, or no executor is chosen.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works a made-up step aloud, from a domain no bank uses: a dog-walking business matching
  three or four new clients a week to walkers, from owners' typed notes about their dogs ("pulls
  hard, scared of bikes"); a bad match could get a dog or a walker hurt, and nothing later catches
  it; the notes include home addresses; the owner does matching on Sundays. The owner rather than
  an agent: it helps correctness, because the notes need judgment about which walker can handle
  which dog and a mistake there can injure someone; it hurts timeliness, because a client who signs
  up on Monday waits until Sunday. Then the tutor shows a generic version ("a person has better
  judgment") and says why it would hold for any step. It may point to Trade-offs and Who does each
  step in `tasks/read-workflow-design.md`.
- **doesn't show:** the step's facts are all present in one short paragraph with only one
  irrelevant detail beside them, so a pass shows the learner can pick what matters out of a loose
  description, but not that they would find it in a longer one, or notice that a fact they need is
  missing and ask, as their own Problem Set 5 workflow would make them. One step is defended at a
  time, so a pass shows nothing about how the choices for
  neighboring steps fit together (an agent's step followed by a person's review, as in the
  reading). Ruling on whether a reason is tied is a judgment; the key's generic reasons narrow it
  without removing it.
- **offer as:** the write-it-yourself check, after session 18: a short workflow, a step with who
  does it left open and a short description of it, and you choose and argue the choice. About 5
  minutes a question. Harder than `a-pick-sound-defense`, since you write the argument and pick the
  facts out yourself.

### `a-pick-sound-defense`

- **serves:** `c-assign-a-lane`
- **supports:** attempt
- **checks:** `c-assign-a-lane`
- **artifact:** no external source. A described workflow, facts about two of its steps and two
  people's defenses of who should do each, from this activity's bank or written live per the
  generator below. About 2 minutes a question, 5 a scenario.
- **learner does:** reads the scenario's setup and the one question served, two defenses of the same
  choice for the same step, and picks the sound one.
- **tutor role:** examiner
- **tutor does:** as `a-defend-a-lane-choice`'s, including the offer to wait for session 18, except
  that it labels a live run `a-pick-sound-defense/<shape>` and rules from the rubric's `answer`.
  Never says which clause differs between the two defenses before the learner has chosen.
- **done when:** the criterion met with no help. Each question gets one ruling: the sound defense
  passes and the other doesn't. There is no half credit.
- **generator:** **A scenario** is set up as in `a-defend-a-lane-choice` (a made-up workflow, two open
  steps with the same three facts each, nothing described with code, a command, a file format or a
  query), with the same three shapes, two different shapes per scenario, and the same rule that no
  two open steps in a bank share the pair of facts behind their reasons, except in one respect: the
  facts are not running prose. For each open step, a short paragraph headed "About step <n>:" gives
  its facts, one sentence each, and nothing else, so the learner can check a defense's clause
  against exactly what the step's paragraph says.

  **A question** reads: "<Name1> and <Name2> both think step <n> should be done by <executor>
  rather than <alternative>. Here is how each puts it." Then two numbered defenses, each two
  sentences in the same frame: "<Executor> rather than <alternative> helps <goal>, because ... It
  hurts <goal>, because ...". Both choose the shape's natural choice over its alternative and name
  the same two goals. Then "Which defense is sound?" with the choices "1. <Name1>'s" and
  "2. <Name2>'s", `type: mcq`. In the sound defense both because-clauses point at facts in the
  step's paragraph and draw from them the direction the fact supports. The near-miss is identical
  except for one because-clause, which is not tied to the step. That clause always uses the step's
  own nouns (the refunds, the receipts, the members), so neither defense can be picked for
  mentioning the step and the other not. The two defenses are within ten words of each other in
  length.
  - Which clause is the untied one varies: the helped clause in half the bank, the hurt clause in
    the other half.
  - Medium, of two kinds, used equally:
    - `fact-not-given`: the clause rests on a fact that sounds particular to the step but that the
      step's paragraph doesn't contain ("because these refunds are all under ten dollars", when
      the paragraph says nothing about amounts).
    - `wrong-direction`: the clause rests on a fact that is in the paragraph but draws from it a
      direction it doesn't support ("helps correctness, because a few entries arrive with a note
      typed where a number should be", a fact that makes a program stop, not one that makes it
      right).
  - Hard, `generic-with-nouns`: the clause borrows the step's nouns while its reason doesn't depend
    on them and would hold for any step given that executor ("because running a program over these
    refunds costs almost nothing"), so it reads as tied.

  **Spread across the bank.** A bank is six scenarios, 12 questions: each shape four times, half the
  questions Hard, three questions of each Medium kind, and the sound defense first in six. Names
  vary and are never reused within a scenario.

  **Domains** are this activity's own, none repeating within the bank: a gym's membership
  cancellations, a recipe site's reader comments, a summer camp's pickup list, a band's merch
  orders, a hotel's room-damage charges, a ride-share co-op's driver payouts, a museum's
  school-group bookings, a plant nursery's delivery routes. No domain from the other three question
  activities' lists, no homework or grading workflow, and no step that downloads files or turns
  documents into text.

  Credit: full for the sound defense, whose position is the rubric's `answer`; none for the other.
- **worked example:** shown only as help when asked for, which records the attempt as helped. As
  `a-defend-a-lane-choice`'s: the dog-walking step, the tied defense and the generic one side by
  side, with the tutor saying which fact each tied clause rests on.
- **doesn't show:** the choice, the alternative and the goals are given, and the learner picks
  between two defenses, so a pass doesn't show they would choose an executor or find a step's
  reasons on their own; with two choices a guess is right half the time. Only the Hard questions
  set a reason that would hold for any step beside a tied one; the Medium ones test whether a
  clause rests on a fact the step has, in the direction it supports. Every defense here argues for
  the natural choice, so a pass says nothing about defending a less obvious one. Each step's facts
  are laid out under a heading, one to a line, so a pass doesn't show the learner would find what
  matters about a step in a looser description; `a-defend-a-lane-choice` gives them as running
  prose. One step is defended at a time, so a pass shows nothing about how the choices for
  neighboring steps fit together. `a-defend-a-lane-choice` checks the same goal with the argument
  written by the learner.
- **offer as:** the quick check, after session 18: a short workflow, a step and two people's
  defenses of the same choice for it, and you pick the one whose reasons are about the step. About
  2 minutes a question. Easier than `a-defend-a-lane-choice`, since the arguments are written for
  you.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
