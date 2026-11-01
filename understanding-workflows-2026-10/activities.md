# Activities: understanding workflows

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

2026-10-28: nothing at file level.

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |
| `c-read-diagram` | read a workflow diagram and say what it claims | given a workflow diagram, says what it claims: what each shape marks, who does each step, what each kind of arrow means, and where the flow splits and merges. Cases: `states` (the shape marking the state a run starts or ends in), `step-box` (the shape marking a step), `gateway-shape` (the shape marking a gateway), `subprocess-box` (the shape marking a collapsed subprocess), `lane-owner` (who does a step, from its lane), `spans-lanes` (who does a step drawn across two lanes), `handoff` (where control, or data a later step uses, passes to a step done by a different actor), `not-handoff` (that a step followed by another step of the same actor is not a handoff), `control-arrow` (what a solid arrow between two steps says [which step runs next]), `branch-label` (what a label on an arrow leaving a gateway says), `data-line` (what a dotted line between a step and a file says [data written or read, not the run moving to the file]), `splits` (where flow splits [a named gateway]), `merges` (where flow merges [an unnamed gateway]), `trace-steps` (what happens after a given step, including when the flow loops back), `trace-end` (which end state follows a given last step). Taught elsewhere: session 18 class. |

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
- **artifact:** the session 2 lecture deck, "What is a workflow?", in its revised form. It is
  `docs/lecture-slides/l-what-is-a-workflow.html` in the learner's `course-materials` clone, a
  self-contained HTML file that opens in any browser with no server (arrow keys move, `Esc` shows
  every slide). The revision is on the `deck-workflow-fixes` branch of `course-materials` until
  the instructor merges it; until then a learner's clone has the session 2 version, whose
  vocabulary slide lists skill beside AI agent and whose glossary labels its arrow "Handoff".
  Only slides 4 to 7 are read: 4, the definition of a workflow and a two-row table of what
  dropping a part leaves (repeatable, or you have a project; a settled order, or you have a
  checklist); 5, the vocabulary list (run, step, trigger, outcome, AI agent (bot), skill, script,
  handoff, with synonyms); 6, an xkcd flowchart; 7, the symbol glossary: states ("the condition
  that starts or ends a run"), step, file ("data a step reads or writes, joined to it by a dotted
  line"), control flow ("which step runs next; when the next step belongs to another actor, it is
  a handoff"), and gateway, split or merge. Slides 1 to 3 and 8 to 10 are class logistics,
  discussion norms, table questions about `bootstrap.bpmn` and lab instructions, and are skipped.
  Public copy, once merged:
  https://github.com/umsi212F2026/course-materials/blob/main/docs/lecture-slides/l-what-is-a-workflow.html
  (the repository is public and the page answers, but GitHub shows the file's source rather than
  the slides, and the repository has no GitHub Pages site, so the local copy is the one to open).
  About 4 minutes for the four slides, about 10 with the stop, the tutor's additions and the close.
- **learner does:** reads slides 4 to 7 once, then stops at slide 7 and answers before going on;
  "I'm not sure" is an honest answer. At the stop, writes one line in their own words for each of
  the glossary's five symbols, saying what it marks in a diagram: a state, a step, a file, a
  control-flow arrow (including when it is a handoff), and a gateway (both what a split is and
  what a merge is). Then hears the tutor's additions (below), and answers the close: with this
  deck beside you, could you now open one of the course's workflow diagrams in Camunda Modeler
  and say where a run starts and ends, who does each step, what each kind of arrow means, where
  the flow splits and merges, and what happens after a given step?
- **tutor role:** explainer
- **tutor does:** gives the learner the full path of the deck in their own `course-materials`
  clone and has them open it in a browser (double-click, or the tutor runs `open "<path>"` on
  macOS or `Start-Process "<path>"` on Windows). If the deck is not in the clone, the clone is out
  of date: bring it up to date first. If the clone has the session 2 version (its glossary arrow
  is labeled "Handoff" rather than "Control flow"), the revision hasn't been merged yet: the tutor
  goes ahead, and adds to the arrow addition below that the slide's "Handoff" label covers only
  the arrows that cross to another actor. Does not paste slides into the chat, and does not open
  any `.bpmn` file: the course's diagrams are this topic's check material. Stays quiet through the
  reading except at the stop and when asked. At the stop, takes the learner's lines first and
  replies to a wrong or vague one with one near-miss question rather than a verdict ("you said a
  gateway is where a decision is made; what about a diamond with two arrows in and one out?").
  Intended lines: a state is a condition that starts or ends a run, not something done; a step is
  one action someone or something takes; a file is data a step reads or writes, joined by a dotted
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
  nothing about `c-read-diagram`. It shows nothing about the sixteen words, which have their own
  supply in `a-words`; the deck names only some of them (it never says lane, subprocess,
  executor, workflow state or data flow), and lane, subprocess and data flow reach the learner
  only through the tutor's spoken additions. The revised slide 7 states the handoff rule for
  control flow only; that a file passed between actors is also a handoff rests on the tutor's
  sentence. Until the revision is merged, a learner opening their own clone reads the session 2
  slides, whose "Handoff" arrow label invites reading every arrow as one.
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
  the generator below. A scenario is one plane: `setup-top` twelve questions (about 16 minutes),
  `get-codex-running` six (about 9), `set-up-workspace` nine (about 11), each one sitting.
- **verified:** 2026-10-28
- **learner does:** opens the diagram in Camunda Modeler, goes to the plane the scenario names, and
  answers the one question served in their own words, pointing at elements by the first words of
  their labels or by the steps or gateways on either side of them.
- **tutor role:** examiner
- **tutor does:** the goal is also taught in the session 18 class (`taught elsewhere`): before
  session 18 the tutor says so and asks whether the learner wants to try now or after, and goes
  ahead if they want. Before serving a scenario, checks that the diagram hasn't changed since the
  key was written: `git -C <course-materials> log -1 --format=%h -- workflows/bootstrap/bootstrap.bpmn`
  must print the commit the scenario's key records (in its rubric file); if it doesn't, the tutor doesn't serve that
  scenario and records it as a bank defect for the instructor. The keys record `eb7b655`, the
  revised layout on the `deck-workflow-fixes` branch, and the check runs against the learner's
  merged `course-materials`; a clone still at the older `6b578e9` fails it, so the bank needs that
  branch merged before it is released. Gives the full path of the file and
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
  (`setup-top` for states, step-box, gateway-shape, subprocess-box, lane-owner, spans-lanes,
  handoff, splits, merges, trace-steps and trace-end; `get-codex-running` for branch-label and
  data-line; `set-up-workspace` for control-arrow and not-handoff), eleven of them one-minute
  multiple choice and four free answers, about 20 minutes, which can be split over sittings.
- **done when:** the criterion met with no help, case by case: a full-credit answer passes the case
  its question carries; half credit or none passes none.
- **generator:** **The material is fixed and real**: the generator picks elements from
  `workflows/bootstrap/bootstrap.bpmn` and writes questions about them; it never draws, edits or
  invents a diagram. Do not use `workflows/learn/learn.bpmn`, which lags the learn workflow it
  depicts. Every answer in a key is read from the `.bpmn` file at the commit the key records,
  checked against the plane in Camunda or a render (`node workflows/diagram/tools/render.mjs`,
  with the subprocess's id for a plane below the top), since a step drawn across lanes shows
  only in the geometry. Keys are written against the revised layout, commit `eb7b655` (on the
  `deck-workflow-fixes` branch until it is merged): no flow changed from `6b578e9`, but `Set up the
  workspace` is now drawn across all three lanes.

  **A scenario is one plane**, and there are three, each a file
  `tasks/a-read-course-diagram/<scenario-id>.md` with its key in
  `rubrics/a-read-course-diagram/<scenario-id>.md`:
  - `setup-top`: the top level, "opens the Day 1 page in Canvas" to its two end states. Carries
    `states`, `step-box`, `gateway-shape`, `subprocess-box`, `lane-owner`, `spans-lanes`,
    `handoff`, `splits`, `merges`, `trace-steps` and `trace-end`, the only plane that carries
    `subprocess-box`, `lane-owner` or `spans-lanes`. Its only handoff pair (step to step,
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
    nor `spans-lanes`. Its states, steps and gateways could carry `states`, `step-box` and
    `gateway-shape`; the bank asks those on `setup-top` only, and live or review runs may ask them
    here, in the same form.
  - `set-up-workspace`: the plane under `Set up the workspace`. Carries `control-arrow` (the only
    plane with solid arrows joining two steps directly: `Write the receipt` to `Check the receipt
    landed`, both in PROGRAM; also `Install tools` to `Check the repositories` and the other
    install-then-check pairs, which cross lanes), `lane-owner` (the stronger form: see question
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
  box to open the diagram underneath it."), and "Each question below is about this plane of the diagram alone." It names no step, lane, gateway or outcome beyond the one needed to reach the plane.

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
  the workspace` only as "a gateway", the lane questions come before the handoff question, and the
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

  **`setup-top`: twelve questions, about 16 minutes if all are answered.**
  1. `start-state` (`states`, Easy, mcq): "Which of these is the state a run of this workflow
     starts in?" Choices: the start event's label, one end state, `Get Codex running`, and "the
     diamond just after `Get Codex running`".
  2. `end-state` (`states`, Easy, mcq): "What does the circle `<end state>` mark?" (`workspace
     ready` or `blocked`.) Choices, word for word: "a state a run starts in"; "a state a run ends
     in"; "one step, an action someone takes"; "a gateway". Right: the second.
  3. `plain-step` (`step-box`, Easy, mcq): "What does the rounded box `Report being stuck` mark?"
     Choices, word for word: "a state a run starts or ends in"; "one step, an action someone
     takes"; "a gateway, where the flow splits or comes back together"; "a step with a diagram of
     its own underneath it". Right: the second.
  4. `subprocess` (`subprocess-box`, Easy, mcq): "Which of these steps has a diagram of its own
     underneath it?" Choices: `Set up the workspace`; `Check the install`; `Report being stuck`;
     `Submit each session's report`. Live runs may ask it with `Get Codex running` as the right
     choice and three other plain steps.
  5. `gateway` (`gateway-shape`, Easy, mcq): "What kind of shape is the diamond just before `Set
     up the workspace`?" Choices: a state; a step; a gateway; a file. Right: a gateway. It asks
     the kind only, never whether this one splits or merges, so it gives nothing away to
     questions 9 and 10.
  6. `lane-step` (`lane-owner`, Easy, mcq): "Who does `<step A>`?" Step A is a step with no plane
     below it: `Check the install` (PROGRAM), `Report being stuck` or `Submit each session's
     report` (both HUMAN operator), varying between the bank and live runs; never `Set up the
     workspace`, which is drawn across all three lanes. Choices: the human; the AI agent; a
     program; more than one of them. This is the weaker `lane-owner` form: on this plane the
     labels give the answer away (`Check the install`'s second line names `check-setup.mjs`, and
     the human steps say "on Canvas"). The stronger form is on `set-up-workspace`.
  7. `lane-span` (`spans-lanes`, Medium, mcq): "Who does `Get Codex running`?" Choices: the human
     only; the AI agent only; the human and the AI agent both take part; the human, the AI agent
     and a program all take part. Right: the third. Live runs may ask the same about `Set up the
     workspace`, where the fourth is right.
  8. `handoff` (`handoff`, Medium, free): "Name one handoff in this plane: a place where the run
     goes from a step done by one actor to the next step, done by a different actor (gateways
     between them don't matter). Name the two steps." Accepted: the plane's one handoff pair,
     `Check the install` to `Submit each session's report`. A pair with `Get Codex running` or
     `Set up the workspace` in it is not accepted, since those are drawn across lanes; the tutor
     says so and asks for another.
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
  9. `one-split` (`splits`, Medium, free): "Name one place where the flow splits. Point to it by
     the steps or gateways just before and after it." Answer: any of the three named gateways.
     Credit: full for one; none for an unnamed merge or a step. (The "what happens after" form is
     not used for `splits` here: the only steps on this plane followed by a split without a
     loop-back are drawn across lanes.)
  10. `one-merge` (`merges`, Medium, free): "Name one place where paths come back together. Point
      to it by the steps or gateways just before and after it." Answer: either unnamed gateway
      (the one before `Set up the workspace`, or the one before `Report being stuck`). Credit:
      full for either; none for a named gateway or a step.
  11. `after-loop` (`trace-steps`, Medium, free): "What happens after `Check the install`?"
      Answer: if `success`, `Submit each session's report`; if `not yet`, back to `Set up the
      workspace`. The `not yet` branch loops back, so it is tagged `trace-steps`. Credit as for a
      conditional above.
  12. `after-last` (`trace-end`, Easy, mcq): "What happens after `<last step>`?" Bank: `Submit
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
     listed above, under the pair rule given at `setup-top`'s question 8. Credit: full for an
     accepted pair; none otherwise.
  4. `lane-step` (`lane-owner`, Easy, mcq): "Who does `<step>`?" An AI AGENT step whose label
     names a skill, not an actor: `Record where things live` in the bank (its second line is
     `setup-addressing`), `Install tools` (`setup-repos`) in live runs. Choices: the human; the AI
     agent; a program; more than one of them. Right: the AI agent. This is the stronger
     `lane-owner` form, since nothing in the label says who does it.
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

  **The bank** is the three scenarios, 27 questions. Study skips a question whose case is already
  met, so a learner rarely answers them all. Live runs, and later review, vary the pointed-at
  elements within the same planes (a different split and answer for
  `branch-label`, a different step A, a different diamond, a different step to ask what follows), keyed by reading the
  file at its current commit.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works the same kind of question aloud on a different diagram, saying what it looks at:
  `workflows/tour/tour.bpmn` (the tour at the end of setup, a single plane with no gateways) for
  start and end states, steps, lanes, handoffs, an arrow inside one lane (`tour skill invoked` to
  `Ask what they want`, control flow with no handoff) and data flow (`Explain the four parts of
  the tour` reads the guide; `Write the record`, in PROGRAM, writes `tour.md`, which `Open the file
  in the editor`, in the human's lane, reads later: a data handoff); and the top level of `workflows/develop/superpowers.bpmn`, which is in no bank, for everything
  else: the box `Brainstorm the design` (a plus, drawn across all three lanes in the revised
  layout on the `deck-workflow-fixes` branch) for a subprocess and a step drawn across lanes; the diamond `how much process does this
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
  label line names `bootstrap-prompt.md`, so the step's own label points at the file. The revised session 2 deck calls its arrow symbol control
  flow and a handoff only between actors, which matches the `not-handoff` ruling; a clone that
  still has the older slides labels the arrow "Handoff", and a learner who learned that slide well
  can fail `not-handoff` for it. The plane has no file that
  one actor's step writes and another's reads, so no question checks a data handoff. The diagram uses exclusive gateways only, so a
  pass says nothing about parallel paths or typed events. Questions point at the elements to read,
  so a pass doesn't show the learner would notice, unasked, what a diagram leaves out, or could say
  whether a step is in the right lane, which this topic leaves to sessions 18 to 21. Each case is
  now spread over several one-thing questions, but a pass on any one question tagged with a case
  records that case, so where a case has more than one question (`states`, start and end;
  `lane-owner`, the weaker form on `setup-top` and the stronger on `set-up-workspace`), the
  easier can stand for both, and a guess
  on a two-choice question (`not-handoff`, `split-or-merge`) can stand for a case.
- **offer as:** the fuller check: planes of the setup diagram, one thing asked per question,
  each with one answer, mostly multiple choice, with short free answers such as "what happens
  after this step?" and "name one handoff". No single plane meets the goal: it takes one question
  per case, fifteen in all across the three planes, about 20 minutes.
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
- **note:** on hold. Its drafted sample (`setup-top`) was keyed to `bootstrap.bpmn` at `6b578e9`,
  before `Set up the workspace` was redrawn across all three lanes, so it needs rekeying to
  `eb7b655` when this activity comes off hold.
- **generator:** **The material** is as `a-read-course-diagram`'s: the same three planes, the
  same cases per plane, the same `diagram commit:` line in each key (never in the task file),
  and nothing drawn or invented. Its
  scenario files are its own, `tasks/a-judge-diagram-summary/<scenario-id>.md` and its key under
  `rubrics/`, named `setup-top`, `get-codex-running` and `set-up-workspace`. The setup is as
  there, then: "An AI agent was asked to say in plain words what this plane of the diagram claims.
  Each question below gives sentences from its summary. For each sentence, say whether the diagram
  says that: yes or no."

  **A question** asks about one case: a stated element, then two numbered sentences, and "Does the diagram say this? Answer yes or no
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
  - `handoff` (`set-up-workspace`, Medium): one sentence about a same-actor pair and one about a
    handoff pair, from that plane's lists in `a-read-course-diagram`. The misreadings: calls a
    same-actor pair (`Write the receipt` to `Check the receipt landed`, both PROGRAM) a handoff,
    which is where reading every arrow as a handoff gets caught, whatever the slide says; or says
    a pair done by different actors is not one. Sentences name two steps under the pair rule at
    `a-read-course-diagram`'s `setup-top` question 8: no sentence mentions data, gateways between them are ignored, no
    sentence points at an arrow ending at a gateway or asks who a gateway belongs to, and `Get
    Codex running` is in no pair. A learner who volunteers a view on a gateway arrow is not marked
    down for it.
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
    splits at a named one; or, in the "after `<step>`" form, a conditional with one branch's label
    or destination wrong ("after `Check the install`: if `not yet`, `Submit each session's
    report`").
  - `merges` (every plane, Medium): calls an unnamed merge a decision, or says two paths never
    come back together when they do.
  - `trace-steps` (every plane, Medium): names the wrong step as coming right after a named one
    ("after `Open U-M GPT` comes `Provide explanations and suggestions`"), or gets a loop wrong
    ("after `Check the install`, on `not yet`, the flow goes on to `Submit each session's
    report`"). Each sentence makes one claim about what follows one named step; no sentence
    states a whole run. At least one `trace-steps` sentence per scenario that has a loop is about
    a branch that loops back.
  - `trace-end` (every plane, Easy): names the wrong end state after a named last step ("after
    `Submit each session's report`, the run ends in `blocked`").

  Credit: full when every sentence in the question is judged right; none otherwise. The rubric's
  `answer` is the yes/no list in order. A scenario carries one question per case its plane
  carries, in the order of the list above: `setup-top` ten questions (`states` to `spans-lanes`,
  then `splits`, `merges`, `trace-steps`, `trace-end`; about 14 minutes), `get-codex-running` six
  (`branch-label`, `data-line`, `splits`, `merges`, `trace-steps`, `trace-end`; about 9),
  `set-up-workspace` six (`handoff`, `control-arrow`, `splits`, `merges`, `trace-steps`,
  `trace-end`; about 9). The bank is the three scenarios, 22 questions, and across it every misreading above appears
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
