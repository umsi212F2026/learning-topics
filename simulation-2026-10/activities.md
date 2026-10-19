# Activities: simulation

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

The minimum route, the orientation, one passed question for each of the seven words and enough of
`c-name-question-kind` to pass its five cases, comes to about 40 minutes: about 14 for
`a-read-simulation`, about 3 a word, and two to five questions of `a-classify-simulation-question`
at 1 to 2 minutes each (two can carry all five cases). The capability carries `taught elsewhere`
(the session 16 class), so its two activities are offered after that class, as practice and
review.

In this topic's banks and live questions, every simulation is a made-up or textbook model, and a
tennis model is never said to be the course's session 16 simulator. Learner-facing text states the
task, never the scoring.

## Check notes

2026-10-19: nothing at file level.

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |
| `c-name-question-kind` | say which kind of question a simulation is being asked to answer | Given a short scenario in which someone wants a simulation to answer one question, says which kind of question it is: what outcomes are likely, whether something can happen at all, which option is better, what setting reaches a target, how bad things can get, or what would have happened if things had gone differently. It passes when they pick the kind the question actually asks rather than one its wording suggests: a process with chance in it whose question is not about likely outcomes, a "what if" about a choice still to be made rather than about the past, and a question that mentions the worst case but asks something other than how bad things can get; and when they name both of the kinds no wording trap points at, a question asking whether something can happen at all and one asking what setting of a model parameter makes an outcome reach a target. Cases: `chance-in-it`, `what-if-ahead`, `worst-case-mention`, `can-happen`, `target-setting`. |

## Coverage

| goal | checks | notes |
| ---- | ------ | ----- |
| `o-orientation` | `a-read-simulation` | |
| `c-name-question-kind` | `a-classify-simulation-question`, `a-name-kind-unprompted` | |

---

## Activities

### `a-read-simulation`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** a reading the course wrote for this topic, `tasks/read-simulation.md` in this
  folder, "Simulations, and the questions they answer" (about 1,620 words, about 7 minutes). No
  external reading is used: the instructor expected none to be aimed the right way. It follows one
  made-up tennis model throughout (on each point the server wins with a fixed chance, scored by
  tennis's rules), which is not the course's session 16 simulator and claims nothing about it, and
  adds a savings account (a deterministic model), a highway jam with no accident and a river's
  100-year flood. Sections: What a simulation is; The model (including what it leaves out); Chance,
  and why one run isn't enough (report at least the average and something about the spread, such
  as the standard deviation); When to simulate (an experiment, existing data or a formula instead,
  and one sentence on simulation for test data); Six kinds of question, one example each, then a
  paragraph on wording that can mislead about the kind; When your agent builds one (tests the
  agent writes, for example with Superpowers, can rule out some implementation mistakes, but there
  is no answer key for the question itself, so understand the model well enough to predict what it
  should do). About 7
  minutes of reading, 12 with the two stops, 14 with the close. Words in place: all seven words,
  each in bold where it is introduced, with every synonym goals.md lists (output measure,
  probabilistic, run, replication, iteration, also in bold) and every nearest confusable: an
  experiment, the real process the model describes, a simulation outcome set against a model
  parameter, deterministic (also in bold), a run with a changed parameter, the answer to the
  question, and the average outcome. The reading names no real simulation tool or library.
- **verified:** 2026-10-19
- **learner does:** reads the page once, top to bottom, and stops twice, answering before reading
  on; "I don't know yet" is an honest answer.
  1. After Chance, and why one run isn't enough: the coach's model treats every point as a
     weighted coin toss, independent of the last. Names one thing about real tennis it leaves out
     and how leaving it out could make the model's answer to the coach's question wrong; then says
     why playing the simulated tournament once wouldn't answer her question.
  2. After When your agent builds one: an agent has built the tennis model and reports that the
     player reaches the final 23% of the time. Names one setting they could try, and what they
     would expect to see if the model was built right.
  Then the close, about 2 minutes (up to 5 if a section is gone over again), with the reading still
  beside them: answers the question the tutor puts: with this page beside you, could you now read a
  short description of a simulation and say what its model leaves out, which of its values are
  model parameters and which are outcomes, and why it needs many trials; and, given someone's
  question for it, say which of the six kinds of question it is?
- **tutor role:** explainer
- **tutor does:** puts the reading in front of the learner by opening the file
  `tasks/read-simulation.md` from the topic folder on the local filesystem, so the learner's agent
  shows it formatted in a sidebar; does not paste it into the chat. Stays quiet through the reading
  except at the stops and when asked. At each stop, takes the learner's answer first and replies
  with one near-miss question rather than a verdict ("you said one run is enough because the rules
  are fixed; what changes from one trial to the next?"). Stop 1's intended answer is anything real
  the model omits (tiring, nerves on big points, momentum, the court surface, the weather) with a
  plausible way it would move the answer, and that one tournament is one trial of a stochastic
  model, showing one outcome rather than how often. Stop 2's intended answer is a setting whose
  result can be predicted: winning every point on her own serve means never losing a game she
  serves; two evenly matched players each win about half their matches; a much stronger opponent
  should push the 23% down. A learner who proposes running it again with the same settings and
  expecting exactly 23% gets one near-miss question ("would two runs of 10,000 tournaments give
  exactly the same percentage?") and the stop is not ruled on. Does not set or rehearse any word
  question from `a-words`: does not ask the learner to define a word, does not put a word against
  its nearest confusable, and does not offer a misused sentence to correct. Does not set or
  rehearse a question from this topic's capability activities either, and does not ask which kind
  the reading's examples are; if the learner asks how to tell the kinds apart in a tricky question,
  says that is what the session 16 class and the practice after it are for. Says that building a
  simulation is Problem Set 4's work, not this topic's, that the When to simulate section is there
  for the shape of the area and is checked nowhere in this topic, and that nothing in the reading
  describes the tennis simulator used in session 16. At the close, puts the readiness question as
  written above and rules on the answer.
- **done when:** criterion met. The bar for this goal is did it once and help is expected
  throughout, so the ruling is on the learner's answer to the readiness question, not on the stops
  or on whether the tutor thinks they are ready. A plain yes to both parts is `criterion: met`. A
  hedge on either part, with no plain no, is `criterion: unclear`: for the first part go over The
  model and Chance, and why one run isn't enough once more, for the second
  Six kinds of question, and put the question again. A second hedge stays `unclear`: on the first
  part the tutor offers the questions from `a-words`, and on the second says the kinds are taught
  in the session 16 class and offers `a-classify-simulation-question` after it. Before session 16,
  an answer to the second part that waits on the class ("not until we've done it in class") is a
  hedge, not a no: it is `criterion: unclear` with no rereading, the tutor says the class teaches
  the kinds, and puts the question again at the learner's first study after it. A plain no to
  either part is `criterion: not met`: record it, ask what is missing, and offer to go back over
  the stop or the section that bears on it; don't put the question again in the same sitting.
  This goal isn't required, so a no never blocks anything else the learner wants to try.
- **worked example:** n/a
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. It
  shows nothing about the seven words, which have their own supply in `a-words`, and nothing about
  `c-name-question-kind`: the six kinds appear with one example each, the readiness question asks
  only whether the learner thinks they could name them, and the stops are helped, ungraded and
  about other things. The reading is one course-written page built on a made-up tennis model and
  a few short examples beside it, so it shows nothing of what a simulation an agent builds actually looks
  like, or of the session 16 simulator. When to simulate rather than experiment, use data or use a
  formula is in the reading and checked nowhere, by design.
- **offer as:** this topic's orientation: one short page the course wrote, following one made-up
  tennis model from what a simulation is, through chance and many trials, to six kinds of question
  and why a simulation your agent builds needs you to understand it, with two short stops and a
  one-question close. About 14 minutes.

### `a-classify-simulation-question`

- **serves:** `c-name-question-kind`
- **supports:** attempt
- **checks:** `c-name-question-kind`
- **artifact:** no external source. A described simulation model and four people's questions for
  it, from this activity's bank or written live per the generator below. 1 to 2 minutes a
  question, about 6 minutes a scenario.
- **learner does:** reads the scenario's setup, a simulation model described in a few sentences,
  and the one question served, in which one person says what they want the simulation to tell
  them, and picks which kind of question that person is asking from four choices.
- **tutor role:** examiner
- **tutor does:** the kinds are taught in the session 16 class (`taught elsewhere`), and this is
  practice for after it: before session 16 the tutor says so and offers to wait, and goes ahead if
  the learner wants. Sets the question as served, without rewording it or hinting; never names the
  cases or says which words in a question might mislead. Gives help whenever it is asked for, and
  records the attempt as helped. When the generator is run live, writes the key and the cases into
  the record before showing the question. Labels the attempt with the question's path, or
  `a-classify-simulation-question/<shape>` when run live, and records the cases with `--cases`. At a
  table in class, each student writes down a choice before any are read out.
- **done when:** the criterion met with no help, case by case. Each question gets one ruling: the
  right choice passes every case the question carries, and any other choice passes none. There is
  no half credit.
- **generator:** **A scenario** is one made-up simulation model, set out in a setup of three to
  five sentences: the process it models; one sentence on something it leaves out; two to four named
  model parameters, each with an example value; what one simulation trial produces; and how chance
  is built into its rules ("on each point the server wins with the chance set by the first
  parameter"). Every model in this activity is stochastic, so every question's process has chance
  in it. Domains vary by scenario, and none repeats within a bank except tennis, which may appear
  twice: a tennis match or tournament, a river town's floods, a bus route's delays, a flu outbreak at a school, a clinic's waiting room, a league's
  season, a food truck's lunch line. A tennis model is presented as a made-up one and never as the
  course's session 16 simulator. The setup ends: "Each question below comes from a different
  person who wants this simulation to answer one question. Each question is about this simulation
  alone."

  **A question** is one to three sentences in a named person's voice saying what they want to
  know, then "Which kind of question is <name> asking?" and four numbered choices, `type: mcq`. The
  choices are taken word for word from this list, and keep its order:
  1. What outcomes are likely
  2. Whether something can happen at all
  3. Which option is better
  4. What setting reaches a target
  5. How bad things can get
  6. What would have happened if things had gone differently

  The four are the right kind, the lure for each wording-trap case the question carries, and
  fillers to make four, taken only from the fillers its shape allows below, numbered 1 to 4 in list
  order. The lures are the common misreadings: for `chance-in-it`, What outcomes are likely; for
  `what-if-ahead`, What would have happened if things had gone differently; for
  `worst-case-mention`, How bad things can get. `can-happen` and `target-setting` have no lure: they
  are carried by the questions whose right kind they name. Each question asks exactly one kind, and
  none of the other choices it offers is defensible. A question never uses the key words of its
  right choice ("likely", "at all", "better", "target", "how bad", "would have happened");
  plain words for the same thing are allowed ("possible", "come out ahead", "how many would it take", "how
  high").

  **Chance words.** A question carries `chance-in-it` only when its wording uses a chance or
  frequency word ("chance", "odds", "how often", "most", "rare", "usually", "typical") while asking
  something other than likely outcomes, so that the pull toward likely outcomes is in the question
  and not only in the model. A shape that doesn't carry `chance-in-it` uses none of these words,
  except `likely-ahead`, whose right kind is likely outcomes.

  **No reading examples.** The reading, `tasks/read-simulation.md`, gives one example per kind: a
  player's chances of reaching a final (likely outcomes), a highway jam forming with no accident or
  other cause (can it happen), serve coaching against a sports psychologist (which option), the serving edge needed
  for most sets to go to a tie-break (what setting reaches a target), the 100-year flood (how bad), and last season under
  different scoring (what would have happened). No question restates one of these under the kind
  the reading gave it, so that none can be answered from memory of the page. A domain the reading
  uses may still carry a different kind of question.

  To keep the kinds apart: a which-option
  question names two or three options and asks which comes out ahead; a likely-outcomes question
  asks about one setting, with no other option named or implied; a what-setting question asks for
  the setting of one parameter at which an outcome reaches a target the question names or plainly
  implies, never for a choice between named options; a how-bad question asks for the most extreme outcomes at fixed settings, over a long
  stretch or many trials, never for a parameter's value; a can-it-happen question asks whether an
  outcome comes about under the model at all, never how often; a would-have-happened question is
  about a stretch of the past replayed with one thing changed.

  **Shapes**, each with its right kind (numbered as in the list above), how hard, the cases it
  carries, which its rubric `cases:` line lists, and the fillers it allows. The examples are
  illustrations of the shape, not bank items; a bank uses its own.
  - `possible-chance` (Medium; `can-happen`, `chance-in-it`; fillers 3, 4, 6): right kind 2. Asks,
    with a chance word, whether an outcome the rules don't aim at could come about under the model
    at all. "Is there any chance the truck sells out before 12:15 on a day when only the usual
    lunch crowd turns up?"
  - `possible-worst` (Hard; `can-happen`, `worst-case-mention`; fillers 1, 3, 4, 6): right kind 2.
    Names a worst case someone fears and asks whether it could come about under the model at all.
    "The worst case people keep raising is every bus on the route running half an hour late by
    noon. With this timetable, could that even occur?"
  - `threshold-ahead` (Hard; `target-setting`, `what-if-ahead`, `chance-in-it`; fillers 2, 5): right
    kind 4. Opens "What if" about a change someone is thinking of making, and asks, with a chance
    word, what setting of a parameter would make an outcome reach a target. "What if the school
    runs a flu-shot drive? How many students would need the shot for most outbreaks to die out
    within a week?"
  - `threshold-worst` (Hard; `target-setting`, `worst-case-mention`; fillers 1, 6): right kind 4.
    Names a worst case and asks what setting of a parameter would keep it from coming about, the
    target. "The worst case is patients still waiting when the clinic closes. How many nurses would
    the clinic need on shift for the last patient to be seen by closing time?"
  - `better-ahead` (Medium; `what-if-ahead`; fillers 2, 5): right kind 3. Opens "What if" about a
    choice among two or three named options still to be made, and asks which comes out ahead on an
    outcome. "What if the clinic hires a second nurse next month, or opens an hour earlier instead?
    Which would get patients seen sooner?"
  - `better-worst` (Hard; `worst-case-mention`, `chance-in-it`; fillers 2, 6): right kind 3. Names a
    worst case and asks which of two or three named options makes it rarer. "The worst case is the
    river flooding the school. Of the two plans, raising the wall or widening the channel, which
    makes that rarer?"
  - `likely-ahead` (Medium; `what-if-ahead`; fillers 2, 5): right kind 1. Opens "What if" about one
    change still to be made, and asks how often an outcome comes about under it, with no other
    option named or implied. "What if the league adds two teams next season? How often would the
    top team finish more than five points clear?"
  - `how-bad-chance` (Medium; `chance-in-it`; fillers 2, 3, 6): right kind 5. Asks, with a chance
    word, for the most extreme outcome at the current settings over a long stretch. The chance word
    marks rarity over that long stretch, never a typical or usual value of the extreme. "Over ten
    years, on the rarest worst days, how late does the last bus get?" It may say "worst", since it
    does ask how bad, so it carries no `worst-case-mention`.
  - `past-chance` (Medium; `chance-in-it`; fillers 2, 4, 5): right kind 6. Asks, with a chance word,
    about a stretch of the past replayed with one thing changed. "If the clinic had kept its old
    booking system last winter, how often would patients have waited more than an hour?"

  The fillers are the kinds a shape may offer beside its right kind and lures; the kinds left off a
  shape's list are ones its wording could make defensible (which option beside a one-change
  "What if", which option beside a count of nurses or students to reach a target), and are never offered with
  it. Outside `possible-worst`, `threshold-worst`, `better-worst` and `how-bad-chance`, no question
  mentions a worst case, a worst outcome or a disaster.

  **A scenario holds four questions** of four different shapes, in no fixed order, carrying at
  least three of the five cases between them. No question's text gives away another's answer.

  **Spread across the bank.** A bank is six scenarios, 24 questions. Every one of the nine shapes
  appears two or three times, `better-worst` at least as often as each of `possible-worst` and
  `threshold-worst`, so the right answers cover all six kinds and a mention of the worst case goes
  with three different right answers. No shape sits in the same slot in two scenarios in a row,
  and across the bank can-it-happen and target-setting questions each appear in every one of the
  four slots. When the generator is run live, the tutor picks each next shape to carry a case the
  learner hasn't passed.

  Credit: full for the right choice, whose number is the rubric's `answer`; none for any other.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works a different made-up question aloud: what would the answer to this person's question
  look like, a percentage at one setting, a yes or no, one of the options, a value for a setting,
  the most extreme result, or a different past? Then it names the kind that answer belongs to. It
  may point to Six kinds of question in `tasks/read-simulation.md`.
- **doesn't show:** the choices are given, four of the six, so a pass doesn't show the learner would
  think of the six kinds unprompted, as posing their own question for Problem Set 4 asks; a guess
  is right one time in four. Every model here is stochastic and every question asks one kind, so a
  pass says nothing about deterministic models or about a question that mixes two kinds. A shape's
  fillers are fixed, so for a few shapes the four choices offered are always the same four; a
  learner who works many questions could come to recognize a set of choices rather than read the
  question. `a-name-kind-unprompted` checks the same goal with no choices.
- **offer as:** the quick check, after session 16: one described simulation and four people's
  questions about it, one at a time, each answered by picking the kind from four choices. 1 to 2
  minutes a question. Easier than `a-name-kind-unprompted`, since the kinds are in front of you.
- **check note:** Two shapes can make their lure close to defensible, and these need a careful reading before a banked question is set or a live one is written. On `how-bad-chance`, a chance word such as "typical" or "usually" that frames the extreme itself ("in a typical year, how late on the worst day") turns the question toward likely outcomes; when writing live, put the chance word on rarity over a long stretch instead ("over ten years, on the rarest worst days"), and if a banked question reads the other way, a learner who picks What outcomes are likely and says why has a point, so record the ruling as `unclear` rather than a miss. On `possible-chance`, "is there any chance" is often heard as a request for a probability; when writing live, make plain that the ask is whether it ever happens at all, not how often.

### `a-name-kind-unprompted`

- **serves:** `c-name-question-kind`
- **supports:** attempt
- **checks:** `c-name-question-kind`
- **artifact:** no external source. A described simulation model and four people's questions for
  it, from this activity's bank or written live per the generator below. About 2 minutes a
  question.
- **learner does:** reads the scenario's setup and the one question served, and says in a sentence,
  in their own words and with no list of kinds in front of them, what kind of question that person
  is asking: what the answer to it would have to be.
- **tutor role:** examiner
- **tutor does:** as `a-classify-simulation-question`'s, including the offer to wait for session 16,
  and also: never lists, names or hints at the six kinds before the learner answers. Showing the
  list, or pointing to Six kinds of question in the reading, is help, and records the attempt as
  helped. Rules from the rubric's accepted phrasings; an answer in words the rubric doesn't list is
  ruled on what it says the answer would be.
- **done when:** as `a-classify-simulation-question`'s: the criterion met with no help, case by
  case, a full-credit answer passing every case its question carries.
- **generator:** as `a-classify-simulation-question`'s for the setup, the shapes with their right
  kinds, difficulty and cases, the chance-word rule, the rule against reading examples, the rules
  keeping the kinds apart and the key words a question avoids, except that there are no choices and
  no fillers. The question ends: "What kind of question is <name> asking? Say it in a sentence, in
  your own words." Its scenarios are its own, not shared with `a-classify-simulation-question`'s
  bank. A bank is four scenarios of four questions, 16 in all; every one of the nine shapes appears
  at least once, `possible-chance` or `possible-worst` three times or more, and `threshold-ahead`
  or `threshold-worst` three times or more. A question carries the same cases as its shape does
  in `a-classify-simulation-question`; with no choices, the lure is whatever its wording pulls
  toward. The rubric's key gives, for the right kind, the label and phrasings that count (for can it
  happen at all: "whether it's possible", "if it can ever occur"; for what setting reaches a
  target: "the setting that gets it there", "how many it would take to hit that"; for which option: "which plan wins";
  for likely outcomes: "how often, under that change"; for how bad: "the extreme", "the worst it
  gets"; for what would have happened: "a replay of last winter with the old system"), and the
  lure's phrasings that don't. Credit: full when the answer names the right kind, by its label or by
  saying what the answer would have to be; none when it names another kind, or names two without
  settling on the right one.
- **worked example:** as `a-classify-simulation-question`'s, except that it never shows the list of
  kinds: the tutor works a different question aloud by asking what its answer would look like.
- **doesn't show:** the question is posed for the learner, so a pass doesn't show they could pose
  one of their own of a given kind, which Problem Set 4 asks; it shows that they can name the kind
  of one they are handed, unprompted. Ruling on free wording is a judgment, and an answer that
  describes the answer loosely ("they want to know what happens") can sit between two kinds; the
  rubric's phrasings narrow this without removing it. The rest of
  `a-classify-simulation-question`'s `doesn't show` applies, except the parts about given choices.
- **offer as:** the harder check, after session 16: the same kind of question with no choices, so
  you have to come up with the kind yourself, as you will when you pose your own for Problem Set 4.
  About 2 minutes a question.
- **check note:** A correct answer to several shapes mentions a frequency: a replayed past ("how often would patients have waited"), a choice among options ("which makes it rarer"), a setting that reaches a target ("for most outbreaks to die out"). The rubric's phrasing for likely outcomes, "how often, under that change", must not catch these. Rule on what the learner says the answer is about: a different past is what would have happened, a pick among named options is which option is better, the value of one setting is what setting reaches a target, the extreme over a long stretch is how bad things can get. A frequency in the answer settles nothing by itself. Label a live run `a-name-kind-unprompted/<shape>`, not with the other activity's id.

### `a-contrast-question-pairs`

- **was:** a check on `c-name-question-kind`: two people's questions about the same simulation,
  worded almost alike, the first asking the kind the wording suggests and the second another kind,
  each answered by picking the kind from four choices.
- **status:** dropped (curator, 2026-10-19): the fixed layout let a learner rule out the lure on the
  second question without reading it, which is what its credited cases test, and a second
  pick-from-four candidate added no different type. `a-name-kind-unprompted` replaces it as the
  menu's second check.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
