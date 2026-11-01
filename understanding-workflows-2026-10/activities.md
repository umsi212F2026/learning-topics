# Activities: understanding workflows

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

2026-11-01: The one capability, `c-read-diagram`, has one live check, `a-read-course-diagram`;
`a-judge-diagram-summary` is on hold for a rewrite. Both use the same three planes of
`bootstrap.bpmn`. Every key in `a-read-course-diagram`'s bank records `eb7b655`, the revised drawing
on the unmerged `deck-workflow-fixes` branch. Until that branch is merged, no banked scenario passes
the commit check on a learner's clone, and the capability can only be served live, keyed from the
file at the learner's current commit.

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |
| `c-read-diagram` | read a workflow diagram and say what it claims | given a workflow diagram, says what it claims: what each shape marks, who does each step, what each kind of arrow means, and where the flow splits and merges. Cases: `states` (the shape marking where a run starts or ends [not a step]), `step-box` (the shape marking a step), `gateway-shape` (the shape marking a gateway), `subprocess-box` (the shape marking a collapsed subprocess), `lane-owner` (who does a step, from its lane), `spans-lanes` (who does a step drawn across two lanes), `handoff` (where control, or data a later step uses, passes to a step done by a different actor), `not-handoff` (that a step followed by another step of the same actor is not a handoff), `control-arrow` (what a solid arrow between two steps says [which step runs next]), `branch-label` (what a label on an arrow leaving a gateway says), `data-line` (what a dotted line between a step and a file says [data written or read, not the run moving to the file]), `splits` (where flow splits [a named gateway]), `merges` (where flow merges [an unnamed gateway]), `trace-steps` (what happens after a given step, including when the flow loops back), `trace-end` (which end state follows a given last step). Taught elsewhere: session 18 class. |

## Coverage

| goal | checks | notes |
| ---- | ------ | ----- |
| `o-orientation` | `a-read-workflow-deck` | |
| `c-read-diagram` | `a-read-course-diagram`, `a-judge-diagram-summary` | Every check uses one diagram the learner has already met in Installation 2 and in session 2. It has exclusive gateways only, and the question points at each element. Meeting the goal therefore shows the learner can read this diagram when asked about specific parts. It does not show they can read an unfamiliar one, notice what a diagram leaves out, or handle parallel paths, and the sessions 18 to 21 use is on other diagrams. No check carries a data handoff, because no step in `bootstrap.bpmn` writes a file that another actor's step reads. `a-judge-diagram-summary` has no `not-handoff` question, so on its own it cannot finish the goal. |

---

## Activities

### `a-read-workflow-deck`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** the session 2 lecture deck, "What is a workflow?", as revised for this topic. It is
  `docs/lecture-slides/l-what-is-a-workflow.html` in the learner's `course-materials` clone, a
  self-contained HTML file that opens in any browser with no server (arrow keys move, `Esc` shows
  every slide). The revised deck reaches learners in the same pull that brings this topic.
  Only slides 4 to 7 are read: 4, the definition of a workflow and a two-row table of what
  dropping a part leaves (repeatable, or you have a project; a settled order, or you have a
  checklist); 5, the vocabulary list (run, step, trigger (start event), outcome, AI agent (bot),
  skill, script, handoff, with synonyms); 6, an xkcd flowchart; 7, the symbol glossary: start and
  end ("where a run starts (its trigger) or ends (its outcome)"), step, file ("data a step reads or writes, joined to it by a dotted
  line"), control flow ("which step runs next; when the next step belongs to another actor, it is
  a handoff"), and gateway, split or merge. Slides 1 to 3 and 8 to 10 are class logistics,
  discussion norms, table questions about `bootstrap.bpmn` and lab instructions, and are skipped.
  Public copy:
  https://github.com/umsi212F2026/course-materials/blob/main/docs/lecture-slides/l-what-is-a-workflow.html
  (the repository is public and the page answers, but GitHub shows the file's source rather than
  the slides, and the repository has no GitHub Pages site, so the local copy is the one to open).
  About 4 minutes for the four slides, about 10 with the stop, the tutor's additions and the close.
- **verified:** 2026-11-01
- **learner does:** reads slides 4 to 7 once, then stops at slide 7 and answers before going on;
  "I'm not sure" is an honest answer. At the stop, writes one line in their own words for each of
  the glossary's five symbols, saying what it marks in a diagram: a start or end circle, a step, a
  file, a control-flow arrow (including when it is a handoff), and a gateway (both what a split is and
  what a merge is). Then hears the tutor's additions (below), and answers the close: with this
  deck beside you, could you now open one of the course's workflow diagrams in Camunda Modeler
  and say where a run starts and ends, who does each step, what each kind of arrow means, where
  the flow splits and merges, and what happens after a given step?
- **tutor role:** explainer
- **tutor does:** gives the learner the full path of the deck in their own `course-materials`
  clone and has them open it in a browser (double-click, or the tutor runs `open "<path>"` on
  macOS or `Start-Process "<path>"` on Windows). If the deck is not in the clone, the clone is out
  of date: bring it up to date first. Does not paste slides into the chat, and does not open
  any `.bpmn` file: the course's diagrams are this topic's check material. Stays quiet through the
  reading except at the stop and when asked. At the stop, takes the learner's lines first and
  replies to a wrong or vague one with one near-miss question rather than a verdict ("you said a
  gateway is where a decision is made; what about a diamond with two arrows in and one out?").
  Intended lines: a start circle marks what starts a run, its trigger (which may be a person's
  action, a time arriving or a message), and an end circle marks an outcome a run ends in; neither
  is a step the workflow does; a step is one action someone or something takes; a file is data a step reads or writes, joined by a dotted
  line; a control-flow arrow says which step runs next, and it is a handoff only when that next
  step belongs to another actor (a line saying every arrow is a handoff gets the near-miss "even
  one between two steps the same actor does?"); a gateway with a question splits the flow by the
  answer, and one with no label is where paths come back together. After the stop, adds what the
  deck doesn't say, a sentence each. **Lane**: each horizontal band in a diagram is a lane, and its
  name says who does the steps drawn in it, so "another actor" on the slide means another lane; a
  box drawn across two or more lanes is a step more than one of them takes part in. The deck's word
  **script** is the diagrams' `PROGRAM` lane: steps a program carries out exactly. A box with a
  small **plus** at its bottom edge is a **subprocess**, a step with a diagram of its own
  underneath; the plus only marks it, and Camunda opens that diagram from the small arrow button
  at the box's bottom-right corner. An arrow labeled with an answer (`yes`, `no`) leaves a gateway
  and says which way a run goes on that answer. **Data flow**: the dotted lines are data flow,
  data one step writes and another reads, possibly later; a dotted line is not the run moving to
  the file, and a file written by one actor's step and read by another actor's step is a handoff
  too, while one written and read inside one lane is not. Does not set or rehearse any word
  question from `a-words` (no asking for a definition, no word against its confusable, no misused
  sentence to correct), and does not set a question from this topic's capability activities. Says
  that reading the course's diagrams is practiced in this topic's other activities and in the
  session 18 class, and that drawing one is not part of this topic. At the close, puts the
  readiness question as written above and rules on the answer.
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
  nothing about `c-read-diagram`. It shows nothing about the fifteen live words (a sixteenth,
  workflow state, is retired), which have their own supply in `a-words`; slides 4 to 7 name only
  some of them (they never say lane, subprocess, executor or data flow), and lane, subprocess and data flow reach the learner
  only through the tutor's spoken additions. The revised slide 7 states the handoff rule for
  control flow only; that a file passed between actors is also a handoff rests on the tutor's
  sentence.
- **offer as:** this topic's orientation: four slides of the session 2 deck, with a one-line
  gloss for each symbol on its glossary slide and a few sentences from the tutor on what the deck
  leaves out (lanes, the plus marker, branch labels, data flow and data handoffs). About 10
  minutes.

### `a-read-course-diagram`

- **serves:** `c-read-diagram`
- **supports:** attempt
- **checks:** `c-read-diagram`
- **artifact:** one plane of the course's own setup diagram, `workflows/bootstrap/bootstrap.bpmn`
  in the learner's `course-materials` clone, which they opened in Camunda Modeler in Installation
  2 and discussed at their table in session 2. Questions from this activity's bank or set live per
  the generator below. A scenario is one plane: `setup-top` eleven questions (about 15 minutes),
  `get-codex-running` six (about 9), `set-up-workspace` nine (about 11), each one sitting.
- **verified:** 2026-11-01
- **learner does:** opens the diagram in Camunda Modeler, goes to the plane the scenario names, and
  answers the one question served in their own words, pointing at elements by the first words of
  their labels or by the steps or gateways on either side of them.
- **tutor role:** examiner
- **tutor does:** the goal is also taught in the session 18 class (`taught elsewhere`): before
  session 18 the tutor says so and asks whether the learner wants to try now or after, and goes
  ahead if they want. Before serving a scenario, checks that the diagram hasn't changed since the
  key was written: `git -C <course-materials> log -1 --format=%h -- workflows/bootstrap/bootstrap.bpmn`
  must print the commit the scenario's key records (in its rubric file); if it doesn't, the tutor doesn't serve that
  scenario and records it as a bank defect for the instructor. The keys must record the diagram's
  commit on `main`: they now record `eb7b655`, the revised layout's commit on its branch, and are
  updated to the commit on `main` when this topic's release package lands. Gives the full path of the file and
  has the learner double-click it (it opens in Camunda Modeler on a machine that finished
  Installation 2); if it doesn't open, opens it by path, as `setup-editors` does (`open -a "Camunda
  Modeler" "<path>"` on macOS, `Start-Process "C:\Program Files\Camunda Modeler\Camunda
  Modeler.exe" -ArgumentList "<path>"` on Windows). Never describes the diagram in words, pastes
  its XML, or names an element the question doesn't already name. Reads the diagram itself from
  the `.bpmn` and rules from the rubric. Sets the question as served, without rewording it or
  hinting; never names the cases. Gives help whenever it is asked for, and records the attempt as
  helped. Labels the attempt with the question's path, or `a-read-course-diagram/<case>` when run
  live, and records the cases with `--cases`. Says when offering it that no one plane carries every
  case: meeting the goal takes one question per case, fifteen in all over the three scenarios
  (`setup-top` for states, step-box, gateway-shape, subprocess-box, spans-lanes, handoff,
  splits, merges, trace-steps and trace-end; `get-codex-running` for branch-label and data-line;
  `set-up-workspace` for control-arrow, not-handoff and lane-owner), eleven of them one-minute
  multiple choice and four free answers, about 20 minutes, which can be split over sittings.
- **done when:** the criterion met with no help, case by case: a full-credit answer passes the case
  its question carries; half credit or none passes none.
- **generator:** **The material is fixed and real**: the generator picks elements from
  `workflows/bootstrap/bootstrap.bpmn` and writes questions about them; it never draws, edits or
  invents a diagram. Do not use `workflows/learn/learn.bpmn`, which lags the learn workflow it
  depicts. Every answer in a key is read from the `.bpmn` file at the commit the key records,
  checked against the plane in Camunda or a render (`node workflows/diagram/tools/render.mjs`,
  with the subprocess's id for a plane below the top), since a step drawn across lanes shows
  only in the geometry. Keys are written against the diagram as learners have it, in which `Set up
  the workspace` is drawn across all three lanes; each key's `diagram commit:` line is the
  diagram's commit on `main` (now `eb7b655` on its branch, updated when the package lands).

  **A scenario is one plane**, and there are three, each a file
  `tasks/a-read-course-diagram/<scenario-id>.md` with its key in
  `rubrics/a-read-course-diagram/<scenario-id>.md`:
  - `setup-top`: the top level, "opens the Day 1 page in Canvas" to its two end states. Carries
    `states`, `step-box`, `gateway-shape`, `subprocess-box`, `spans-lanes`,
    `handoff`, `splits`, `merges`, `trace-steps` and `trace-end`, the only plane that carries
    `subprocess-box` or `spans-lanes`. It does not carry `lane-owner`: its step labels give each
    step's actor away (`check-setup.mjs`, "on Canvas"). Its only handoff pair (step to step,
    gateways between ignored, steps drawn across lanes left out) is `Check the install` to
    `Submit each session's report`. It has no same-actor pair, so it carries no `not-handoff`
    question. It has two collapsed subprocesses (`Get Codex running`, `Set up the workspace`), both
    drawn across lanes: `Get Codex running` across HUMAN operator and AI AGENT, `Set up the
    workspace` across all three (its own plane has steps in all three), three named splits (`Codex running?`,
    `Able to complete?`, `install correct?`), two unnamed merges, and a loop (`not yet` at
    `install correct?` leads back to the merge before `Set up the workspace`). It has no solid arrow
    joining two steps directly, so it doesn't carry `control-arrow`, and the bank asks
    `branch-label` elsewhere. It does not carry `data-line`: its one file, `U-M API key`, is drawn
    as read by `Get Codex running`, and a question should not turn on that drawing.
  - `get-codex-running`: the plane under `Get Codex running` (opened from the small arrow button at the bottom-right corner of its box). Carries `branch-label`,
    `data-line` (the only plane that does), `splits`, `merges`, `trace-steps` and `trace-end`. It has two lanes, a file (`bootstrap-prompt.md`, read by `Open
    U-M GPT; paste the bootstrap prompt`), three named splits (`stuck?`, `worth trying?`,
    `checklist done?`), one unnamed merge with three arrows in (two of them loops), and two end
    states. Its step pairs (for live and review runs of `handoff` and `not-handoff`; the bank asks them elsewhere): same-actor
    `Open U-M GPT` to `Do the next step on the checklist` (HUMAN) and `Provide explanations and
    suggestions` to `Write a status report` (AI AGENT); handoffs `Do the next step on the
    checklist` to `Provide explanations and suggestions` and back. It has no subprocess and no step
    across two lanes, so it carries neither `subprocess-box`
    nor `spans-lanes`. Its start and end circles, steps and gateways could carry `states`, `step-box` and
    `gateway-shape`; the bank asks those on `setup-top` only, and live or review runs may ask them
    here, in the same form.
  - `set-up-workspace`: the plane under `Set up the workspace`. Carries `control-arrow` (the only
    plane with solid arrows joining two steps directly: `Write the receipt` to `Check the receipt
    landed`, both in PROGRAM; also `Install tools` to `Check the repositories` and the other
    install-then-check pairs, which cross lanes), `lane-owner` (the only plane that does: see question
    4 below), `not-handoff` and `handoff` (same-actor pairs for `not-handoff`:
    `Write the receipt` to `Check the receipt landed`, `Check the repositories` to `Write the
    receipt` and `Check the addressing` to `Write the receipt`, all PROGRAM; handoff pairs for `handoff`: `Install
    tools` to `Check the repositories`, `Check the repositories` to `Record where things live`,
    `Record where things live` to `Check the addressing`, `Check the receipt landed` to `Submit
    Installation 1`, `Submit Installation 1` to `Install the editors`, `Install the editors` to
    `Check the editors`, `Check the editors` to `Submit Installation 2`, `Submit Installation 2`
    to `Publish the repositories`, `Publish the repositories` to `Check the remote`, `Check the
    remote` to `Submit Installation 3`, and `Check the repositories` to `Install the editors` or
    to `Publish the repositories`), `splits`,
    `merges`, `trace-steps` and `trace-end`. It has six named splits, one of them with four answers (`how far did I get
    previously?`), four unnamed merges, one of which gathers every `no` into `stopped at a
    checkpoint`, and two end states. It has no file, so it does not carry `data-line`.

  **The setup** is three sentences: what the workflow is ("the course's setup workflow, as drawn
  for Installations 1 to 3"; never "the setup you went through", and nothing implying it covers
  everything the student did, since later installations, such as Installation 4's Superpowers and
  the optional switch to a personal ChatGPT account, are not drawn), the path of the file and how
  to reach the plane ("Open
  `workflows/bootstrap/bootstrap.bpmn` in your `course-materials` folder. It opens in Camunda
  Modeler. Click the small arrow button at the bottom-right corner of the `Get Codex running`
  box to open the diagram underneath it, and read that diagram only."; on the top level, "Read
  this top level only, without opening the diagrams underneath its boxes."). It names no step,
  lane, gateway or outcome beyond the one needed to reach the plane, and says nothing about the
  questions as a set.

  **The key**, `rubrics/a-read-course-diagram/<scenario-id>.md`, records in its top part, on a line
  of its own, `diagram commit: <hash>`, the commit of `bootstrap.bpmn` it was written against. The
  line goes in the key, not in the task file the learner sees.

  **Questions ask one thing each, with one answer.** No question asks for several answers ("where
  does the flow split?", "name every end state", "which steps run, in order?"). Each either asks
  for exactly one instance ("name one place where...") or identifies one element and asks one
  thing about it. Multiple choice (`type: mcq`, four numbered choices unless said otherwise,
  shuffled so the right answer's position varies across the bank) wherever picking shows the
  reading; free answer where producing it is the point. Each question's rubric tags the one case
  it bears on. Elements are named by the first words of their label, enough to pick the element
  out (`Open U-M GPT`, `Install tools`; an end state by its first words, `blocked`, `stuck`), not
  necessarily the whole first line. A diamond is pointed at by its neighbors, never by its label.
  **Order:** questions come in the order listed, and no question's text or choices may reveal the
  answer to a later one (a later one may reveal an earlier one's, which study has already
  ruled on). On `setup-top` the shape questions come first and point at the merge before `Set up
  the workspace` only as "a gateway", the lane question comes before the handoff question, and the
  split, merge and "what happens after" questions come last. On `get-codex-running` the split
  question comes before `branch-label`, since a diamond with labeled arrows shows it is a split,
  and the bank's `branch-label` avoids `worth trying?`, whose labels the later `after-loop`
  answer needs. On `set-up-workspace` `not-handoff` and `handoff` come before `lane-owner`, which
  would reveal a step's actor. Mcq credit is
  full for the right choice and none otherwise. **In every free answer** (`handoff`,
  `one-merge`, `one-split`, `after-loop`, `after-step` and any other), credit a
  paraphrased step or gateway name when it is clear which element the learner means; ask which
  they mean only when it is not. About 1 minute a multiple-choice question, 2 a
  free one. The examples show the shape, not bank items; a case may carry several such questions
  across the bank and live runs.

  **"What happens after `<step>`?"** is the preferred free shape. Its answer is one thing: the
  next step (or end state), passing through any merge; or, when a named split comes next, a
  conditional built from the branch labels ("if `success`, `Submit each session's report`; if
  `not yet`, back to `Set up the workspace`"). Pick only steps whose split, if any, leads on every
  branch (through merges only) straight to a step or an end state, never to a second split, and
  never a step drawn across lanes. **Which case it carries:** the one the answer most depends
  on. When a single step comes next, `trace-steps`. When an end state comes next, `trace-end`
  (the step is a last step). When a named split comes next and one of its branches loops back to
  an earlier step, `trace-steps`, since following the loop back is what that case now asks.
  When a named split comes next and no branch loops back, `splits`, since the answer's shape
  rests on seeing that the flow divides there. No question states a whole run ("a run starts
  when...", "in this run..."). bootstrap.bpmn has no step whose single next step loops back:
  every loop leaves from a split, so the loop-back `trace-steps` questions are conditionals. `branch-label`
  keeps its own multiple-choice question and is not tagged on this shape. **Credit for a
  conditional:** full when every branch is there with its label and the right step or end state;
  half when one branch is missing, or one label or one destination is wrong; none when only one
  next step is given with no condition, or more than one part is wrong. For a single next step:
  full for the right step or end state, none otherwise.

  **`setup-top`: eleven questions, about 15 minutes if all are answered.**
  1. `start-circle` (`states`, Easy, mcq): "Which of these marks what starts a run of this
     workflow?" Choices: the start event's label, one end state, `Get Codex running`, and "the
     diamond just after `Get Codex running`".
  2. `end-circle` (`states`, Easy, mcq): "What does the circle `<end circle>` mark?" (`workspace
     ready` or `blocked`.) Choices, word for word: "what starts a run, its trigger"; "an outcome a
     run ends in"; "one step, work the workflow does"; "a gateway". Right: the second. A circle is
     never called a state, and the start circle's being a person's action is never treated as a
     misreading: the misreadings are calling a circle a step, or the start an end and the reverse.
  3. `plain-step` (`step-box`, Easy, mcq): "What does the rounded box `Report being stuck` mark?"
     Choices, word for word: "where a run starts or ends"; "one step, work the workflow does"; "a
     gateway, where the flow splits or comes back together"; "a step with a diagram of its own
     underneath it". Right: the second.
  4. `subprocess` (`subprocess-box`, Easy, mcq): "Which of these steps has a diagram of its own
     underneath it?" Choices: `Set up the workspace`; `Check the install`; `Report being stuck`;
     `Submit each session's report`. Live runs may ask it with `Get Codex running` as the right
     choice and three other plain steps.
  5. `gateway` (`gateway-shape`, Easy, mcq): "What kind of shape is the diamond just before `Set
     up the workspace`?" Choices: a start or end circle; a step; a gateway; a file. Right: a gateway. It asks
     the kind only, never whether this one splits or merges, so it gives nothing away to
     questions 8 and 9.
  6. `lane-span` (`spans-lanes`, Medium, mcq): "Who does `Get Codex running`?" Choices: the human
     only; the AI agent only; the human and the AI agent both take part; the human, the AI agent
     and a program all take part. Right: the third. Live runs may ask the same about `Set up the
     workspace`, where the fourth is right.
  7. `handoff` (`handoff`, Medium, free): "Name one handoff in this plane: a place where the run
     goes from a step done by one actor to the next step, done by a different actor (gateways
     between them don't matter). Leave out `Get Codex running` and `Set up the workspace`, which
     are drawn across more than one lane. Name the two steps." Accepted: the plane's one handoff
     pair, `Check the install` to `Submit each session's report`. A pair with either excluded step
     in it is not accepted; the tutor points back to the question's exclusion and asks for
     another. **On any plane**, a `handoff` or `not-handoff` question whose plane has a step drawn
     across lanes names those steps as excluded in the question's own text, in the same words.
     **Pairs, not arrows.** A handoff question names two steps, A and B, such that the run can go
     from A to B with no other step between them (only gateways, or nothing). The pair is a
     handoff exactly when A and B are done by different actors, a not-handoff when the same actor
     does both. A question never points at an arrow that ends at a gateway and never asks who a
     gateway belongs to, and a step drawn across lanes (`Get Codex running`, `Set up the
     workspace`) is never in a pair. No diagram question mentions data: bootstrap.bpmn has no data handoff (no step writes
     a file another actor's step reads), so the questions narrow handoff to control passing from
     one actor's step to the next step, done by a different actor; the words bank keeps the broad
     control-or-data definition. In a free answer, a learner who names an arrow ending at a
     gateway is not marked wrong: credit it when the steps on either side of that gateway make a
     qualifying pair, and otherwise ask which steps they mean.
  8. `one-split` (`splits`, Medium, free): "Name one place where the flow splits. Point to it by
     the steps or gateways just before and after it." Answer: any of the three named gateways.
     Credit: full for one; none for an unnamed merge or a step. (The "what happens after" form is
     not used for `splits` here: the only steps on this plane followed by a split without a
     loop-back are drawn across lanes.)
  9. `one-merge` (`merges`, Medium, free): "Name one place where paths come back together. Point
      to it by the steps or gateways just before and after it." Answer: either unnamed gateway
      (the one before `Set up the workspace`, or the one before `Report being stuck`). Credit:
      full for either; none for a named gateway or a step.
  10. `after-loop` (`trace-steps`, Medium, free): "What happens after `Check the install`?"
      Answer: if `success`, `Submit each session's report`; if `not yet`, back to `Set up the
      workspace`. The `not yet` branch loops back, so it is tagged `trace-steps`. Credit as for a
      conditional above.
  11. `after-last` (`trace-end`, Easy, mcq): "What happens after `<last step>`?" Bank: `Submit
      each session's report` (right: `workspace ready`); live: `Report being stuck` (right: the end
      state `blocked`). Choices: both end states and two steps from this plane.

  **`get-codex-running`: six questions, about 9 minutes.**
  1. `one-split` (`splits`, Medium, free): "Name one place where the flow splits. Point to it by
     the steps or gateways just before and after it." Answer: any of the three named gateways.
     Credit: full for one; none for the unnamed merge or a step.
  2. `branch-label` (`branch-label`, Medium, mcq): "What does the label `<answer>` on the arrow
     leaving the diamond just after `<step or gateway>` tell you?" Choices: "a run goes this way
     when the answer to that gateway's question is `<answer>`" (right); "a step called `<answer>`
     runs next"; "the run ends with the outcome `<answer>`"; "the work passes to another lane".
     Only arrows that stay in one lane: `no` at `stuck?` (the diamond just after `Do the next step
     on the checklist`) in the bank, either answer at `checklist done?` or `try suggestion` at
     `worth trying?` in live runs (`try suggestion` only when `after-loop` isn't still to come).
     Never `yes` at `stuck?` or `give up` at `worth trying?`, which cross into AI AGENT and make
     "the work passes to another lane" defensible.
  3. `file-line` (`data-line`, Medium, mcq): "What does the dotted line between
     `bootstrap-prompt.md` and `Open U-M GPT` tell you?" Choices: "that step reads, or uses, that
     file" (right); "after that step, the run moves on to the file"; "the file is the next step";
     "the run ends at the file". No choice turns on whether the line is a handoff.
  4. `one-merge` (`merges`, Medium, free): "Name one place where paths come back together. Point
     to it by the steps or gateways just before and after it." Answer: the one unnamed gateway,
     between `Open U-M GPT` and `Do the next step on the checklist`.
  5. `after-loop` (`trace-steps`, Medium, free): "What happens after `Provide explanations and
     suggestions`?" Answer: if `try suggestion`, back to `Do the next step on the checklist`; if
     `give up`, `Write a status report on where it stalled`. The `try suggestion` branch loops
     back, so it is tagged `trace-steps`. Live runs may ask "What happens after `Open U-M GPT`?"
     (answer: `Do the next step on the checklist`, through the merge), also `trace-steps`. Not `Do
     the next step on the checklist`, whose split leads to a second split.
  6. `after-last` (`trace-end`, Easy, mcq): "What happens after `Write a status report on where
     it stalled`?" Choices: the end state `stuck` (right); the end state `Codex answers with the
     U-M key`; `Do the next step on the checklist`; `Provide explanations and suggestions`.

  **`set-up-workspace`: nine questions, about 11 minutes.** The plane is long, so its gateway
  questions take one diamond at a time.
  1. `next-arrow` (`control-arrow`, Easy, mcq): "What does the solid arrow from `Write the receipt`
     to `Check the receipt landed` tell you?" Choices: "`Check the receipt landed` runs next"
     (right); "`Write the receipt` reads a file"; "both steps run at the same time"; "the run ends
     here". No choice mentions a handoff; that lives under `handoff`. Live runs may use another
     step-to-step pair on this plane (`Install tools` to `Check the repositories`).
  2. `not-handoff` (`not-handoff`, Easy, mcq, two choices): "When a run goes from `<step A>` to
     `<step B>`, is that a handoff?" A and B are one of this plane's same-actor pairs listed above
     (`Write the receipt` to `Check the receipt landed` in the bank; the two pairs ending at `Write
     the receipt`, through gateways, in live runs). Choices: yes; no. Right: no, the same actor
     (the program) does both. This is where reading every arrow as a handoff gets caught.
  3. `handoff` (`handoff`, Medium, free): "Name one handoff in this plane: a place where the run
     goes from a step done by one actor to the next step, done by a different actor (gateways
     between them don't matter). Name the two steps." Accepted: any of this plane's handoff pairs
     listed above, under the pair rule given at `setup-top`'s question 7. Credit: full for an
     accepted pair; none otherwise.
  4. `lane-step` (`lane-owner`, Easy, mcq): "Who does `<step>`?" An AI AGENT step whose label
     names a skill, not an actor: `Record where things live` in the bank (its second line is
     `setup-addressing`), `Install tools` (`setup-repos`) in live runs. Choices: the human; the AI
     agent; a program; more than one of them. Right: the AI agent. This is the only `lane-owner`
     question: nothing in the label says who does it.
  5. to 7. `split-or-merge` (`splits` or `merges`, whichever the diamond is; Easy, mcq, two
     choices): "At the diamond just after `<step or gateway>`, does the flow split, or do paths
     come back together?" Choices: "it splits"; "paths come back together". Three questions, at
     least one about a split and one about a merge, each pointing at a different diamond and
     tagged with the case its right answer names. Live runs may instead ask "What happens after
     `Check the receipt landed`?" (if `yes`, `Submit Installation 1`; if `no`, `stopped at a
     checkpoint`), tagged `splits`.
  8. `after-step` (`trace-steps`, Easy, free): "What happens after `<step>`?" with `Submit
     Installation 1` (answer: `Install the editors`, through the merge) in the bank and `Submit
     Installation 2` (`Publish the repositories`) in live runs.
  9. `after-last` (`trace-end`, Easy, mcq): "What happens after `Submit Installation 3`?" Choices:
     `set up, checked and submitted` (right); `stopped at a checkpoint`; `Publish the
     repositories`; `Check the remote`.

  **The bank** is the three scenarios, 26 questions. Study skips a question whose case is already
  met, so a learner rarely answers them all. Live runs, and later review, vary the pointed-at
  elements within the same planes (a different split and answer for
  `branch-label`, a different step A, a different diamond, a different step to ask what follows), keyed by reading the
  file at its current commit.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works the same kind of question aloud on a different diagram, saying what it looks at:
  `workflows/tour/tour.bpmn` (the tour at the end of setup, a single plane with no gateways) for
  start and end circles, steps, lanes, handoffs and data flow (`Explain the four parts of
  the tour` reads the guide; `Write the record`, in PROGRAM, writes `tour.md`, which `Open the file
  in the editor`, in the human's lane, reads later: a data handoff); the plane under `Execute the
  plan, task by task` in `workflows/develop/superpowers.bpmn` for `control-arrow` and `not-handoff`, using the solid arrow from
  `Open this plan's ledger, or start one` to `Scan the plan for conflicts and rule on each`, two
  AI AGENT steps, so the second runs next and it is not a handoff (tour.bpmn has no same-actor
  step-to-step pair); and the top level of `workflows/develop/superpowers.bpmn`, which is in no bank, for everything
  else: the box `Brainstorm the design` (a plus, drawn across all three lanes) for a subprocess and a step drawn across lanes; the diamond `how much process does this
  need?` for a split, with its labels `spike`, `bounded` and `architectural` for branch labels;
  the unnamed diamond it follows, where the start and the two `yes` branches from `hidden
  complexity?` meet, for a merge (and for a loop back); "what happens after `Brainstorm the
  design`?" (`Write the implementation plan`) and "after `Run the project's full test suite`?"
  (if `yes`, `Finish the branch`; if `no`, the end state `stopped, suite red`) for traces. These
  point at the drawing only, with no claim about how Superpowers runs today. Help is never worked
  on a bootstrap plane, since all three are check material.
- **doesn't show:** every question is on one diagram the learner has seen before, so a pass doesn't
  show they could read a brand-new diagram, drawn by someone else or in another style, and later
  attempts may draw on memory of this one rather than reading. `subprocess-box`, `spans-lanes`,
  `not-handoff`, `control-arrow`, `branch-label` and `data-line` are each asked on only one plane
  (`data-line` about one file), so they have little room to vary. `data-line` asks only about a
  file being read, since no step on bootstrap.bpmn writes a file, and `Open U-M GPT`'s second
  label line names `bootstrap-prompt.md`, so the step's own label points at the file. The deck calls its arrow symbol control flow and a
  handoff only between actors, which matches the `not-handoff` ruling. The plane has no file that
  one actor's step writes and another's reads, so no question checks a data handoff. The diagram uses exclusive gateways only, so a
  pass says nothing about parallel paths or typed events. Questions point at the elements to read,
  so a pass doesn't show the learner would notice, unasked, what a diagram leaves out, or could say
  whether a step is in the right lane, which this topic leaves to sessions 18 to 21. Each case is
  now spread over several one-thing questions, but a pass on any one question tagged with a case
  records that case, so where a case has more than one question (`states`, start and end), the
  easier can stand for both, and a guess
  on a two-choice question (`not-handoff`, `split-or-merge`) can stand for a case.
- **offer as:** the fuller check: planes of the setup diagram, one thing asked per question,
  each with one answer, mostly multiple choice, with short free answers such as "what happens
  after this step?" and "name one handoff". No single plane meets the goal: it takes one question
  per case, fifteen in all across the three planes, about 20 minutes.
- **check note:** Treat these three points as part of running it.
  - **`data-line`:** `Open U-M GPT`'s own label names `bootstrap-prompt.md`, so the right choice is
    easier than it looks.
  - **Help on `not-handoff` or `control-arrow`:** `tour.bpmn` has no step-to-step arrow inside one
    lane, and its start arrow leaves a state, not a step. Work the help on the plane under `Execute
    the plan, task by task` in `superpowers.bpmn` instead. Its pair `Open this plan's ledger, or
    start one` to `Scan the plan for conflicts and rule on each` is a solid arrow between two AI
    AGENT steps.
  - **Commit check:** until `deck-workflow-fixes` is merged, every scenario fails it. Ask the
    questions live instead, keyed from the learner's commit. Nothing that the bank asks about
    differs between `6b578e9` and `eb7b655` except that `Set up the workspace` is now drawn across
    all three lanes.

### `a-judge-diagram-summary`

- **serves:** `c-read-diagram`
- **supports:** attempt
- **checks:** `c-read-diagram`
- **artifact:** the same diagram, `workflows/bootstrap/bootstrap.bpmn`, with sentences from a
  summary of it that an AI agent wrote, from this activity's bank or written live per the generator
  below. About 2 to 3 minutes a question, 5 to 10 a scenario.
- **verified:** 2026-11-01
- **learner does:** opens the plane the scenario names in Camunda Modeler and reads the question
  served: sentences from an AI agent's summary about one named element. In a compound question,
  picks True or False for each sentence, part by part; in a four-choice question, picks the one
  sentence the diagram supports.
- **tutor role:** examiner
- **tutor does:** as `a-read-course-diagram`'s (the session 18 offer, the commit check against
  the diagram's commit on `main` recorded in each key, opening the diagram, never describing it,
  help recorded as helped), and also: shows a compound's stem and its parts lettered `(a)`, `(b)`
  in one message and takes the learner's answers to every part in one reply; settles each part
  from the key. While the learner answers, gives no hint: never says which sentences are wrong or
  how many, and doesn't ask them to explain a False or a choice. After the ruling, gives feedback
  by part, as the compound design describes: for each part, the learner's answer, whether it was
  right, and for a missed part what was expected. A learner who adds what the diagram does say is welcome to and gains nothing
  for it. Labels a live run `a-judge-diagram-summary/<case>`. Says when offering it that no one
  plane carries every case: meeting the goal takes one question per case, fifteen over the three
  scenarios, about 25 minutes, splittable over sittings.
- **done when:** the criterion met with no help, case by case. A four-choice question passes its
  case when its one answer is right. A compound passes its case only when every part is right (study
  records `met` only then; quiz grading scores the mean of the parts).
- **generator:** **The material** is as `a-read-course-diagram`'s: `workflows/bootstrap/bootstrap.bpmn`
  as learners have it, the diagram's commit on `main` recorded as `diagram commit:` in each rubric
  key's top part (now `eb7b655`, updated when the package lands) and never in the task file, the same three planes, and nothing drawn or invented. `Set up the
  workspace` is drawn across all three lanes and `Get Codex running` across two. All of that
  entry's reading rules hold here: elements named by the first words of their label, diamonds
  pointed at by their neighbors, the plane under a subprocess opened from the small arrow button
  at the box's bottom-right corner, handoff pairs named step to step with gateways between them
  ignored and never a box drawn across lanes (named in the question as excluded whenever the plane
  has one), no mention of data in a handoff sentence, and trace sentences that claim what follows
  one named step, never a stated run. Scenario files are this activity's own:
  `tasks/a-judge-diagram-summary/<scenario-id>.md` and `rubrics/a-judge-diagram-summary/<scenario-id>.md`,
  named `setup-top`, `get-codex-running` and `set-up-workspace`.

  **A scenario file.** Its top part says only what the diagram is ("the course's setup workflow,
  as drawn for Installations 1 to 3", with the same caution as `a-read-course-diagram`'s setup),
  the file's path, and how to reach the plane. Under `## Framing`: "An AI agent was asked to say in
  plain words what this plane of the diagram claims. Each question below gives sentences from its
  summary about one element of the plane." How to answer goes in each question, never in the top
  part or the framing.

  **Two question forms, one case each, one element each.**
  - **Compound** (`type: compound` on the rubric's `###` entry): the `###` body is the stem, "The
    agent's summary says these things about `<element>`. Is each sentence true or false?" Then two
    or three parts, `#### a`, `#### b`, `#### c`, lettered in order. Each part is one quoted
    sentence followed by `1. True` and `2. False`. The rubric's `###` entry carries `goal:
    c-read-diagram`, the one case, and `type: compound`; each `####` rubric part carries `type:
    mcq`, `answer: 1` or `2`, and an optional `tutor note`, never `goal` or `cases`. No image or
    image link inside a part.
  - **Four-choice** (`type: mcq`): "The agent's summary says several things about `<element>`.
    Which one does the diagram support?" then four numbered sentences from the summary, exactly one
    right; the wrong three are misreadings for that case (below), each stated as plainly as the
    right one. The rubric carries goal, the one case, `type: mcq` and `answer`. The right
    sentence's position varies across the bank and within a scenario, with no fixed pattern.

  **How to choose, per case.** Compound when the element supports two or three claims that are
  not simply each other's opposite, so that each part is a separate reading; four-choice when two
  sentences would be opposites, or one right sentence settles the case.
  - `states`, `step-box`, `gateway-shape`, `subprocess-box`: four-choice. What kind of shape an
    element is makes one claim; the four sentences offer it and three misreadings.
  - `lane-owner`: compound. Sentences about who does one step ("the AI agent does it", "a program
    does it, since its label names `setup-addressing`", "the human does it"): any of them can be
    false, so both can be.
  - `spans-lanes`: compound. One sentence per actor or about all of them ("the human takes part",
    "a program takes part", "only the AI agent does it").
  - `handoff`: four-choice, about one step pair done by different actors (the element is the
    pair): the right sentence says it is a handoff; the others say it is not, or misplace an actor.
  - `not-handoff`: four-choice, about one same-actor pair: the right sentence says it is not a
    handoff, since the same actor does both; the others call it one, or misplace an actor.
  - `control-arrow`: compound. Claims about one solid arrow between two steps ("the second step
    runs next", "both steps run at the same time", "the first step reads a file").
  - `branch-label`: compound. Claims about one label ("a run goes this way when the gateway's
    answer is `no`", "a step called `no` runs next", "the run ends here").
  - `data-line`: compound. Claims about the one dotted line ("`Open U-M GPT` reads the file",
    "after `Open U-M GPT`, the run moves on to the file", "the file is the next step").
  - `splits`, `merges`: four-choice, about one diamond pointed at by its neighbors (a named split
    for `splits`, an unnamed merge for `merges`): the right sentence says what happens there; the
    others are misreadings.
  - `trace-steps`: compound when the named step is followed by a split, one part per branch
    ("after `Check the install`, on `success`, comes `Submit each session's report`"; "on `not
    yet`, the flow goes back to `Set up the workspace`"); four-choice when one step comes next
    (four sentences each naming a different next step).
  - `trace-end`: four-choice, about a named last step: four sentences naming what follows, one the
    right end circle.

  **The misreadings** a False part or a wrong choice states, as plainly as a right one; no sentence
  is half right or turns on a word. A circle is never called a state, and the start circle's being
  a person's action is never a misreading; the right sentence says the start circle marks what
  starts a run (its trigger) and an end circle an outcome a run ends in.
  - `states`: calls a circle a step the workflow does, or calls the start circle an end or an end
    circle the start.
  - `step-box`: calls a plain step a start or end circle, or a step with a diagram underneath it.
  - `gateway-shape`: calls a gateway a step someone does, or a start or end circle; never says
    whether it splits or merges.
  - `subprocess-box`: calls a collapsed subprocess a single action with nothing more to it.
  - `lane-owner`: gives the step to the actor its label suggests rather than the one its lane
    names.
  - `spans-lanes`: gives a box drawn across lanes to one actor alone, or leaves out an actor whose
    lane it crosses.
  - `handoff`: says a pair done by different actors is not a handoff.
  - `not-handoff`: calls a same-actor pair a handoff, which is where reading every arrow as a
    handoff gets caught.
  - `control-arrow`: reads the arrow as a step reading a file, or as both steps running at once.
  - `branch-label`: reads the label as a step that runs, or as an end state.
  - `data-line`: reads the dotted line as the run moving to the file, or as the next step. No
    sentence turns on whether the line is a handoff.
  - `splits`: says the flow comes back together at a named split.
  - `merges`: calls an unnamed merge a decision, a place where the flow splits.
  - `trace-steps`: names the wrong step after a named one, or gets a loop's branch wrong.
  - `trace-end`: names the wrong end state.

  **True and False** (compound parts only). Across a scenario's compound parts, True and False
  each make up between a third and two thirds of the answers. No fixed pattern: not every compound
  is one True and one False (each scenario with two or more compounds has at least one with two
  Trues or two Falses), and the True part is not always in the same position. For four-choice
  questions, the right choice's position varies instead.

  **Planes, cases and order.** One question per case, in this order, so that no question reveals a
  later one's answer:
  - `setup-top`: nine questions (seven four-choice, two compound), about 14 minutes. `states` (a circle), `step-box` (`Report being
    stuck`), `gateway-shape` (the diamond just before `Set up the workspace`, said to be a gateway
    only), `subprocess-box` (`Set up the workspace` or `Get Codex running`), `spans-lanes`
    (`Set up the workspace`, all three actors; live runs `Get Codex running`, two), `splits` (the
    diamond just after `Get Codex running` or `Set up the workspace`), `merges` (the diamond just
    before `Set up the workspace` or `Report being stuck`), `trace-steps` (compound, after `Check
    the install`, whose `not yet` branch loops back), `trace-end` (after `Submit each session's
    report` or `Report being stuck`). No handoff question here; those are on `set-up-workspace`.
  - `get-codex-running`: six questions (three four-choice, three compound), about 11 minutes. `splits` first (`stuck?` or `checklist
    done?`, by neighbors), then `branch-label` (only labels on arrows that stay in one lane: `no`
    at `stuck?`, either at `checklist done?`, `try suggestion` at `worth trying?` only in live runs
    where `trace-steps` doesn't follow), `data-line`, `merges` (the one unnamed diamond),
    `trace-steps` (compound, after `Provide explanations and suggestions`, whose `try suggestion`
    branch loops back), `trace-end` (after `Write a status report on where it stalled`).
  - `set-up-workspace`: eight questions (six four-choice, two compound), about 13 minutes. `control-arrow` (`Write the receipt` to
    `Check the receipt landed`), `not-handoff` (a same-actor pair from `a-read-course-diagram`'s
    list for this plane), `handoff` (a pair done by different actors, not one that includes
    `Record where things live`), `lane-owner` (`Record where things live` or `Install tools`),
    `splits`, `merges` (one diamond each, by neighbors), `trace-steps` (single, after `Submit
    Installation 1`), `trace-end` (after `Submit Installation 3`).

  The bank is the three scenarios, 23 questions, and across it every misreading above appears at
  least once. Live runs vary the elements and sentences within the same planes, keyed from the
  file at its current commit.
- **worked example:** as `a-read-course-diagram`'s, on `tour.bpmn` or superpowers.bpmn and never
  on a bootstrap plane, with the tutor judging two sentences of its own aloud, one right and one a
  misreading ("the AI agent writes the record": false, `Write the record` is in the PROGRAM lane).
- **doesn't show:** a four-choice question passes on a guess one time in four; ten cases are
  carried by four-choice questions. A compound passes only when every part is right, so a guess
  passes a two-part one a quarter of the time and a three-part one an eighth. The
  misreadings are the ones listed, so a pass shows the learner can reject those, not every way a
  diagram can be misread, and it shows recognizing a right reading rather than producing one,
  which `a-read-course-diagram` asks for. The rest of `a-read-course-diagram`'s `doesn't show`
  applies, including that the diagram is a familiar one, here met again after that activity if
  both are done.
- **offer as:** the check against someone else's reading: an AI agent's summary of a plane of the
  setup diagram, judged sentence by sentence (True or False) or by picking the one sentence the
  diagram supports. Closest to the course's use, checking what an agent says a workflow does. No
  single plane meets the goal: it takes one question per case, fifteen in all across the three
  planes, about 25 minutes.
- **check note:** This activity is on hold. If it is served anyway, note four things.
  - **Only `setup-top` is drafted.** Its key records `6b578e9`, so it passes the commit check on a
    clone that predates the merge and fails on a merged one. Its key also describes `Set up the
    workspace` as sitting in AI AGENT, which is the old drawing; no question turns on that.
  - **No question carries `not-handoff`.** The learner needs that case from somewhere else. Set it
    live from `a-read-course-diagram`'s `set-up-workspace` `not-handoff` question.
  - **Correct the count.** Tell the learner fifteen cases, not fourteen.
  - **Each question is ruled as one.** A learner who judges one sentence right and the other wrong
    earns nothing on that case. The `get-codex-running` and `set-up-workspace` questions don't exist
    yet and would have to be written live from the generator.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
