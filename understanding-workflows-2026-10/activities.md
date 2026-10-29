# Activities: understanding workflows

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

2026-10-28: nothing at file level.

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |
| `c-read-diagram` | read a workflow diagram and say what it claims | given a workflow diagram, says what it claims: what each shape marks, who does each step, what each kind of arrow means, and where the flow splits and merges. Cases: `states` (the shape marking the state a run starts or ends in), `step-box` (the shape marking a step), `gateway-shape` (the shape marking a gateway), `subprocess-box` (the shape marking a collapsed subprocess), `lane-owner` (who does a step, from its lane), `spans-lanes` (who does a step drawn across two lanes), `handoff` (where control, or data a later step uses, passes to a step done by a different actor), `control-arrow` (what a solid arrow between two steps says [which step runs next]), `branch-label` (what a label on an arrow leaving a gateway says), `data-line` (what a dotted line between a step and a file says [data written or read, not the run moving to the file]), `splits` (where flow splits [a named gateway]), `merges` (where flow merges [an unnamed gateway]), `trace-steps` (given a trigger and the answer at each named gateway, which steps run, in order), `trace-end` (given the same, which outcome the run reaches). Taught elsewhere: session 18 class. |

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
  a step reads or writes; a handoff is where the next step, or data a later step uses, belongs to a
  different actor, which on a diagram means the arrow or the data's path crosses from one lane into
  another (this departs from the slide on purpose: the slide labels its one arrow symbol "Handoff",
  and the tutor's arrow addition below corrects that, so a line copying the slide gets the
  near-miss "is every arrow a handoff, even one between two steps the same actor does?"); a
  gateway with a question splits the flow by the answer, and one with no label is where
  paths come back together. After the stop, adds what the deck doesn't say, a sentence each.
  **Lane**: each horizontal band in a diagram is a lane, and its name says who does the steps drawn
  in it; a box drawn across two lanes is a step more than one of them takes part in. The deck's
  word **script** is the diagrams' `PROGRAM` lane: steps a program carries out exactly. A box with
  a small **plus** at its bottom edge is a **subprocess**, a step with a diagram of its own
  underneath, which Camunda opens when the plus is clicked. An arrow labeled with an answer (`yes`,
  `no`) leaves a gateway and says which way a run goes on that answer. **Arrows**, correcting the
  slide: the solid arrows are **control flow**, which step runs next; the dotted lines to and from
  a file are **data flow**, data one step writes and another reads, possibly later. A dotted line
  is not the run moving to the file. A **handoff** is either kind of flow where the two steps
  belong to different actors: a solid arrow that crosses into another lane, or a file written by a
  step in one lane and read by a step in another. A solid arrow, or a file written and read,
  inside one lane is not a handoff. So not every arrow is a handoff. Does not set or rehearse any
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
  additions. Slide 7 labels its one arrow symbol a handoff, which invites reading every arrow as one,
  the misreading `c-read-diagram`'s `handoff` case checks for; the correction (control flow, data
  flow, and a handoff only where the actor changes) rests on a few spoken sentences from the
  tutor, so a learner who missed them meets the slide's version first. The deck lists "skill" beside AI agent as another name, while this topic treats the
  two as different things; the tutor does not raise it.
- **offer as:** this topic's orientation: four slides of the session 2 deck, with a one-line
  gloss for each symbol on its glossary slide and a few sentences from the tutor on what the deck
  leaves out or gets loose (lanes, the plus marker, branch labels, control flow and data flow,
  and which of them are handoffs).
  About 10 minutes.

### `a-read-course-diagram`

- **serves:** `c-read-diagram`
- **supports:** attempt
- **checks:** `c-read-diagram`
- **artifact:** one plane of the course's own setup diagram, `workflows/bootstrap/bootstrap.bpmn`
  in the learner's `course-materials` clone, which they opened in Camunda Modeler in Installation
  2 and discussed at their table in session 2. Questions from this activity's bank or set live per
  the generator below. A scenario is one plane: `setup-top` thirteen questions (about 18 minutes),
  `get-codex-running` six (about 10), `set-up-workspace` six (about 8), each one sitting.
- **verified:** 2026-10-28
- **learner does:** opens the diagram in Camunda Modeler, goes to the plane the scenario names, and
  answers the one question served in their own words, pointing at elements by the first line of
  their labels or by the steps or gateways on either side of them.
- **tutor role:** examiner
- **tutor does:** the goal is also taught in the session 18 class (`taught elsewhere`): before
  session 18 the tutor says so and asks whether the learner wants to try now or after, and goes
  ahead if they want. Before serving a scenario, checks that the diagram hasn't changed since the
  key was written: `git -C <course-materials> log -1 --format=%h -- workflows/bootstrap/bootstrap.bpmn`
  must print the commit the scenario's key records (in its rubric file); if it doesn't, the tutor doesn't serve that
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
  case: meeting the goal takes one question per case, fourteen in all over the three scenarios
  (`setup-top` for states, step-box, gateway-shape, subprocess-box, lane-owner, spans-lanes,
  handoff, splits, merges, trace-steps and trace-end; `get-codex-running` for branch-label and
  data-line; `set-up-workspace` for control-arrow), ten of them one-minute multiple choice and
  four free answers, about 15 to 25 minutes, which can be split over sittings.
- **done when:** the criterion met with no help, case by case: a full-credit answer passes the case
  its question carries; half credit or none passes none.
- **generator:** **The material is fixed and real**: the generator picks elements from
  `workflows/bootstrap/bootstrap.bpmn` and writes questions about them; it never draws, edits or
  invents a diagram. Do not use `workflows/learn/learn.bpmn`, which lags the learn workflow it
  depicts. Every answer in a key is read from the `.bpmn` file at the commit the key records,
  checked against the plane in Camunda or a render (`node workflows/diagram/tools/render.mjs`,
  with the subprocess's id for a plane below the top), since a step drawn across two lanes shows
  only in the geometry.

  **A scenario is one plane**, and there are three, each a file
  `tasks/a-read-course-diagram/<scenario-id>.md` with its key in
  `rubrics/a-read-course-diagram/<scenario-id>.md`:
  - `setup-top`: the top level, "opens the Day 1 page in Canvas" to its two end states. Carries
    `states`, `step-box`, `gateway-shape`, `subprocess-box`, `lane-owner`, `spans-lanes`,
    `handoff`, `splits`, `merges`, `trace-steps` and `trace-end`, the only plane that carries
    `subprocess-box`, `lane-owner`, `spans-lanes` or `handoff`. It has two collapsed subprocesses (`Get Codex
    running`, `Set up the workspace`), one step drawn across two lanes (`Get Codex running`, in
    the HUMAN operator lane and reaching into AI AGENT), three named splits (`Codex running?`,
    `Able to complete?`, `install correct?`), two unnamed merges, and a loop (`not yet` at
    `install correct?` leads back to the merge before `Set up the workspace`). It has no solid arrow
    joining two steps directly, so it doesn't carry `control-arrow`, and the bank asks
    `branch-label` elsewhere. It does not carry `data-line`: its one file, `U-M API key`, is drawn
    as read by `Get Codex running`, and a question should not turn on that drawing.
  - `get-codex-running`: the plane under `Get Codex running` (click its plus). Carries `branch-label`,
    `data-line` (the only plane that does), `splits`, `merges`, `trace-steps` and `trace-end`. It has two lanes, a file (`bootstrap-prompt.md`, read by `Open
    U-M GPT; paste the bootstrap prompt`), three named splits (`stuck?`, `worth trying?`,
    `checklist done?`), one unnamed merge with three arrows in (two of them loops), and two end
    states. It has no subprocess and no step across two lanes, so it carries neither `subprocess-box`
    nor `spans-lanes`. Its states, steps and gateways could carry `states`, `step-box` and
    `gateway-shape`; the bank asks those on `setup-top` only, and live or review runs may ask them
    here, in the same form.
  - `set-up-workspace`: the plane under `Set up the workspace`. Carries `control-arrow` (the only
    plane with solid arrows joining two steps directly: `Write the receipt` to `Check the receipt
    landed`, both in PROGRAM; also `Install tools` to `Check the repositories` and the other
    install-then-check pairs, which cross lanes), `splits`, `merges`, `trace-steps` and `trace-end`. It has six named splits, one of them with four answers (`how far did I get
    previously?`), four unnamed merges, one of which gathers every `no` into `stopped at a
    checkpoint`, and two end states. It has no file, so it does not carry `data-line`.

  **The setup** is three sentences: what the workflow is ("the course's setup workflow, as drawn
  for Installations 1 to 3"; never "the setup you went through", and nothing implying it covers
  everything the student did, since later installations, such as Installation 4's Superpowers and
  the optional switch to a personal ChatGPT account, are not drawn), the path of the file and how
  to reach the plane ("Open
  `workflows/bootstrap/bootstrap.bpmn` in your `course-materials` folder. It opens in Camunda
  Modeler. Click the plus at the bottom of `Get Codex running` to open the diagram underneath
  it."), and "Each question below is about this plane of the diagram alone." It names no step, lane, gateway or outcome beyond the one needed to reach the plane.

  **The key**, `rubrics/a-read-course-diagram/<scenario-id>.md`, records in its top part, on a line
  of its own, `diagram commit: <hash>`, the commit of `bootstrap.bpmn` it was written against. The
  line goes in the key, not in the task file the learner sees.

  **Questions ask one thing each.** Multiple choice (`type: mcq`, four numbered choices unless
  said otherwise, shuffled so the right answer's position varies across the bank) wherever
  picking shows the reading; free answer where producing it is the point (finding the splits and
  merges, naming a handoff, listing a run's steps). Each question's rubric tags the one case it
  bears on. Elements are named by the first line of their label; an end state whose label holds a
  long dash is named by its first words (`blocked`, `stuck`). A diamond is pointed at by its
  neighbors, never by its label. Questions come in the order listed (study order: a later question
  may name something an earlier one asked the learner to find, never the reverse). Mcq credit is
  full for the right choice and none otherwise. About 1 minute a multiple-choice question, 2 to 3
  a free one. The examples show the shape, not bank items.

  **`setup-top`: thirteen questions, about 18 minutes if all are answered.**
  1. `start-state` (`states`, Easy, mcq): "Which of these is the state a run of this workflow
     starts in?" Choices: the start event's label, one end state, `Get Codex running`, and the
     split just after it described as "the diamond just after `Get Codex running`".
  2. `end-states` (`states`, Easy, mcq): "Which of these lists every state a run of this workflow
     can end in?" Choices: the two end states; one end state alone; one end state with the start
     state; one end state with `Submit each session's report`.
  3. `plain-step` (`step-box`, Easy, mcq): "What does the rounded box `Report being stuck` mark?"
     Choices, word for word: "a state a run starts or ends in"; "one step, an action someone
     takes"; "a gateway, where the flow splits or comes back together"; "a step with a diagram of
     its own underneath it". Right: the second.
  4. `subprocess` (`subprocess-box`, Easy, mcq): "Which steps have a diagram of their own underneath
     them?" Choices: `Get Codex running` and `Set up the workspace`; `Get Codex running` only;
     `Set up the workspace` and `Check the install`; none of them.
  5. `gateway` (`gateway-shape`, Easy, mcq): "What kind of shape is the diamond just before `Set up the
     workspace`?" Choices: a state; a step; a gateway; a file. Right: a gateway. It asks the kind
     only, never whether this one splits or merges, so it gives nothing away to questions 10 and 11.
  6. `lane-step` (`lane-owner`, Easy, mcq): "Who does `<step A>`?" Step A is a step with no plane below
     it: `Check the install` (PROGRAM), `Report being stuck` or `Submit each session's report`
     (both HUMAN operator), varying between the bank and live runs; never `Set up the workspace`,
     whose own plane has steps in other lanes. Choices: the human; the AI agent; a program; more
     than one of them.
  7. `lane-span` (`spans-lanes`, Medium, mcq): "Who does `Get Codex running`?" Choices: the human only;
     the AI agent only; the human and the AI agent both take part; a program. Right: the third.
  8. `not-handoff` (`handoff`, Easy, mcq, two choices): "Is the solid arrow from `Check the
     install` to the diamond just after it a handoff?" Choices: yes; no. Right: no, both sit in
     the PROGRAM lane, so the same actor carries on. This is where reading every arrow as a
     handoff gets caught. Live runs may use another same-lane arrow (`Submit each session's report`
     to its end state, `Report being stuck` to its end state).
  9. `handoff` (`handoff`, Medium, free): "Name one handoff in this plane: a place where the next
     step, or data a later step uses, belongs to a different actor. Give the two things at its
     ends." Accepted: any one solid arrow whose two ends each sit wholly inside one lane, in
     different lanes (gateways count as ends): `Codex running?` to the merge before `Set up the
     workspace`; `Able to complete?` to `Check the install`, or (on `no`) to the merge before
     `Report being stuck`; `install correct?` to `Submit each session's report`, or (on `not yet`)
     back to the merge before `Set up the workspace`. Not accepted: an arrow into or out of `Get
     Codex running`, which sits in two lanes, and the dotted line from `U-M API key`, since no step
     in this diagram writes that file and the step reading it is `Get Codex running`. Credit: full
     for an accepted one; none otherwise.
  10. `splits` (`splits`, Medium, free): "Where does the flow split? Point to each place by the
     steps or gateways just before and after it." Answer: the three named gateways. Credit: full
     when all three are found and no merge is given as a split; half when one is missed or one
     merge is added; none otherwise.
  11. `merges` (`merges`, Medium, free): "Where do paths come back together? For each place,
      say which paths meet there." Answer: the two unnamed gateways, with the paths meeting at each
      (by the answer they leave a split on, such as `not yet`, or the step they come from). Credit:
      full when both are found with their paths; half when one is missed, or its paths are
      missing; none otherwise.
  12. `trace-steps` (`trace-steps`, Hard, free): "A run starts when `<trigger>`. At `<split 1>` the
      answer is `<x>`; at `<split 2>` it is `<y>`; at `<split 3>` it is `<z>` the first time and
      `<w>` the second. Which steps run, in order?" The answers take the run once around the loop,
      so a step runs twice; a subprocess counts as one step; merges and gateways are not listed.
      Credit: full when every step is there in order; half when one is missing, extra or out of
      order; none otherwise.
  13. `trace-end` (`trace-end`, Medium, mcq, two choices): "In the same run, which end state does
      it reach?" Choices: the two end states. The bank's runs reach each end state at least once
      across its trace questions.

  **`get-codex-running`: six questions, about 10 minutes.**
  1. `branch-label` (`branch-label`, Medium, mcq): "What does the label `<answer>` on the arrow leaving
     `<named split>` tell you?" Choices: "a run goes this way when the answer to that gateway's
     question is `<answer>`" (right); "a step called `<answer>` runs next"; "the run ends with the
     outcome `<answer>`"; "the work passes to another lane". The split and answer vary across the
     bank and live runs.
  2. `file-line` (`data-line`, Medium, mcq): "What does the dotted line between `bootstrap-prompt.md`
     and `Open U-M GPT` tell you?" Choices: "that step reads, or uses, that file" (right); "after
     that step, the run moves on to the file"; "the file is the next step"; "the run ends at the
     file". No choice turns on whether the line is a handoff: no step in this diagram writes the
     file, so the diagram doesn't show whether another actor's step supplies it.
  3. `splits` (`splits`) and 4. `merges` (`merges`): as on `setup-top`, for this plane's three named
     splits and its one merge with three arrows in.
  5. `trace-steps` (`trace-steps`) and 6. `trace-end` (`trace-end`): as on `setup-top`, with a run that goes once
     around a loop; `trace-end` has the plane's two end states as its choices.

  **`set-up-workspace`: six questions, about 8 minutes.** The plane is long, so its gateway
  questions take one diamond at a time.
  1. `next-arrow` (`control-arrow`, Easy, mcq): "What does the solid arrow from `Write the receipt`
     to `Check the receipt landed` tell you?" Choices: "`Check the receipt landed` runs next"
     (right); "`Write the receipt` reads a file"; "both steps run at the same time"; "the run ends
     here". No choice mentions a handoff; that lives under `handoff`. Live runs may use another
     step-to-step pair on this plane (`Install tools` to `Check the repositories`).
  2. to 4. `split-or-merge` (`splits` or `merges`, whichever the diamond is; Easy, mcq, two choices): "At the diamond just after
     `<step or gateway>`, does the flow split, or do paths come back together?" Choices: "it
     splits"; "paths come back together". Three questions, at least one about a split and one
     about a merge, each pointing at a different diamond and tagged with the case its right answer
     names.
  5. `trace-steps` (`trace-steps`) and 6. `trace-end` (`trace-end`): as on `setup-top`; the answer at `how far
     did I get previously?` is not `first time`, so some steps are skipped.

  **The bank** is the three scenarios, 25 questions. Study skips a question whose case is already
  met, so a learner rarely answers them all. Live runs, and later review, vary the pointed-at
  elements and the traced answers within the same planes (a different split and answer for
  `branch-label`, a different step A, a different diamond, a different run), keyed by reading the
  file at its current commit.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works the same kind of question aloud on a different diagram, saying what it looks at:
  `workflows/tour/tour.bpmn` (the tour at the end of setup, a single plane with no gateways) for
  start and end states, steps, lanes, handoffs, an arrow inside one lane (`tour skill invoked` to
  `Ask what they want`, control flow with no handoff) and data flow (`Explain the four parts of
  the tour` reads the guide; `Write the record`, in PROGRAM, writes `tour.md`, which `Open the file
  in the editor`, in the human's lane, reads later: a data handoff); the box `Brainstorm the design` at the top level of
  `workflows/develop/superpowers.bpmn`, which has a plus and is drawn across the HUMAN operator and
  AI AGENT lanes, for a subprocess and a step across two lanes (pointing at the drawing only, with
  no claim about how Superpowers runs today); and, for splits, merges, branch
  labels and traces, whichever of the three bootstrap planes the question is not on, working only
  the one element or one short run needed.
- **doesn't show:** every question is on one diagram the learner has seen before, so a pass doesn't
  show they could read a brand-new diagram, drawn by someone else or in another style, and later
  attempts may draw on memory of this one rather than reading. `subprocess-box`, `lane-owner`, `spans-lanes`, `handoff`,
  `control-arrow`, `branch-label` and `data-line` are each asked on only one plane (`data-line` about one file),
  so they have little room to vary. The `not-handoff` ruling departs from the session 2 deck,
  whose glossary labels its one arrow symbol a handoff; a learner who learned the slide well can
  fail it for that. The plane has no file that
  one actor's step writes and another's reads, so no question checks a data handoff. The diagram uses exclusive gateways only, so a
  pass says nothing about parallel paths or typed events. Questions point at the elements to read,
  so a pass doesn't show the learner would notice, unasked, what a diagram leaves out, or could say
  whether a step is in the right lane, which this topic leaves to sessions 18 to 21. Each case is
  now spread over several one-thing questions, but a pass on any one question tagged with a case
  records that case, so where a case has more than one question on a plane (`states`, start and
  end; `handoff`, the same-lane arrow and the named handoff), one can stand for both, and a guess
  on a two-choice question (`not-handoff`, `trace-end`, `split-or-merge`) can stand for a case.
- **offer as:** the fuller check: planes of the setup diagram, one thing asked per question,
  mostly multiple choice, with free answers for finding splits and merges, naming a handoff and
  listing a run's steps. No single plane meets the goal: it takes one question per case,
  fourteen in all across the three planes, about 15 to 25 minutes.
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
  below. About 2 to 3 minutes a question, 5 to 10 a scenario.
- **verified:** 2026-10-28
- **learner does:** opens the plane the scenario names in Camunda Modeler and, for each sentence in
  the question served, says whether the diagram says that: yes or no.
- **tutor role:** examiner
- **tutor does:** as `a-read-course-diagram`'s (the session 18 offer, the commit check, opening the
  diagram, never describing it, help recorded as helped), and also: never says which sentences are
  wrong or how many, and doesn't ask the learner to explain a no. A learner who adds what the
  diagram does say is welcome to and gains nothing for it. Labels a live run
  `a-judge-diagram-summary/<case>`. Says when offering it, as for `a-read-course-diagram`, that
  meeting the goal takes one question per case, fourteen over the three scenarios, about 20
  minutes, splittable over sittings.
- **done when:** as `a-read-course-diagram`'s: the criterion met with no help, case by case.
- **generator:** **The material** is as `a-read-course-diagram`'s: the same three planes, the
  same cases per plane, the same `diagram commit:` line in each key (never in the task file),
  and nothing drawn or invented. Its
  scenario files are its own, `tasks/a-judge-diagram-summary/<scenario-id>.md` and its key under
  `rubrics/`, named `setup-top`, `get-codex-running` and `set-up-workspace`. The setup is as
  there, then: "An AI agent was asked to say in plain words what this plane of the diagram claims.
  Each question below gives sentences from its summary. For each sentence, say whether the diagram
  says that: yes or no."

  **A question** asks about one case: a stated element, or for the trace cases a stated run, then
  two numbered sentences (one for `trace-end`), and "Does the diagram say this? Answer yes or no
  for each." Each sentence is plainly what the diagram says or one of the misreadings below,
  stated as plainly; none is half right or turns on a word. Across a scenario, yeses and noes
  each make up between a third and two thirds of the sentences, and no position in a question is
  always the yes. Where a sentence restates something `a-read-course-diagram`'s key for the same
  plane gives, it is allowed: the planes are few. Elements are named and pointed at as there; a
  diamond is pointed at by its neighbors, and a `gateway-shape` sentence never says whether it
  splits or merges.

  The misreadings, by case, with where each case is asked:
  - `states` (`setup-top`, Easy): calls the start state the first step, or an end state a step.
  - `step-box` (`setup-top`, Easy): calls a plain step a state, or a step with a diagram
    underneath it.
  - `gateway-shape` (`setup-top`, Easy): calls a gateway a step someone does, or a state.
  - `subprocess-box` (`setup-top`, Easy): calls a collapsed subprocess a single action with
    nothing more to it.
  - `lane-owner` (`setup-top`, Easy): gives a step with no plane below it to the actor its label
    suggests rather than the one its lane names ("the human checks the install").
  - `spans-lanes` (`setup-top`, Easy): gives `Get Codex running` to one actor alone.
  - `handoff` (`setup-top`, Medium): calls a solid arrow between two elements in the same lane a
    handoff, which is where reading every arrow as a handoff gets caught, whatever the slide says;
    or says an arrow crossing lanes is not one.
  - `control-arrow` (`set-up-workspace`, Easy): reads a solid arrow between two steps as a step
    reading a file, or as both steps running at once.
  - `branch-label` (`get-codex-running`, Medium): reads a branch label as a step that runs, or as
    an end state.
  - `data-line` (`get-codex-running`, Medium): reads the dotted line between
    `bootstrap-prompt.md` and its step as the run moving to the file, or as the next step. No
    sentence turns on whether the line is a handoff: no step in the diagram writes
    `bootstrap-prompt.md`, so the diagram doesn't show whether another actor's step supplies it. A
    learner who adds "and it's a data handoff" to a right yes or no is not marked down for it.
  - `splits` (every plane, Medium): says the flow splits at an unnamed gateway, or misses that it
    splits at a named one.
  - `merges` (every plane, Medium): calls an unnamed merge a decision, or says two paths never
    come back together when they do.
  - `trace-steps` (every plane, Hard): for a stated run, a step list that skips a step or adds one
    from the other branch.
  - `trace-end` (every plane, Medium): for a stated run, the wrong end state.

  Credit: full when every sentence in the question is judged right; none otherwise. The rubric's
  `answer` is the yes/no list in order. A scenario carries one question per case its plane
  carries, in the order of the list above: `setup-top` eleven questions (`states` to `handoff`,
  then `splits`, `merges`, `trace-steps`, `trace-end`; about 15 minutes), `get-codex-running` six
  (`branch-label`, `data-line`, `splits`, `merges`, `trace-steps`, `trace-end`; about 9),
  `set-up-workspace` five (`control-arrow`, `splits`, `merges`, `trace-steps`, `trace-end`; about
  8). The bank is the three scenarios, 22 questions, and across it every misreading above appears
  at least once. Live runs vary the sentences within the same
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
  says a workflow does. No single plane meets the goal: it takes one question per case,
  fourteen in all across the three planes, about 20 minutes.
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
