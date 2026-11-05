# Activities: triggers

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

The initial study, the orientation and one passed question for each of the five words, comes to
about 26 minutes: about 11 for `a-read-triggers` (the reading is about 6 to 7 minutes on its own)
and about 3 a word. All three capabilities carry `taught elsewhere` (the session 19 class), so
their six activities are offered after that class, as practice and review. Meeting all three
through the write-it checks takes eight questions, one per case: three for `a-argue-a-trigger` and
two for `a-argue-noticing` at about 3 minutes each, and three for `a-place-the-waiting-work` at
about 4, so about 27 minutes. Through the pick-one checks it is about 3 minutes a question for
each of `a-pick-trigger-defense`, `a-pick-noticing` and `a-trace-the-waiting-work`, so about 24.

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
Git, Canvas), and no operating system other than Mac and Linux, which the reading also names; a form, mailbox or website in a scenario is "the sign-up form", "the shop's
website", never a brand. Learner-facing text states the task, never the scoring.

## Check notes

2026-11-04. Each capability has a write-it check and a pick-one check, and either can meet the
goal alone. The topic's depth asks the learner to make each decision and say why, which only the
write-it checks (`a-argue-a-trigger`, `a-argue-noticing`, `a-place-the-waiting-work`) have them
do. Where there is time, have at least one case of each capability met through one of those. An
activity with no bank folder under `tasks/` is written live from its generator: check each live
scenario against the shape it claims before serving it, and in a pick-one question check the
option pattern its generator requires. Every scenario states the facts its decision needs, and
every machine that is off is turned off. So no check shows that the learner would notice a missing
fact and ask, or would plan for a laptop that only sleeps. Planning their own Problem Set 5
workflow may require both.

## Goals

| id                 | Goal | Criterion: what gets examined, and what counts |
| ------------------ | ---- | ---------------------------------------------- |
| `o-orientation`    | get the shape of this area before working on any particular part of it | `orientation` |
| `c-choose-trigger` | choose what triggers a workflow's runs, and say why | given a described workflow, says what should trigger its runs (a person, a schedule or an event) and why, with a reason tied to this workflow of any of three kinds: what makes that trigger good here, what would go wrong here without it, or what would make a specific other kind worse. The facts that bear on it include how soon its result is needed, how often there is work to do, who would have to remember to start it, and whether the machine or person that does the work will be available when the trigger fires. A reason that doesn't refer to this workflow at all, such as "a schedule is automatic", does not meet it. Cases: `event`, `unavailable`, `not-event` |
| `c-choose-noticing` | decide how an event-driven workflow finds out that its event happened | given a workflow started by an event, says whether it should notice the event by polling or through a hook, and why, with a reason tied to this workflow of any of three kinds: what makes that method good here, what would go wrong here without it, or what would make the other method worse. The facts that bear on it include whether the source can send word, how soon the result is needed, what each check costs, and who would have to set up receiving the message. A reason that doesn't refer to this workflow at all does not meet it. Cases: `hook`, `poll` |
| `c-when-to-queue`  | decide where a workflow's work waits until a worker can take it up | given a described workflow, says where its work should wait until a worker can take it up (a queue the workflow keeps, a source that already holds the waiting work, a list worked out each time from the state of files, or nowhere) and why, with a reason tied to this workflow of any of three kinds: what makes that place good here, what would go wrong here without it, or what would make a specific other place worse. For nowhere, the reason is that the worker is always available and never overloaded, or that dropping some work is acceptable. A reason that doesn't refer to this workflow at all does not meet it. Cases: `worker-unavailable`, `spread-out`, `no-queue` |

## Coverage

| goal               | checks | notes |
| ------------------ | ------ | ----- |
| `o-orientation`    | `a-read-triggers` |       |
| `c-choose-trigger` | `a-argue-a-trigger`, `a-pick-trigger-defense` |       |
| `c-choose-noticing` | `a-argue-noticing`, `a-pick-noticing` | The `poll` case can be met through a `no-word` or `cant-be-reached` scenario, where one fact (the source can't send word, or the machine has nothing its messages can arrive at) settles the choice on its own. A learner can therefore meet this goal without ever weighing set-up effort or the cost of a check against how soon the result is needed. Where there is time, have `poll` met through a `costly-setup` question. Neither check puts the work on a machine that is turned off, though the reading raises a hook on a laptop that is off. |
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
  example and Canvas sending a webhook as the web one); Schedules, and the laptop problem (cron jobs on Mac and Linux, launchd on a Mac, and a
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
  real tool or service except cron, launchd, Git and Canvas, all generically, and names Mac and Linux as
  operating systems. It says nothing about how state is
  stored, how failures are handled or what each part may touch, all later topics.
- **verified:** 2026-11-04
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
  not ask the learner to define any of the five words, to say what separates a word from its
  nearest confusable in goals.md (polling and a hook, a hook and event-driven, event-driven and a
  schedule, a work queue and a log), or to correct a misused sentence. Does not set or rehearse a
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
- **verified:** 2026-11-04
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

  **Facts kept to the case.** The list above is what a scenario may draw on, not what each must
  carry. A scenario states its case's defining fact or facts (named in each shape below), the
  facts needed to show each choice the key never accepts to be wrong, the one irrelevant detail,
  and nothing else that offers a tied reason for the accepted choice that doesn't rest on a
  defining fact. A "good here" reason counts on its own, so an extra helpful fact (that the
  machine is never turned off, that nobody has to remember) would let a learner meet the case
  without its defining fact. Where ruling out a choice needs a fact that could also serve as such
  a reason, rule that choice out another way, or word the fact so that it only rules it out.

  **A question** reads: "What should start this workflow's runs: a person, a schedule or an event?
  Say why. Answer in two or three sentences." Free response, `type: free`. One question per
  scenario, asking only this.

  **Shapes**, each with the case it carries, which its rubric `cases:` line lists. In every shape
  the facts make one kind of trigger fit better than the other two, and the key names the fact or
  facts that show it; in a Hard question two kinds fit about equally and the key accepts both.
  Every choice the key accepts is a workable design, one that would actually run and produce a
  result; a design that would never run (a schedule set for when the machine is turned off) is
  never accepted. The examples are illustrations, not bank items, and their domains (a pet-sitting
  service, a running club, a community choir, a garden club, a family's trip albums) are used by
  no bank in this topic.
  - `event-best` (`event`): a result is needed within minutes or an hour; work arrives a few times
    a day at unpredictable times, so most runs on a schedule frequent enough to be timely would
    find nothing, and a run is costly (an agent rereads everything). Natural choice an event. The
    defining facts: how soon the result is needed (a slow schedule would be too late), how rarely
    and unpredictably the work comes, which is also what rules out a person (a person would have to
    watch for forms all day, since they come at no set times, and the scenario says so in those
    terms), and what each run costs (a frequent schedule would mostly run for nothing, at a cost).
    The cost fact is stated even when no near-miss is a schedule, since it is a defining fact.
    The key cites the watching fact for the person. The scenario doesn't say when the machine is
    on: "it is never turned off" would be a reason for an event resting on none of those. "New
    clients fill in a form on the service's website, a few a day at no set times, and the owner
    wants the agent's care sheet for each pet ready before the first visit, often within the hour.
    Nobody can sit watching for forms all day, since they come at no set times. Each care-sheet run
    has the agent reread the whole client file."
  - `unavailable` (`unavailable`): the machine that does the work, or a person who does a step,
    is unavailable at known times, and the facts bear on whether each option would find them
    available when it fires. Two variants, which the key names:
    - `machine-off`: the work is done on the runner's own laptop, which the runner turns off
      (shuts down, not just closes) at known times, never said to be asleep. When it is turned
      back on varies (most mornings at 7, some not until 9 or later). Natural choice the runner
      starting it by hand when they turn the laptop on. The defining facts are the laptop's hours:
      when it is turned off, and that its morning on-time varies, so a schedule that fires while it
      is still off simply doesn't run that day. There is no set deadline: the result is wanted as
      soon as the laptop is on, said as part of the on-time fact ("she wants the board up as soon
      as the laptop is on"), and the board must include that morning's runs ("members want that
      morning's runs on the board"). Work arrives at all hours, said as part of the laptop's hours
      ("members log runs at all hours, including late at night and early in the morning while her
      laptop is off"). So an evening schedule just before shutdown is never accepted (its board
      lacks that morning's runs), and neither is an event that starts a run for each logged run
      (each logged run would make a board of only the runs since the previous board); the key
      lists both by name, with those reasons. No cost fact is used to rule out the per-run event.
      The laptop being turned on starting the run is an event by the design rule in Credit, and it
      works, so the key accepts it with the hand start. The scenario says nothing about how
      reliably the runner remembers, either way: "she never forgets" would be a reason for the hand
      start that doesn't rest on the laptop's hours. "Each morning the club's agent turns all runs
      logged since the last board into a leaderboard, and members want that morning's runs on it.
      Members log runs at all hours, including late at night and early in the morning while the
      captain's laptop is off. She turns it off at 11 p.m. Most mornings she turns it on at 7, on
      her early shifts not until noon, and she wants the board up as soon as it is on."
    - `person-away`: each run can only begin once a person has done the first step by hand (typed
      in that week's input, signed off on what goes in), and that person is away at known times and
      gets back at a time that varies. Natural choice the person starting it themselves when they
      have done that step. The defining facts are when the person is away and that their return
      time varies, and the scenario always puts the timing of the first step into the return fact,
      so it can't have been done before they left ("she types in the soloists once she is back,
      anywhere from 8 a.m. to noon on Monday"). A fixed schedule early enough to catch an early
      return would fire before a late one, when the run can't begin without the step, and one late
      enough to be safe would leave the result waiting after an early return, since the scenario
      says, again as part of the return fact, that they want the result the moment the step is
      done. So no fixed schedule is accepted, and the key lists both by name. A design where the
      person's own input starts the run (saving the soloists starts the draft) is ruled as the
      person starting it, and accepted; so is a design that checks every few minutes for the
      person's input and starts the run once it is there. The scenario says nothing about how reliably the person
      remembers, how costly a run is, or what changes while they are away, since each of those
      would offer a reason not resting on their being away. Never the reading's example of a TA
      approving feedback, or any approval of student work. "A community choir's agent drafts each
      week's seating chart from the soloists the director types in. She is away most weekends, and
      she types in the soloists once she is back, anywhere from 8 a.m. to noon on Monday, and
      wants the chart the moment she has."
  - `person-or-schedule` (`not-event`): two variants, which the key names. `schedule`: work
    accumulates steadily, a result is needed by a set time and not before, and reacting to each
    item one at a time would mean many runs where one would do; natural choice a schedule, the
    defining facts being the set time, the steady flow, and either that each run is costly or that
    the result is one summary of the period ("one report covering the whole week"), so that an
    event's many runs are plainly worse. Every `schedule` scenario states one of those last two.
    The set time is also what rules out a person: the result is due when nobody is there to start
    it, and the scenario says so as part of the set-time fact ("the digest must be in members'
    inboxes by 6 a.m. Monday, before anyone is up"). Work keeps arriving into the hours when
    nobody is up, said as part of the flow fact ("notices come in until midnight on Sunday"), so
    a person starting it before going to bed would miss work. It doesn't say when the machine is on or who
    would remember, since "the computer is never off" or "nobody would have to remember" would be
    reasons resting on none of the defining facts. "Members post notices to the garden club's
    board all week, a dozen a day, until midnight on Sunday. The agent turns the week's notices into one digest, which must
    be in members' inboxes by 6 a.m. Monday, before anyone is up."
    `person`: runs are rare and irregular, and the person has to be there anyway (to supply the
    input or look over the result straight away); natural choice a person, the defining facts
    being the irregular need and the person's presence (a schedule would mostly run before there
    is anything to do or when nobody is there to look). A design where the person's own input
    starts the run (uploading the photos starts the album) is ruled as the person starting it, and
    accepted; so is a design that checks every few minutes for the person's input and starts the
    run once it is there. "After each family trip, a few a year at no set times, Dad uploads the photos, and
    the agent builds an album that he looks over straight away."

  **How hard.** Medium when the facts favor the natural choice clearly. Hard, in
  `person-or-schedule`, when a second kind is nearly as good, so both are defensible; the key then
  accepts both, each with its defining fact. In `unavailable`, Hard comes from the on-times or
  return times alone: the late ones are rarer or closer to the usual ones, so a learner must check
  whether a fixed time would ever miss. In `event-best` the event
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
  choice it never accepts, by name (one that would fire while the machine is turned off or the
  person away and so produce nothing, an evening schedule whose result lacks that morning's
  work, an event per logged item, which would make a result of only the items since the previous
  one, a fixed schedule that fires before the person is back); the irrelevant detail; two or three
  generic reasons that would fail ("a schedule is automatic", "events are faster", "a person can
  make sure it's done right"); one or two facts of this scenario that are true but have no
  bearing on the choice at all, which also fail ("the care sheet is a one-page form"); and an
  example of each of the three kinds of tied reason below, for the choice it accepts.

  Credit: full when the answer chooses a trigger the key accepts and gives a reason tied to this
  workflow of any of three kinds:
  - **what makes that trigger good here**: a fact of this workflow the choice suits, needs or
    meets ("new clients fill in the form at no set times", for an event);
  - **what would go wrong here without it**: a consequence in this workflow of not using it ("a
    care sheet could be hours late");
  - **what would make a specific other kind worse**: a fact that tells against a named other
    option ("the captain's laptop is off until noon on early-shift days, so a 7:15 schedule
    wouldn't run then").
  One tied reason is enough; the answer need not compare with every other kind, and a reason that
  also names what the choice costs ("it means remembering each morning, but the laptop is often
  off at 7:15") still earns full credit. A fact with no bearing on the choice is not a tied reason
  (what the result looks like, who designed the form); nor is one resting on the irrelevant detail, or
  one the scenario's facts contradict. An answer is
  ruled on the design it describes, not the name it gives it: cheap repeated looks that start the
  costly run only when something is new ("a schedule every ten minutes that checks for anything
  new and starts the agent only then") are an event choice, whatever the answer calls them. The
  ruling is on the design the answer commits to: an answer that lists two choices, outside a
  question whose key accepts both, is ruled as choosing neither; in a question whose key accepts
  both, an answer listing both without committing is accepted and ruled on its reason; a combined
  design ("an event, with a weekly schedule as a backup") is ruled by its main choice. In an
  `unavailable` question the ruling is on whether the design the answer describes would actually
  run while the machine is on or the person there, and produce a result that isn't stale, by the
  scenario's facts; it is not on whether the reason uses the word "available". An answer that
  relies on a missed run being caught up when the laptop wakes (as the reading says launchd does
  after sleep) rests on a fact the scenario contradicts, since the laptop is turned off, not
  asleep, so that reason is not tied. Half when the choice is one the key doesn't accept but the
  reason rests on a fact that bears on the choice (the learner read the scenario but drew the
  wrong verdict), or when the choice is accepted but the reason is generic, not tied, or missing.
  None when the choice is not accepted and the reason is generic, not tied, or missing, or no
  trigger is chosen.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works the illustration of the same shape as the question aloud, from the facts to the
  choice: says which of the facts the scenario states bear on how soon the result is needed, how
  often there is work, who would have to remember and whether the machine or person will be
  available, never adding a fact the illustration leaves out, says which kind
  those facts favor and why the other two fit worse. Then shows a generic version ("a schedule is
  automatic") and says why it doesn't refer to this workflow at all. It may point to Three kinds
  of trigger and Schedules, and the laptop problem in `tasks/read-triggers.md`.
- **doesn't show:** the workflow's facts are all in one short paragraph with one irrelevant detail
  beside them, so a pass shows the learner can pick what matters out of a loose description, but
  not that they would notice a fact they need is missing and ask, as their own Problem Set 5
  workflow would make them. The `machine-off` variant always puts the work on the runner's own
  laptop, so it shows nothing about choosing a different machine, which is a later topic, and
  every machine that is off is turned off, so nothing tests one that is only asleep. One tied
  reason earns full credit, so a pass doesn't show the learner weighed every kind against the
  others. How an event is noticed is not asked here; `a-argue-noticing` asks it. Ruling on whether
  a reason is tied is a judgment; the key's generic reasons narrow it without removing it.
  Scenarios keep their facts to their case, but a learner may still bring in a reason from outside
  the scenario (assuming the office computer is never off); such an answer is credited and counts
  toward the case, so a pass doesn't always show the learner used the case's defining fact. In
  `person-away`, the person wanting the result as soon as the step is done gives the hand start a
  reason that doesn't rest on their being away ("she wants it the moment she has typed them in");
  that is the instructor-approved design, and such an answer is accepted and counts toward
  `unavailable`.
- **offer as:** the write-it-yourself check, after session 19: a short description of a workflow,
  and you say what should start it and why. About 3 minutes a question. Harder than
  `a-pick-trigger-defense`, since you choose, find the facts and write the reason yourself.

### `a-pick-trigger-defense`

- **serves:** `c-choose-trigger`
- **supports:** attempt
- **checks:** `c-choose-trigger`
- **artifact:** no external source. A described workflow, its facts set out one to a sentence, and
  one four-choice question offering four triggers for it, usually each with a reason, from this
  activity's bank or written live per the generator below. About 3 minutes a question.
- **verified:** 2026-11-04
- **learner does:** reads the scenario, then picks which of four options, each a trigger (a person,
  a schedule or an event), usually with its reason, fits the workflow.
- **tutor role:** examiner
- **tutor does:** as `a-argue-a-trigger`'s, including the offer to wait for session 19, except that
  it labels a live run `a-pick-trigger-defense/<shape>` and rules from the rubric's `answer`. Never
  says what is wrong with an option before the learner has chosen.
- **done when:** the criterion met with no help, case by case. Each question gets one ruling: the
  sound option passes the case the question carries, and the others pass none. There is no half
  credit.
- **generator:** **A scenario** uses the same three shapes and variants as `a-argue-a-trigger`, with
  one natural choice only (no Hard question with two acceptable choices), and its facts are not
  running prose. After one or two sentences saying what the workflow is for and what does its
  work, a short paragraph headed "About this workflow:" gives the facts one sentence each: the
  deciding fact or facts, every fact a near-miss needs to be shown wrong, and one neutral sentence
  (none in a choices-only question) that has no bearing on when runs should start, and nothing
  else. The neutral sentence says what
  the result looks like or who made something ("The leaderboard is a single page with a photo of
  the week's top runner", "The owner's niece designed the form"). It never touches timing,
  availability or cost: not how long a run takes (a short run could help meet a tight deadline),
  not that the machine is never turned off, not that the person is in on weekdays, since under the
  criterion any of those can be a reason of the "good here" kind.

  **Facts kept to the case**, as in `a-argue-a-trigger`: the paragraph states the case's defining
  fact or facts, the facts each near-miss needs to be shown wrong, the one neutral sentence (none
  in a choices-only question), and nothing else that offers a tied reason for the natural choice that doesn't rest on a defining
  fact. When a near-miss needs a fact that could also serve as such a reason, choose a different
  near-miss, or word the fact so that it only rules the near-miss out (for the `machine-off`
  evening schedule, "Members want that morning's runs on the board", which bears only on a board
  made before the morning).

  **A question** reads "Which of these fits this workflow?", then four numbered options, each one
  sentence in the same frame: "<Choice>, because <reason>." A choice is said concretely: "<Who>
  starts each run by hand <when>", "A schedule <time, in words>", or "An event: each new <item>
  starts a run". Each reason is one fact from the paragraph, stated as the paragraph states it,
  with no added "so ..." explanation, no hedge and no intensifier. The four sentences are within ten
  words of each other in length. `type: mcq`. The four options are:
  - **sound**: the natural choice, with a fact that separates it from the other kinds;
  - **wrong choice, true reason**: a different choice with a reason that is true by the facts, or
    sounds true, but doesn't rescue it: another fact in the paragraph rules the choice out;
  - **not a difference**: the natural choice with the neutral sentence as its reason, a true fact
    with no bearing on the choice. It is never an availability fact or any fact that makes the
    choice good here, would go wrong without it, or tells against a named other kind, since any of
    those is a reason the criterion accepts;
  - **ruled-out alternative**: a coherent design, a choice and the reason that would go with it,
    that a stated fact rules out (it would fire while the machine is turned off, miss work that is
    still arriving, be too late, or cost a run per change where each run is costly).
  The four split two and two by choice, so counting choices gives nothing away: the sound option
  and the not-a-difference option name the natural choice, and the wrong-choice option and the
  ruled-out alternative name one and the same other kind (two schedules at different times, two
  person starts at different times, or two events where each run is costly). Exactly one option is
  right by the facts. No option is wrong merely because it does more than it
  needs to (a frequent schedule whose only fault is extra runs is never a near-miss unless the
  paragraph says each run is costly). Every fact a near-miss needs to be shown wrong is in the
  paragraph.

  **Choices only.** When a wrong choice can't be given a reason that would naturally support it,
  the question gives four bare choices instead, each one sentence saying the choice concretely with
  no "because": the natural choice, and three near-misses, each ruled out by a stated fact. They
  still split two and two by choice, and their lengths are still within ten words of each other.
  The paragraph then has no neutral sentence, and the reasons move to the tutor note. For example,
  `person-or-schedule`, variant `person`, the quilting guild: the paragraph gives "The guild meets
  a few times a year, at no set dates", "The secretary types in her notes the morning after each
  meeting", "She finishes at different times of the morning" and "She reads the minutes over as
  soon as she has typed in her notes". Options: sound, "The secretary starts it by hand once her
  notes are in"; "A schedule every morning at 9 a.m." (on a late morning it comes before her notes
  are in); "The secretary starts it by hand on the first Monday of each month" (that can come weeks
  after her notes are in); "A schedule at noon the day after each meeting" (with no set dates,
  nobody can set it ahead of time). Two hand starts, two schedules.

  **Examples**, which obey the because-form above. The paragraph sentences are given in quotation marks.
  - `machine-off`. The paragraph gives "The laptop is turned off at 11 p.m.", "Members log runs at
    all hours, including while the laptop is off", "Members want that morning's runs on the
    board", "On most days the laptop is turned on at 7 a.m.", "On early-shift days the laptop is
    turned on at noon", "She wants the board up as soon as the laptop is on" and the neutral
    sentence "The leaderboard has the top runner's photo." It gives no set deadline. Options (word counts in parentheses): sound, "She
    starts it by hand when she turns the laptop on, because on early-shift days the laptop is
    turned on at noon" (22); wrong choice, true reason, "A schedule at 7:15 a.m. each morning,
    because on most days the laptop is turned on at 7 a.m." (19); not a difference, "She starts it
    by hand when she turns the laptop on, because the leaderboard has the top runner's photo" (19);
    ruled-out alternative, "A schedule at 10:30 p.m., just before shutdown, because the laptop is
    turned off at 11 p.m." (17), wrong because members want that morning's runs on the board,
    which a board made the night before can't have. The 7:15 a.m. schedule is wrong because on
    early-shift days it fires while the laptop is still off. The longest and
    shortest differ by 5 words, and a schedule option ties a hand-start option for second
    longest, so length points to no choice. Two hand starts, two schedules. No fact about whether
    she remembers appears.
  - `event-best`, a pet-sitting service. The paragraph gives "New clients fill in the form a few a
    day, at no set times", "Each care sheet is needed within the hour", "Every run, even one that
    finds no new form, has the agent reread the whole client file, which costs real money", "The
    owner starts work at 8 a.m." and the neutral sentence "The owner's niece designed the form."
    Options: sound, "An event: each new form starts a run, because new clients fill in the form a
    few a day, at no set times"; wrong choice, true reason, "A schedule every hour, because each
    care sheet is needed within the hour" (most hourly runs would find no new form and still cost
    real money); not a difference, "An event: each new form starts a run, because the owner's niece
    designed the form"; ruled-out alternative, "A schedule every morning at 8 a.m., because the
    owner starts work at 8 a.m." (forms come in all day, and each care sheet is needed within the
    hour). Two events, two schedules. The tutor note cites the every-run sentence as what rules out
    the hourly schedule.
  - `person-away`, as in `a-argue-a-trigger`: the run can't begin until the person has done its
    first step, and the step's timing is part of the return fact. The paragraph gives "The agent
    drafts each chart from the soloists the director types in", "She is away from Friday evening
    until Monday", "She types in the soloists when back, between 8 a.m. and noon Monday", "She
    wants the chart the moment she has typed them in" and the neutral sentence "The chart is
    printed on letterhead." It says nothing about whether she remembers, what a draft costs, or
    what changes while she is away. Options (word counts): sound, "She starts it by hand once the
    soloists are in, because she types in the soloists when back, between 8 a.m. and noon Monday"
    (24); wrong choice, true reason, "A schedule at 8 a.m. Monday, because she is away from Friday
    evening until Monday" (15), wrong because on a late Monday the soloists aren't in yet; not a
    difference, "She starts it by hand once the soloists are in, because the chart is printed on
    letterhead" (17); ruled-out alternative, "A schedule at noon on Monday, because the agent
    drafts each chart from the soloists the director types in" (19), wrong because on an early
    Monday the chart comes hours after she wants it. The longest and shortest differ by 9 words. A design where her saving the
    soloists starts the draft would be the person starting it, and is not among the options. Two
    hand starts, two schedules.
  - `person-or-schedule`: the two options on the other kind are both of the other of person and
    schedule, at different times, or both events where reacting to each item would mean many runs
    and the paragraph says each run is costly or that the result is one summary of the period. For
    example, `schedule`, the garden club: the paragraph gives "Members post notices to the board
    all week, until midnight on Sunday", "The agent turns the week's notices into one digest",
    "The digest must be in members' inboxes by 6 a.m. Monday, before anyone is up" and the neutral
    sentence "The digest has the club's logo at the top." Options (word counts): sound, "A schedule
    at 5 a.m. Monday, because the digest must be in members' inboxes by 6 a.m. Monday, before
    anyone is up" (22); wrong choice, true reason, "The secretary starts it by hand on Monday
    morning, because the agent turns the week's notices into one digest" (19), wrong because
    nobody is up before 6 a.m.; not a difference, "A schedule at 5 a.m. Monday, because the digest
    has the club's logo at the top" (16); ruled-out alternative, "The secretary starts it by hand
    on Sunday evening, because members post notices to the board all week" (18), wrong because
    notices keep coming until midnight on Sunday. Two schedules, two person starts. For the
    `person` variant, the writer builds the options the same way from the trip-album illustration's
    pattern in `a-argue-a-trigger`, in a domain no bank here uses.

  **Spread across the bank.** A bank is six scenarios, six questions: each shape twice;
  `unavailable` once `machine-off` and once `person-away`; `person-or-schedule` once `schedule` and
  once `person`. The sound option sits in each of the four positions at least once and in none
  more than twice, and the order of the three near-misses varies.

  **Domains** are this activity's own, none repeating within the bank: a florist's delivery route
  sheet, a youth soccer club's field-closure notices, a toy store's holiday layaway pickups, a carpool's
  weekly driving schedule, a yoga studio's class waitlists, a museum's lost-and-found listings, a
  quilting guild's meeting minutes, a car wash's daily sales summary. No domain from the other five
  question activities' lists, and no homework or grading workflow.

  The rubric gives the `answer` (the 1-based choice) and, in a `tutor note`, the sentence that
  settles the sound option and, for each near-miss, which kind it is and the fact that rules it out.
  For a choices-only question, it gives instead the fact that rules out each near-miss's choice.
  Credit: full for the sound option; none for the others.
- **worked example:** shown only as help when asked for, which records the attempt as helped. As
  `a-argue-a-trigger`'s, then the tutor sets four options for the same illustration in this
  activity's style and goes through them aloud, saying for each near-miss which fact rules it out
  or why its reason has no bearing on the choice.
- **doesn't show:** the learner picks among four options rather than writing one, so a pass doesn't
  show they would find the deciding fact or word the reason themselves; with four choices a guess
  is right a quarter of the time. Every scenario has one natural choice, so a pass shows nothing
  about weighing two defensible ones. Every option's reason is a fact from the paragraph, so a pass
  doesn't show the learner would reject a reason that refers to nothing about this workflow. A
  choices-only question checks only the choice, so passing it shows nothing about the "and why" in
  the criterion, though it still passes its case. The
  facts are laid out one to a sentence under a heading, so a pass doesn't show the learner would
  find them in a looser description; `a-argue-a-trigger` gives them as running prose and has the
  learner write the reason.
- **offer as:** the quick check, after session 19: a short workflow and four triggers for it,
  usually each with a reason, and you pick the one that fits. About 3 minutes a question. Easier than
  `a-argue-a-trigger`, since the options are written for you.

### `a-argue-noticing`

- **serves:** `c-choose-noticing`
- **supports:** attempt
- **checks:** `c-choose-noticing`
- **artifact:** no external source. A described workflow that is started by an event, told in a
  short paragraph, with how it finds out about each event left open, from this activity's bank or
  written live per the generator below. About 3 minutes a question.
- **verified:** 2026-11-04
- **learner does:** reads the scenario and its one question; says in two or three sentences
  whether the workflow should find out about each new item by polling or through a webhook (a
  hook, where the source isn't a website), and why.
- **tutor role:** examiner
- **tutor does:** as `a-argue-a-trigger`'s (the offer to wait for session 19, setting the question
  as served, help on request recorded as helped, the key and case written before a live question,
  ruling from the question alone), except that it labels a live run `a-argue-noticing/<shape>`.
  Never names the cases or which fact matters.
- **done when:** the criterion met with no help, case by case: a full-credit answer passes the case
  its question carries.
- **generator:** **A scenario** is one made-up workflow, told in one paragraph of running prose,
  six to nine sentences, in the voice of the person who runs it. It shows, without saying so
  outright, that each new item is handled after it arrives rather than at set times (the agent
  "reads each rush job" and customers want the reply "within a few minutes"), so the workflow is
  started by an event (how soon is one of the facts below, and may be anything from a minute to the day); the
  question is only how it finds out. It says what does the work, in plain words, and on which
  machine; nothing is described with code, a command, a file format or a query. Mixed through the
  paragraph, in no fixed order and never under labels, are these facts:
  - where the items come from, and whether that source can tell the workflow when one arrives,
    said plainly ("the sign-up form can send a webhook each time someone signs up", or "can send a
    message to a web address each time") or that it can only be looked at ("the mailbox sends no
    notice of new mail; a program can open it and look");
  - how soon a result is needed after an item arrives (within a minute, within the hour, by the
    end of the day);
  - what each check would cost: a quick look by a program that takes a moment and costs nothing,
    or a look that means the agent reading everything again;
  - who would have to set up receiving the source's message, and whether that is easy for them or
    a bother; where it can't be done in time, a deadline in the same sentence ("receiving those
    messages means asking my nephew, who next helps in three weeks, and sign-ups open tomorrow");
  - in a `hook-best` scenario only, that the machine that would receive the message is never
    turned off, said as part of the set-up fact ("the kennel's computer person can set up the
    office computer, which is never turned off, to take in those messages in an afternoon"); this
    topic never sets a noticing question on a machine that is off. A `poll-best` scenario doesn't
    say when the machine is on.
  Plus one irrelevant detail, said as plainly as the facts and bearing on neither method. The facts
  are stated as facts, never as what they mean for the choice.

  **Words in context.** The topic's vocabulary is used in context, with no gloss. Questions,
  options and keys name the two methods with the words: polling (with its interval, "polling for
  new requests every ten minutes") and a webhook ("a webhook: the website sends a notice each time
  a request arrives"), or a hook where the source isn't a website (a tool that runs a command when
  something happens). A scenario may use "webhook" where a real person would ("the website can
  send a webhook each time a request comes in"), but the fact that decides the answer is still
  said plainly, never left to be inferred from a word (in `cant-be-reached`, that notices need a
  web server to arrive at and the machine doesn't run one). In the rest of this entry, "checking"
  means polling and "being told" means a webhook or hook.

  **Facts kept to the case.** The list above is what a scenario may draw on, not what each must
  carry. A scenario states its case's defining facts (named in each shape below), the facts
  needed to show the other method wrong, the one irrelevant detail, and nothing else that offers a
  tied reason for the accepted method that doesn't rest on a defining fact. A "good here" reason
  counts on its own, so an extra helpful fact (a machine that is never off, in a `poll-best`
  scenario) would let a learner meet the case without its defining fact. Where showing the other
  method wrong needs a fact that could also serve as such a reason, word it so that it only rules
  the other method out, or leave it out and rule the method out another way.

  **A question** reads: "Should this workflow find out about each new <item> by polling or through a
  webhook? Say why. Answer in two or three sentences." Where the source isn't a website, it says
  "through a hook" instead. Free response, `type: free`. One question per scenario, asking only
  this.

  **Shapes**, each with the case it carries. The examples are illustrations, not bank items, and
  their domains (a kennel, a tenants' association) are used by no bank in this topic.
  - `hook-best` (`hook`): the source can send a message each time; the result is needed soon (a
    minute or a few), so checking would have to be very frequent; receiving the message is easy to
    set up for whoever must do it. Every `hook-best` scenario also states a fact that rules out
    frequent checking: each check is costly (it means the agent reading everything again) or the
    source limits how often it may be looked at ("the booking site lets a program look at most
    once an hour"). Defining facts: the source can send word, receiving it can be set up, how soon
    the result is needed, and the fact that rules out frequent checking. "Owners book boarding
    through the kennel's website, and the manager wants each booking confirmed within a few
    minutes. The website can send a message to a web address each time a booking comes in, and the
    kennel's computer person can set up the office computer, which is never turned off, to take in
    those messages in an afternoon. Each look at the bookings means the agent reading every booking
    again."
  - `poll-best` (`poll`): three variants, which the key names. `no-word`: the source can only be
    looked at, so checking again and again is the only way; the result can wait long enough that
    checking every so often is fine, and each look is cheap. `costly-setup`: the source can send
    a message, but receiving it means setting something up that can't be done in time, and the
    scenario always says so in plain terms, not merely that it is a bother, with the deadline in
    the same sentence as the set-up's delay ("receiving those messages means asking my nephew, who
    next helps in three weeks, and sign-ups open tomorrow"), while each look is cheap and the
    result can wait (within the hour), so a cheap check every ten minutes serves.
    `cant-be-reached`: the source can send word each time, but the machine that does the work
    can't receive it, and the scenario says so plainly in one sentence that also says what the
    missing piece is for, so the learner never has to infer what a web server does ("The website
    can send a notice each time a request comes in, but notices need a web server to arrive at,
    and the office computer doesn't run one"). The scenario also says the machine can reach out
    and fetch from the source ("The office computer is connected to the internet and can fetch the
    list of requests from the website"). The difference this variant teaches is that asking only
    needs your machine to reach out, while being told needs something the source can reach.
    Natural method checking; each look is cheap and the result can wait. The scenario says nothing
    about when any machine is on. The source in a `cant-be-reached` scenario is always a website,
    so the question always says "through a webhook".
    Defining facts, in every variant: whatever rules out being told (the source sends no notice;
    the set-up can't be done in time; the machine has nothing the notices can arrive at), that the
    machine can look (a program can open the mailbox; the computer can fetch the list), that a
    look is cheap, and how long the result can wait. In `cant-be-reached` the fetch fact is a
    defining fact, the reaching-out half of the contrast, so a reason resting on it ("checking,
    because the office computer can fetch the list itself") rests on a defining fact and is
    allowed under the facts-kept rule. "Repair requests arrive in the
    association's shared mailbox, a few a day, and a reply within the day is fine. The mailbox
    sends no notice of new mail; a program can open it and look, which takes a moment."

  **How hard.** Medium when one deciding fact settles it (the source can't send word; the result
  is needed within a minute; in `cant-be-reached`, the office computer has nothing the notices
  can arrive at). Hard when the facts pull both ways: in `costly-setup`, a source that
  can send word but a set-up nobody can do in time; in a Hard `hook-best`, a set-up that is some
  bother but a result needed so soon that checking would have to be constant. The question's
  wording is unchanged. A question where the facts truly balance and the key accepts both methods
  carries no case (see the key below), so the bank's case-carrying questions never balance.

  **Spread across the bank.** A bank is five scenarios, five questions: `hook-best` twice, one
  Hard; `poll-best` three times, once `no-word` (Medium), once `costly-setup` (Hard) and once
  `cant-be-reached` (Medium). When the generator is run live, the tutor picks each next shape to
  carry a case the learner hasn't passed.

  **Domains** vary by scenario, none repeating within the bank: a vet clinic's appointment
  requests, a farm stand's preorders, a theater's volunteer usher sign-ups, a ski shop's tune-up
  drop-offs, a youth band's rehearsal absences, a print shop's rush jobs. No domain
  from the other five question activities' lists, and no homework or grading workflow.

  **The key** gives every design it accepts, which is every design that would work on the facts
  (both methods, in a Hard question where the facts truly balance, each with its deciding fact;
  polling at an interval the facts allow counts as polling), as `a-argue-a-trigger`'s key does,
  naming each method with the topic's words, the deciding fact or facts and the sentence carrying
  each, why the other method fits worse, the irrelevant detail, two or three generic reasons that
  would fail ("a webhook is faster", "polling wastes resources", "it's simpler to just poll"), one
  or two
  facts of this scenario that are true but have no bearing on the method at all, which also fail
  ("the booking form was designed by the manager's cousin"), and an example of each of the three
  kinds of tied reason below, for the method it accepts. A question whose key accepts both methods
  carries no case, since `hook` and `poll` are each a workflow best served by one method; its
  rubric `cases:` line is left empty and a pass on it meets neither case.

  Credit: full when the answer chooses a method the key accepts and gives a reason tied to this
  workflow of any of three kinds:
  - **what makes that method good here**: a fact of this workflow the method suits, needs or
    meets. For a webhook or hook, that the source can send a message each time is a full reason of
    this kind on its own, as are a set-up that is easy for whoever must do it and a machine that is
    never turned off to receive the message. For polling, that the source sends no notice is a
    full reason on its own, as is that the machine has nothing the notices can arrive at
    (`cant-be-reached`) and that it can fetch from the source itself, and so are a cheap look and
    a result that can wait;
  - **what would go wrong here without it**: a consequence in this workflow of not using it
    ("bookings would wait for the next poll, past the few minutes the manager wants");
  - **what would make the other method worse**: a fact that tells against the other method ("each
    look means the agent reading every booking again"; "receiving the messages means asking my
    nephew, who next helps in three weeks, and sign-ups open tomorrow").
  One tied reason is enough. A fact with no bearing on the method is not a tied reason; nor is one
  resting on the irrelevant detail, or one the scenario's facts contradict. An answer is still
  ruled on the design it describes, whatever it calls it: "a program looks every ten minutes" is
  polling, and "the website pings the computer when a request comes in" is a webhook, whether or
  not the answer uses those words, and an answer that names one method but describes the other is
  ruled as the one it describes. The ruling is on the design the answer commits to: an answer that
  lists both methods, outside a question whose key accepts both, is ruled as choosing neither; in
  a question whose key accepts both, it is accepted and ruled on its reason; a combined design ("a webhook, with a daily poll as a backup") is ruled by its main method. Half
  when the method is one the key doesn't accept but the reason
  rests on a fact that bears on the method, or the method is accepted but the reason is generic,
  not tied, or missing. None when the answer chooses a webhook or hook for a source the scenario says
  can only be looked at, or for a machine the scenario says has nothing the notices can arrive at
  (`cant-be-reached`), when the method is not accepted and the reason is generic, not tied, or
  missing, or no method is chosen. Where a Half clause and a None clause both fit (a webhook in
  either of those cases, with a reason that bears on the method), the None clause governs. In a
  `cant-be-reached` question the key accepts polling at any interval within how long the result
  can wait, and never accepts a webhook, nor a design that adds a web server or other receiver
  the scenario doesn't supply.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works the illustration of the same shape aloud: says, of the facts the scenario states,
  whether the source can send word, how soon the result is needed, what a check costs and who
  would set up receiving the message, never adding a fact the illustration leaves out, then which
  method those facts favor and why. Then shows a generic version ("a webhook is faster") and says
  why it doesn't refer to this workflow. It may point to Noticing an event in
  `tasks/read-triggers.md`.
- **doesn't show:** no scenario has a machine that is off, so a pass shows nothing about a
  message arriving at a machine that is off, which the reading mentions. One tied reason earns
  full credit, so a pass doesn't show the learner weighed every fact. How often to poll, once
  polling is chosen, is not asked. Scenarios keep their facts to their case, but a learner may
  still bring in a reason from outside the scenario; such an answer is credited and counts toward
  the case, so a pass doesn't always show the learner used the case's defining fact.
- **offer as:** the write-it-yourself check, after session 19: a workflow that reacts to each new
  item, and you say whether it should find out by polling or through a webhook, and why. About 3
  minutes a question. Harder than `a-pick-noticing`, since you choose and write the reason
  yourself.

### `a-pick-noticing`

- **serves:** `c-choose-noticing`
- **supports:** attempt
- **checks:** `c-choose-noticing`
- **artifact:** no external source. A described workflow started by an event, its facts set out one
  to a sentence, and one four-choice question offering four ways of finding out about each event,
  each with a reason, from this activity's bank or written live per the generator below. About 3
  minutes a question.
- **verified:** 2026-11-04
- **learner does:** reads the scenario, then picks which of four options, each a way of finding out
  (polling, or a webhook or hook) with its reason, fits the workflow.
- **tutor role:** examiner
- **tutor does:** as `a-argue-noticing`'s, except that it labels a live run `a-pick-noticing/<shape>`
  and rules from the rubric's `answer`. Never says what is wrong with an option before the learner
  has chosen.
- **done when:** the criterion met with no help, case by case. Each question gets one ruling: the
  sound option passes the case the question carries, and the others pass none. There is no half
  credit.
- **generator:** **A scenario** uses the same shapes and variants as `a-argue-noticing`, with one
  natural method only (no Hard question where the facts balance), and its facts are not running
  prose: after one to three sentences saying what the workflow does, showing without saying so outright
  that each new item is handled after it arrives (the agent "replies to each makeup-class
  request"), and possibly carrying how soon the result is needed and the neutral sentence, a short
  paragraph headed "About this workflow:" gives the remaining facts one sentence each. Between
  them, the opening and the paragraph give: the deciding fact or facts, every fact a near-miss needs to be shown
  wrong (how soon the result is needed, what each check costs, whether the source can send word,
  who would set up receiving it), and one neutral sentence with no bearing on either method, and
  nothing else. The neutral sentence says what the result looks like or who made something ("The
  confirmation is a short note with the club's logo", "The manager's cousin designed the form").
  It never touches timing, availability or cost: not how long each item takes (a quick job could
  help meet a tight deadline), not that the machine is never turned off (so a message would be
  received), since under the criterion any of those can be a reason of the "good here" kind. The
  topic's words are used in context with no gloss, as in `a-argue-noticing`: a scenario may say
  "webhook" where a real person would, but the fact that decides the answer is still said plainly.
  In the rest of this entry, "checking" means polling and "being told" means a webhook or hook.

  **Facts kept to the case**, as in `a-argue-noticing`: the scenario states the case's defining
  facts, the facts each near-miss needs to be shown wrong, the one neutral sentence, and nothing
  else that offers a tied reason for the natural method that doesn't rest on a defining fact.
  When a near-miss needs a fact that could also serve as such a reason, choose a different
  near-miss, or word the fact so that it only rules the near-miss out. A machine that is never
  turned off appears only in a `hook-best` paragraph, folded into the set-up fact as in
  `a-argue-noticing`.

  **A question** reads "Which of these fits this workflow?", then four numbered options, each one
  sentence in the same frame: "<Method>, because <reason>." A method is named with the topic's
  words and said concretely: "Polling for new <items> every <interval>", or "A webhook: <the
  source> sends a notice each time <an item> arrives" ("A hook: ..." where the source isn't a
  website). Each
  reason is one fact from the scenario (the opening or the paragraph), stated as the scenario
  states it, with no added
  explanation, no hedge and no intensifier. The four sentences are within ten words of each other in
  length. `type: mcq`. The four options are:
  - **sound**: the natural method, with a fact that separates it from the other method;
  - **not a difference**: the natural method with the neutral sentence as its reason, a true fact
    with no bearing on the method;
  - two options on **the other method**, each with a different fact from the scenario that is
    true, or sounds true, but doesn't rescue that method.
  So the four split two and two by method, and counting methods gives nothing away. By shape:
  - `costly-setup`: both other-method options are being told. One gives the fact that the source
    can send a message each time; the other gives a different true fact from the scenario that
    sounds like a reason to want word at once (how many items arrive, who is waiting on them),
    never a slack deadline, which argues for checking. Neither rescues being told, because receiving the message
    needs a set-up that can't be done in time, which the paragraph says in one sentence that also
    gives the deadline, as in `a-argue-noticing`; the tutor note cites that sentence.
  - `no-word`: both other-method options are being told. The source sends no notice, so neither
    may claim it does; each gives a different true fact from the scenario that sounds like a
    reason to want word at once (how many items arrive a day, who is waiting on them), never a
    slack deadline, which argues for checking. Being told is ruled out by the fact that the source sends no notice.
  - `cant-be-reached`: both other-method options are being told, each with a different true fact
    from the scenario: one that the source can send a notice each time, the other a fact that
    sounds like a reason to want word at once (how many items arrive, who is waiting on them),
    never a slack deadline, which argues for checking. Neither rescues being told, because the paragraph's one sentence on the
    missing receiver ("notices need a web server to arrive at, and the office computer doesn't run
    one") leaves the notices nowhere to arrive; the tutor note cites that sentence. The sound
    option gives that sentence as its reason. The paragraph also states the fetch fact ("can fetch
    the list of requests from the website"), a defining fact as in `a-argue-noticing`, and says
    nothing about when any machine is on.
  - `hook-best`: both other-method options are checking, at intervals the paragraph's facts rule
    out: one frequent enough to be timely, with a true fact such as how soon the result is needed
    (ruled out because each check is costly, or the source limits how often it may be looked at);
    one slow enough to keep checks few, with a true fact such as what each check costs (ruled out
    because the result is needed within minutes).
  Exactly one option is right by the facts. No option is wrong merely because it does more than it
  needs to (checking more often than needed is never a near-miss unless the paragraph says each
  check is costly). Every fact a near-miss needs to be shown wrong is in the scenario.

  **Example**, a `costly-setup` question. The paragraph gives "The sign-up form can send a message
  to a web address each time", "Receiving those messages means asking my nephew, who next helps in
  three weeks, and sign-ups open tomorrow", "A quick look at the form's list by a program takes a
  moment", "A reply within the hour is fine", "Each new member is waiting to hear they are signed
  up" and the neutral sentence "The confirmation is a short
  note with the club's logo." Options (word counts): sound, "Polling for new sign-ups every ten
  minutes, because receiving those messages means asking my nephew, who next helps in three
  weeks, and sign-ups open tomorrow" (25); not a difference, "Polling for new sign-ups every ten
  minutes, because the confirmation is a short note with the club's logo" (18); other method, "A
  webhook: the form sends a notice each time a sign-up arrives, because the sign-up form can send
  a message to a web address each time" (26); other method, "A webhook: the form sends a notice
  each time a sign-up arrives, because each new member is waiting to hear they are signed up"
  (24). The spread is 8
  words. Both webhook options fail on the nephew sentence, which the tutor note cites. Two
  polling, two webhook.

  **Example**, a `cant-be-reached` question, from the bank's dance studio scenario
  (`dance-makeup-requests`). The paragraph gives "Students ask for makeup classes through a form on
  our website, which keeps a list of all requests", "The agent runs on the office computer", "The office computer is connected to the internet
  and can fetch the list of requests from the website and send email", "Fetching the list is
  quick and costs almost nothing", "The website can send a
  notice each time a request comes in, but notices need a web server to arrive at, and the office
  computer doesn't run one", "Each student is waiting to hear which class they can join"; the
  opening gives "A reply within the hour is fine" and the neutral
  sentence "The reply is a short note with a picture of ballet shoes." Options (word counts): other method, "A
  webhook: the website sends a notice each time a request arrives, because the website can send a
  notice each time a request comes in" (25); sound, "Polling for new requests every ten minutes,
  because notices need a web server to arrive at, and the office computer doesn't run one" (23);
  other method, "A webhook: the website sends a notice each time a request arrives, because each
  student is waiting to hear which class they can join" (24); not a difference, "Polling for new requests every ten
  minutes, because the reply is a short note with a picture of ballet shoes" (20). The spread is 5
  words. Both webhook options fail on the web-server sentence, which the tutor note cites;
  polling only needs the office computer to reach out to the website. Two polling, two webhook.

  **Spread across the bank.** A bank is five scenarios, five questions: `hook` twice and `poll`
  three times, the three `poll` questions one each of `no-word`, `costly-setup` and
  `cant-be-reached`. The sound option sits in each of the four positions at least once and in none
  more than twice, and the order of the three near-misses varies.

  **Domains** are this activity's own, none repeating within the bank: a pet groomer's bookings, a
  church's prayer-request line, a used bookshop's trade-in offers, a climbing gym's waiver forms, a
  neighborhood swap group's listings, a dance studio's makeup-class requests. No domain from the
  other five question activities' lists, and no homework or grading workflow.

  The rubric gives the `answer` (the 1-based choice) and, in a `tutor note`, the sentence that
  settles the sound option and, for each near-miss, which kind it is and the fact that rules it out.
  Credit: full for the sound option; none for the others.
- **worked example:** shown only as help when asked for, which records the attempt as helped. As
  `a-argue-noticing`'s, then the tutor sets four options for the same illustration in this
  activity's style and goes through them aloud, saying for each near-miss which fact rules it out
  or why its reason has no bearing on the method.
- **doesn't show:** the learner picks among four options rather than writing one, so a pass doesn't
  show they would find the deciding fact or word the reason themselves; with four choices a guess
  is right a quarter of the time. Every scenario has one natural method, so a pass shows nothing
  about weighing facts that pull both ways. Every option's reason is a fact from the paragraph, so a
  pass doesn't show the learner would reject a reason that refers to nothing about this workflow.
  `a-argue-noticing` has the learner choose and write the reason.
- **offer as:** the quick check, after session 19: a workflow that reacts to each new item and four
  ways of finding out about it, each with a reason, and you pick the one that fits. About 3
  minutes a question. Easier than `a-argue-noticing`, since the options are written for you.

### `a-place-the-waiting-work`

- **serves:** `c-when-to-queue`
- **supports:** attempt
- **checks:** `c-when-to-queue`
- **artifact:** no external source. A described workflow, told in a short paragraph, that says how
  its work arrives and when its worker is available but not where the work waits, from this
  activity's bank or written live per the generator below. About 4 minutes a question.
- **verified:** 2026-11-04
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
  - whether losing some work matters, said through what the work is for (a
    display that each new reading replaces, or a request somebody is waiting on).
  Plus one irrelevant detail, said as plainly as the facts and bearing on no goal. The facts never
  use the words queue, waiting list, backlog, poll, hook, cron or trigger. **How pointed a fact may
  be:** each fact says what is kept, done or left behind ("the agent emails each reply and keeps no
  copy"; "each request is saved into the shared folder"), never what that does or doesn't let
  someone tell. A sentence such as "nothing shows which inquiries have been answered" draws the
  inference the learner is meant to draw, and is not used.

  **Facts kept to the case.** The list above is what a scenario may draw on, not what each must
  carry. A scenario states its case's defining fact or facts (named in each shape below), the
  facts that make the natural kind of place the natural one, the facts needed to show other
  places wrong, the one irrelevant detail, and nothing else that offers a tied reason for the
  accepted place that doesn't rest on a defining fact. A "good here" reason counts on its own, so
  a free-standing helpful fact would let a learner meet the case without its defining fact: in a
  `burst` scenario, "the office computer is never off" would let "a list the program keeps,
  because the computer is never off" earn full credit without the burst. So the facts that make a
  place work are worded to carry the case's defining fact, and any place reason drawn from them
  rests on it:
  - `unavailable`: the holding fact is tied to the worker's off hours ("the website keeps every
    request that comes in while Ana's laptop is off, with the time it came in"), and so is how
    soon a result is needed ("a reply on her next working morning is soon enough");
  - `burst`: the holding fact is tied to the burst ("the program that receives each sign-up as it
    arrives can pass only twenty a minute to the agent"; "the form keeps all three hundred
    sign-ups from the hour after the newsletter"). The scenario never says on its own that a
    machine is never turned off;
  - `no-queue`: the facts are the condition's own (for `always-ready`, that the machine is never
    turned off and each item takes a second; for `drop-ok`, that each reading replaces the last
    and the worker is turned off at times).
  Where showing another place wrong needs a fact that could also serve as such a reason, word it
  so that it only rules that place out, or leave that place out of the key's listed alternatives.

  **A question** reads: "Where, if anywhere, should this workflow's work wait until it can be done?
  Say why. Answer in two or three sentences." Free response, `type: free`. One question per
  scenario, asking only this.

  **Shapes**, each with the case it carries. The examples are illustrations, not bank items, and
  their domain (a bike repair shop) is used by no bank in this
  topic.
  **Kinds of queue, and the facts that make each the natural one.** Each `unavailable` or `burst`
  scenario has one natural kind, and its facts rule the others out as the simplest:
  - `source`: the source keeps every item and can list them by when they came in, so the new ones
    since the last run can be found; the workflow leaves nothing behind for a finished item (a
    reply is emailed and no copy kept), so neither files nor a log could say what is done.
  - `files`: each item lands somewhere that holds it but cannot say which items are finished or
    new (each request saved into a shared folder, with nothing marking which are done), and the
    workflow saves a file beside each finished item, so an item with no such file is waiting.
    The folder alone is not enough: it holds the items, but nothing in it marks which are finished.
    In a `burst` question, though, the folder named alone is ruled workable, as a place named only
    generically is, and the tutor asks how finished items are told apart.
  - `log`: as `files`, except that the workflow writes a line to a log for each finished item, so
    the waiting work is every held item not in the log.
  - `kept`: the source keeps nothing (an alert shown once and gone), and a program receives each
    item as it arrives, so it can add each one to a list of its own. A kept list needs something
    on to receive each arrival, so `kept` is used only in `burst`, where the receiving program is
    part of the burst fact ("receives each sign-up as it arrives"), never in `unavailable`.
  The key names both facts behind the natural kind: where the items are held, and what (if
  anything) says which are done. These patterns are for the writer; the scenario itself states only
  what is saved where, by the pointedness rule above (for `files`, "each request is saved into the
  shared folder" and "a reply file is saved beside each request answered", never "nothing marks
  which are done").

  - `unavailable` (`worker-unavailable`): work arrives at any hour, including when the worker is
    off (the laptop turned off overnight, the person away until Friday), and the worker keeps up
    with any arrivals when it is on. What goes wrong without a queue: work arriving while the
    worker is off is never done. The natural kind is `source`, `files` or `log`, never `kept`.
    Defining facts: the worker's off hours, that work arrives during them, and that the result can
    wait until the worker is next on. "Repair requests come in through the shop's website at all
    hours. The agent that answers them runs on Ana's laptop, which is on from about 8 a.m. to 6
    p.m. on weekdays and turned off the rest of the time. The website keeps every request that
    comes in while her laptop is off, with the time it came in. The agent emails a reply to each
    request; no copy of the reply is kept. A reply on her next working morning is soon enough."
    (Here only
    the source fits: nothing is left behind per request, and nothing is on
    overnight to add requests to a list.)
  - `burst` (`spread-out`): work arrives in a burst faster than the worker should take it (three
    hundred sign-ups in the hour after a newsletter goes out, against a provider that takes about
    twenty requests a minute). The worker is always a program or an agent on a machine that is
    never turned off, never a person, since a person is not always available; that is the writer's
    constraint, and the scenario never states it as a fact of its own (see the rule above). What
    goes wrong without a queue: the burst hits the worker all at once, past what it can take.
    Defining facts: the burst and the worker's limit, which the scenario always states in plain
    words. The natural kind is any of the four, its holding fact worded with the burst.
  - `no-queue` (`no-queue`): two variants, which the key names. `always-ready`: a quick program on
    a machine that is never off, with a few items an hour, each taking a second, so nothing ever
    has to wait. `drop-ok`: losing some items does no harm, because each is replaced by
    the next (a display showing the latest reading, a count that each update corrects); its worker is
    turned off at times, so `always-ready` doesn't hold. The key: no queue is needed, which
    condition holds and the fact that makes it hold, and why the other condition doesn't.

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
  photo picks, a school newspaper's reader letters, a community pool's lane bookings, a food
  truck's catering inquiries, a scout troop's permission slips, an apartment building's package
  notices, a volunteer translators' group's requests, a bird count's sighting reports. No domain
  from the other five question activities' lists, and no homework or grading workflow.

  **The key** gives the shape and the natural kind of queue, named concretely for this workflow
  ("the website's list of requests"), any other kind the facts make workable, the consequence
  without a queue and the sentence it rests on, and, for `no-queue`, which condition holds and why
  the other doesn't; the irrelevant detail; two or three generic reasons that would fail ("work
  might get lost", "a queue is safer", "it's good to keep a record"); one or two facts of this
  scenario that are true but have no bearing on where the work waits, which also fail ("the
  replies are signed with the shop's name"); and an example of each of the three kinds of tied
  reason below, for the place it accepts.

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
  one that passes the rule above), and gives a reason tied to this workflow of any of three kinds:
  - **what makes that place good here**: the fact that makes it work for this workflow's arrivals
    (the website keeps every request with its time, so the agent can find the night's requests in
    the morning);
  - **what would go wrong here without it**: requests arriving overnight never get a reply; three
    hundred sign-ups at once overrun the provider's limit;
  - **what would make a specific other place worse**: a fact that tells against a named other
    place (a list the workflow keeps would miss the night's requests, since nothing is on overnight
    to add them; doing nothing would lose every request that comes in while the laptop is off).
  A fact with no bearing on where the work waits is not a tied reason; nor is one resting on the
  irrelevant detail, or one the scenario's facts contradict. A place named only generically ("put
  them in a queue"), with nothing saying what holds the items, is ruled as a list the workflow
  keeps: workable in a `burst` question, not in an `unavailable` one. Half when the place is
  workable but the reason is generic, not tied, or missing, or when the reason is tied but the
  place is unworkable. None when the place is unworkable and the reason is generic, not tied, or
  missing, or when the answer says no place is needed.

  In a `no-queue` question the criterion's rule for nowhere applies: full when the answer says the
  work needn't wait and gives as the reason the condition that holds, that the worker is always
  available and never overloaded or that dropping some work is acceptable, tied to the fact that
  makes it hold (the program is on a machine that's never off and takes a second for each of a few
  an hour; each reading replaces the last). The `always-ready` condition has two halves, and the
  reason must give both (the worker is always available, and it is never overloaded). Half when:
  - it says no place is needed but the reason is generic, not tied, or missing, or names the
    condition that doesn't hold;
  - it says no place is needed with only half of the `always-ready` condition ("it never gets more
    than it can handle", with nothing about the worker always being available, or the reverse);
  - it proposes a place while correctly saying that one of the two conditions holds here;
  - it proposes a place with a "good here" reason that is true of this workflow (the form keeps
    every reading, so nothing would be lost), since a place is workable but not needed;
  - in `drop-ok`, it proposes a place for a loss that is real but harmless (keeping every reading
    so none is missed, when each is replaced by the next).
  None when it proposes a place and names a loss the facts rule out, or with a reason that is
  generic or not tied, or gives no reason.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works the illustration of the same shape aloud: says, of the facts the scenario states,
  when work arrives and when the worker is available, what already holds or leaves behind a
  record of the waiting work, which kind of queue that gives, and what would be lost without it.
  Only `unavailable` has an illustration above. For `no-queue` `always-ready` it works a made-up
  case of its own (a program on an office computer that is never off, turning each of a few emails
  an hour into a line on a sign-in sheet). For `burst` and `drop-ok` it otherwise makes up one of
  its own in this activity's style, in a domain no bank here uses, obeying the facts-kept rule. It may point to Where the work waits and
  When there's no queue in `tasks/read-triggers.md`.
- **doesn't show:** the workflow's facts are all in one short paragraph, so a pass doesn't show the
  learner would notice a fact they need is missing. Any workable kind of queue earns credit, so a
  pass doesn't show the learner would pick the simplest one, and in a `burst` question a list the
  workflow keeps passes even where something already holds the work, and so does the shared folder
  named alone, without saying how finished items are told apart. Each scenario carries one reason for a queue, so a
  pass shows nothing about weighing two at once. Nothing here asks how the queue is stored or what
  happens when the worker fails partway, which are later topics. Scenarios keep their facts to
  their case, but a learner may still bring in a reason from outside the scenario; such an answer
  is credited and counts toward the case, so a pass doesn't always show the learner used the
  case's defining fact.
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
- **verified:** 2026-11-04
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
  workflow already leaves behind for each finished item, whether losing some items
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

  **Facts kept to the case**, as in `a-place-the-waiting-work`: the scenario states the case's
  defining fact or facts, the facts that make the sound place the natural one (worded to carry the
  defining fact, as that activity's rule says), the facts each near-miss needs to be shown wrong,
  the one irrelevant detail, and nothing else that offers a tied reason for the sound place that
  doesn't rest on a defining fact. A fact a near-miss needs is worded so that it only rules that
  near-miss out: in a `burst` question, the fact that makes the worker-unavailable reason false is
  folded into the receiving fact ("the program that takes in sign-ups, at any hour, as they
  arrive, passes only twenty a minute to the agent"; in the log variant, "the program on the
  agent's computer saves each sign-up into the folder as it arrives, at any hour"), never a
  free-standing "the computer is never
  turned off", and never a sentence saying the sign-ups reach the agent itself as they arrive,
  which would describe a design with no queue; in an `unavailable` question, the limit and
  arrival rate that make the burst reason false are said together ("requests come a few an hour,
  well under the twenty a minute the agent's provider takes").

  **A question** is one multiple-choice question, `type: mcq`, with one goal, `c-when-to-queue`,
  and the case its shape carries. It reads "Where, if anywhere, should this workflow's work wait,
  and why?", then four numbered designs, each one sentence in the same frame: "<Where>, because
  <why>." Each place and each reason is said as briefly as its facts allow ("In the text line,
  asking it for new requests each run"; "because requests sent while the agent's computer is off,
  each with a listener waiting, would never be handled"), so an option runs to about 25 words.
  Brevity never drops the first why statement's "each with someone waiting on it" or its
  equivalent, which is what makes that statement false in `drop-ok`. The four are within ten words of each other in length. One is sound on both its
  place and its reason. The four cross two places with two reasons, so the sound one can't be found
  from the options alone:
  - In an `unavailable` or `burst` question, every place and every reason appears in exactly two
    options. The two places are the sound place and one unworkable
    place (chosen below), and the two reasons are the sound reason and the other queue reason,
    which the facts make false. The four options are sound place with sound reason (the answer),
    sound place with false reason, unworkable place with sound reason, and unworkable place with
    false reason. All four are coherent queue designs with queue reasons.
  - In a `no-queue` question, nowhere appears twice, once with the true no-queue reason (the
    answer) and once with the other no-queue reason, which the facts make false (`always-ready`:
    the items each have someone waiting on them; `drop-ok`: the worker is turned off at times).
    One place appears twice, a list the workflow keeps, once with each queue reason, both false by
    the facts: the first because the worker is never off (`always-ready`) or because no one is
    waiting on a reading the next replaces (`drop-ok`), the second because the arrivals stay well
    under the stated limit. So each of the two places appears twice, each time with a different
    reason, and each of the four reasons appears once.
  Exactly one option is right by the facts, and every question tests both the place and the reason:

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
    list, when nothing is on to add each arrival. Never one that merely does more than it needs to,
    and never one that `a-place-the-waiting-work` would accept as a newly kept file or log. A
    source-side wrong place (asking the source) is used only where the scenario says outright that
    the source keeps nothing. Which wrong place to use, by the sound place:
    - in an `unavailable` question (source or files), the wrong place is a list the workflow keeps,
      since nothing is on while the worker is off to add each arrival;
    - in a `burst` question with a kept list, the wrong place is asking the source, which the
      scenario says keeps nothing (an alert shown once);
    - in a `burst` question with a log, the scenario says the source keeps nothing and that the
      program on the agent's computer saves each item into a folder as it arrives, at any hour; the
      wrong place is asking the source.
    When the sound place is nowhere, the `no-queue` rule above applies instead.

  **Why** (the `<why>` slot), one of four statements put in this workflow's terms and making the
  same claim in every shape: otherwise <items> arriving while <worker> is <unavailable>, each with
  someone waiting on it, would never be handled; otherwise a burst of <items> would reach <worker>
  faster than <its limit>; nothing
  needs to wait, as <worker> is always available and never overloaded; nothing needs to wait, as
  losing some <items> does no harm here. Exactly one is true by the facts, and it is the
  shape's case. The false reasons are the ones the crossing above names, and the scenario states
  the fact that makes each false.

  **Shapes**, each carrying one case, which its rubric `cases:` line lists:
  - `unavailable` (`worker-unavailable`): work arrives while the worker's machine is turned off,
    and the worker can keep up with any arrivals when it is on; the sound why is the first
    statement.
  - `burst` (`spread-out`): work arrives in a burst past what the worker can take, and the worker's
    machine is never turned off; the sound why is the second.
  - `no-queue` (`no-queue`): the sound where is nothing; the sound why is the third or the fourth
    statement, by variant (`always-ready` or `drop-ok`, as in `a-place-the-waiting-work`). The
    facts rule out the other one: a `drop-ok` worker is turned off at times (so `always-ready` is
    false; it is never ruled out by being slow); an `always-ready` workflow's items each have
    someone waiting on them.
  In every shape exactly one of the four statements is true by the facts. The first is worded so
  that it holds only when the lost items matter: in a `drop-ok` scenario, whose worker is turned
  off at times, it is false, because no one is waiting on a reading that the next one replaces.

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
  place or its reason is wrong, or both, and the fact that shows it.
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
