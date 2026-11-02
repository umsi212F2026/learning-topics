# Activities: triggers

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

The initial study, the orientation and one passed question for each of the five words, comes to
about 25 minutes: about 11 for `a-read-triggers` (the reading is about 6 to 7 minutes on its own)
and about 3 a word. Both capabilities carry `taught elsewhere` (the session 19 class), so their
four activities are offered after that class, as practice and review. Meeting both capabilities
through the write-it checks takes six questions, one per case, at about 5 minutes each, so about 30
minutes; through the pick-one checks, about 2 minutes a question for `a-pick-trigger-defense` and
about 4 for `a-trace-the-waiting-work`, so about 18.

In this topic's banks and live questions, every workflow is a made-up one described in words:
never the learner's own app, repo, machine or project, never the reading's grading example or any
other homework or grading workflow. No question needs reading code, a command or a schedule
written in cron's notation: a schedule is always said in words ("every weekday at noon"). No
question names a real tool or service other than the ones the reading names (cron, launchd,
Git), and no operating system other than Mac and Linux, which the reading also names; a form, mailbox or website in a scenario is "the sign-up form", "the shop's
website", never a brand. Learner-facing text states the task, never the scoring.

## Check notes

2026-11-02. No bank exists yet for any of the four question activities, so every question is
written live from its generator; check each live scenario against the shape it claims before
serving it. Each capability has a write-it check and a quick check, and either can meet the goal
alone. The topic's depth asks the learner to make and defend each decision, which only the
write-it checks have them do, so where there is time, have at least one case of each capability
met through `a-argue-a-trigger` or `a-place-the-waiting-work`. Every scenario states the facts its
decision needs, so no check shows the learner would notice that a fact is missing and ask, which
planning their own Problem Set 5 workflow will require.

## Goals

| id                 | Goal | Criterion: what gets examined, and what counts |
| ------------------ | ---- | ---------------------------------------------- |
| `o-orientation`    | get the shape of this area before working on any particular part of it | `orientation` |
| `c-choose-trigger` | choose what triggers a workflow's runs, and defend the choice by its trade-offs | given a described workflow, says what should trigger its runs (a person, a schedule or an event) and compares that choice with the strongest alternative. Names one goal the choice helps and one it hurts, compared with that alternative, such as timeliness, people's effort or cost, and ties each to something about this workflow: how soon its result is needed, how often there is work to do, who would have to remember to start it, or whether the machine that does the work will be on when the trigger fires. A reason that doesn't refer to this workflow at all, such as "a schedule is automatic", does not meet it. Where the trigger is an event, also says whether the workflow notices it by checking repeatedly or by being told when it happens, and why that fits this workflow. Cases: `event`, `machine-off`, `not-event` |
| `c-when-to-queue`  | decide where a workflow's work waits until a worker can take it up | given a described workflow, says what its work queue is: a queue the workflow keeps, a source that already holds the waiting work, or a list worked out each time from the state of files. Says what triggers the worker that takes work from it, and what would go wrong in this workflow without it. Having no queue is right only when the worker is always available and never overloaded, or when dropping some work is acceptable, and saying so means naming which of those holds here. A verdict with no consequence tied to this workflow does not meet it. Cases: `worker-unavailable`, `spread-out`, `no-queue` |

## Coverage

| goal               | checks | notes |
| ------------------ | ------ | ----- |
| `o-orientation`    | `a-read-triggers` |       |
| `c-choose-trigger` | `a-argue-a-trigger`, `a-pick-trigger-defense` | No check holds the learner to the strongest alternative: `a-pick-trigger-defense` supplies it, and `a-argue-a-trigger` accepts any alternative its key doesn't count as plainly weak. In both, the `machine-off` alternative is a schedule that would never run, so the goal the choice hurts is measured against the runner's first wish rather than a workable rival. The `machine-off` case says "off or asleep", but every question says turned off, so nothing tests a machine that is asleep. |
| `c-when-to-queue`  | `a-place-the-waiting-work`, `a-trace-the-waiting-work` |       |

---

## Activities

### `a-read-triggers`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** a reading the course wrote for this topic, `tasks/read-triggers.md` in this folder,
  "What starts a workflow, and where its work waits" (about 1,300 words, about 6 to 7 minutes). No
  external reading is used: the instructor wanted a course-written one, a sequel to
  `workflow-steps-design-2026-10/tasks/read-workflow-design.md`. It continues that reading's
  made-up example, a teaching assistant who grades about 200 homework submissions a week, and adds
  two facts the earlier reading doesn't give: homework is due Friday at midnight, and most
  submissions arrive in the last few hours before that. Sections: an untitled opening (this is
  one more of the design decisions the last reading listed, plus where work waits); Three kinds of
  trigger (a person, a schedule, an event; trade-offs in timeliness, people's effort and the cost
  of runs that find nothing to do; which matters depends on facts about the workflow, with the
  TA's one Saturday-morning run as the worked case); Noticing an event (checking again and again,
  and being told through a hook, a webhook being the web kind, with Git's commit hook as an
  example); Schedules, and the laptop problem (cron jobs on Mac and Linux, launchd on a Mac, and a
  schedule or a hook on a laptop that is off or asleep not firing, with launchd's catch-up after
  sleep noted); Where the work waits (work queue in a loose sense, its three kinds, a queue worked
  out from a log, the worker's own trigger, a queue spreading out a burst); When there's no queue
  (the two situations where none is needed, and what is lost otherwise); Putting it to use. Words
  in place, each in bold where first used and each introduced through the TA's example rather
  than a definition (event-driven is attached to grading that begins the moment a student submits;
  work queue is named as where the waiting work is found, then shown through its three kinds):
  event-driven, polling, hook (with its synonym webhook, also bold), cron job, work queue. Also in bold, though
  none is a word of this topic: the three kinds of trigger, the three trade-offs, the two ways of
  noticing an event, the three kinds of queue, and the worker's own trigger. The reading names no
  real tool or service except cron, launchd and Git, all generically, and names Mac and Linux as
  operating systems. It says nothing about how state is
  stored, how failures are handled or what each part may touch, all later topics.
- **verified:** 2026-11-02
- **learner does:** reads the page once, top to bottom, and stops once, in Three kinds of trigger
  after the three trade-off bullets and before the paragraph beginning "Which matters most",
  answering before reading on ("I don't know yet" is an honest answer): which kind of trigger
  would you pick for the TA's grading, and what about the TA's workflow makes you think so? The
  next paragraph gives the page's own answer, which the learner then reads. Then the
  close, about 2 minutes, with the reading still beside them: answers the question the tutor
  puts: with this page beside you, could you now take a short description of a workflow and say
  what should start its runs and argue that choice against another; and say where its work should
  wait until something takes it up, or why it needn't wait?
- **tutor role:** explainer
- **tutor does:** puts the reading in front of the learner by opening the file
  `tasks/read-triggers.md` from the topic folder on the local filesystem, so the learner's agent
  shows it formatted in a sidebar; does not paste it into the chat. Stays quiet through the
  reading except at the stop and when asked. At the stop, takes the learner's answer first and
  replies with one near-miss question rather than a verdict, then lets the learner read on to the
  page's own answer. Any kind of trigger is a fine pick here; what the tutor looks for is a reason
  drawn from the TA's workflow as the opening describes it (the Friday-midnight deadline, most
  submissions arriving in the last few hours). The page's answer, one scheduled run on Saturday
  morning, rests on two facts: nobody needs feedback before the deadline, and nearly all the work
  arrives in one burst. An answer that gives only a reason true of any workflow ("a schedule is
  automatic", "events are faster") gets one near-miss question ("would a run every hour be better,
  then? What about this workflow says yes or no?"). Does not set or rehearse any word question from `a-words`: does
  not ask the learner to define any of the five words, to say what separates polling from a hook
  or event-driven from polling, or to correct a misused sentence. Does not set or rehearse a
  question from this topic's capability activities: does not ask the learner to choose a trigger or
  a queue for a new workflow beyond what the reading itself works through; if the learner asks how
  to do that, says that is what the session 19 class and the practice after it are for. Says that
  building a workflow is Problem Set 5's work, not this topic's; that how state is stored, how
  failures are handled, what each part may touch and where else a workflow could run come in later
  topics and are checked nowhere here; and that the launchd aside is there so a Mac user isn't
  surprised, and no question turns on it (every scenario with a machine that is off says it is
  turned off, not asleep). At the close, puts the readiness question as written above and
  rules on the answer.
- **done when:** criterion met. The bar for this goal is did it once and help is expected
  throughout, so the ruling is on the learner's answer to the readiness question, not on the stop
  or on whether the tutor thinks they are ready. A plain yes to both parts is `criterion: met`. A
  hedge on either part, with no plain no, is `criterion: unclear`: for the first part go over
  Three kinds of trigger and Noticing an event once more, for the second Where the work waits and
  When there's no queue, and put the question again. A second hedge stays `unclear`: the tutor says
  both decisions are taught in the session 19 class and offers this topic's practice activities
  after it. Before session 19, an answer that waits on the class ("not until we've done it in
  class") is a hedge, not a no: it is `criterion: unclear` with no rereading, the tutor says the
  class teaches both decisions, and puts the question again at the learner's first study after it.
  A plain no to either part is `criterion: not met`: record it, ask what is missing, and offer to go
  back over the section that bears on it; don't put the question again in the same sitting. This
  goal isn't required, so a no never blocks anything else the learner wants to try.
- **worked example:** n/a
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. It
  shows nothing about the five words, which have their own supply in `a-words`, and nothing about
  either capability: the reading works one example of each decision, the readiness question asks
  only whether the learner thinks they could do the same, and the stop is helped, ungraded and
  answered just before the page gives its own answer. The reading is one course-written page built on one made-up grading
  workflow, so it shows nothing of a workflow in a different domain, or of the case worked in the
  session 19 class.
- **offer as:** this topic's orientation: one short page the course wrote, the sequel to the last
  topic's reading and following the same grading workflow, from what can start a run, through how
  an event is noticed and what a laptop that is off does to a schedule, to where the work waits and when
  it needn't. One short stop and a one-question close. About 11 minutes.

### `a-argue-a-trigger`

- **serves:** `c-choose-trigger`
- **supports:** attempt
- **checks:** `c-choose-trigger`
- **artifact:** no external source. A described workflow whose trigger is left open, told in a
  short paragraph, from this activity's bank or written live per the generator below. About 5
  minutes a question.
- **verified:** 2026-11-02
- **learner does:** reads the scenario and its one question; says what should start the
  workflow's runs, compares that with the strongest other option, names one goal the choice helps
  and one it hurts, saying what about the workflow makes it so, and, if the choice is an event,
  says whether the workflow should notice it by checking repeatedly or by being told, and why.
- **tutor role:** examiner
- **tutor does:** choosing a trigger is taught in the session 19 class (`taught elsewhere`), and
  this is practice for after it: before session 19 the tutor says so and offers to wait, and goes
  ahead if the learner wants. Sets the question as served, without rewording it or hinting; never
  names the cases, which fact matters, which trigger the key expects or that a reason must avoid
  being generic. Gives help whenever it is asked for, and records the attempt as helped. When the
  generator is run live, writes the key and the case into the record before showing the question.
  Labels the attempt with the question's path, or `a-argue-a-trigger/<shape>` when run live, and
  records the case with `--cases`. Rules on the reasons, not on the choice: any trigger defended by
  reasons tied to the workflow passes, within the credit rules below.
- **done when:** the criterion met with no help, case by case: a full-credit answer passes the case
  its question carries.
- **generator:** **A scenario** is one made-up workflow that someone runs, told in one paragraph of
  running prose, seven to ten sentences, in the voice of the person who runs it. It says what the
  workflow is for and what does its work, in plain words (a program, an AI agent, or a person
  named by role), and on which machine; nothing is described with code, a command, a file format
  or a query. It never says what starts the runs. Mixed through the paragraph, in no fixed order and
  never under labels, are these facts:
  - how the work arrives: how much, and how evenly (steady through the day, in one burst, a few at
    unpredictable times, rarely);
  - how soon a result is needed after the work arrives (within minutes, by the next morning, by
    the end of the month, whenever the person gets to it);
  - who would have to remember to start a run, and how reliable they are about it;
  - when the machine that does the work is on (always, being an office computer that is never
    turned off; during the working day; a laptop its owner turns off, not just closes, overnight;
    a machine that is off is always said to be turned off, never closed, asleep or shut);
  - what an empty run costs (a program glancing at a folder, or an agent reading every message
    again to find that nothing is new);
  - where the work comes from, and whether that source can tell the workflow when something
    arrives ("the sign-up form can send a message to a web address each time someone signs up")
    or can only be looked at ("the shared mailbox has no way to announce new mail; it can only be
    checked").
  Plus one irrelevant detail, said as plainly as the facts and bearing on no goal (how long the
  workflow has run, what the form's heading says, which day the team meets). The facts are stated
  plainly, never as a hint, and never using the words trigger, schedule, event, polling, hook,
  cron or queue.

  **A question** reads: "What should start this workflow's runs: a person, a schedule or an event?
  Compare your choice with the strongest other option: name one goal your choice helps and one it
  hurts, and say what about this workflow makes it so. If you choose an event, also say whether the
  workflow should notice it by checking repeatedly or by being told, and why." Free response,
  `type: free`. One question per scenario.

  **Shapes**, each with the case it carries, which its rubric `cases:` line lists. In every shape
  the facts give the natural choice one goal it helps and one it hurts against the strongest
  alternative, each traceable to a fact, and give the alternative the same, so a learner who picks
  the alternative can also pass, except in `event-best`: that shape's case is about how an event is
  noticed, so a non-event choice there can earn at most half (see Credit). The examples are illustrations, not bank items, and their domains
  (a dentist's office, a running club) are used by no bank in this topic.
  - `event-best` (`event`): a result is needed within minutes or an hour; work arrives a few times
    a day at unpredictable times, so most scheduled runs would be empty, and an empty run is costly
    (an agent rereads everything); the machine is always on. Natural choice an event; strongest
    alternative a schedule frequent enough to be timely. Helped: timeliness, tied to how soon the
    result is needed, or the cost of empty runs, tied to how rarely work comes. Hurt: people's
    effort at set-up, tied to what the source needs done to tell the workflow, or the cost of a
    burst, tied to a fact that work sometimes comes many at once (each starting its own run). Two
    variants, which the key names: `told`, where the source can send word when something arrives,
    so being told fits (quicker, and no empty looks); and `poll`, where it can only be looked at,
    so checking repeatedly is the only way, at an interval tied to how soon the result is needed.
    In a `poll` scenario the facts make the difference from a schedule concrete: a look is cheap
    (a program checks whether anything new has come in, which takes a moment and costs nothing),
    while a run is costly (the agent reads the whole mailbox or every record). So the event
    noticed by checking repeatedly means many cheap looks that start the costly agent only when
    something is new, against the strongest alternative, a schedule that runs the agent itself as
    often, paying the full cost every time. The key states that difference in those terms. A
    `poll` scenario also carries one fact that gives the event choice its hurt goal against that
    schedule: people's effort at set-up, because a separate checking program has to be set up
    beside the agent, and the scenario says who would have to do that and that it is a bother for
    them ("anything beyond the agent itself means asking my nephew, who helps once a month"). The
    key names that hurt goal and its sentence.
    "New patients fill in a form on the office's website, a few a day, and the dentist wants the
    agent's summary of each patient's history waiting before the patient arrives, often within the
    hour. The website can send a message to a web address each time a form comes in."
  - `machine-off` (`machine-off`): the work is done on the runner's own laptop, which the runner
    turns off (shuts down, not just closes) at known times (overnight, or all weekend), and the
    time a run would most naturally be wanted falls in that gap, said in the runner's own words
    ("I'd like it done overnight"). Work accumulates through the day and a result is needed by a
    set time (first thing in the morning). Natural choice a schedule at a time the laptop is
    reliably on, or the runner starting it when they turn the laptop on; strongest alternative the
    schedule the runner first thought of, inside the gap. Helped: correctness or timeliness, tied
    to the run actually happening because the laptop is on then. Hurt: timeliness, tied to the result now arriving later than first wanted, or
    people's effort, tied to the runner having to remember. "Each evening the club's agent turns
    the day's run logs into a leaderboard. The captain turns her laptop off at about 11 p.m. and
    back on at 7 a.m., and she'd like it done overnight so it's ready when members check at
    breakfast."
  - `person-or-schedule` (`not-event`): two variants, which the key names. `schedule`: work
    accumulates steadily, a result is needed by a set time and not before, the machine is always
    on or always on at that time, and reacting to each item one at a time would mean many runs
    where one would do; natural choice a schedule, strongest alternative an event (or a person,
    where the key says so). `person`: runs are rare and irregular, and the person has to be there
    anyway (to supply the input or look over the result straight away); natural choice a person,
    strongest alternative a schedule, which would mostly run before there is anything to do or
    when nobody is there to look. Helped and hurt goals tied to those facts: for a schedule,
    people's effort (nobody has to remember) and the cost of many runs, against timeliness for
    work that waits until the set time; for a person, the cost of empty runs and the result
    being looked at straight away, against people's effort and the run not happening when they
    forget.

  **How hard.** Medium when the facts favor the natural choice clearly. Hard when the strongest
  alternative is nearly as good (a run once an hour against an event, with a result needed within
  two hours), so both are defensible; the key then treats both as natural choices, each with its
  own helped and hurt goals. The question's wording is unchanged.

  **Spread across the bank.** A bank is six scenarios, six questions: each shape twice, one of
  each pair Hard; `event-best` once `told` and once `poll`; `person-or-schedule` once `schedule` and
  once `person`. When the generator is run live, the tutor picks each next shape to carry a case
  the learner hasn't passed.

  **Domains** vary by scenario, none repeating within the bank: a dog daycare's photo updates to
  owners, a food pantry's weekly inventory count, a hardware store's low-stock alerts, a
  bed-and-breakfast's booking confirmations, a city council member's constituent emails, a road
  race's finish-time results, a family's monthly budget summary, a robotics team's sponsor
  thank-you notes. No domain from the other three question activities' lists, and no homework or
  grading workflow.

  **The key** gives the natural choice (two in a Hard question) and the strongest alternative; for
  each, the goal it helps and the goal it hurts against the other, and the sentence carrying each
  fact; any option the key counts as plainly weak (a person for work arriving a hundred times a
  day); for `event-best`, the noticing method the facts favor and why, and for a `poll` scenario
  the cheap-look, costly-run difference from a schedule; for `machine-off`, which times the laptop
  is on; the irrelevant detail; and two or three generic reasons that would fail
  ("a schedule is automatic", "events are faster", "polling wastes resources", "a person can make
  sure it's done right").

  Credit: full when the answer chooses a trigger, compares it with a strongest alternative, and
  names a goal the choice helps and a goal it hurts compared with that alternative, each with a
  reason tied to a fact about this workflow. A strongest alternative is the key's, or in a Hard
  question the other natural choice; an alternative outside the key that the key doesn't count as
  plainly weak also counts, and its helped and hurt goals are judged on the same terms, each
  needing a reason tied to a fact in this scenario. The choice itself may likewise be outside the
  key, except in `event-best` (below). A reason is tied when it refers to this workflow ("the
  summaries are needed within the hour", "the captain's laptop is off overnight"); one resting on
  the irrelevant detail is not, and neither is one the scenario's facts contradict.
  An intermediate goal from the last topic's reading counts on the same terms as a final goal.
  Also, in an `event-best` question, the answer says whether to check repeatedly or be told, with
  a reason tied to this workflow (whether the source can send word, how soon the result is needed,
  what each look costs); choosing to be told when the source can only be looked at fails that part.
  An answer is ruled on the design it describes, not the name it gives it: cheap repeated looks
  that start the costly run only when something is new ("a schedule every ten minutes that checks
  for anything new and starts the agent only then") are the event choice noticed by checking
  repeatedly, whatever the answer calls them, and are judged as that. An `event-best` answer that
  chooses a person, or a schedule that runs the whole workflow each time, gets at most half,
  however well tied its reasons, and does not pass `event`: the case asks how the event would be noticed, which a
  non-event answer never says. After the ruling the tutor may ask the learner how the workflow
  would notice the event if one started it, as help. In a `machine-off` question, at least one of
  the two reasons rests on whether the laptop is on when the trigger fires; a trigger that would
  fire while the laptop is off, from an answer that doesn't notice that, gets at most half. An
  answer that relies on a missed run being caught up when the laptop wakes (as the reading says
  launchd does after sleep) rests on a fact the scenario contradicts, since the laptop is turned
  off, not asleep: that reason is not tied, and the tutor says so after the ruling. Half when one
  of the two goal reasons is tied and the other is generic or missing; when both are tied but the alternative is missing or one the key
  counts as plainly weak; or, in an `event-best` question, when everything else is there but the
  noticing part is missing or untied. None when neither reason is tied, or no trigger is chosen.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works the illustration of the same shape as the question aloud, from the facts to the
  choice: says which facts bear on timeliness, on people's effort and on the cost of empty runs,
  picks the strongest alternative and says why it is the strongest, names the goal helped and the
  goal hurt with the fact behind each, and, for `event-best`, says whether the source can send word.
  Then shows a generic version ("a schedule is automatic") and says why it doesn't refer to this
  workflow at all. It may point to Three kinds of trigger, Noticing an event, and Schedules, and
  the laptop problem in `tasks/read-triggers.md`.
- **doesn't show:** the workflow's facts are all in one short paragraph with one irrelevant detail
  beside them, so a pass shows the learner can pick what matters out of a loose description, but
  not that they would notice a fact they need is missing and ask, as their own Problem Set 5
  workflow would make them. The `machine-off` shape always puts the work on the runner's own laptop,
  so it shows nothing about choosing a different machine, which is a later topic. An `event-best`
  question passes only an event choice, so it doesn't show the learner would defend a non-event
  choice there well. Ruling on whether
  a reason is tied is a judgment; the key's generic reasons narrow it without removing it.
- **offer as:** the write-it-yourself check, after session 19: a short description of a workflow,
  and you say what should start it and argue the choice. About 5 minutes a question. Harder than
  `a-pick-trigger-defense`, since you choose, find the facts and write the argument yourself.
- **check note:** Four things the rubric leaves to you. First, Credit accepts any alternative the
  key doesn't count as plainly weak, so a pass does not show the learner found the strongest one.
  If their alternative is clearly not the strongest, say so after the ruling, as help. Second, How
  hard's example of a Hard question (a run once an hour against an event) is an `event-best`
  question, but Credit caps any non-event choice there at half. When writing a Hard `event-best`
  question, keep the event the only natural choice and make it hard through the facts instead, for
  example a `poll` scenario whose checking interval has to be close to how soon the result is
  needed. Third, in a `machine-off` question the key's strongest alternative is a schedule while
  the laptop is turned off, which never runs. A goal the choice "hurts" against it, such as a later
  result, is hurt only against what the runner first wanted. Accept that comparison as the key
  does. If the learner instead compares with a workable alternative (starting it by hand when the
  laptop is turned on, or a run just before it is turned off that misses the last of the day's
  work), judge it on the same terms: it is the stronger answer. Fourth, outside `event-best` the
  Credit doesn't ask how a chosen event would be noticed. If a learner chooses an event there and
  doesn't say, ask after the ruling, as help, and don't withhold credit for it.

### `a-pick-trigger-defense`

- **serves:** `c-choose-trigger`
- **supports:** attempt
- **checks:** `c-choose-trigger`
- **artifact:** no external source. A described workflow, its facts set out one to a sentence, and
  two people's defenses of the same trigger for it, from this activity's bank or written live per
  the generator below. About 2 minutes a question.
- **verified:** 2026-11-02
- **learner does:** reads the scenario and the one question served, two defenses of the same
  choice of trigger, and picks the sound one.
- **tutor role:** examiner
- **tutor does:** as `a-argue-a-trigger`'s, including the offer to wait for session 19, except that
  it labels a live run `a-pick-trigger-defense/<shape>` and rules from the rubric's `answer`. Never
  says which clause differs between the two defenses before the learner has chosen.
- **done when:** the criterion met with no help, case by case. Each question gets one ruling: the
  sound defense passes the case the question carries, and the other passes none. There is no half
  credit.
- **generator:** **A scenario** uses the same three shapes, variants and facts as
  `a-argue-a-trigger`, except in one respect: the facts are not running prose. After one or two
  sentences saying what the workflow is for and what does its work, a short paragraph headed "About
  this workflow:" gives its facts, one sentence each, then one sentence that would be true whatever
  started the runs (how long each run takes, or who reads the result), and nothing else, so the
  learner can check a defense's clause against exactly what the paragraph says. No irrelevant
  detail beyond that sentence.

  **A question** reads: "<Name1> and <Name2> both think this workflow's runs should be started by
  <choice> rather than <alternative>. Here is how each puts it." Then two defenses, each a paragraph
  starting with a bold label, "**Defense 1, <Name1>'s:**" and "**Defense 2, <Name2>'s:**", each in
  the same frame: "<Choice> rather than <alternative> helps <goal>, because ... It hurts <goal>,
  because ...". In an `event-best` question each defense adds a third sentence: "It should notice
  each <item> by <checking every N minutes / being told by the <source>>, because ...". Both choose
  the shape's natural choice over its strongest alternative, name the same two goals (except in a
  `machine-off` question, below) and, in an `event-best` question, the same noticing method. Then "Which defense is sound?" with the choices
  "1. <Name1>'s" and "2. <Name2>'s", `type: mcq`. In the sound defense every because-clause points
  at a fact in the paragraph and draws from it the direction the fact supports. The near-miss is
  identical except for one because-clause, faulty in one of three ways:
  - Medium, `generic`: the clause refers to nothing about this workflow ("because a schedule runs
    on its own", "because being told is always faster"), the kind of reason the criterion names as
    not meeting it.
  - Medium, `does-not-support`: the clause rests on a fact in the paragraph, one no other clause of
    either defense uses (except where the shape rules below say otherwise), but draws from it a
    conclusion it doesn't support, either the opposite
    direction or a goal the fact doesn't bear on ("helps timeliness, because the results are read
    by the coach", a fact about who reads the result).
  - Hard, `not-a-difference`: the clause rests on the sentence that would be true whatever started
    the runs, which bears on the goal but would hold just as much under the alternative, so it is no
    help or cost of the choice compared with it ("hurts timeliness, because each run takes twenty
    minutes", when a scheduled run would take twenty minutes too).
  The two defenses are within ten words of each other in length, and the differing clause matches
  the one it replaces in form: one fact or claim, said as concretely, with no hedge or intensifier
  ("might", "always", "clearly") the other lacks, except that a `generic` clause may say "always"
  when the sound one it replaces carries a fact of similar length. Which defense is longer varies.

  **Which clause differs, and how**, by shape. Each shape's two questions are fixed, so the fault
  rules and the spread below agree:
  - `machine-off`, both questions `does-not-support`, and in both the near-miss rests on the fact
    that the laptop is turned off when the alternative would fire, unlike the general rule above.
    Every clause, sound or faulty, states only its fact, with no added "so ..." explanation. The two
    questions differ in which clause differs and how it goes wrong, so the second is not a repeat
    of the first:
    - First question, the helped clause. Sound: "A noon run rather than one at 2 a.m. helps
      correctness, because the laptop is turned off at 2 a.m." Near-miss, the one place where the
      two defenses name different goals, drawing its goal from the reading's trade-offs: "helps
      keep down runs that find nothing to do, because the laptop is turned off at 2 a.m." The key
      says why only the sound clause holds: a noon run and a 2 a.m. run would each find the same
      day's work, so the laptop being off bears on whether the run happens at all, not on whether
      it finds anything to do.
    - Second question, the hurt clause, with the two defenses naming the same goals. Both say "A
      7:15 a.m. run rather than one at 2 a.m. helps correctness, because the laptop is turned on at
      7 a.m." Sound hurt clause: "It hurts timeliness, because members check the board from 6
      a.m." Near-miss: "It hurts timeliness, because the laptop is turned off at 2 a.m." The
      paragraph gives "turned off at 11 p.m." and "turned back on at 7 a.m." as separate sentences.
      The key says why only the sound clause holds: the laptop being off at 2 a.m. is what stops
      the alternative from running at all, so it makes the 7:15 run sooner than the alternative's
      result, not later, and is no cost of the choice.
    So the pick turns on what the machine being off actually affects.
  - `event-best`, one `told` question and one `poll` question, and in both the differing clause is
    the noticing clause, so `event` is never passed with noticing untested. Both defenses name the
    same noticing method. In the `told` question the fault is `generic` ("by being told by the
    sign-up form, because being told is always faster", against the sound "because each summary is
    needed within the hour and the form can send word the moment one comes in"). In the `poll`
    question the fault is `does-not-support`, of a kind particular to polling: the near-miss checks
    at an interval that the fact about how soon the result is needed rules out, and gives that fact
    as its reason ("by checking every three hours, because each reply is wanted within the hour",
    against the sound "by checking every ten minutes, because each reply is wanted within the
    hour"). The two then differ in the interval as well as the clause.
  - `person-or-schedule`, both questions `not-a-difference`: the helped clause in one, the hurt
    clause in the other.

  **Spread across the bank.** A bank is six scenarios, six questions: each shape twice, made up as
  above, so three `does-not-support` questions (two `machine-off`, one `poll`), one `generic`
  (`told`) and two `not-a-difference` (`person-or-schedule`); the sound defense first in three.
  Names vary and are never reused within a scenario.

  **Domains** are this activity's own, none repeating within the bank: a florist's delivery route
  sheet, a youth soccer club's field-closure notices, a bookstore's preorder arrivals, a carpool's
  weekly driving schedule, a yoga studio's class waitlists, a museum's lost-and-found listings, a
  quilting guild's meeting minutes, a car wash's daily sales summary. No domain from the other three
  question activities' lists, and no homework or grading workflow.

  Credit: full for the sound defense, whose position is the rubric's `answer`; none for the other.
- **worked example:** shown only as help when asked for, which records the attempt as helped. As
  `a-argue-a-trigger`'s, then the tutor sets the tied defense of the same illustration beside one
  version of it with a faulty clause, says which fact each clause rests on, and says why the changed
  one doesn't support its goal or would hold just as much for the alternative.
- **doesn't show:** the choice, the alternative, the goals and the noticing method are given, and
  the learner picks between two defenses, so a pass doesn't show they would choose a trigger, find
  the strongest alternative or find the workflow's facts on their own; with two choices a guess is
  right half the time. Every defense argues for the natural choice, so a pass says nothing about
  defending a less obvious one. The facts are laid out one to a sentence under a heading, so a pass
  doesn't show the learner would find them in a looser description; `a-argue-a-trigger` gives them
  as running prose and has the learner write the argument.
- **offer as:** the quick check, after session 19: a short workflow and two people's defenses of the
  same trigger for it, and you pick the one whose reasons actually hold up. About 2 minutes a
  question. Easier than `a-argue-a-trigger`, since the arguments are written for you.
- **check note:** A pass here leaves most of this goal untested. The trigger, the alternative, the
  two goals and, in `event-best`, the noticing method are all given, and the learner only judges
  whose reasons hold. Where the learner has time, have at least one case met through
  `a-argue-a-trigger`. In the second `machine-off` question, the sound hurt clause (a 7:15 a.m. run
  hurts timeliness because members check from 6 a.m.) is weighed against a 2 a.m. run that would
  never happen with the laptop turned off, which is the reasoning the key uses to reject the
  near-miss. If a learner says neither hurt clause holds for that reason, don't count a miss; serve
  another question. When writing a `told` question live, keep "always" out of the generic clause:
  it is the only intensifier the rules allow, so it would mark the faulty defense by its wording
  alone.

### `a-place-the-waiting-work`

- **serves:** `c-when-to-queue`
- **supports:** attempt
- **checks:** `c-when-to-queue`
- **artifact:** no external source. A described workflow, told in a short paragraph, that says how
  its work arrives and when its worker is available but not where the work waits, from this
  activity's bank or written live per the generator below. About 5 minutes a question.
- **verified:** 2026-11-02
- **learner does:** reads the scenario and its one question; says where the work should wait until
  the worker takes it up and what should start the worker, and what would go wrong in this workflow
  without that; or says the work needn't wait anywhere and why that is safe here.
- **tutor role:** examiner
- **tutor does:** deciding where work waits is taught in the session 19 class (`taught elsewhere`),
  and this is practice for after it: before session 19 the tutor says so and offers to wait, and
  goes ahead if the learner wants. Sets the question as served, without rewording it or hinting;
  never names the cases, the three kinds of queue or the two situations where none is needed. Gives
  help whenever it is asked for, and records the attempt as helped. When the generator is run live,
  writes the key and the case into the record before showing the question. Labels the attempt with
  the question's path, or `a-place-the-waiting-work/<shape>` when run live, and records the case
  with `--cases`.
- **done when:** the criterion met with no help, case by case: a full-credit answer passes the case
  its question carries.
- **generator:** **A scenario** is one made-up workflow, told in one paragraph of running prose,
  seven to ten sentences, in the voice of the person who runs it. It names the worker, what takes
  up each piece of work, in plain words (a program, an AI agent, or a person named by role), and
  says what the workflow is for; nothing is described with code, a command, a file format or a
  query. It never says where the work waits or what starts the worker. Mixed through the paragraph,
  in no fixed order and never under labels, are these facts:
  - where the work comes from and how it arrives: how many, how evenly, at what hours;
  - when the worker is available (a laptop turned on only during the working day, and turned off,
    not just closed, the rest of the time; a person who works
    through these on Friday afternoons; an office computer that is never turned off), and how fast
    it can go (an agent's provider takes only so many requests a minute; a person can do about
    twenty in a sitting; a program handles each in a second);
  - what the source keeps, if anything (the form service keeps every response with its time; an
    alert appears once and is gone);
  - what the workflow already leaves behind for each finished piece of work, if anything (a reply
    file saved beside each request; a line in a log naming each order shipped);
  - whether losing an occasional piece of work matters, said through what the work is for (a
    display that each new reading replaces, or a request somebody is waiting on).
  Plus one irrelevant detail, said as plainly as the facts and bearing on no goal. The facts never
  use the words queue, waiting list, backlog, poll, hook, cron or trigger.

  **A question** reads: "Where should this workflow's work wait until <worker> takes it up, and
  what should start <worker>? What would go wrong in this workflow without that? If you think the
  work needn't wait anywhere, say why that is safe here, and still say what should start
  <worker>." Free response, `type: free`. One question per scenario.

  **Shapes**, each with the case it carries. The examples are illustrations, not bank items, and
  their domains (a bike repair shop, a neighborhood tool library) are used by no bank in this
  topic.
  **Kinds of queue, and the facts that make each the natural one.** Each `unavailable` or `burst`
  scenario has one natural kind, and its facts rule the others out as the simplest:
  - `source`: the source keeps every item and can list them by when they came in, so the new ones
    since the last run can be found; the workflow leaves nothing behind for a finished item (a
    reply is emailed and no copy kept), so neither files nor a log could say what is done.
  - `files`: each item lands somewhere that holds it but cannot say which items are finished or
    new (each request saved into a shared folder, with nothing marking which are done), and the
    workflow saves a file beside each finished item, so an item with no such file is waiting.
    The source cannot say which are finished, so it alone is not enough.
  - `log`: as `files`, except that the workflow writes a line to a log for each finished item, so
    the waiting work is every held item not in the log.
  - `kept`: the source keeps nothing (an alert shown once and gone), and the worker's machine is
    never off, so a program on it can add each item to a list of its own as it arrives. A kept
    list needs something on to receive each arrival, so `kept` is used only in `burst`, where the
    worker is never off, never in `unavailable`.
  The key names both facts behind the natural kind: where the items are held, and what (if
  anything) says which are done.

  - `unavailable` (`worker-unavailable`): work arrives at any hour, including when the worker is
    off (the laptop turned off overnight, the person away until Friday), and the worker keeps up
    with any arrivals when it is on. What goes wrong without a queue: work arriving while the
    worker is off is never done. The natural kind is `source`, `files` or `log`, never `kept`.
    "Repair requests come in through the shop's website at all hours, and the website keeps every
    request with the time it came in, so it can list everything since any given morning. Each
    morning when Ana turns her laptop on, the agent emails a reply to each new request; no copy of
    the reply is kept." (Here only the source fits: nothing is left behind per request, and nothing
    is on overnight to add requests to a list.)
  - `burst` (`spread-out`): work arrives in a burst faster than the worker should take it (three
    hundred sign-ups in the hour after a newsletter goes out, against a provider that takes about
    twenty requests a minute, or a volunteer who can handle about twenty in a sitting), and the
    worker is never off. What goes wrong without a queue: the burst hits the worker all at once,
    past what it can take. The natural kind is any of the four. Starting the worker once for each arriving
    item undoes the spreading, since three hundred arrivals then start three hundred runs at once,
    so the key names a per-item start as ruled out by the worker's limit, unless the answer says
    the worker takes waiting items one at a time (a single run that works through the queue at
    its own pace, started by an arrival when it isn't already running).
  - `no-queue` (`no-queue`): two variants, which the key names. `always-ready`: a quick program on
    a machine that is never off, with a few items an hour, each taking a second, so nothing ever
    has to wait. `drop-ok`: losing an occasional item does no harm, because the next one replaces
    it (a display showing the latest reading, a count that each update corrects). The key: no
    queue is needed, which condition holds and the fact that makes it hold, and what starts the
    worker: each item's arrival, and in `drop-ok` also a schedule that takes only the latest item,
    unless the scenario says the result must change the moment an item arrives, in which case the
    key says that fact rules a schedule out.

  **How hard.** Medium when the natural kind of queue is `source` or `kept`, or the `no-queue`
  variant is `always-ready`. Hard when it is `files` or `log`, where the learner must notice that
  something the workflow already leaves behind tells what is still waiting, or the variant is
  `drop-ok`, where the work looks as if it matters until the replacing is noticed. The question's
  wording is unchanged.

  **Spread across the bank.** A bank is six scenarios, six questions: each shape twice. The two
  `unavailable` scenarios use `source` and `files`; the two `burst` scenarios use `kept` and `log`.
  So each shape has one Hard question (`files`, `log`, `drop-ok`). `no-queue` once in each variant.
  When the generator is run live, the tutor picks each next shape to carry a case the learner
  hasn't passed, and never sets `kept` in `unavailable`.

  **Domains** vary by scenario, none repeating within the bank: a wedding photographer's client
  photo picks, a school newspaper's reader letters, a repair cafe's sign-ups, a food truck's
  catering inquiries, a scout troop's permission slips, an apartment building's package notices, a
  volunteer translators' group's requests, a bird count's sighting reports. No domain from the other
  three question activities' lists, and no homework or grading workflow.

  **The key** gives the shape and the natural kind of queue, named concretely for this workflow
  ("the website's list of requests"), any other kind the facts make workable, what should start
  the worker and which facts allow it, the consequence without a queue and the sentence it rests
  on, and, for `no-queue`, which condition holds and why the other doesn't; plus the irrelevant
  detail.

  Credit: in an `unavailable` or `burst` question, full when the answer does all three: names where
  the work waits, as something concrete in this workflow that the facts make workable (the key's
  natural kind or another it lists; in a `burst` question a list the workflow keeps is workable
  though not always needed, since the worker's machine is never off and can take in each arrival;
  in an `unavailable` question it is not, unless the answer says what stays on to add each item
  as it arrives, which the scenario never supplies, so such an answer has invented a machine and
  earns no credit for this part); says what starts the worker, a person, a schedule or an event, that the facts don't rule
  out (not a schedule set for when the laptop is off, and, in a `burst` question, not a start for
  each arriving item unless the worker takes the waiting items one at a time, as the `burst` shape
  says); and names what would go wrong without the
  queue, tied to this workflow (requests arriving overnight never get a reply; three hundred
  sign-ups at once overrun the provider's limit). Half when two of the three are there, or when the
  consequence is generic ("work might get lost"). None when fewer than two are there, or when the
  answer says no queue is needed. In a `no-queue` question, full when the answer does all three:
  says the work needn't wait; names the condition that holds and ties it to the fact that makes it
  hold (the program is on a machine that's never off and takes a second for each of a few an hour;
  each reading replaces the last); and says what starts the worker. In `always-ready` that is each
  item's arrival (a schedule or a person would leave items waiting, which is a queue after all).
  In `drop-ok` it is each item's arrival, or a schedule that takes only the latest item and drops
  the ones between, when the answer ties that to each item replacing the last, unless the scenario
  says the result must change the moment an item arrives. Half
  when two of the three are there, including the case where the condition is named but tied to
  nothing about this workflow; or when it proposes a queue while correctly saying that one of the
  two conditions holds here. None when it proposes a queue and names a loss the facts rule out, or
  says nothing about why waiting is or isn't needed.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works the illustration of the same shape aloud: says when work arrives and when the worker
  is available, what already holds or leaves behind a record of the waiting work, which kind of
  queue that gives, what starts the worker, and what would be lost without it. For `no-queue` it
  works a made-up case of its own (a program on an office computer that is never off, turning each
  of a few emails an hour into a line on a sign-in sheet). It may point to Where the work waits and
  When there's no queue in `tasks/read-triggers.md`.
- **doesn't show:** the workflow's facts are all in one short paragraph, so a pass doesn't show the
  learner would notice a fact they need is missing. Any workable kind of queue earns credit, so a
  pass doesn't show the learner would pick the simplest one, and in a `burst` question a list the
  workflow keeps passes even where something already holds the work. Each scenario carries one reason for a queue, so a
  pass shows nothing about weighing two at once. Nothing here asks how the queue is stored or what
  happens when the worker fails partway, which are later topics.
- **offer as:** the write-it-yourself check, after session 19: a short description of a workflow,
  and you say where its work should wait, what starts the worker, and what goes wrong without it,
  or why nothing needs to wait. About 5 minutes a question. Harder than `a-trace-the-waiting-work`,
  since nothing is laid out for you to choose from.
- **check note:** The `unavailable` illustration ("Each morning when Ana turns her laptop on, the
  agent emails a reply") says what starts the worker, which the generator forbids. When writing
  live, say only when the laptop is on. The `burst` shape needs a worker that is never off but
  lists a volunteer's pace among its examples. In a `burst` scenario, make the worker a program or
  an agent on a machine that is never off.

### `a-trace-the-waiting-work`

- **serves:** `c-when-to-queue`
- **supports:** attempt
- **checks:** `c-when-to-queue`
- **artifact:** no external source. A described workflow whose design is left open, as in
  `a-place-the-waiting-work`, and one three-part multiple-choice question asking how it should be
  designed, from this activity's bank or written live per the generator below. About 4 minutes a
  question.
- **verified:** 2026-11-02
- **learner does:** reads the scenario, then answers three parts, each by picking one of four
  choices: where the worker should find the work still to be done, what should start the worker,
  and which statement about the workflow is true.
- **tutor role:** examiner
- **tutor does:** as `a-place-the-waiting-work`'s, including the offer to wait for session 19,
  except that it labels a live run `a-trace-the-waiting-work/<shape>` and the multiple-choice parts
  are settled from the rubric. Never says which part was wrong before all three are answered.
- **done when:** the criterion met with no help, case by case. The question is one attempt, met
  only when all three parts are right; it then passes the case it carries. There is no half credit.
- **generator:** **A scenario** is written as in `a-place-the-waiting-work`: one made-up workflow in
  running prose, in the voice of the person who runs it, giving the same kinds of fact (how the work
  arrives, when the worker is available and how fast it can go, what the source keeps, what the
  workflow already leaves behind for each finished item, whether losing an occasional item
  matters, and how soon a result is needed), plus one irrelevant detail. Like that activity's, it
  never says where the work waits or what starts the worker; those are what the question asks.
  Nothing is described with code, a command, a file format or a query, and the words queue,
  waiting list, backlog, poll, hook, cron and trigger never appear; a log may be called a log. A
  machine that is off is said to be turned off, never closed or asleep. Because each part has one
  key, the facts are chosen so that exactly one choice in each part fits, as below.

  **A question** is a compound, `type: compound`, with one goal, `c-when-to-queue`, and the case
  its shape carries. Its stem reads "Three questions about how this workflow should be set up." All
  three parts are `type: mcq`, each with four choices, in an order that varies:
  - `#### a`: "What is the simplest way for <worker> to find the work still to be done, without
    losing any work that matters here?" The four choices are always the same four, put in this
    workflow's terms: a list the workflow keeps, adding each <item> as it arrives; asking <the
    source> for the <items> that came in since the last run; working it out from which held
    <items> have no <file> yet, or which aren't in the log yet; nothing, because each <item> can go
    straight to <worker> as it arrives. The facts make exactly one the answer, using the fact
    patterns under "Kinds of queue" in `a-place-the-waiting-work`: for the source, the source keeps
    every item and can list them by when they came in, and the workflow leaves nothing behind per
    item; for files or a log, each item lands somewhere that holds it but can't say which are new
    or finished, so asking the source can't find the waiting ones, and the workflow leaves a file
    or a log line per finished item; for a kept list, the source keeps nothing and leaves nothing
    behind, and the worker's machine is never off to take in each arrival, so a kept list is the
    answer only in a `burst` question; for nothing, a `no-queue` condition holds, which makes every
    list unneeded and so not the simplest. The key names both facts behind the answer: where the
    items are held, and what (if anything) says which are done.
  - `#### b`: "What should start <worker>?" Four choices, exactly one of which the facts allow.
    The ruled-out choices are drawn from: a schedule, said in words, at a time the scenario says
    the worker is off; a schedule at a time too late for when the scenario says the result is
    needed; <the person> starting it by hand, where the scenario says that person is often away or
    forgets; a schedule that comes round less often than the work needs.
    - In an `unavailable` or `burst` question the answer is a schedule, said in words, at a time
      the worker is on and soon enough for the result. The other three are each new <item>
      arriving, ruled out because the worker is off when items arrive or, in a `burst` question,
      because three hundred arrivals would start three hundred runs at once; and two from the
      list above.
    - In a `no-queue` question the answer is each new <item> arriving, since any of the others
      would leave items waiting; the other three come from the list above. A `drop-ok` scenario
      here always says the result must change the moment an item arrives (the display should show
      each reading as it comes in), so a schedule that takes only the latest item is plainly wrong
      on that fact, and none of the three distractors is a sound design.
  - `#### c`: "Which of these is true of this workflow?" Four statements, put in this workflow's
    terms and worded the same way in every shape: if nothing held the waiting <items>, any that
    arrived while <worker> is <unavailable> would never be handled; if nothing held the waiting
    <items>, a burst of them would reach <worker> faster than <its limit>; nothing needs to wait,
    because <worker> is always available and never overloaded; nothing needs to wait, because
    losing an occasional <item> does no harm here. Exactly one is true by the facts, and it is the
    shape's case.

  **Shapes**, each carrying one case, which its rubric `cases:` line lists:
  - `unavailable` (`worker-unavailable`): work arrives while the worker is off, and the worker can
    keep up with any arrivals when it is on; part (c)'s answer is the first statement.
  - `burst` (`spread-out`): work arrives in a burst past what the worker can take, and the worker
    is never off; part (c)'s answer is the second.
  - `no-queue` (`no-queue`): part (a)'s answer is "nothing", part (b)'s is each item's arrival, and
    part (c)'s is the third or the fourth statement, by variant (`always-ready` or `drop-ok`, as in
    `a-place-the-waiting-work`), the facts ruling out the other one (a `drop-ok` worker is
    sometimes off or slow; an `always-ready` workflow's items each matter).

  **How hard.** Medium by default. Hard when part (a)'s answer is files or a log, where the learner
  must notice that something the workflow already leaves behind tells what is still waiting, or
  when the `no-queue` variant is `drop-ok`, where the work looks as if it matters until the
  replacing is noticed. The question's wording is unchanged.

  **Spread across the bank.** A bank is six scenarios, six questions: each shape twice;
  `no-queue` once in each variant; the two `unavailable` scenarios have part (a)'s answer the
  source and files, the two `burst` scenarios a kept list and a log (files and log share one
  choice, so that choice is the answer twice); three questions Hard, the files, log and `drop-ok`
  ones. A kept list is never the answer in an `unavailable` question, live or banked.
  No part's answer sits in the same position in more than two of the six questions.

  **Domains** are this activity's own, none repeating within the bank: a makerspace's 3D-print
  requests, a community radio station's song requests, a school weather station's readings display,
  a thrift store's donation pickups, a neighborhood watch's tip line, a little league's rain-delay
  texts, a language exchange's partner matching, a parking garage's open-space sign. No domain
  from the other three question activities' lists, and no homework or grading workflow.

  Each part's rubric gives its `answer` (the 1-based choice) and, in a `tutor note`, the sentence
  of the scenario that settles it and the fact that rules out each other choice.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor takes the illustration in `a-place-the-waiting-work` of the same shape, sets the three parts
  for it in this activity's style, and answers them aloud, saying for each which fact settles it
  and why the nearest wrong choice is wrong. It may point to Where the work waits and When there's
  no queue in `tasks/read-triggers.md`.
- **doesn't show:** the learner chooses among four designs in each part rather than proposing one,
  so a pass doesn't show they would come up with the queue, the worker's trigger or the
  consequence on their own, or say why; `a-place-the-waiting-work` checks that. Each part's facts
  are chosen so one choice fits, so a pass doesn't show the learner could weigh two workable
  designs. With all three parts needed a guess rarely passes, but the four kinds in part (a) and
  the four statements in part (c) are the same in every question, so they become familiar with
  repetition.
- **offer as:** the quick check, after session 19: a short description of a workflow, and three
  multiple-choice parts on where its work should wait, what should start the worker, and why it
  matters. About 4 minutes a question. Easier than `a-place-the-waiting-work`, since the choices
  are in front of you.
- **check note:** Part (b)'s answer is always a schedule in an `unavailable` or `burst` question
  and always each item's arrival in a `no-queue` one, and part (c)'s four statements name the
  shape's case. After a few questions, part (b) follows from part (c), so a later pass is thinner
  than an early one. Keep the worker a program or an agent in this activity's scenarios: when the
  worker is a person, a schedule that starts them makes an odd key for part (b). For a `burst`
  scenario, the machine that worker runs on must never be off.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
