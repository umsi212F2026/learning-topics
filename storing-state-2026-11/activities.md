# Activities: storing state

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

The initial study comes to about 40 minutes, inside the topic's 60-minute budget: about 13 for
`a-read-storing-state` (the reading is about 1,500 words, 7 or 8 minutes on its own), about 3 a
word for the five words, so 15, and meeting `c-choose-access`. Each scenario asks one access
question per party that writes to or queries the kept thing, each carrying the one case its
answer exercises (`edit`, `append-only` or `query`), and last a race question, carrying `race` or
`no-race`. So two scenarios can meet all five cases, for example a `hand-edit-runs-add` with a
query party (three party questions and its race question) and then only the race question of an
`everyone-adds`, since its party questions are no longer needed. That is five questions: the
first of a scenario takes about 3 minutes with the reading, each later one about 1 or 2, so about
12 minutes through `a-assign-access` and about 10 through `a-pick-access`. The rest of the hour is
room for missed questions.

Every question asks for one thing and works on its own as a bank question, never relying on a
tutor's follow-up to collect the rest of an answer. A scenario's party questions and its race
question are always separate `###` questions, never parts of a compound, and the race question
comes last. No question's text gives away another's answer: a party question names only its own
party and the kept thing, never another party's kind, and none says whether anyone writes at the
same time as anyone else. A free-response question's fixed text says
how to answer. No question asks for a reason, how a race should be handled, or which file format
or storage to use, and no answer depends on knowing any format. Learner-facing text states the
task, never the scoring.

In this topic's banks and live questions, every workflow is a made-up one described in words,
running on one person's laptop, with at least one step done by an agent following a skill file,
and one thing it keeps that two or three parties (the person, programs, the agent) touch. Never
the learner's own app, repo, machine or project; never an internship or job postings tracker;
never the reading's grading example (its TA, grades sheet or posting program) or any other
homework or grading workflow. Every scenario states every fact its answers need. No scenario
contains code, a query, SQL or a command, and none says how the kept thing is stored: no file
format, file type, database or storage product is named, and the kept thing is called by what it
holds ("the pattern list", "the sightings record"). No real product, site or brand is named other
than Git, a spreadsheet app and a text editor, which the reading names; a source is "a food blog
she follows", "the local classified ads site". The topic's words append-only, query, race
condition and single source of truth are used in question text where they fit, with no gloss.
Least privilege is a word of this topic only, not part of its capability, so no question turns on
narrowing anyone's access.

## Check notes


## Goals

| id                | Goal | Criterion: what gets examined, and what counts |
| ----------------- | ---- | ---------------------------------------------- |
| `o-orientation`   | get the shape of this area before working on any particular part of it | `orientation` |
| `c-choose-access` | decide who gets which kind of access to each thing a workflow keeps | given a described workflow and one thing it keeps, names every person, program or agent that should access it and which kind of access each needs (read it through, query it, edit it, or only append to it), and says whether there is a danger of a race condition. The facts that bear on it include who needs to see or change it, whether several runs or entities may write to it at the same time, and whether anyone needs to find particular records without reading all of them. Cases: `edit`, `append-only`, `query`, `race`, `no-race` |

## Coverage

| goal              | checks | notes |
| ----------------- | ------ | ----- |
| `o-orientation`   | `a-read-storing-state` |       |
| `c-choose-access` | `a-assign-access`, `a-pick-access` |       |

---

## Activities

### `a-read-storing-state`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** a reading the course wrote for this topic, `tasks/read-storing-state.md` in this
  folder, "What a workflow keeps, and who gets to touch it" (about 1,500 words, about 7 or 8
  minutes). No external reading is used: the instructor wanted a course-written one. It continues
  the made-up example of the workflow design and triggers readings, a teaching assistant who grades
  about 200 homework submissions a week: a program downloads each submission, an agent following a
  skill file drafts a score and feedback, and the TA reviews the drafts before grades are posted.
  Sections: an untitled opening (how things are stored was left for later; the decision here is
  who touches each kept thing and how, while formats and databases are the agent's); What a
  workflow stores (state, and the five things the TA's workflow keeps); Four kinds of access
  (reading it through, querying it, editing it, append-only, with a log file as the classic
  append-only store); Who, and which kind (the grades sheet's four parties and the kind each needs,
  why that drives format and storage, and narrowing access as least privilege); When two writers
  collide (the posting program saving over the TA's three changes, the two things a race needs, the
  two ways to prevent one, Git's merge conflict as a race detected rather than prevented, and no
  danger when writes never overlap); One place for each thing (a score kept in two places, and the
  single source of truth); Telling your agent (a table from each access decision to what the
  storage has to do, and telling an agent requirements instead of a format). Words in place, each
  in bold where introduced: query, append-only (as the label of the fourth kind of access), least
  privilege, race condition, single source of truth. Also in bold, though none is a word of this
  topic: state, the other three kinds of access, log file, the grades sheet parties' kinds, merge
  conflict. It names no real product other than Git, a spreadsheet app and a text editor, and says
  nothing about storing things in the cloud or what happens when a step fails.
- **learner does:** reads the page once, top to bottom, and stops once, in Who, and which kind,
  after "Take the grades sheet." and before the four bullets, answering before reading on ("I don't
  know yet" is an honest answer): who touches the grades sheet, and which kind of access does each
  need? The bullets give the page's own answer, which the learner then reads. Then the close, about
  2 minutes, with the reading still beside them: answers the one question the tutor puts: with this
  page beside you, could you now take a short description of a workflow and one thing it keeps, say
  who should get which kind of access to it, and say whether there is a danger of a race condition?
- **tutor role:** explainer
- **tutor does:** puts the reading in front of the learner by opening the file
  `tasks/read-storing-state.md` from the topic folder on the local filesystem, so the learner's
  agent shows it formatted in a sidebar; does not paste it into the chat. Stays quiet through the
  reading except at the stop and when asked. At the stop, takes the learner's answer first and
  replies with one near-miss question rather than a verdict, then lets the learner read on to the
  page's own answer. What the tutor looks for is a party from the workflow as the page has
  described it so far (the download program, the agent, the TA) given a kind from Four kinds of
  access that fits what it does; the answer need not match the bullets, and the posting program
  appears only in them. An answer giving every party "edit", or naming no kind, gets one near-miss
  question ("does the download program ever need to change a row that's already there?"). Does not
  set or rehearse any word question from `a-words`: does not ask the learner to define any of the
  five words, to say what separates a word from its nearest confusable in goals.md (single source
  of truth and a backup, append-only and read-only, query and search, race condition and merge
  conflict, least privilege and authorization), or to correct a misused sentence. Does not set or
  rehearse a question from this topic's capability activities for any workflow beyond the one the
  reading works through; if the learner asks how to do that, says that is what `a-assign-access`
  and `a-pick-access` are for. Says that building a workflow is Problem Set 5's work, not this
  topic's; that choosing a format or storage is left to the agent, so the Telling your agent table
  is there for Problem Set 5 and no question turns on it; that no question asks how a race should
  be handled, only whether there is a danger of one; and that what happens when a step fails comes
  in a later topic. At the close, puts the readiness question as written above and rules on the
  answer.
- **done when:** criterion met. The bar for this goal is did it once and help is expected
  throughout, so the ruling is on the learner's answer to the readiness question, not on the stop
  or on whether the tutor thinks they are ready. A plain yes is `criterion: met`. A hedge, with no
  plain no, is `criterion: unclear`: ask which part feels shaky, go over its section once more
  (Four kinds of access and Who, and which kind, or When two writers collide), and put the question
  again. A second hedge stays `unclear`: the tutor offers one of the capability activities with
  help as the next step. A plain no is `criterion: not met`: record it, ask what is missing, and
  offer to go back over the section that bears on it; don't put the question again in the same
  sitting. This goal isn't required, so a no never blocks anything else the learner wants to try.
- **worked example:** n/a
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. It
  shows nothing about the five words, which have their own supply in `a-words`, and nothing about
  the capability: the reading works one example, the stop is helped, ungraded and answered just
  before the page gives its own answer, and the readiness question asks only whether the learner
  thinks they could do the same. The reading is one course-written page built on one grading
  workflow, so it shows nothing of a workflow in another domain, such as the personal trackers the
  capability activities use.
- **offer as:** this topic's orientation: one short page the course wrote, following the same
  grading workflow as the last topics' readings, from what a workflow keeps, through the four kinds
  of access and who needs which, to when two writers collide and keeping one place for each thing.
  One short stop and a one-question close. About 13 minutes.

### `a-assign-access`

- **serves:** `c-choose-access`
- **supports:** attempt
- **checks:** `c-choose-access`
- **artifact:** no external source. A described personal workflow and one thing it keeps, told in a
  short paragraph, with one question per party and then a race question, asked one at a time, from
  this activity's bank or written live per the generator below. About 3 minutes for a scenario's
  first question, with the reading, and 1 or 2 for each after.
- **learner does:** reads the scenario, then answers its questions one at a time: for each party
  asked about, says in a short phrase or a sentence what kind of access to the kept thing it needs;
  last, says whether there is a danger of a race condition on it, and if so between which writers.
- **tutor role:** examiner
- **tutor does:** sets each question as served, in file order, without rewording it or hinting;
  never names the cases, which fact matters, or which kind or verdict the key expects. Gives help
  whenever it is asked for, and records the attempt as helped. When the generator is run live,
  writes the key and the case into the record before showing each question. Labels the attempt
  with the question's path, or `a-assign-access/<shape>/<party>` or `a-assign-access/<shape>/race`
  when run live, and records the case with `--cases`. Rules each
  question from it alone, by the credit rules below; no follow-up question collects part of the
  answer. If the learner asks how a race should be handled, or what format or storage would fit,
  says that is the agent's to choose and this question doesn't ask it.
- **done when:** the criterion met with no help, case by case: a full-credit answer passes the case
  its question carries.
- **generator:** **A scenario** is one made-up personal workflow on one person's laptop, told in one
  paragraph of running prose, six to ten sentences, in the third person about that person, who is
  named. It says what the workflow is for and what its steps are, in plain words; at least one step
  is done by an agent following a skill file the person wrote. At least half of a bank's scenarios
  are a small personal tracker with acquire, assess and extract steps (a program collects items
  from somewhere, an agent judges each one, some step pulls out fields); the rest are other personal
  workflows (sorting family photos, keeping a household's bills). It names one thing the workflow
  keeps, by what it holds, and two or three parties that touch it, each with a short handle the
  questions can use ("the collector", "the judging agent", "Mira"). Mixed through the paragraph,
  never under labels, are these facts:
  - for each party, what it does with the kept thing, as a need in plain words ("adds an entry for
    each pattern worth keeping", "changes an entry's status to 'knitted'", "picks out only the
    entries marked 'queued'", "goes over the whole list"), never with the words read through,
    query, edit, append or append-only;
  - for each party that only adds, why adding is all it should do: other writers write while it
    does, or past entries must stay as they were ("he wants every past sighting kept as it was, to
    see how prices move");
  - how many entries the kept thing holds, wherever a party needs only particular entries (always
    thousands) or every entry;
  - for every writer, when it writes: when its runs start and how long one takes, or when the
    person makes changes ("most evenings", "only on Sunday afternoons").

  **How pointed a fact may be.** A fact states times, durations and actions. It never says what kind
  of access anyone needs, what a collision would do, or that there is or isn't a danger, and never
  uses the words race, collide, overwrite or conflict. A Medium scenario may say plainly that two
  writers write at once ("on busy days a run is still going when the next one starts"; "she often
  makes changes while a run is going"); a Hard one gives only the times, for the learner to compare.

  **Parties.** Each party's need is exactly one kind: a party that changes entries already there
  (fills in a field, changes a status, deletes one) is keyed edit; one that only adds new entries,
  append-only; one that needs only particular entries from thousands and changes nothing, query; one
  that takes in every entry and changes nothing, read it through. No party both adds entries and
  changes ones already there, and no party that changes entries has to find them among thousands
  (the person picks hers as she looks the list over; an agent changes every entry its run checks).
  A step that doesn't touch the kept thing may appear only where the paragraph says what it touches
  instead ("saves each post into a folder"); no question is asked about it. A race scenario has
  exactly one pair of writers in danger, and a no-race scenario none.

  **Questions**, each its own `###` question under the scenario's shared setup, never parts of a
  compound, in this order: one party question for each party keyed edit, append-only or query, in
  the order the paragraph introduces them, then the race question last. A party keyed read it
  through gets no question, since it would carry no case; it stays in the scenario as a reader that
  the race question's pairs can include. No question's text names another party's kind or says
  whether any two parties write at the same time.

  **A party question** reads: "What kind of access to the <kept thing> does <party> need? Answer in
  a short phrase or a sentence." It lists no kinds. Free response, `type: free`. Its rubric
  `cases:` line lists the one case its key kind exercises: `edit`, `append-only` or `query`.

  **The race question** reads: "Is there a danger of a race condition on the <kept thing>? If there
  is, say between which writers. Answer in one or two sentences." Free response, `type: free`. It
  carries `race` or `no-race`, by shape.

  **Shapes**, each with the case its race question carries; its party questions carry the access
  cases named. Between them every case is carried.
  - `hand-edit-runs-add` (`race`): the person changes entries by hand at times that include when
    runs happen, and the runs only add entries. Parties: the person (edit), the adding step
    (append-only, because the person writes while it does), and optionally a third party that
    queries or reads it through. The pair in danger: the person and the adding step's runs. Access
    cases `edit`, `append-only`, and `query` when there is a query party.
  - `runs-overlap-change` (`race`): runs of one step start on a schedule and some last past the next
    start, and each run changes the same entries (an agent updating every tracked item's current
    price and verdict, where only the current one is wanted). Parties: that step (edit), and a
    person who reads it through or a program that queries. The pair in danger: one run of the step
    and the next. Access cases `edit`, and `query` when there is a query party.
  - `everyone-adds` (`no-race`): two or more writers only add, and some of them write at the same
    times (two collectors whose runs coincide, or runs that last past the next start). A third
    party queries or reads it through. Access cases `append-only`, and `query` when there is a query
    party.
  - `takes-turns` (`no-race`): two writers, at least one of them changing entries, whose stated
    times never meet (the person changes entries only on Sunday afternoons, and the run starts at 6
    a.m. and is done by 6:15; or each run is started by hand once the last has finished). Access
    cases `edit`, and `append-only` when one writer only adds.

  **Illustrations**, not bank items; their domains are used by no bank in this topic.
  - `hand-edit-runs-add`, Medium: "Mira keeps a list of knitting patterns she might make, now over
    three thousand entries. Every hour from 8 a.m. to 10 p.m., a program on her laptop saves new
    posts from six pattern blogs she follows into a folder. Then the judging agent, following a
    skill file Mira wrote, reads each new post, decides whether it suits her skill level, and adds
    an entry to the pattern list for each one worth keeping, with its yarn weight and skein count.
    A run takes about ten minutes. Mira opens the list most evenings, often while a run is going,
    and changes entries' statuses to 'queued' or 'knitted', or fixes a skein count the agent got
    wrong. Every Saturday morning the shopping program picks out only the entries marked 'queued'
    and makes her a yarn shopping list." Key: the judging agent, append-only; Mira, edit it; the
    shopping program, query it. The download program never touches the list. Race: yes, between
    Mira and the judging agent's runs. Ruled out: the shopping program (it only reads), and one run
    and the next (a ten-minute run, once an hour). Questions, in order: the judging agent
    (`append-only`), Mira (`edit`), the shopping program (`query`), race (`race`).
  - `everyone-adds`, Hard: "Theo collects back issues of an old comic series. Two collector programs
    on his laptop each check a different seller's site for new listings: one starts every 20
    minutes, the other every 30, and each run takes about four minutes. Each adds every new listing
    it finds to the sightings record, with the price and when it was seen, and Theo wants every
    past sighting kept as it was, to see how prices move. The record now holds about twelve
    thousand sightings. Each evening at 9 the deal agent, following a skill file listing the issues
    Theo wants and what he would pay, picks out only that day's sightings under his price and
    writes him a short note about them." Key: each collector, append-only; the deal agent, query
    it. Race: no. Both collectors start on the hour and on the half hour, so they do write at the
    same time, but both only add. Questions, in order: the 20-minute collector (`append-only`), the
    30-minute collector (`append-only`), the deal agent (`query`), race (`no-race`). A bank scenario
    with two parties of the same kind may ask about only one of them.

  **How hard.** Medium when the timing is said plainly (as above) and each party's need is said in
  words close to its kind. Hard when the times must be compared (a run every hour that on some days
  takes seventy minutes; the person changes entries "after dinner, until about nine", against runs
  every hour from 7 a.m. to 11 p.m.), when writers that do write at once only add, as in the comics
  illustration, or when an adding party's reason to only add is that past entries must stay as
  they were. The question wording is unchanged.

  **Spread across the bank.** A bank is six scenarios: `hand-edit-runs-add` and `everyone-adds`
  twice each, `runs-overlap-change` and `takes-turns` once each, half of them Hard. That is six race
  questions and about fifteen party questions, at least three each carrying `edit`, `append-only`
  and `query`. A query party appears in at least three scenarios, at least one race and one
  no-race, and a read-through party in at least two. At least three scenarios are trackers with acquire, assess
  and extract steps. When the generator is run live, the tutor picks each next shape and its parties
  to carry a case the learner hasn't passed.

  **Domains** vary by scenario, none repeating within the bank: a home cook's recipes from food
  blogs she follows, a used-bike watch on the local classified ads site, a houseplant watering
  log, a podcast listening list, a birder's sightings from the regional birding mailing list, a
  board-game price watch, a household's bills from emailed statements, a family's photo sorting.
  No domain from `a-pick-access`'s list.

  **The key**, per question. For a party question: the party's kind, the sentence that settles it,
  and each other kind with the sentence that rules it out (an adding party's reason to only add
  rules out edit; that it writes rules out read it through and query; that a changing party changes
  entries already there rules out append-only; that a query party needs only particular entries
  among thousands rules out read it through). For race: the verdict; for `race`, the pair in danger, the ways of naming it that count
  (for the runs in `hand-edit-runs-add`, the adding step, its agent or "the runs"; in
  `runs-overlap-change`, "two runs of the price checker" or "one run and the next"), and the
  sentences giving each writer's times; and each other pair of parties with the fact that rules it
  out (one only reads, both only add, their times never meet).

  Credit, party question: full when the answer names the key kind, in any words that clearly name
  it ("adds only" is append-only, "looks up the ones it needs" is query, "changes entries" is edit).
  For an editing party, "reads it and edits it" is full, since changing an entry means seeing it.
  None when it names a different kind, or offers two kinds without committing ("edit or
  append-only"). There is no half.

  Credit, race question: in a `race` question, full when the answer says yes and names the pair in
  danger; half when it says yes but names no pair, a pair the facts rule out, or the right pair
  together with one the facts rule out; none when it says no. In a `no-race` question, full when it
  says no; none when it says yes. The verdict is what is ruled: a reason given alongside it is not
  marked, and an answer that commits to neither yes nor no is none.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works the illustration of the nearest shape aloud: for a party question, what that party
  does with the kept thing and which kind that is; for the race question, each writer's times, which writers write at once, and
  whether one of them changes entries already there. It never adds a fact the illustration leaves
  out. It may point to Four kinds of access, Who, and which kind, and When two writers collide in
  `tasks/read-storing-state.md`.
- **doesn't show:** each party question names its party, so a pass doesn't show the learner would
  name on their own every party that should access the kept thing, which the criterion asks;
  nothing here checks that part. Every scenario also gives every writer's times, so a pass doesn't
  show the learner would find a party or a timing nobody mentioned, as their own Problem Set 5
  workflow will make them. A read-through party is never asked about, so "read it through" is
  never a right answer. No reason is asked, so a pass, especially on a `no-race` question, can be
  a guess. Nothing checks least privilege. Each scenario has at most one pair in danger, so a pass
  shows nothing about finding two. Nothing checks turning the decisions into storage requirements
  for the agent, the reading's last section.
- **offer as:** the write-it-yourself check: a short description of a personal workflow and one
  thing it keeps; you say what kind of access each party needs, one party at a time, then whether
  there is a danger of a race condition. About 3 minutes for a scenario's first question and 1 or 2
  for each after. Harder than `a-pick-access`, since you name the kinds and the writers yourself.

### `a-pick-access`

- **serves:** `c-choose-access`
- **supports:** attempt
- **checks:** `c-choose-access`
- **artifact:** no external source. A described personal workflow and one thing it keeps, its facts
  set out one to a sentence, with one four-choice question per party and then a four-choice race
  question, asked one at a time, from this activity's bank or written live per the generator
  below. About 2 or 3 minutes for a scenario's first question, with the reading, and about 1 for
  each after.
- **learner does:** reads the scenario, then for each party asked about picks which of the four
  kinds of access it needs, and last picks which of four answers about a race condition is right.
- **tutor role:** examiner
- **tutor does:** as `a-assign-access`'s, except that it labels a live run
  `a-pick-access/<shape>/<party>` or `a-pick-access/<shape>/race` and rules from the rubric's
  `answer`. Never says what is wrong with an option before the learner has chosen.
- **done when:** the criterion met with no help, case by case. Each question gets one ruling: the
  sound option passes the case the question carries, and the others pass none. There is no half
  credit.
- **generator:** **A scenario** uses `a-assign-access`'s shapes, party rules, pointedness rule and
  question order (one question per party keyed edit, append-only or query, none for a read-through
  party, then the race question last, each its own `###` question, never a compound), and its facts
  are not running prose. After one or two sentences saying what the workflow is for
  and what its steps are, a short paragraph headed "About this workflow:" gives the facts one
  sentence each: what each party does with the kept thing, why each adding party should only add,
  how many entries it holds where that bears, and each writer's times, and nothing else.

  **A party question** reads "What kind of access to the <kept thing> does <party> need?", then four
  numbered choices, always in this order: "Read it through", "Query it", "Edit it", "Only append
  to it". `type: mcq`. Exactly one is right by the facts, and the scenario states the fact that
  rules out each other one, as listed under the key in `a-assign-access`. The question carries the
  one case its answer exercises: `edit`, `append-only` or `query`.

  **The race question** reads "Is there a danger of a race condition on the <kept thing>?", then four
  numbered options: "No, there is no danger of a race condition." and three of the form "Yes,
  between <writer> and <writer>." `type: mcq`. One run and the next run of a step count as a pair
  ("Yes, between one run of the price checker and the next"). In a `race` question, one yes names
  the pair in danger; one names a pair including a party that only reads; one names a pair that
  both only add or whose times never meet. In a `no-race` question, "No" is the answer and all three
  yes options name pairs the facts rule out, at least one of them a pair that does write at the
  same time but only adds, or, in `takes-turns`, the two writers whose times come close. Every party
  in an option is one the scenario names. The question carries `race` or `no-race`, by shape.

  **Example**, the knitting illustration in `a-assign-access` set this way. Three party questions,
  in order: "What kind of access to the pattern list does the judging agent need?" (answer 4, Only
  append to it, `append-only`), "... does Mira need?" (answer 3, Edit it, `edit`), "... does the
  shopping program need?" (answer 2, Query it, `query`). Then the race question, whose options are "No, there is no danger of a race
  condition"; "Yes, between Mira and the judging agent's runs" (the answer); "Yes, between the
  judging agent's runs and the shopping program" (the shopping program only reads); "Yes, between
  one run of the judging agent and the next" (a run takes ten minutes, once an hour).

  **How hard**, as in `a-assign-access`. The question wording is unchanged.

  **Spread across the bank.** A bank is six scenarios, with `a-assign-access`'s spread of shapes,
  parties and party questions. A party question's choices are in a fixed order, so its answer's
  position follows from its kind and needs no spreading. Across the six race questions, the sound
  option sits in at least three different positions, "No" in more than one, and the order of the
  near-misses varies.

  **Domains** are this activity's own, none repeating within the bank: an amateur astronomer's
  observing list, a newsletter reading list, a gardener's seed orders, a vintage camera price
  watch, a trail-conditions tracker from hiking forum posts, a library holds list, a record
  collector's wish list, a family's scanned recipe cards. No domain from `a-assign-access`'s list.

  The rubric gives the `answer` (the 1-based choice) and, in a `tutor note`, the sentence that
  settles the sound option and, for each near-miss (each other kind, or each other pair), the fact
  that rules it out. Credit: full for the sound option; none for the others.
- **worked example:** shown only as help when asked for, which records the attempt as helped. As
  `a-assign-access`'s, then the tutor sets one party question and the race question for the same
  illustration in this activity's style and goes through the options aloud, saying for each
  near-miss which fact rules it out.
- **doesn't show:** the learner picks among four options rather than writing one, so a pass doesn't
  show they would name the kinds or the pair themselves. Each party question names its party, so
  nothing here checks that the learner would name every party that should access the kept thing,
  which the criterion asks. A read-through party is never asked about, so "Read it through" is
  never the right choice, and a learner who notices can guess right a third of the time rather than
  a quarter. The race options name the candidate pairs, so a pass doesn't show the learner would
  find the pair unprompted. The facts are laid out one to a sentence under a heading, so a pass
  doesn't show the learner would find them in a looser description; `a-assign-access` gives them
  as running prose.
- **offer as:** the quick check: a short personal workflow and one thing it keeps, then the kind of
  access each party needs and an answer about a race condition, each picked from four. About 2 or
  3 minutes for a scenario's first question and about 1 for each after. Easier than
  `a-assign-access`, since the options are written for you.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
