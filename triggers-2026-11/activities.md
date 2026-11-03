# Activities: triggers

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

The initial study, the orientation and one passed question for each of the five words, comes to
about 25 minutes: about 11 for `a-read-triggers` (the reading is about 6 to 7 minutes on its own)
and about 3 a word. All three capabilities carry `taught elsewhere` (the session 19 class), so
their six activities are offered after that class, as practice and review. Meeting all three
through the write-it checks takes eight questions, one per case: three for `a-argue-a-trigger` and
two for `a-argue-noticing` at about 3 minutes each, and three for `a-place-the-waiting-work` at
about 4, so about 27 minutes. Through the pick-one checks it is about 2 minutes a question for
`a-pick-trigger-defense` and `a-pick-noticing` and about 3 for `a-trace-the-waiting-work`, so
about 19.

Every question asks for one thing, and every question works on its own as a bank question, never
relying on a tutor's follow-up to collect the rest of an answer. A free-response question's fixed
text always says how to answer ("Answer in two or three sentences.").

In this topic's banks and live questions, every workflow is a made-up one described in words:
never the learner's own app, repo, machine or project, never the reading's grading example (nor
its TA who approves feedback and is away for a weekend) or any other homework or grading workflow.
Banks need not avoid the domain the session 19 class works in, but every scenario stands alone: it
states every fact its answer needs, so a learner who missed the class can answer it. No question needs reading code, a command or a schedule
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
| `c-choose-trigger` | choose what triggers a workflow's runs, and say why | given a described workflow, says what should trigger its runs (a person, a schedule or an event) and why, with a reason tied to something about this workflow that makes the choice fit better than the other kinds: how soon its result is needed, how often there is work to do, who would have to remember to start it, or whether the machine or person that does the work will be available when the trigger fires. A reason that doesn't refer to this workflow at all, such as "a schedule is automatic", does not meet it. Cases: `event`, `unavailable`, `not-event` |
| `c-choose-noticing` | decide how an event-driven workflow finds out that its event happened | given a workflow started by an event, says whether it should notice the event by polling or through a hook, and why, with a reason tied to this workflow: whether the source offers a hook, how soon the result is needed, what each check costs, and who would have to set up receiving the message. A reason that doesn't refer to this workflow at all does not meet it. Cases: `hook`, `poll` |
| `c-when-to-queue`  | decide where a workflow's work waits until a worker can take it up | given a described workflow, says where its work should wait until a worker can take it up (a queue the workflow keeps, a source that already holds the waiting work, a list worked out each time from the state of files, or nowhere) and why, with a reason tied to this workflow: what would go wrong here without it, or, for nowhere, whether the worker is always available and never overloaded or dropping some work is acceptable. A reason with no consequence tied to this workflow does not meet it. Cases: `worker-unavailable`, `spread-out`, `no-queue` |

## Coverage

| goal               | checks | notes |
| ------------------ | ------ | ----- |
| `o-orientation`    | `a-read-triggers` |       |
| `c-choose-trigger` | `a-argue-a-trigger`, `a-pick-trigger-defense` |       |
| `c-choose-noticing` | `a-argue-noticing`, `a-pick-noticing` |       |
| `c-when-to-queue`  | `a-place-the-waiting-work`, `a-trace-the-waiting-work` |       |

---

## Activities

### `a-read-triggers`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** a reading the course wrote for this topic, `tasks/read-triggers.md` in this folder,
  "What starts a workflow, and where its work waits" (about 1,400 words, about 6 to 7 minutes). No
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
  sleep noted; then a person who is unavailable, the TA who must approve each student's feedback
  being away the weekend the run fires, so the feedback sits unsent); Where the work waits (work queue in a loose sense, its three kinds, a queue worked
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
- **verified:** 2026-11-03
- **learner does:** reads the page once, top to bottom, and stops once, in Three kinds of trigger
  after the three trade-off bullets and before the paragraph beginning "Which matters most",
  answering before reading on ("I don't know yet" is an honest answer): which kind of trigger
  would you pick for the TA's grading, and what about the TA's workflow makes you think so? The
  next paragraph gives the page's own answer, which the learner then reads. Then the
  close, about 2 minutes, with the reading still beside them: answers the one question the tutor
  puts: with this page beside you, could you now take a short description of a workflow and make
  the three decisions this page covers, saying why for each: what should start its runs, how it
  should find out that its event happened, and where its work should wait?
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
  question from this topic's capability activities: does not ask the learner to choose a trigger, a
  way of noticing an event or a place for work to wait for a new workflow beyond what the reading itself works through; if the learner asks how
  to do that, says that is what the session 19 class and the practice after it are for. Says that
  building a workflow is Problem Set 5's work, not this topic's; that how state is stored, how
  failures are handled, what each part may touch and where else a workflow could run come in later
  topics and are checked nowhere here; and that the launchd aside is there so a Mac user isn't
  surprised, and no question turns on it (every scenario with a machine that is off says it is
  turned off, not asleep). At the close, puts the readiness question as written above and
  rules on the answer.
- **done when:** criterion met. The bar for this goal is did it once and help is expected
  throughout, so the ruling is on the learner's answer to the readiness question, not on the stop
  or on whether the tutor thinks they are ready. A plain yes is `criterion: met`. A hedge, with no
  plain no, is `criterion: unclear`: ask which decision feels shaky, go over its section once more
  (Three kinds of trigger, Noticing an event, or Where the work waits and When there's no queue),
  and put the question again. A second hedge stays `unclear`: the tutor says all three decisions
  are taught in the session 19 class and offers this topic's practice activities after it. Before
  session 19, an answer that waits on the class ("not until we've done it in class") is a hedge,
  not a no: it is `criterion: unclear` with no rereading, the tutor says the class teaches all
  three decisions, and puts the question again at the learner's first study after it. A plain no is
  `criterion: not met`: record it, ask what is missing, and offer to go
  back over the section that bears on it; don't put the question again in the same sitting. This
  goal isn't required, so a no never blocks anything else the learner wants to try.
- **worked example:** n/a
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. It
  shows nothing about the five words, which have their own supply in `a-words`, and nothing about
  any capability: the reading works one example of each decision, the readiness question asks
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
  short paragraph, from this activity's bank or written live per the generator below. About 3
  minutes a question.
- **learner does:** reads the scenario and its one question; says in two or three sentences what
  should start the workflow's runs, and why.
- **tutor role:** examiner
- **tutor does:** choosing a trigger is taught in the session 19 class (`taught elsewhere`), and
  this is practice for after it: before session 19 the tutor says so and offers to wait, and goes
  ahead if the learner wants. Sets the question as served, without rewording it or hinting; never
  names the cases, which fact matters, which trigger the key expects or that a reason must avoid
  being generic. Gives help whenever it is asked for, and records the attempt as helped. When the
  generator is run live, writes the key and the case into the record before showing the question.
  Labels the attempt with the question's path, or `a-argue-a-trigger/<shape>` when run live, and
  records the case with `--cases`. Rules from the question alone, by the credit rules below; no
  follow-up question collects part of the answer.
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
    a machine that is off is always said to be turned off, never closed, asleep or shut), and,
    where a person does a step (approving, signing off, adding something by hand), when that
    person is there and when they are away;
  - what an empty run costs (a program glancing at a folder, or an agent reading every message
    again to find that nothing is new);
  - where the work comes from. How an event would be noticed is `a-argue-noticing`'s question,
    not this one's, so the scenario need not say whether the source can send word.
  Plus one irrelevant detail, said as plainly as the facts and bearing on no goal (how long the
  workflow has run, what the form's heading says, which day the team meets). The facts are stated
  plainly, never as a hint, and never using the words trigger, schedule, event, polling, hook,
  cron or queue.

  **A question** reads: "What should start this workflow's runs: a person, a schedule or an event?
  Say why. Answer in two or three sentences." Free response, `type: free`. One question per
  scenario, asking only this.

  **Shapes**, each with the case it carries, which its rubric `cases:` line lists. In every shape
  the facts make one kind of trigger fit better than the other two, and the key names the fact or
  facts that show it; in a Hard question two kinds fit about equally and the key accepts both.
  Every choice the key accepts is a workable design, one that would actually run and produce a
  result; a design that would never run (a schedule set for when the machine is turned off) is
  never accepted. The examples are illustrations, not bank items, and their domains (a dentist's
  office, a running club, a community choir) are used by no bank in this topic.
  - `event-best` (`event`): a result is needed within minutes or an hour; work arrives a few times
    a day at unpredictable times, so most runs on a schedule frequent enough to be timely would
    find nothing, and a run is costly (an agent rereads everything); the machine is always on.
    Natural choice an event. The deciding facts: how soon the result is needed (a person or a
    slow schedule would be too late) and how rarely and unpredictably the work comes (a frequent
    schedule would mostly run for nothing). "New patients fill in a form on the office's website,
    a few a day at no set times, and the dentist wants the agent's summary of each patient's
    history waiting before the patient arrives, often within the hour. Each summary run has the
    agent reread the whole patient file."
  - `unavailable` (`unavailable`): the machine that does the work, or a person who does a step,
    is unavailable at known times, and the facts bear on whether each option would find them
    available when it fires. Two variants, which the key names:
    - `machine-off`: the work is done on the runner's own laptop, which the runner turns off
      (shuts down, not just closes) at known times, never said to be asleep. When it is turned
      back on varies (most mornings at 7, some not until 9 or later). Work accumulates through the
      day and a result is needed by a set time. The two workable options are a schedule at a time
      the laptop is usually on and the runner starting it by hand when they turn the laptop on;
      which is natural depends on the facts (how irregular the on-time is against how reliable
      the runner is at remembering). For the hand start, the deciding fact is the late mornings:
      a schedule that fires while the laptop is still off simply doesn't run that day. For the
      schedule, it is a runner who forgets, against a laptop that is reliably on by the set time.
      "Each evening the club's agent turns the day's run logs
      into a leaderboard. The captain turns her laptop off at about 11 p.m.; most mornings she
      turns it on at 7, but on her early shifts not until noon. Members check the board at
      breakfast, and she admits she forgets small chores."
    - `person-away`: a person must do a step of each run (approve, sign off, add something by
      hand) and is away at known times (weekends, every other Friday), and the input changes
      while they are away, so a result made before they leave is stale by the time they act on it.
      The workable options are a schedule timed for just before the person is back, the person
      starting it themselves when they return, and a schedule before they leave; the key names
      which it accepts. The deciding fact is that the input changes while the person is away, so a
      run made before they leave is stale when they act on it; between the first two, whether the
      person reliably remembers decides. Never the
      reading's example of a TA approving feedback, or any approval of student work. "A community
      choir's agent drafts each week's seating chart from who has said they'll attend, and the
      director approves it before it goes out. She is away from Friday evening to Monday morning,
      and singers keep changing their answers all weekend."
  - `person-or-schedule` (`not-event`): two variants, which the key names. `schedule`: work
    accumulates steadily, a result is needed by a set time and not before, the machine is always
    on or always on at that time, and reacting to each item one at a time would mean many runs
    where one would do; natural choice a schedule, the deciding facts being the set time and the
    steady flow (an event would start many runs where one would do, and a person would have to
    remember). `person`: runs are rare and irregular, and the person has to be there anyway (to
    supply the input or look over the result straight away); natural choice a person, the
    deciding facts being the irregular need and the person's presence (a schedule would mostly run
    before there is anything to do or when nobody is there to look).

  **How hard.** Medium when the facts favor the natural choice clearly. Hard, in `unavailable` and
  `person-or-schedule`, when a second kind is nearly as good (in `machine-off`, a laptop that is
  late coming on only now and then, against a runner who sometimes forgets), so both are
  defensible; the key then accepts both, each with its deciding fact. In `event-best` the event
  stays the only natural choice; a Hard `event-best` question is hard through its facts instead:
  work that comes often enough that a frequent schedule looks tempting, with the cost of each run
  the fact that tips it. The question's wording is unchanged.

  **Spread across the bank.** A bank is six scenarios, six questions: each shape twice, one of
  each pair Hard; `unavailable` once `machine-off` and once `person-away`; `person-or-schedule` once
  `schedule` and once `person`. When the generator is run live, the tutor picks each next shape to carry a case
  the learner hasn't passed.

  **Domains** vary by scenario, none repeating within the bank: a dog daycare's photo updates to
  owners, a food pantry's weekly inventory count, a hardware store's low-stock alerts, a
  bed-and-breakfast's booking confirmations, a city council member's constituent emails, a road
  race's finish-time results, a family's monthly budget summary, a robotics team's sponsor
  thank-you notes. No domain from the other five question activities' lists, and no homework or
  grading workflow.

  **The key** gives the choice it accepts (two in a Hard question), the deciding fact or facts and
  the sentence carrying each, why each other kind fits worse and the fact that shows it, any
  choice it never accepts (one that would fire while the machine is turned off or the person away
  and so produce nothing, or a stale result); the irrelevant detail; and two or three generic
  reasons that would fail ("a schedule is automatic", "events are faster", "a person can make
  sure it's done right").

  Credit: full when the answer chooses a trigger the key accepts and gives a reason tied to a fact
  about this workflow that makes that choice fit better than the other kinds. One tied reason is
  enough; the answer need not compare with every other kind, and a reason that also names what the
  choice costs ("it means remembering each morning, but the laptop is often off at 7:15") still
  earns full credit. A reason is tied when it refers to this workflow ("the summaries are needed
  within the hour", "the captain's laptop is off until noon on early-shift days"); one resting on
  the irrelevant detail is not, and neither is one the scenario's facts contradict. An answer is
  ruled on the design it describes, not the name it gives it: cheap repeated looks that start the
  costly run only when something is new ("a schedule every ten minutes that checks for anything
  new and starts the agent only then") are an event choice, whatever the answer calls them. In an
  `unavailable` question the accepted choices are those that account for when the machine is on or
  the person there, and the reason must rest on that; an answer that relies on a missed run being
  caught up when the laptop wakes (as the reading says launchd does after sleep) rests on a fact
  the scenario contradicts, since the laptop is turned off, not asleep, so that reason is not
  tied. Half when the choice is one the key doesn't accept but the reason is tied to a real fact
  of this workflow (the learner read the scenario but drew the wrong verdict), or when the choice
  is accepted but the reason is generic or missing. None when the choice is not accepted and the
  reason is generic or missing, or no trigger is chosen.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works the illustration of the same shape as the question aloud, from the facts to the
  choice: says which facts bear on how soon the result is needed, how often there is work, who
  would have to remember and whether the machine or person will be available, says which kind
  those facts favor and why the other two fit worse. Then shows a generic version ("a schedule is
  automatic") and says why it doesn't refer to this workflow at all. It may point to Three kinds of trigger, Noticing an event, and Schedules, and
  the laptop problem in `tasks/read-triggers.md`.
- **doesn't show:** the workflow's facts are all in one short paragraph with one irrelevant detail
  beside them, so a pass shows the learner can pick what matters out of a loose description, but
  not that they would notice a fact they need is missing and ask, as their own Problem Set 5
  workflow would make them. The `machine-off` variant always puts the work on the runner's own
  laptop, so it shows nothing about choosing a different machine, which is a later topic, and
  every machine that is off is turned off, so nothing tests one that is only asleep. One tied
  reason earns full credit, so a pass doesn't show the learner weighed every kind against the
  others. How an event is noticed is not asked here; `a-argue-noticing` asks it. Ruling on whether
  a reason is tied is a judgment; the key's generic reasons narrow it without removing it.
- **offer as:** the write-it-yourself check, after session 19: a short description of a workflow,
  and you say what should start it and why. About 3 minutes a question. Harder than
  `a-pick-trigger-defense`, since you choose, find the facts and write the reason yourself.

### `a-pick-trigger-defense`

- **serves:** `c-choose-trigger`
- **supports:** attempt
- **checks:** `c-choose-trigger`
- **artifact:** no external source. A described workflow, its facts set out one to a sentence, and
  two people's defenses of the same trigger for it, from this activity's bank or written live per
  the generator below. About 2 minutes a question.
- **verified:** 2026-11-02
- **learner does:** reads the scenario and the one question served, two one-sentence defenses of
  the same choice of trigger, and picks the one whose reason is sound.
- **tutor role:** examiner
- **tutor does:** as `a-argue-a-trigger`'s, including the offer to wait for session 19, except that
  it labels a live run `a-pick-trigger-defense/<shape>` and rules from the rubric's `answer`. Never
  says which reason is faulty before the learner has chosen.
- **done when:** the criterion met with no help, case by case. Each question gets one ruling: the
  sound defense passes the case the question carries, and the other passes none. There is no half
  credit.
- **generator:** **A scenario** uses the same three shapes, variants and facts as
  `a-argue-a-trigger`, except in two respects: it adds one fact that bears on something other
  than when runs should start (who reads the result, what form it takes), for a `does-not-support`
  near-miss to use, and the facts are not running prose. After one or two
  sentences saying what the workflow is for and what does its work, a short paragraph headed "About
  this workflow:" gives its facts, one sentence each, then one sentence that would be true whatever
  started the runs (how long each run takes), and nothing else, so the
  learner can check a defense's clause against exactly what the paragraph says. No irrelevant
  detail beyond that sentence.

  **A question** reads: "<Name1> and <Name2> both think this workflow's runs should be started by
  <choice>. Here is the reason each gives." Then two defenses, each one sentence starting with a
  bold label, "**Defense 1, <Name1>'s:**" and "**Defense 2, <Name2>'s:**", in the same frame:
  "<Choice> fits this workflow best, because <reason>." Then "Which defense gives a sound reason?"
  with the choices "1. <Name1>'s" and "2. <Name2>'s", `type: mcq`. Both choose the shape's natural
  choice. Each reason is one fact from the paragraph, stated as the paragraph states it, with no
  added "so ..." explanation, no hedge and no intensifier ("might", "always", "clearly"). The two
  defenses differ only in their reason, and the two sentences are within ten words of each other
  in length. Which is longer varies. The sound defense's reason is a fact that makes the choice fit
  better than the other kinds. The near-miss's reason is also a fact from the paragraph, so it is
  never generic: both reasons refer to this workflow, and the pick turns only on whether the fact
  bears on the choice. Its fault is one of two kinds:
  - Medium, `does-not-support`: the fact bears on something other than when the run should start,
    such as who reads the result or what form it takes, or points toward a different kind of
    trigger ("because the summaries are read on the dentist's tablet").
  - Hard, `not-a-difference`: the fact bears on when runs could happen but holds just as much for
    the other kinds, so it doesn't make this choice fit better (the neutral sentence, "because
    each run takes the agent about twenty minutes", or an availability fact that holds for every
    option alike).

  **Which reason differs, and how**, by shape. Each shape's two questions are fixed, so the fault
  rules and the spread below agree. The examples obey the form rule above.
  - `unavailable`, one `machine-off` question and one `person-away` question, as in
    `a-argue-a-trigger`, with workable choices only. In both, the near-miss rests on an
    availability fact, so the pick turns on what the machine being off, or the person being away,
    actually affects.
    - `machine-off`, `not-a-difference`. The paragraph gives "The laptop is turned off at 11
      p.m.", "Most mornings it is turned on at 7, but on early-shift days not until noon" and "She
      sometimes forgets small chores." Both: "Starting it by hand when she turns the laptop on fits
      this workflow best, because ..." Sound (9 words): "on early-shift days the laptop isn't on
      until noon." Near-miss (9 words): "the laptop is turned off every night at 11." The key says
      why only the sound reason holds: every option runs after the laptop comes on in the morning,
      so its being off from 11 p.m. separates nothing; only the late mornings, when a 7:15
      schedule would fire while the laptop is still off and simply not run, make the hand start fit
      better.
    - `person-away`, `does-not-support`. The paragraph gives "The director approves the chart
      before it goes out", "She is away from Friday evening to Monday morning", "Singers keep
      changing their answers all weekend" and "She prints the approved chart for the folders."
      Both: "Her starting it on Monday morning fits this workflow best, because ..." Sound (7
      words): "singers keep changing their answers all weekend." Near-miss (8 words): "she prints
      the approved chart for the folders." The key says why only the sound reason holds: printing
      happens whenever the chart is made, so it has no bearing on when to start; the weekend
      changes make a Friday run stale by Monday.
  - `event-best`: one `does-not-support` and one `not-a-difference`. For example, sound (12
    words): "forms come in only a few a day, at no set times"; near-miss `does-not-support` (8
    words): "the dentist reads each summary on her tablet"; near-miss `not-a-difference` (8
    words), the neutral sentence: "each summary takes the agent about two minutes".
  - `person-or-schedule`: one `does-not-support` and one `not-a-difference`.

  **Spread across the bank.** A bank is six scenarios, six questions: each shape twice, made up as
  above, so three `does-not-support` and three `not-a-difference`; the sound defense first in
  three. Names vary and are never reused within a scenario.

  **Domains** are this activity's own, none repeating within the bank: a florist's delivery route
  sheet, a youth soccer club's field-closure notices, a bookstore's preorder arrivals, a carpool's
  weekly driving schedule, a yoga studio's class waitlists, a museum's lost-and-found listings, a
  quilting guild's meeting minutes, a car wash's daily sales summary. No domain from the other five
  question activities' lists, and no homework or grading workflow.

  Credit: full for the sound defense, whose position is the rubric's `answer`; none for the other.
- **worked example:** shown only as help when asked for, which records the attempt as helped. As
  `a-argue-a-trigger`'s, then the tutor sets the sound defense of the same illustration beside one
  with a faulty reason, says which fact each rests on, and says why the changed one has no bearing
  on when to start, or would hold just as much for another kind of trigger.
- **doesn't show:** the choice is given and the learner picks between two reasons, so a pass
  doesn't show they would choose a trigger or find the workflow's facts on their own; with two
  choices a guess is right half the time. Every defense argues for the natural choice, so a pass
  says nothing about defending a less obvious one. Both reasons refer to this workflow, so a pass
  doesn't show the learner would reject a reason that refers to nothing about it. The facts are laid out one to a sentence under a heading, so a pass
  doesn't show the learner would find them in a looser description; `a-argue-a-trigger` gives them
  as running prose and has the learner write the argument.
- **offer as:** the quick check, after session 19: a short workflow and two people's defenses of the
  same trigger for it, and you pick the one whose reasons actually hold up. About 2 minutes a
  question. Easier than `a-argue-a-trigger`, since the arguments are written for you.
- **check note:** A pass here leaves most of this goal untested. Where the learner has time, have
  at least one case met through `a-argue-a-trigger`.

### `a-argue-noticing`

- **serves:** `c-choose-noticing`
- **supports:** attempt
- **checks:** `c-choose-noticing`
- **artifact:** no external source. A described workflow that is started by an event, told in a
  short paragraph, with how it finds out about each event left open, from this activity's bank or
  written live per the generator below. About 3 minutes a question.
- **learner does:** reads the scenario and its one question; says in two or three sentences
  whether the workflow should find out about each new item by checking again and again or by
  being told each time, and why.
- **tutor role:** examiner
- **tutor does:** as `a-argue-a-trigger`'s (the offer to wait for session 19, setting the question
  as served, help on request recorded as helped, the key and case written before a live question,
  ruling from the question alone), except that it labels a live run `a-argue-noticing/<shape>`.
  Never names the cases or which fact matters.
- **done when:** the criterion met with no help, case by case: a full-credit answer passes the case
  its question carries.
- **generator:** **A scenario** is one made-up workflow, told in one paragraph of running prose,
  six to nine sentences, in the voice of the person who runs it. It says plainly that each new
  item should be handled soon after it arrives, so the workflow is started by an event; the
  question is only how it finds out. It says what does the work, in plain words, and on which
  machine; nothing is described with code, a command, a file format or a query. Mixed through the
  paragraph, in no fixed order and never under labels, are these facts:
  - where the items come from, and whether that source can tell the workflow when one arrives,
    said in plain words ("the sign-up form can send a message to a web address each time someone
    signs up") or that it can only be looked at ("the shared mailbox has no way to announce new
    mail; it can only be checked"), never with the words hook, webhook, polling or callback;
  - how soon a result is needed after an item arrives (within a minute, within the hour, by the
    end of the day);
  - what each check would cost: a quick look by a program that takes a moment and costs nothing,
    or a look that means the agent reading everything again;
  - who would have to set up receiving the source's message, and whether that is easy for them or
    a bother ("anything beyond the agent itself means asking my nephew, who helps once a month");
  - that the machine doing the work is never turned off (an office computer), so a message sent
    to it would be received; this topic never sets a noticing question on a machine that is off.
  Plus one irrelevant detail, said as plainly as the facts and bearing on neither method. The facts
  are stated as facts, never as what they mean for the choice.

  **A question** reads: "Should this workflow find out about each new <item> by checking for new
  ones again and again, or by being told each time one arrives? Say why. Answer in two or three
  sentences." Free response, `type: free`. One question per scenario, asking only this.

  **Shapes**, each with the case it carries. The examples are illustrations, not bank items, and
  their domains (a dentist's office, a tenants' association) are used by no bank in this topic.
  - `hook-best` (`hook`): the source can send a message each time; the result is needed soon (a
    minute or a few), so checking would have to be very frequent; receiving the message is easy to
    set up for whoever must do it. Deciding facts: the source can send word, and how soon the
    result is needed (or what frequent checks would cost). "New patients fill in a form on the
    office's website, and the dentist wants each summary within a few minutes. The website can send
    a message to a web address each time a form comes in, and the office's computer person sets
    that kind of thing up in an afternoon."
  - `poll-best` (`poll`): two variants, which the key names. `no-word`: the source can only be
    looked at, so checking again and again is the only way; the result can wait long enough that
    checking every so often is fine, and each look is cheap. `costly-setup`: the source can send
    a message, but receiving it means setting something up that the person who would have to do it
    finds a bother or can't get to soon, while each look is cheap and the result can wait (within
    the hour), so a cheap check every ten minutes serves. "Repair requests arrive in the
    association's shared mailbox, a few a day, and a reply within the day is fine. The mailbox can
    only be checked; a quick look by a program takes a moment."

  **How hard.** Medium when one deciding fact settles it (the source can't send word; the result
  is needed within a minute). Hard when the facts pull both ways: in `costly-setup`, a source that
  can send word but a set-up nobody can do soon; in a Hard `hook-best`, a set-up that is some
  bother but a result needed so soon that checking would have to be constant. The question's
  wording is unchanged.

  **Spread across the bank.** A bank is four scenarios, four questions: `hook-best` twice, one Hard;
  `poll-best` twice, once `no-word` (Medium) and once `costly-setup` (Hard). When the generator is
  run live, the tutor picks each next shape to carry a case the learner hasn't passed.

  **Domains** vary by scenario, none repeating within the bank: a vet clinic's appointment
  requests, a farm stand's preorders, a theater's volunteer usher sign-ups, a housing co-op's
  maintenance reports, a youth band's rehearsal absences, a bakery's wholesale orders. No domain
  from the other five question activities' lists, and no homework or grading workflow.

  **The key** gives the method it accepts (both, in a Hard question where the facts truly balance,
  each with its deciding fact), the deciding fact or facts and the sentence carrying each, why the
  other method fits worse, the irrelevant detail, and two or three generic reasons that would fail
  ("being told is faster", "checking wastes resources", "it's simpler to just check").

  Credit: full when the answer chooses a method the key accepts and gives a reason tied to a fact
  about this workflow (whether the source can send word, how soon the result is needed, what each
  check costs, who would set up receiving the message). One tied reason is enough. An answer is
  ruled on the design it describes: "a program looks every ten minutes" is checking again and
  again, whatever it is called. Half when the method is one the key doesn't accept but the reason
  is tied to a real fact of this workflow, or the method is accepted but the reason is generic or
  missing. None when the answer chooses being told for a source the scenario says can only be
  looked at, when the method is not accepted and the reason is generic, or no method is chosen.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works the illustration of the same shape aloud: says whether the source can send word,
  how soon the result is needed, what a check costs and who would set up receiving the message,
  then which method those facts favor and why. Then shows a generic version ("being told is
  faster") and says why it doesn't refer to this workflow. It may point to Noticing an event in
  `tasks/read-triggers.md`.
- **doesn't show:** every scenario's machine is always on, so a pass shows nothing about a
  message arriving at a machine that is off, which the reading mentions. One tied reason earns
  full credit, so a pass doesn't show the learner weighed every fact. How often to check, once
  checking is chosen, is not asked.
- **offer as:** the write-it-yourself check, after session 19: a workflow that reacts to each new
  item, and you say whether it should keep checking for new ones or be told, and why. About 3
  minutes a question. Harder than `a-pick-noticing`, since you choose and write the reason
  yourself.

### `a-pick-noticing`

- **serves:** `c-choose-noticing`
- **supports:** attempt
- **checks:** `c-choose-noticing`
- **artifact:** no external source. A described workflow started by an event, its facts set out one
  to a sentence, and two people's one-sentence defenses of the same way of noticing the event,
  from this activity's bank or written live per the generator below. About 2 minutes a question.
- **learner does:** reads the scenario and the one question served, two defenses of the same
  method, and picks the one whose reason is sound.
- **tutor role:** examiner
- **tutor does:** as `a-argue-noticing`'s, except that it labels a live run `a-pick-noticing/<shape>`
  and rules from the rubric's `answer`. Never says which reason is faulty before the learner has
  chosen.
- **done when:** the criterion met with no help, case by case. Each question gets one ruling: the
  sound defense passes the case the question carries, and the other passes none. There is no half
  credit.
- **generator:** **A scenario** uses the same shapes, variants and facts as `a-argue-noticing`,
  except that the facts are not running prose: after one or two sentences saying what the workflow
  does and that each new item should be handled soon after it arrives, a short paragraph headed
  "About this workflow:" gives the facts one sentence each, plus one fact that bears on neither
  method (who reads the result, how long each item takes the agent), and nothing else.

  **A question** reads: "<Name1> and <Name2> both think this workflow should find out about each
  new <item> by <checking for new ones every N minutes / being told each time one arrives>. Here is
  the reason each gives." Then two defenses, each one sentence starting with a bold label,
  "**Defense 1, <Name1>'s:**" and "**Defense 2, <Name2>'s:**", in the frame "<Method> fits this
  workflow best, because <reason>." Then "Which defense gives a sound reason?" with the choices
  "1. <Name1>'s" and "2. <Name2>'s", `type: mcq`. Both name the shape's natural method. Each reason
  is one fact from the paragraph, stated as the paragraph states it, with no added explanation, no
  hedge and no intensifier, and the two sentences are within ten words of each other in length.
  The near-miss's reason is also a fact from the paragraph, never a generic claim, and is faulty in
  one of two ways:
  - Medium, `does-not-support`: the fact bears on neither method (who reads the result), or points
    toward the other method (for being told, "because a quick look by a program costs nothing").
  - Hard, `not-a-difference`: the fact holds just as much for either method ("because each summary
    takes the agent about two minutes", "because the office computer is never turned off").
  For example, in a `hook-best` question with the method "being told each time one arrives", sound
  (9 words): "the dentist wants each summary within a few minutes"; near-miss `does-not-support` (8
  words): "the dentist reads each summary on her tablet".

  **Spread across the bank.** A bank is four scenarios, four questions: each case twice, one of each
  fault kind per case; in the two `poll` questions, one `no-word` and one `costly-setup`; the sound
  defense first in two. Names vary and are never reused within a scenario.

  **Domains** are this activity's own, none repeating within the bank: a pet groomer's bookings, a
  church's prayer-request line, a used bookshop's trade-in offers, a climbing gym's waiver forms, a
  neighborhood swap group's listings, a dance studio's makeup-class requests. No domain from the
  other five question activities' lists, and no homework or grading workflow.

  Credit: full for the sound defense, whose position is the rubric's `answer`; none for the other.
- **worked example:** shown only as help when asked for, which records the attempt as helped. As
  `a-argue-noticing`'s, then the tutor sets the sound defense of the same illustration beside one
  with a faulty reason and says why the faulty fact has no bearing on the choice, or holds for
  both methods alike.
- **doesn't show:** the method is given and the learner picks between two reasons, so a pass
  doesn't show they would choose the method or find the deciding fact on their own; with two
  choices a guess is right half the time. Both reasons refer to this workflow, so a pass doesn't
  show the learner would reject a reason that refers to nothing about it. `a-argue-noticing` has
  the learner choose and write the reason.
- **offer as:** the quick check, after session 19: a workflow that reacts to each new item and two
  people's reasons for the same way of finding out about it, and you pick the sound one. About 2
  minutes a question. Easier than `a-argue-noticing`, since the method and the reasons are given.

### `a-place-the-waiting-work`

- **serves:** `c-when-to-queue`
- **supports:** attempt
- **checks:** `c-when-to-queue`
- **artifact:** no external source. A described workflow, told in a short paragraph, that says how
  its work arrives and when its worker is available but not where the work waits, from this
  activity's bank or written live per the generator below. About 4 minutes a question.
- **learner does:** reads the scenario and its one question; says in two or three sentences where
  the work should wait until it can be done, or that it needn't wait anywhere, and why.
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
  query. It never says where the work waits. What starts the worker is not asked and need not be
  said. Mixed through the paragraph, in no fixed order and never under labels, are these facts:
  - where the work comes from and how it arrives: how many, how evenly, at what hours;
  - how soon a result is needed (a reply by mid-morning is fine; the display should show each
    reading as it comes in), stated in every scenario, since whether work may wait at all depends
    on it: an `unavailable` scenario's result can always wait until the worker is next available;
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
  use the words queue, waiting list, backlog, poll, hook, cron or trigger. **How pointed a fact may
  be:** each fact says what is kept, done or left behind ("the agent emails each reply and keeps no
  copy"; "each request is saved into the shared folder"), never what that does or doesn't let
  someone tell. A sentence such as "nothing shows which inquiries have been answered" draws the
  inference the learner is meant to draw, and is not used.

  **A question** reads: "Where should this workflow's work wait until it can be done? Say why.
  Answer in two or three sentences." Free response, `type: free`. One question per scenario,
  asking only this.

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
  anything) says which are done. These patterns are for the writer; the scenario itself states only
  what is saved where, by the pointedness rule above (for `files`, "each request is saved into the
  shared folder" and "a reply file is saved beside each request answered", never "nothing marks
  which are done").

  - `unavailable` (`worker-unavailable`): work arrives at any hour, including when the worker is
    off (the laptop turned off overnight, the person away until Friday), and the worker keeps up
    with any arrivals when it is on. What goes wrong without a queue: work arriving while the
    worker is off is never done. The natural kind is `source`, `files` or `log`, never `kept`.
    "Repair requests come in through the shop's website at all hours, and the website keeps every
    request with the time it came in, so it can list everything since any given morning. The agent
    that answers them runs on Ana's laptop, which is on from about 8 a.m. to 6 p.m. on weekdays and
    turned off the rest of the time. It emails a reply to each request; no copy of the reply is
    kept. A reply by mid-morning is soon enough." (Here only the source fits: nothing is left
    behind per request, and nothing is on overnight to add requests to a list.)
  - `burst` (`spread-out`): work arrives in a burst faster than the worker should take it (three
    hundred sign-ups in the hour after a newsletter goes out, against a provider that takes about
    twenty requests a minute). The worker is always a program or an agent on a machine that is
    never turned off, never a person, since a person is not always available. What goes wrong
    without a queue: the burst hits the worker all at once, past what it can take. The natural kind
    is any of the four. The scenario always states the worker's limit in plain words, so the
    consequence can be tied to it.
  - `no-queue` (`no-queue`): two variants, which the key names. `always-ready`: a quick program on
    a machine that is never off, with a few items an hour, each taking a second, so nothing ever
    has to wait. `drop-ok`: losing an occasional item does no harm, because the next one replaces
    it (a display showing the latest reading, a count that each update corrects). The key: no
    queue is needed, which condition holds and the fact that makes it hold, and why the other
    condition doesn't.

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
  ("the website's list of requests"), any other kind the facts make workable, the consequence
  without a queue and the sentence it rests on, and, for `no-queue`, which condition holds and why
  the other doesn't; plus the irrelevant detail.

  **Places the facts don't already supply.** An answer may propose something the workflow would
  newly start doing: a list it keeps, or a file or log line it begins writing for each finished
  item. That counts as a workable place when it would work with the facts as given. A list the
  workflow keeps needs something on to add each item as it arrives, so it is workable in a `burst`
  question (the worker's machine is never off) and not in an `unavailable` one, where the scenario
  supplies nothing that is on while the worker is off; an answer that invents such a machine earns
  nothing for the place. A new file or log line per finished item needs the items themselves to be
  held somewhere the worker can look (the source, a shared folder); where they are, it is workable,
  though not the simplest when the source can already list the new ones.

  Credit: in an `unavailable` or `burst` question, full when the answer names a workable place for
  the work, said concretely for this workflow (the key's natural kind, another it lists, or a new
  one that passes the rule above), and gives as the reason what would go wrong here without it,
  tied to this workflow (requests arriving overnight never get a reply; three hundred sign-ups at
  once overrun the provider's limit). Half when the place is workable but the reason is generic
  ("work might get lost") or missing, or when the reason is tied but the place is unworkable. None
  when neither holds, or when the answer says no place is needed. In a `no-queue` question, full
  when the answer says the work needn't wait and gives as the reason the condition that holds,
  tied to the fact that makes it hold (the program is on a machine that's never off and takes a
  second for each of a few an hour; each reading replaces the last). Half when it says no place is
  needed but the reason is generic or names the condition that doesn't hold, or when it proposes a
  place while correctly saying that one of the two conditions holds here. None when it proposes a
  place and names a loss the facts rule out, or gives no reason.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works the illustration of the same shape aloud: says when work arrives and when the worker
  is available, what already holds or leaves behind a record of the waiting work, which kind of
  queue that gives, and what would be lost without it. For `no-queue` it
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
  and you say where its work should wait, or that it needn't, and why. About 4 minutes a question. Harder than `a-trace-the-waiting-work`,
  since nothing is laid out for you to choose from.

### `a-trace-the-waiting-work`

- **serves:** `c-when-to-queue`
- **supports:** attempt
- **checks:** `c-when-to-queue`
- **artifact:** no external source. A described workflow whose design is left open, as in
  `a-place-the-waiting-work`, and one four-choice question offering four designs for it, each a
  place for the work to wait and a reason, from this activity's bank or written live per the
  generator below. About 3 minutes a question.
- **learner does:** reads the scenario, then picks which of four designs, each a place for the work
  to wait (or none) with its reason, fits it.
- **tutor role:** examiner
- **tutor does:** as `a-place-the-waiting-work`'s, including the offer to wait for session 19,
  except that it labels a live run `a-trace-the-waiting-work/<shape>` and the choice is settled
  from the rubric. Never says whether a wrong design's place or its reason is wrong before the
  learner has chosen.
- **done when:** the criterion met with no help, case by case. Each question gets one ruling: the
  sound design passes the case the question carries, and the others pass none. There is no half
  credit.
- **generator:** **A scenario** is written as in `a-place-the-waiting-work`: one made-up workflow in
  running prose, in the voice of the person who runs it, giving the same kinds of fact (how the work
  arrives, when the worker is available and how fast it can go, what the source keeps, what the
  workflow already leaves behind for each finished item, whether losing an occasional item
  matters, and how soon a result is needed), plus one irrelevant detail, and by the same
  pointedness rule. Like that activity's, it never says where the work waits; that is what the
  question asks. Nothing is described with code, a command, a file format or a query, and the words
  queue, waiting list, backlog, poll, hook, cron and trigger never appear; a log may be called a
  log. A machine that is off is said to be turned off, never closed or asleep. The worker is always
  a program or an agent, never a person. Because the question has one key, the facts are chosen so
  that exactly one design fits, as below, and the scenario states every fact a near-miss needs to
  be shown wrong: a `burst` reason used as a near-miss needs the worker's limit and the arrival rate
  stated (well under the limit, where that reason is false); a no-queue reason needs the fact that
  makes it false stated (the laptop is turned off at night; each request is someone waiting on a
  reply).

  **A question** is one multiple-choice question, `type: mcq`, with one goal, `c-when-to-queue`,
  and the case its shape carries. It reads "Which design, with its reason, fits this workflow?",
  then four numbered designs, each one sentence in the same frame: "The work should wait <where>,
  because <why>." The four are within ten words of each other in length. One is sound on both its
  place and its reason. The three near-misses are:
  - **wrong place**: an unworkable place with the sound design's reason;
  - **wrong reason**: the sound design's place with a reason the facts make false;
  - **other design**: a different, coherent design, nowhere with the no-queue reason the facts
    make false, so it reads as a real alternative and is wrong on the facts, not on fit.
  In a `no-queue` question, where a place with the sound no-queue reason would not hang together,
  the three near-misses are instead: the wrong reason (nowhere, with the other no-queue reason, the
  facts making it false), and two other designs, each a workable-looking place with a queue reason
  the facts make false, one with each queue reason (the worker's machine is never turned off; the
  arrivals stay well under its stated limit).
  So no choice is wrong only in a way that leaves it an equal setup, and every question tests both
  the place and the reason:

  **Where** (the `<where>` slot). The options, put in this workflow's terms: a list the workflow
    keeps, adding each <item> as it arrives; asking <the source> for the <items> that came in since
    the last run; working out which held <items> have no <file> yet, or which aren't in the log
    yet; nothing, each <item> going straight to <worker> as it arrives. The sound design uses the
    simplest that loses no work that matters, and the facts make exactly one of them that, using the fact
    patterns under "Kinds of queue" in `a-place-the-waiting-work`: for the source, the source keeps
    every item and can list them by when they came in, and the workflow leaves nothing behind per
    item; for files or a log, each item lands somewhere that holds it but can't say which are new
    or finished, so asking the source can't find the waiting ones, and the workflow leaves a file
    or a log line per finished item; for a kept list, the source keeps nothing and leaves nothing
    behind, and the worker's machine is never off to take in each arrival, so a kept list is the
    answer only in a `burst` question; for nothing, a `no-queue` condition holds, which makes every
    list unneeded and so not the simplest. The key names both facts behind the answer: where the
    items are held, and what (if anything) says which are done. A wrong place is one the facts
    make unworkable, so it would lose work: nothing, when items arrive while the worker is off or
    faster than it can take them; asking the source, when the source keeps nothing or can't say
    which items are new; files or a log, when the workflow leaves nothing behind per item; a kept
    list, when nothing is on to add each arrival. Never one that merely does more than it needs to.
    Which wrong place to use, by the sound place: when the sound place is the source, the wrong
    place is files or a log (the workflow leaves nothing behind per item) and the other design is
    nowhere; when it is files or a log, the wrong place is asking the source (it can't say which
    items are new) and the other design is nowhere; when it is a kept list, the wrong place is
    asking the source (it keeps nothing) and the other design is nowhere. When it is nowhere, the
    `no-queue` rule above applies instead.

  **Why** (the `<why>` slot), one of four statements put in this workflow's terms and worded the
  same way in every shape: otherwise <items> arriving while <worker> is <unavailable> would never
  be handled; otherwise a burst of <items> would reach <worker> faster than <its limit>; nothing
  needs to wait, as <worker> is always available and never overloaded; nothing needs to wait, as
  losing an occasional <item> does no harm here. Exactly one is true by the facts, and it is the
  shape's case. The wrong-reason near-miss uses one the facts make false that sits naturally with
  the sound place (the other queue reason when there is a queue, the other no-queue reason when
  there is none), and the scenario states the fact that makes it false.

  **Shapes**, each carrying one case, which its rubric `cases:` line lists:
  - `unavailable` (`worker-unavailable`): work arrives while the worker's machine is turned off,
    and the worker can keep up with any arrivals when it is on; the sound why is the first
    statement.
  - `burst` (`spread-out`): work arrives in a burst past what the worker can take, and the worker's
    machine is never turned off; the sound why is the second.
  - `no-queue` (`no-queue`): the sound where is nothing; the sound why is the third or the fourth
    statement, by variant (`always-ready` or `drop-ok`, as
    in `a-place-the-waiting-work`), the facts ruling out the other one (a `drop-ok` worker is
    sometimes off or slow; an `always-ready` workflow's items each matter).

  **How hard.** Medium by default. Hard when the sound where is files or a log, where the learner
  must notice that something the workflow already leaves behind tells what is still waiting, or
  when the `no-queue` variant is `drop-ok`, where the work looks as if it matters until the
  replacing is noticed. The question's wording is unchanged.

  **Spread across the bank.** A bank is six scenarios, six questions: each shape twice;
  `no-queue` once in each variant; the two `unavailable` scenarios have the source and files as
  their sound where, the two `burst` scenarios a kept list and a log; three questions Hard, the
  files, log and `drop-ok` ones. A kept list is never the sound where in an `unavailable`
  question, live or banked. The sound design sits in each of the four positions at least once and
  in none more than twice, and the order of the three near-misses varies.

  **Domains** are this activity's own, none repeating within the bank: a makerspace's 3D-print
  requests, a community radio station's song requests, a school weather station's readings display,
  a thrift store's donation pickups, a neighborhood watch's tip line, a little league's rain-delay
  texts, a language exchange's partner matching, a parking garage's open-space sign. No domain
  from the other five question activities' lists, and no homework or grading workflow.

  The rubric gives the `answer` (the 1-based choice) and, in a `tutor note`, the sentences of the
  scenario that settle the sound design's place and reason and, for each near-miss, whether its
  place or its reason is wrong (or both, for the other design) and the fact that shows it.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor takes the illustration in `a-place-the-waiting-work` of the same shape where there is one
  (for `unavailable`, the bike repair shop; for `no-queue` `always-ready`, the office computer case
  in its worked example), and otherwise makes up one of its own in that activity's style, in a
  domain no bank here uses. It writes four
  designs for it in this activity's style, and goes through them aloud, saying for each near-miss
  whether its place or its reason is wrong and which fact shows it. It may point to Where the work waits and When
  there's no queue in `tasks/read-triggers.md`.
- **doesn't show:** the learner picks among four designs rather than proposing one, so a pass
  doesn't show they would come up with the place or the consequence on their own;
  `a-place-the-waiting-work` checks that. The facts are chosen so one design fits,
  so a pass doesn't show the learner could weigh two workable designs. With four choices a guess is
  right a quarter of the time. The four kinds of where and the four statements of why are the same
  in every question, so they become familiar with repetition.
- **offer as:** the quick check, after session 19: a short description of a workflow and four
  designs for it, each saying where the work waits and why, and you pick the one that fits. About 3 minutes a question. Easier than `a-place-the-waiting-work`, since
  the choices are in front of you.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
