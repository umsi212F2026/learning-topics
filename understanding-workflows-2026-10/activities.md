# Activities: understanding workflows

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

2026-10-28: nothing at file level.

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |
| `c-read-diagram` | read a workflow diagram and say what it claims | given a workflow diagram, says what it claims: what each shape marks, who does each step, what each kind of arrow means, and where the flow splits and merges. Cases: `shapes` (the state a run starts or ends in, a step, a gateway, a collapsed subprocess), `lanes` (who does a step, from its lane, including a step that spans two lanes, and where work passes from one lane to another), `arrows` (tells apart a next-step arrow, a branch label, and a document read by a step, and doesn't read every arrow as a handoff), `split-merge` (where flow splits [a named gateway] and where it merges [an unnamed one]), `trace-run` (given a trigger and the answer at each named gateway, says which steps run and which outcome the run reaches). Taught elsewhere: session 18 class. |

## Coverage

| goal | checks | notes |
| ---- | ------ | ----- |
| `o-orientation` | `a-read-workflow-deck` | |
| `c-read-diagram` | `a-read-course-diagram`, `a-judge-diagram-summary` | Both checks use the same three planes of one diagram the learner has already met in Installation 2 and in session 2, with exclusive gateways only and every element pointed at by the question. Meeting the goal therefore shows the learner can read this diagram when asked about specific parts. It does not show they can read an unfamiliar one, notice what a diagram leaves out, or handle parallel gateways. If both activities are done, the second one is answered on a plane the learner has already worked through, so treat it as review rather than new evidence. |

---

## Activities

### `a-read-workflow-deck`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** the session 2 lecture deck, "What is a workflow?". It is
  `docs/lecture-slides/l-what-is-a-workflow.html` in the learner's `course-materials` clone, a
  self-contained HTML file that opens in any browser with no server (arrow keys move, `Esc` shows
  every slide). Only slides 4 to 7 are read: 4, the definition of a workflow and what dropping each
  part leaves (a project, a checklist, a habit); 5, the vocabulary list (run, step, trigger,
  outcome, AI agent, script, handoff, with synonyms); 6, an xkcd flowchart; 7, the symbol glossary
  (states, step, file, handoff arrows, gateway split or merge). Slides 1 to 3 and 8 to 10 are class
  logistics, discussion norms, table questions about `bootstrap.bpmn` and lab instructions, and
  are skipped. Public copy:
  https://github.com/umsi212F2026/course-materials/blob/main/docs/lecture-slides/l-what-is-a-workflow.html
  (the repository is public and the page answers, but GitHub shows the file's source rather than
  the slides, and the repository has no GitHub Pages site, so the local copy is the one to open).
  About 4 minutes for the four slides, about 10 with the stop, the tutor's additions and the close.
- **verified:** 2026-10-28
- **learner does:** reads slides 4 to 7 once, then stops at slide 7 and answers before going on;
  "I'm not sure" is an honest answer. At the stop, writes one line in their own words for each of
  the glossary's five symbols, saying what it marks in a diagram: a state, a step, a file, a
  handoff arrow, and a gateway (both what a split is and what a merge is). Then hears the tutor's
  additions (below), and answers the close: with this deck beside you, could you now open one of
  the course's workflow diagrams in Camunda Modeler and say where a run starts and ends, who does
  each step, what each kind of arrow means, where the flow splits and merges, and which steps a
  given run goes through?
- **tutor role:** explainer
- **tutor does:** gives the learner the full path of the deck in their own `course-materials`
  clone and has them open it in a browser (double-click, or the tutor runs `open "<path>"` on
  macOS or `Start-Process "<path>"` on Windows). If the deck is not in the clone, the clone is out
  of date: bring it up to date first (the deck was published after session 2). Does not paste
  slides into the chat, and does not open any `.bpmn` file: the course's diagrams are this topic's
  check material. Stays quiet through the reading except at the stop and when asked. At the stop,
  takes the learner's lines first and replies to a wrong or vague one with one near-miss question
  rather than a verdict ("you said a gateway is where a decision is made; what about a diamond
  with two arrows in and one out?"). Intended lines: a state is a condition that starts or ends a
  run, not something done; a step is one action someone or something takes; a file is a document
  a step reads or writes; a handoff arrow is an arrow that crosses from one lane into another,
  where work passes from one actor to the next (this departs from the slide on purpose: the slide
  labels its one arrow symbol "Handoff" and includes arrows to and from a document, and the tutor's
  arrow addition below corrects that, so a line copying the slide gets the near-miss "is every
  arrow a handoff, even one between two steps the same actor does?"); a gateway with a question splits the flow by the answer, and one with no label is where
  paths come back together. After the stop, adds what the deck doesn't say, a sentence each.
  **Lane**: each horizontal band in a diagram is a lane, and its name says who does the steps drawn
  in it; a box drawn across two lanes is a step more than one of them takes part in. The deck's
  word **script** is the diagrams' `PROGRAM` lane: steps a program carries out exactly. A box with
  a small **plus** at its bottom edge is a **subprocess**, a step with a diagram of its own
  underneath, which Camunda opens when the plus is clicked. An arrow labeled with an answer (`yes`,
  `no`) leaves a gateway and says which way a run goes on that answer. **Arrows**, correcting the
  slide: not every arrow is a handoff. A solid arrow inside one lane just says what comes next,
  done by the same actor; only a solid arrow that crosses into another lane is a handoff of work.
  A dotted line between a file and a step says that step reads (or writes) the file; it is not the
  run moving to the file, and the thing to read off it is which step uses which file. Does not set or rehearse any
  word question from `a-words` (no asking for a definition, no word against its confusable, no
  misused sentence to correct), and does not set a question from this topic's capability
  activities. Says that reading the course's diagrams is practiced in this topic's other
  activities and in the session 18 class, and that drawing one is not part of this topic. At the
  close, puts the readiness question as written above and rules on the answer.
- **done when:** criterion met. The bar is did it once and help is expected throughout, so the
  ruling is on the learner's answer to the readiness question, not on the stop. A plain yes is
  `criterion: met`. A hedge with no plain no is `criterion: unclear`: go back over slide 7 and the
  tutor's additions once more, then put the question again; a second hedge stays `unclear`, and the
  tutor offers `a-read-course-diagram` as the place to find out. A plain no is `criterion: not
  met`: record it, ask what is missing, and offer to go back over the part that bears on it; don't
  put the question again in the same sitting. This goal isn't required, so a no blocks nothing.
- **worked example:** n/a
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. The
  stop is helped, ungraded and about the symbols in general, with no diagram open, so it shows
  nothing about `c-read-diagram`. It shows nothing about the thirteen words, which have their own
  supply in `a-words`; the deck names only some of them (it never says lane, subprocess, executor
  or workflow state), and lane and subprocess reach the learner only through the tutor's spoken
  additions. Slide 7 labels every arrow a handoff, including lines to and from a document, which is
  the misreading `c-read-diagram`'s `arrows` case checks for; the correction rests on one spoken
  sentence from the tutor, so a learner who missed it meets the slide's version first. The deck lists "skill" beside AI agent as another name, while this topic treats the
  two as different things; the tutor does not raise it.
- **offer as:** this topic's orientation: four slides of the session 2 deck, with a one-line
  gloss for each symbol on its glossary slide and a few sentences from the tutor on what the deck
  leaves out or gets loose (lanes, the plus marker, branch labels, which arrows are handoffs).
  About 10 minutes.

### `a-read-course-diagram`

- **serves:** `c-read-diagram`
- **supports:** attempt
- **checks:** `c-read-diagram`
- **artifact:** one plane of the course's own setup diagram, `workflows/bootstrap/bootstrap.bpmn`
  in the learner's `course-materials` clone, which they opened in Camunda Modeler in Installation
  2 and discussed at their table in session 2. Questions from this activity's bank or set live per
  the generator below. About 2 minutes a question; a scenario is two to four questions, 4 to 10
  minutes, one sitting.
- **verified:** 2026-10-28
- **learner does:** opens the diagram in Camunda Modeler, goes to the plane the scenario names, and
  answers the one question served in their own words, pointing at elements by the first line of
  their labels or by the steps on either side of them.
- **tutor role:** examiner
- **tutor does:** the goal is also taught in the session 18 class (`taught elsewhere`): before
  session 18 the tutor says so and asks whether the learner wants to try now or after, and goes
  ahead if they want. Before serving a scenario, checks that the diagram hasn't changed since the
  key was written: `git -C <course-materials> log -1 --format=%h -- workflows/bootstrap/bootstrap.bpmn`
  must print the commit the scenario's setup records; if it doesn't, the tutor doesn't serve that
  scenario and records it as a bank defect for the instructor. Gives the full path of the file and
  has the learner double-click it (it opens in Camunda Modeler on a machine that finished
  Installation 2); if it doesn't open, opens it by path, as `setup-editors` does (`open -a "Camunda
  Modeler" "<path>"` on macOS, `Start-Process "C:\Program Files\Camunda Modeler\Camunda
  Modeler.exe" -ArgumentList "<path>"` on Windows). Never describes the diagram in words, pastes
  its XML, or names an element the question doesn't already name. Reads the diagram itself from
  the `.bpmn` and rules from the rubric. Sets the question as served, without rewording it or
  hinting; never names the cases. Gives help whenever it is asked for, and records the attempt as
  helped. Labels the attempt with the question's path, or `a-read-course-diagram/<case>` when run
  live, and records the cases with `--cases`. Says when offering it that no one plane carries every
  case: meeting the goal takes `setup-top` (shapes, lanes, split-merge, trace-run) and the `arrows`
  question on `get-codex-running`, at least five questions over two scenarios, about 10 to 20
  minutes, which can be split over two sittings.
- **done when:** the criterion met with no help, case by case: a full-credit answer passes the case
  its question carries; half credit or none passes none.
- **generator:** **The material is fixed and real**: the generator picks elements from
  `workflows/bootstrap/bootstrap.bpmn` and writes questions about them; it never draws, edits or
  invents a diagram. Do not use `workflows/learn/learn.bpmn`, which lags the learn workflow it
  depicts. Every answer in a key is read from the `.bpmn` file at the commit the setup records,
  checked against the plane in Camunda or a render (`node workflows/diagram/tools/render.mjs`,
  with the subprocess's id for a plane below the top), since a step drawn across two lanes shows
  only in the geometry.

  **A scenario is one plane**, and there are three, each a file
  `tasks/a-read-course-diagram/<scenario-id>.md` with its key in
  `rubrics/a-read-course-diagram/<scenario-id>.md`:
  - `setup-top`: the top level, "opens the Day 1 page in Canvas" to its two end states. Carries
    `shapes`, `lanes`, `split-merge` and `trace-run`. It has two collapsed subprocesses (`Get Codex
    running`, `Set up the workspace`), one step drawn across two lanes (`Get Codex running`, in
    the HUMAN operator lane and reaching into AI AGENT), three named splits (`Codex running?`,
    `Able to complete?`, `install correct?`), two unnamed merges, and a loop (`not yet` at
    `install correct?` leads back to the merge before `Set up the workspace`). It does not carry
    `arrows`: its one file, `U-M API key`, is drawn as read by `Get Codex running`, and a question
    should not turn on that drawing.
  - `get-codex-running`: the plane under `Get Codex running` (click its plus). Carries `arrows`,
    `split-merge` and `trace-run`. It has two lanes, a file (`bootstrap-prompt.md`, read by `Open
    U-M GPT; paste the bootstrap prompt`), three named splits (`stuck?`, `worth trying?`,
    `checklist done?`), one unnamed merge with three arrows in (two of them loops), and two end
    states. It has no subprocess and no step across two lanes, so it carries neither `shapes` nor
    `lanes`.
  - `set-up-workspace`: the plane under `Set up the workspace`. Carries `split-merge` and
    `trace-run`. It has six named splits, one of them with four answers (`how far did I get
    previously?`), four unnamed merges, one of which gathers every `no` into `stopped at a
    checkpoint`, and two end states. It has no file, so it does not carry `arrows`.

  **The setup** is three sentences: what the workflow is (the first-day machine setup students
  went through), the path of the file and how to reach the plane ("Open
  `workflows/bootstrap/bootstrap.bpmn` in your `course-materials` folder. It opens in Camunda
  Modeler. Click the plus at the bottom of `Get Codex running` to open the diagram underneath
  it."), and "Each question below is about this plane of the diagram alone." It also records, on
  a line of its own, `diagram commit: <hash>`, the commit of `bootstrap.bpmn` the key was written
  against. It names no step, lane, gateway or outcome beyond the one needed to reach the plane.

  **Questions**, one per case the plane carries, in this order (study order: a later question may
  name a gateway or a branch an earlier one asked the learner to find, never the reverse).
  Elements are named by the first line of their label; an end state whose label holds a long dash
  is named by its first words (`blocked`, `stuck`). The examples show the shape, not bank items.
  1. `shapes` (Easy; `setup-top` only): "Name the state a run of this workflow starts in, and every
     state a run can end in. What does the rounded box `Report being stuck` mark? Which steps have
     a diagram of their own underneath them? What is the diamond just after `Get Codex running`?"
     The diamond is pointed at by its neighbor, never by its label, so the question doesn't say it
     carries a question. Answer: the start event's label; both end states; one step, an action
     someone does (here the human), with nothing more underneath it; both subprocesses; a gateway
     where the flow splits, the run going one way or the other by the answer to its question.
     Credit: full when all five parts are right; half when one is missing or wrong (one end state
     or one subprocess left out counts as one); none otherwise.
  2. `lanes` (Medium; `setup-top` only): "Who does `<step A>`? Who does `Get Codex running`? Name
     one place where work passes from one of them to another." Step A is a step with no plane below
     it: `Check the install` (in PROGRAM), `Report being stuck` or `Submit each session's report`
     (both in HUMAN operator), varying between the bank and live runs. Never `Set up the
     workspace`, whose own plane has steps in other lanes. Answer: A's lane, as the actor it names
     (the program, or the human); for `Get Codex running`, that the human and the AI
     agent both take part (naming the human as the main one is welcome, not required); and any one
     solid arrow whose two ends each sit wholly inside one lane, in different lanes, named by its
     two ends (gateways count as ends): `Codex running?` to the merge before `Set up the
     workspace`, `Able to complete?` to `Check the install` or (on `no`) to the merge before `Report being
     stuck`, or `install correct?` to `Submit each
     session's report` or (on `not yet`) back to the merge before `Set up the workspace`. An arrow into or out of `Get Codex running` doesn't
     count, since that box sits in two lanes; offering one makes this part wrong. Credit: full when all three are
     right; half when `Get Codex running` is given to one actor only and the rest is right; none
     otherwise.
  3. `split-merge` (Medium; every plane): "Where does the flow split, and where does it come back
     together? Point to each place by the steps just before and after it." On `set-up-workspace`,
     whose plane is long, the question names three of its splits and two of its merges by a
     neighbor and asks, for each, whether the flow splits or comes back together there, and which
     paths. Answer: each named gateway, as a split; each unnamed gateway, as a merge, with the paths
     that come together there. Credit: full when every one asked about is found and called the
     right one, and for every merge the paths that come together there are named (by the answer
     they leave a split on, such as `not yet`, or by the step they come from); half when one is
     missed or called the wrong one, or the paths are missing for one merge; none otherwise.
  4. `arrows` (Medium; `get-codex-running` only): "(a) the arrow from `Do the next step on the
     checklist` to `stuck?`: what does it tell you, and is it a handoff? (b) the label `<answer>` on
     the arrow leaving `<named split>`: what does it tell you? (c) the dotted line between
     `bootstrap-prompt.md` and `Open U-M GPT`: what does it tell you?" Answer: (a) `stuck?` comes
     next, in the same lane, so it is not a handoff; (b) a run goes that way when the answer to the
     gateway's question is that answer; (c) that step reads (uses) that file, which is not the run
     moving to the file and not a step. Credit: full when all three are right; half when one is
     wrong; none otherwise. Calling (a) a handoff, or reading (c) as the next step, is wrong. For
     (c), the deck's slide 7 calls a line to a document a handoff, so: "it's a handoff to the
     document", with nothing saying the step reads or uses the file, is wrong; an answer that says
     the step reads or uses the file is right whether or not it also uses the word handoff. For
     (b), vary which split and answer across the bank and live runs; for a live run (a) may instead
     name `Open U-M GPT` to the unnamed merge, which is also inside one lane.
  5. `trace-run` (Hard; every plane): "A run starts when `<trigger>`. At `<split 1>` the answer is
     `<x>`; at `<split 2>` it is `<y>` the first time and `<z>` the second. Which steps run, in
     order, and which end state does the run reach?" The answers take the run once around a loop
     where the plane has one, so a step runs twice. On `setup-top` a subprocess counts as one step;
     on `set-up-workspace` the answer at `how far did I get previously?` is not `first time`, so
     some steps are skipped. Answer: every step in order, merges and gateways not listed, and the
     end state reached. Credit: full when the steps and the end state are right; half when the end
     state is right and one step is missing, extra or out of order; none when the end state is
     wrong.

  **The bank** is the three scenarios, nine questions. Live runs, and later review, vary the
  pointed-at elements and the traced answers within the same planes (a different split for (b), a
  different step A, a different set of answers for a trace), and are keyed by reading the file at
  its current commit.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works the same kind of question aloud on a different diagram, saying what it looks at:
  `workflows/tour/tour.bpmn` (the tour at the end of setup, a single plane with no gateways) for
  start and end states, steps, lanes, handoffs, an arrow inside one lane (`tour skill invoked` to
  `Ask what they want`) and files (`Explain the four parts of the tour` reads the guide; `Write the
  record` writes `tour.md`); the box `Brainstorm the design` at the top level of
  `workflows/develop/superpowers.bpmn`, which has a plus and is drawn across the HUMAN operator and
  AI AGENT lanes, for a subprocess and a step across two lanes (pointing at the drawing only, with
  no claim about how Superpowers runs today); and, for splits, merges, branch
  labels and traces, whichever of the three bootstrap planes the question is not on, working only
  the one element or one short run needed.
- **doesn't show:** every question is on one diagram the learner has seen before, so a pass doesn't
  show they could read a brand-new diagram, drawn by someone else or in another style, and later
  attempts may draw on memory of this one rather than reading. `shapes`, `lanes` and `arrows` are
  each asked on only one plane (and `arrows` about one file), so they have little room to vary.
  The `arrows` ruling departs from the session 2 deck, whose glossary calls every arrow a
  handoff; a learner who learned the slide well can fail (a) for it. The diagram uses exclusive gateways only, so a
  pass says nothing about parallel paths or typed events. Questions point at the elements to read,
  so a pass doesn't show the learner would notice, unasked, what a diagram leaves out, or could say
  whether a step is in the right lane, which this topic leaves to sessions 18 to 21.
- **offer as:** the open-ended check: planes of the setup diagram, two to four questions each,
  answered in your own words. No single plane meets the goal: it takes the top level plus the
  arrows question on `Get Codex running`, at least five questions, about 10 to 20 minutes in all.
- **check note:** On the `get-codex-running` plane, the step `Open U-M GPT` carries the path of
  `bootstrap-prompt.md` as the second line of its own label. In Camunda, the learner can therefore
  see which file the step uses without reading the dotted line at all. Part (c) of the `arrows`
  question still catches the misreading that matters (the run moving to the file as its next
  step), but a right answer to "which step uses the file" is easier than it looks. For the `lanes`
  question, prefer `Check the install` as step A: `Set up the workspace` has HUMAN and PROGRAM
  steps on the plane underneath it, so "who does it" is open to argument.

### `a-judge-diagram-summary`

- **serves:** `c-read-diagram`
- **supports:** attempt
- **checks:** `c-read-diagram`
- **artifact:** the same diagram, `workflows/bootstrap/bootstrap.bpmn`, with sentences from a
  summary of it that an AI agent wrote, from this activity's bank or written live per the generator
  below. About 2 minutes a question, 4 to 10 a scenario.
- **verified:** 2026-10-28
- **learner does:** opens the plane the scenario names in Camunda Modeler and, for each sentence in
  the question served, says whether the diagram says that: yes or no.
- **tutor role:** examiner
- **tutor does:** as `a-read-course-diagram`'s (the session 18 offer, the commit check, opening the
  diagram, never describing it, help recorded as helped), and also: never says which sentences are
  wrong or how many, and doesn't ask the learner to explain a no. A learner who adds what the
  diagram does say is welcome to and gains nothing for it. Labels a live run
  `a-judge-diagram-summary/<case>`. Says when offering it, as for `a-read-course-diagram`, that
  meeting the goal takes `setup-top` and the `arrows` question on `get-codex-running`: at least
  five questions over two scenarios, about 10 to 20 minutes, splittable over two sittings.
- **done when:** as `a-read-course-diagram`'s: the criterion met with no help, case by case.
- **generator:** **The material** is as `a-read-course-diagram`'s: the same three planes, the
  same cases per plane, the same commit line in the setup, and nothing drawn or invented. Its
  scenario files are its own, `tasks/a-judge-diagram-summary/<scenario-id>.md` and its key under
  `rubrics/`, named `setup-top`, `get-codex-running` and `set-up-workspace`. The setup is as
  there, then: "An AI agent was asked to say in plain words what this plane of the diagram claims.
  Each question below gives sentences from its summary. For each sentence, say whether the diagram
  says that: yes or no."

  **A question** gives numbered sentences about one case and asks "Does the diagram say this?
  Answer yes or no for each." Together its sentences cover every part of its case: four for
  `shapes` (the start or end states, a step, a gateway, a subprocess), three for `lanes` (a step's
  actor, the step across two lanes, a handoff), three for `arrows` (an arrow inside one lane, a
  branch label, the file's dotted line), three for `split-merge` (each about one gateway, at least
  one a split and one a merge), and three for `trace-run` (one stated run, then three sentences
  about the steps it runs and the end state it reaches). Each sentence is plainly what the diagram says or one of the misreadings
  below, stated as plainly; none is half right or turns on a word. Within a scenario at least one
  question has two yeses or more and at least one has two noes or more, and no more than one
  question is all yes or all no. Questions come in the order of `a-read-course-diagram`'s, one per
  case the plane carries, at the same difficulty. Where a sentence restates something
  `a-read-course-diagram`'s key for the same plane gives, it is allowed: the planes are few.

  The misreadings, by case:
  - `shapes`: calls the start state the first step, or an end state a step; calls a collapsed
    subprocess a single action with nothing more to it; calls a gateway a step someone does.
  - `lanes`: gives a step to the actor its label suggests rather than the one its lane names (on
    `setup-top`, "the human checks the install"); gives `Get Codex running` to one actor alone;
    puts a handoff between two elements in the same lane.
  - `arrows`: calls an arrow inside one lane a handoff; reads a branch label as a step that runs;
    reads the dotted line between `bootstrap-prompt.md` and its step as the next step in the run.
    No sentence turns on whether the dotted line is a handoff, since the session 2 deck's glossary
    calls a line to a document one: the file sentence is about which step reads the file, or a
    misreading of it as the next step. A learner who adds "and it's a handoff" to a right yes or no
    is not marked down for it. The misreading that an arrow inside one lane is a handoff stays, and
    is wrong whatever the slide says.
  - `split-merge`: calls an unnamed merge a decision; says two paths never come back together when
    they do; says the flow splits where it merges.
  - `trace-run`: for a stated run, a step list that skips a step, adds one from the other branch,
    or an end state that is the wrong one.

  Credit: full when every sentence in the question is judged right; none otherwise. The rubric's
  `answer` is the yes/no list in order. The bank is the three scenarios, nine questions, and across
  it every misreading above appears at least once. Live runs vary the sentences within the same
  planes, keyed from the file at its current commit.
- **worked example:** as `a-read-course-diagram`'s, with the tutor judging two sentences of its
  own aloud on `tour.bpmn`, one right and one a misreading ("the AI agent writes the record": no,
  `Write the record` is in the PROGRAM lane).
- **doesn't show:** each sentence is a yes or a no, so a lucky guess is possible on any one, though
  a question passes only when all its sentences are right. The misreadings are the ones listed, so
  a pass shows the learner can reject those, not every way a diagram can be misread, and it shows
  recognizing a right reading rather than producing one, which `a-read-course-diagram` asks for.
  The rest of `a-read-course-diagram`'s `doesn't show` applies, including that the diagram is a
  familiar one, here met again after that activity if both are done.
- **offer as:** the check against someone else's reading: an AI agent's summary of a plane of the
  setup diagram, judged sentence by sentence. Closest to the course's use, checking what an agent
  says a workflow does. No single plane meets the goal: it takes the top level plus the arrows
  question on `Get Codex running`, at least five questions, about 10 to 20 minutes in all.
- **check note:** Its `trace-run` question is the weakest substitute for the case. Judging
  sentences about a run that is already stated can be done piece by piece without tracing the
  run, so a pass here says less about tracing than a pass on `a-read-course-diagram`'s trace
  question. Where a learner will do only one of the two activities and has shown trouble following
  loops, `a-read-course-diagram` is the better check for that case. The same label caveat applies
  to the file sentence: `Open U-M GPT`'s label names the file.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
