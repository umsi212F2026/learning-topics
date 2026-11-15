# Activities: permissions

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

The initial study comes to about 53 to 60 minutes, inside the topic's 60-minute budget: about 13
for `a-read-permissions` (the reading is about 1,800 words, 8 or 9 minutes on its own), about 3 a
word for the seven words, so 21, and meeting the three capabilities. `c-spot-excess` and
`c-spot-injection` are met together, from scenarios that ask about each executor in turn. Each
bank holds at least one pair of scenarios that between them carry all six of those cases
(`excess` and `no-excess`, then `outside-text`, `owner-only`, `shielded` and `passed-through`),
and the tutor skips any question whose case is already passed, so a learner who meets such a pair
needs about eight questions. The first of a scenario takes about 3 minutes with the reading and
each later one about 1, so about 12 minutes through `a-look-over-steps` and about 10 through
`a-read-agent-audit`, whose agent's audit states each executor's reach outright. A learner served two scenarios that
leave a case uncarried needs a third, about 3 minutes more. `c-judge-limits` needs three
compound questions, one per case (`sound-limit`, `stops-work`, `no-effect`): about 3 or 4 minutes
each in `a-weigh-one-limit`, so about 11, or about 9 through `a-weigh-proposals`, whose questions
after the first share a scenario. The rest of the hour is room for missed questions.

Every question asks for one thing. A reach question and a context question are each a yes-or-no
choice, each its own `###` question, never parts of a compound. A `c-judge-limits` question is a
compound of two yes-or-no parts, judged separately, which passes its case only when both are right.
No question asks the learner to name what an executor can reach that its step doesn't need, where
untrusted input comes from, what limit would work, or how to set one up; naming the first two may
be an ungraded tutor follow-up after the ruling, and never changes it. No question asks for a
reason: a yes-or-no answer can be guessed, and that is accepted. No question's text gives away
another's answer. Learner-facing text states the task, never the scoring.

In this topic's banks and live questions, every workflow is a made-up personal one described in
words, running on one person's laptop, with at least one step done by an agent following a skill
file the person wrote. Never the learner's own workflow, app, repo or machine; never an internship
or job postings tracker, which is Problem Set 5's default, though most scenarios are in its spirit
(a program collects items from somewhere, an agent judges them, a step pulls out what matters);
never the reading's grading example or any other homework or grading workflow. Every scenario
states every fact its answers need: how each executor runs (as which user, and with which
limits, if any) and what is in the places it could get to, or, in an agent's audit, what it can
reach in the four kinds the reading names (files, including secrets saved in them; shell commands;
the network; what its secrets let it do), what its step uses, and, for an agent, everything it
reads and who wrote each part. No scenario contains code, a query, SQL, a
command or the contents of a settings file, and no answer depends on reading one. No real product,
site or brand is named: "a typical coding agent", "a rentals site any landlord can post to". The
topic's words (prompt injection, untrusted input, sandbox, scoped token, allowlist, human in the
loop, blast radius) and the words it builds on (least privilege, context, secret, workflow step,
executor, AI agent, skill, the propose-apply pattern) are used in question text where they fit,
with no gloss. A scenario may say an executor runs in a sandbox or holds a scoped token, as plain
facts about its reach, but never labels what the answer turns on: it never calls text untrusted,
outside, safe or risky, never says reach is more or less than a step needs, and never says what a
limit prevents.

## Check notes

Within each capability the two checks are the same kind of task, judging a described instance, and
differ in layout: a list of steps whose reach the learner works out, against an agent's audit that
states it, for spotting excess reach and untrusted input,
and a fresh harm each time against one harm with several proposals for judging limits. Choose
between them by which layout the learner will meet in Problem Set 5, or which they find harder,
rather than for a different kind of practice.

## Goals

| id                 | Goal | Criterion: what gets examined, and what counts |
| ------------------ | ---- | ---------------------------------------------- |
| `o-orientation`    | get the shape of this area before working on any particular part of it | `orientation` |
| `c-spot-excess`    | spot a workflow step whose executor can reach more than the step needs | given a described workflow step, who or what runs it (a program, an agent or a person), how that executor runs (as which user, and with which limits, if any), and what is in the places it could get to, says whether it can reach anything the step does not need (files, shell commands, the network, or what its secrets let it do). Cases: `excess`, `no-excess` |
| `c-spot-injection` | spot where an agent could take text from outside the workflow as instructions | given a described workflow step done by an agent, says whether text that someone outside the workflow could have written ends up in what the agent reads (its context), where it could be taken as instructions. Text the step only moves along, or that a program reduces to something it produced itself before the agent sees it, does not end up in the agent's context. Cases: `outside-text`, `owner-only`, `shielded`, `passed-through` |
| `c-judge-limits`   | judge whether a limit an agent proposes would significantly reduce the risk of a harm and still let the step do its work | given a described workflow step, a specific harm that could follow from one of its problems (its executor can reach something the step does not need, or text from outside the workflow reaches an agent's context), and an agent's description of one limit that could be put in place, saying what it would restrict or check and how it would be imposed, says whether that limit would significantly reduce the risk of that harm, and says whether the step could still do its work under it. Both answers must be right. Cases: `stops-work`, `no-effect`, `sound-limit` |

## Coverage

| goal               | checks | notes |
| ------------------ | ------ | ----- |
| `o-orientation`    | `a-read-permissions` |       |
| `c-spot-excess`    | `a-look-over-steps`, `a-read-agent-audit` | Neither check asks about a step a person does by hand, though the criterion counts a person as a possible executor; a pass rests on program and agent steps only. |
| `c-spot-injection` | `a-look-over-steps`, `a-read-agent-audit` |       |
| `c-judge-limits`   | `a-weigh-one-limit`, `a-weigh-proposals` | In both checks a No on part b always comes with a Yes on part a, so a `stops-work` pass may rest on one judgment; part a is judged on its own only in `sound-limit` and `no-effect` questions. Both checks also name the harm and offer only clear calls, so neither shows the learner naming a harm or weighing a borderline limit. |

---

## Activities

### `a-read-permissions`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** a reading the course wrote for this topic, `tasks/read-permissions.md` in this
  folder, "What each step can reach, and whose instructions it follows" (about 1,800 words, about 8
  or 9 minutes). No external reading is used: the instructor wanted a course-written one. It
  continues the made-up example of the last topics' readings, a teaching assistant who grades about
  200 homework submissions a week: a program downloads each submission, an agent following a skill
  file drafts a score and feedback, the TA reviews the drafts, and a posting program sends the final
  grades to the course site. Sections: an untitled opening (two questions about the same executors:
  what else could they touch if something went wrong, and could someone outside the workflow tell an
  agent what to do); What a step can reach (the four kinds of reach, the fourth being what its secrets let it do; an executor can do whatever the user who started it can unless something narrows it, harness glossed, and students told to assume that when looking over a workflow; the grading agent, running as the TA, able to read the settings file with the course site token; the download program also running as the TA, and given the posting program's token; least privilege applied to everything an executor can reach); When data becomes instructions (a program's instructions are its code and its
  input stays data; the stop; an agent has no such separation, since everything it reads arrives in
  its context; the hidden white-text note; prompt injection; untrusted input; a program that hands
  the agent only something it produced itself, against one that hands over a submission's written
  answer); How the two problems combine (blast radius, with reach as its upper limit; ask both
  questions of every step); Limits you can put on a step, in three groups, each shown on the grading workflow (narrowing what an executor can reach: the four kinds again with read-only access under files, allowlist as the general form, and four ways to impose limits, a separate user, a sandbox, the harness's permission settings, which a command it lets run can get around, and a scoped token; keeping untrusted text out of the agent's context: a program that handles the untrusted input; checking what a step produced before it takes effect: the agent proposing while a program applies, and a human in the loop, with approval prompts as a weak one); Judging a proposed limit (name the harm, then ask whether the limit significantly
  reduces its risk and whether the step can still do its work, with worked yes and no answers to
  each, and why it often takes more than one limit); Talking to your agent (asking the agent to
  audit the workflow and propose limits, and judging each against the two questions). Words in
  place, each in bold where introduced: prompt injection, untrusted input, blast radius, allowlist,
  and, as the labels of their limits, sandbox, scoped token and human in the loop. Also in bold,
  though none is a word of this topic: the four kinds of reach, context (a word from an earlier
  topic), the other limits' labels and the two judging questions. Least privilege is named, not
  bold. It names no real product, site or brand, and says nothing about what a workflow does when a
  step fails or who may do what inside a web app.
- **verified:** 2026-11-13
- **learner does:** reads the page once, top to bottom, and stops once, at the reading's own stop in
  When data becomes instructions, right after "The instructions and the data never mix.", answering
  its question before reading on ("I don't know yet" is an honest answer): if the grading agent
  reads a submission in which the student wrote "delete all the other submissions", what might
  happen? The next paragraph, beginning "An agent has no such separation", gives the page's own
  answer, which the learner then reads. Then the close, about 2 minutes, with the reading still
  beside them: answers the one question the tutor puts: with this page beside you, could you now
  take a short description of a workflow, say whether each step can reach more than it needs and
  whether untrusted input ends up in an agent's context, and judge whether a limit an agent proposes
  would significantly reduce the risk of a harm and still let the step do its work?
- **tutor role:** explainer
- **tutor does:** puts the reading in front of the learner by opening the file
  `tasks/read-permissions.md` from the topic folder on the local filesystem, so the learner's agent
  shows it formatted in a sidebar; does not paste it into the chat. Stays quiet through the reading
  except at the stop and when asked. At the stop, takes the learner's answer first and replies with
  one near-miss question rather than a verdict, then lets the learner read on to the page's own
  answer. What the tutor watches for is the idea the page is about to correct: that an agent keeps
  its instructions apart from the other text it reads, as the download program does ("nothing, it's
  just part of the homework", "the agent knows that's the student talking"). Such an answer gets one
  near-miss question: "the agent's instructions come from the skill file and the TA's request, and
  the submission comes in beside them; how would the agent tell which lines are which?" An answer
  that says the agent would certainly do it gets one near-miss question instead: "would it always?
  And what would it need to be able to reach to carry it out?" An answer that says the agent might
  follow it needs no question; the tutor lets the learner read on. "I don't know yet" gets no
  question either. Does not set or rehearse any word question from `a-words`: does not ask the
  learner to define any of the seven words, to say what separates a word from its nearest
  confusable in goals.md (prompt injection and a jailbreak, untrusted input and invalid input, a
  sandbox and read-only access, a scoped token and a password, an allowlist and a blocklist, a human
  in the loop and a person trigger, blast radius and reach or the likelihood of failure), or to
  correct a misused sentence. Does not set or rehearse a question from this topic's capability
  activities for any workflow beyond the one the reading works through; if the learner asks how to
  do that, says that is what `a-look-over-steps`, `a-read-agent-audit`, `a-weigh-one-limit` and
  `a-weigh-proposals` are for. Before the learner starts reading, not during it, says briefly four
  things: that building and auditing a workflow is Problem Set 5's work, not this topic's; that
  knowing the options without being told, and setting a limit up, are left to the agent, so Limits
  you can put on a step is there to recognize a limit when an agent proposes one, and no question
  asks the learner to come up with a limit or set one up; that the questions ask only whether a step
  can reach more than it needs, whether untrusted input ends up in an agent's context, and whether a
  proposed limit would significantly reduce the risk of a named harm and still let the step work;
  and that what a workflow does when a step fails comes in a later topic, and who may do what inside
  a web app was sign-in-and-permissions. At the close, puts the readiness question as written above
  and rules on the answer.
- **done when:** criterion met. The bar for this goal is did it once and help is expected
  throughout, so the ruling is on the learner's answer to the readiness question, not on the stop or
  on whether the tutor thinks they are ready. A plain yes is `criterion: met`. A hedge, with no plain
  no, is `criterion: unclear`: ask which part feels shaky, go over its section once more (What a
  step can reach, When data becomes instructions, or Limits you can put on a step and Judging a
  proposed limit), and put the question again. A second hedge stays `unclear`: the tutor offers one
  of the capability activities with help as the next step. A plain no is `criterion: not met`:
  record it, ask what is missing, and offer to go back over the section that bears on it; don't put
  the question again in the same sitting. This goal isn't required, so a no never blocks anything
  else the learner wants to try.
- **worked example:** n/a
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. It
  shows nothing about the seven words, which have their own supply in `a-words`, and nothing about
  any capability: the reading works one example, the stop is helped, ungraded and answered just
  before the page gives its own answer, and the readiness question asks only whether the learner
  thinks they could do the same. The reading is one course-written page built on one grading
  workflow, so it shows nothing of a workflow in another domain, such as the personal trackers the
  capability activities use.
- **offer as:** this topic's orientation: one short page the course wrote, following the same
  grading workflow as the last topics' readings, from what each step can reach, through how an agent
  can take what it reads as instructions, to the limits an agent might propose and how to judge one.
  One short stop and a one-question close. About 13 minutes.

### `a-look-over-steps`

- **serves:** `c-spot-excess`, `c-spot-injection`
- **supports:** attempt
- **checks:** `c-spot-excess`, `c-spot-injection`
- **artifact:** no external source. A described personal workflow, a short opening and then one
  bullet per step with sub-bullets saying how its executor runs, with a yes-or-no question about each
  executor's reach and, for each agent, one about its context, asked one at a time, from this
  activity's bank or written live per the generator below. About 3 minutes for a scenario's first
  question, with the reading, and about 1 for each after.
- **learner does:** reads the scenario, then answers its questions one at a time, each by picking
  yes or no: whether an executor can reach anything its step does not need, and, for an agent,
  whether untrusted input ends up in its context.
- **tutor role:** examiner
- **tutor does:** sets each question as served, in file order, without rewording it or hinting;
  never names the cases, which fact matters, or which answer the key expects. Gives help whenever it
  is asked for, and records the attempt as helped. When the generator is run live, writes the key
  and the case into the record before showing each question. Labels the attempt with the question's
  path, or `a-look-over-steps/<scenario>/<executor>-reach` or
  `a-look-over-steps/<scenario>/<agent>-context` when run live, and records the case with `--cases`.
  Once a scenario's remaining questions would carry only cases the learner has already passed,
  skips them, as study skips questions no longer needed. Rules each question from its choice alone.
  After ruling, may ask one ungraded follow-up, which never changes the ruling and is not recorded
  as an attempt: for a reach question answered yes, "what can it reach that its step doesn't need?";
  for a context question answered yes, "where does that text come from?". If the learner asks what
  limit would fix a problem, says that is `c-judge-limits`'s ground, and that coming up with limits
  is the agent's.
- **done when:** the criterion of each goal met with no help, case by case: a right answer passes
  the case its question carries.
- **generator:** **A scenario** is one made-up personal workflow on one person's laptop, in the
  third person about that person, who is named. One or two short opening sentences say what the
  workflow is for. Then comes one top-level bullet per step, in order, in plain words. At least half of a bank's scenarios are a small personal tracker with acquire, assess and extract
  steps (a program collects items from somewhere, an agent judges each one, some step pulls out what
  matters); the rest are other personal workflows (sorting a household's receipts, drafting replies
  to a club's messages). It has two or three executors, each a program or an agent following a skill
  file the person wrote, each with a short handle the questions can use ("the fetcher", "the rating
  agent"); at least one is an agent and at most two are. A step the person does by hand may appear,
  but no question is asked about it; its bullet has no sub-bullets. Write the opening and each
  bullet and sub-bullet as one long line; never hard-wrap the scenario's prose.
  - **The step bullet** says what the step does, concretely enough that what it uses follows: who or
    what runs it, which files or folders it reads and which it writes, whether it fetches anything
    from the internet (and from which sites), which account it acts on and what it does there, and,
    for an agent, everything it reads, saying who wrote each part wherever the source could be
    unclear: the skill file ("following a skill file Nadia wrote"), anything others write ("the
    listings, which any landlord can post"; "the pages, which each university's staff write and
    update"), anything the person types that could be mistaken for someone else's ("her own profile,
    which she typed"; "her class schedule, which she types herself"), and anything a program writes
    ("the count the fetcher writes into a file"). Material that is plainly the person's own (her
    essay drafts in her own essays folder) gets no authorship statement. Where a program handles
    outside text before the agent sees it, exactly what the program hands the agent. The step bullet
    never uses the word "can". Its last sentence says how the executor runs. For a sandboxed
    executor it is "It runs in a sandbox with the following restrictions:", and the sub-bullets
    below give the restrictions. For one running as a separate user it is "It runs as a separate user
    <Name> set up for it, with the following restrictions:", and for an agent limited by its harness
    "Its harness's permission settings set the following restrictions:". For an executor the
    workflow puts no limit on, it says only who starts it ("Nadia starts it herself."): never that it
    runs with default settings or its harness's default settings, since the reading says defaults
    vary between harnesses, and never which folder it starts in, as if that folder were a boundary.
  - **Restriction sub-bullets**, for a limited executor only, one restriction each, each starting
    lowercase and ending with a semicolon, the last with a full stop, said as what was set up. The
    sandbox's or separate user's file access is stated as "it allows access to only <files>" ("it
    allows access to only the pages folder;"), and every file or folder the step only reads is stated
    read-only ("it allows access to only its skill file, the essays folder, her class schedule and the plan
    file, all read-only except the plan file;"); a file the step only reads that is not stated
    read-only is change access the step does not need. Then shell commands ("shell commands are
    turned off;"), the network, as an allowlist stated with no "and nothing else" ("the network
    allowlist has the four universities' sites on it;") or as "the network is turned off;", and
    secrets ("it holds a scoped token that reads her calendar;"; "it holds a token for her bank that
    reads her balance and moves money;"; "it holds no logins, keys or tokens."). A harness's
    restrictions are said the same way ("it allows reading and writing files in the posts folder;";
    "shell commands are refused;"; "shell commands run without asking;"). Where an agent with no other limit has had its harness set to let shell commands run without asking, that is a fact sub-bullet instead ("Omar has set its harness's permission settings to let it run shell commands without asking.").
  - **Fact sub-bullets**, each a full sentence starting with a capital and ending with a full stop,
    state plainly what sits in places the executor could get to ("Her home folder holds the skill
    files, the pages folder, her profile, the matches file, a folder of her essay drafts, her
    financial aid forms and a settings file with her bank login."; "The shared folder it has been
    given also holds her tax returns."), and, for an executor with no limit, what secrets it holds of
    its own ("It holds no logins, keys or tokens of its own."). An executor with no limit gets fact
    sub-bullets and no restriction sub-bullets. Who writes something an agent reads may also go in a fact sub-bullet instead of the step bullet when it would make the step bullet long ("On the website, anyone with an account can post. Anyone can read without logging in.").

  **How pointed a fact may be.** A fact states what an executor does, how it runs, what limits it
  runs under, what sits where, what it reads and who wrote that. The scenario never spells out what
  that means for reach: no "so it can read and change every file there", no "it can't run shell
  commands" unless that refusal is itself the stated limit; the learner works out reach from the
  reading's rule. It never says whether reach is more or less than a step needs, never calls text
  trusted, untrusted, safe, outside or risky, and never uses the words untrusted input, prompt
  injection, least privilege, blast radius or "more than it needs". **No wording cue gives the
  answer without comparing step and reach:** a limit's contents are listed neutrally, never with
  "just" or "nothing else", and with "only" in one place alone, the fixed phrase "it allows access to
  only <files>", which says what the sandbox or separate user admits and is used for every limited
  executor, `excess` or `no-excess`; an executor with no limit is never described with "every",
  "whole", "all" or "any". The restriction sub-bullets of `excess` and `no-excess` executors take
  the same forms and about the same number.

  **Reach**, as the key works it out from the reading's rule: an executor can do whatever the user
  it runs as can do (read and change that user's files, including secrets saved in them, run shell
  commands, reach the internet, and use any login, key or token it holds or can read) unless a
  stated limit narrows it. An executor described only by who starts it is narrowed by nothing, as
  the reading tells learners to assume. A sandbox, a separate user or a scoped token
  narrows everything the executor runs. The harness's permission settings narrow only what the agent
  asks the harness to do: where they let the agent run shell commands without asking, those commands
  can do anything the user could, so a file or network limit in the harness does not cover them.
  An executor keyed `excess` can reach at least one thing its step never uses, and the key names
  each such thing: the person's other files and folders, for a step that uses one folder; a login
  saved in one of them, and what it lets one do; change access to a file or folder the step only
  reads, where a limit admits it without making it read-only; a token that can also change, delete, send or move money,
  for a step that only reads; a folder in its sandbox that the step never uses; the internet, for a
  step that works only on files already on the laptop; sites beyond the ones its step fetches from.
  Shell commands are never the only unneeded thing, since whether a step needs one can turn on how
  the agent works; but where an `excess` executor can also run shell commands and its step runs no
  named program, the key lists them beside the other unneeded things. An executor keyed `no-excess`
  runs under limits that leave it exactly what its step uses: the folders it reads, each stated
  read-only, change of only what it writes, on the internet the sites it fetches from (and no network if it fetches nothing),
  shell commands only if its step runs a named program, and a token whose permissions its step all
  uses. So every `no-excess` executor is limited, and since a limit must not mark the answer, at
  least a third of a bank's `excess` executors, and never fewer than two, are limited too, by a limit
  that still leaves one unneeded thing: a sandbox that also allows access to a folder the step never
  uses, or to the settings file with her email login; a sandbox that admits a file the step only
  reads without stating it read-only; harness settings that refuse shell commands but leave the
  network, for a step that works on saved files; a separate user that has also been given a shared
  folder holding her tax returns; a scoped token that also deletes; or harness settings that limit
  files to one folder while letting the agent run shell commands without asking.

  **Context**, for each agent, by case:
  - `outside-text`: the agent itself reads text someone other than the person could have written or
    changed: listings or posts on a site others post to, messages from other people, web pages it
    fetches, a shared document others can edit, or a list into which a program earlier copied such
    text word for word.
  - `owner-only`: everything the agent reads is the person's own and nobody else can change it: the
    skill file, notes or lists she typed herself, numbers she entered. Never a calendar, inbox or
    anything else others can add to. Where the
    workflow collects outside text elsewhere, this agent never reads it or anything copied from it.
    Never an agent that reads another agent's summary of outside text: whether that summary carries
    the outside words is not a clear call.
  - `shielded`: a program reads the outside text and hands the agent only something the program
    produced itself, such as a count, a yes or no, the date the program fetched something, or a score
    the program worked out by its own rule. Never a value copied out of the text, such as a price, a
    name or a title.
  - `passed-through`: a program handles the outside text but hands the agent some of it word for
    word, such as a description, a title, the text of a review, or a message's subject line.
  Neither `shielded` nor `passed-through` hands the agent a single copied number or date, which
  would make the call unclear.

  **Questions**, each its own `###` question under the scenario's shared setup, never parts of a
  compound, in this order: for each executor, in the order the paragraph introduces it, its reach
  question, then, for an agent, its context question straight after.

  **A reach question** reads "Can <executor> reach anything its step does not need?", then two
  numbered choices, "Yes" and "No", in that order. `type: mcq`. Its rubric `goal:` is
  `c-spot-excess`, and its `cases:` line lists `excess` (answer 1) or `no-excess` (answer 2).

  **A context question** reads "Does untrusted input end up in <agent>'s context while it does its
  step?", then two numbered choices, "Yes" and "No", in that order. `type: mcq`. Its rubric `goal:` is `c-spot-injection`, and
  its `cases:` line lists `outside-text` or `passed-through` (answer 1), or `owner-only` or
  `shielded` (answer 2).

  **Illustration**, not a bank item; its domain is used by no bank in this topic.

  > Lena wants to find weekend volunteer shifts near her apartment. Her workflow has three steps.
  >
  > - Every morning the fetcher, a program, downloads the new posts from a community volunteering board, where any organization can post, and saves them in a folder called posts. It runs in a sandbox with the following restrictions:
  >   - it allows access to only the posts folder;
  >   - shell commands are turned off;
  >   - the network allowlist has the volunteering board's site on it;
  >   - it holds no logins, keys or tokens.
  > - Then the sorting agent, following a skill file Lena wrote, reads each new post and her own list of what she likes doing and when she is free, which she typed, and writes a one-line verdict on each post into a file called picks. Lena starts it herself.
  >   - Her home folder holds the skill files, the posts folder, her list, the picks file, her tax returns and a settings file with her email login.
  >   - It holds no logins, keys or tokens of its own.
  > - On Sunday evenings the planning agent, also following a skill file Lena wrote, reads the list of shifts she has signed up for and her list of other plans for the week, both of which she types herself, and writes a draft plan for the week into a file called plan. It runs in a sandbox with the following restrictions:
  >   - it allows access to only its skill file, those two lists and the plan file, all read-only except the plan file;
  >   - shell commands are turned off;
  >   - the network is turned off;
  >   - it holds no logins, keys or tokens.

  Questions and keys, in order: the fetcher's reach, No (`no-excess`: the sandbox leaves it the
  posts folder it writes and the board it fetches from, and nothing in its step runs a command or
  uses a login); the sorting agent's reach, Yes (`excess`: nothing narrows it ("Lena starts it
  herself", with no restrictions listed), so it can do whatever Lena can; its step reads the posts and her list and writes picks, but it can read her tax returns
  and the settings file with her email login, which would let it send mail as her, run shell
  commands and reach the internet, none of which a step working on saved posts and running no
  program uses); the sorting agent's context, Yes (`outside-text`: it reads the posts, which any
  organization can write); the planning agent's reach, No (`no-excess`: the sandbox allows the
  skill file and the two lists it reads, read-only, and the plan it writes, with no commands,
  network or logins); the planning agent's context, No (`owner-only`: it reads only the skill file
  and the two lists Lena types). An `excess` variant of a limited executor: the planning agent's
  sandbox also allows access to her journal folder; key Yes, naming the journal folder. Another: the
  planning agent's sandbox allows the same four files with no read-only clause; key Yes, naming
  change access to the skill file and the two lists. A `shielded` variant: the fetcher also counts how many new
  posts fall on a weekend and writes only that number into a file in the posts folder, and the
  planning agent instead reads only that file and Lena's list of other plans; key No. A `passed-through`
  variant: the fetcher writes each post's title into a file that the planning agent reads; key Yes.

  **How hard.** Medium when the excess is plain (an agent the person starts herself, with no
  restrictions, against a step that uses one folder), a `no-excess` executor's
  limits plainly match its step, and the outside text is plainly someone else's (listings any
  landlord can post). Hard when the excess is one item a limit leaves among things the step does
  use (a token that also deletes, for a step that only reads; the network left on, for a step that
  works on saved files; no network allowlist, for a step that fetches from two named sites; a
  sandbox that also allows access to the settings file or an unused folder; a file the step only
  reads left without a read-only clause; harness file limits beside shell commands allowed without
  asking), when a `no-excess` executor's limits look broad but leave only
  what is used (a token that changes entries, for a step that changes them; a sandbox holding
  several folders, each of which the step reads), when outside text arrives indirectly (copied into a list earlier
  by a program; a message the person forwarded to herself; a shared document others can edit; only
  titles passed through), when an `owner-only` agent can reach the internet or the workflow collects
  outside text elsewhere that this agent never reads, or when a `shielded` program reads a great
  deal of outside text and hands over only a count. The question wording is unchanged.

  **Spread across the bank.** A bank is six scenarios and 24 questions, half of the scenarios Hard.
  Three scenarios have three executors, two agents and a program (three reach questions and two
  context questions each), and three have two executors, an agent and a program (two reach
  questions and one context question each). That is fifteen reach questions, at least six carrying
  each of `excess` and `no-excess`, and nine context questions: three `outside-text` and two each of
  `owner-only`, `shielded` and `passed-through`. At least four scenarios have both reach answers
  among their questions. Two of the three-executor scenarios form a pair that between them carry
  all six cases: both reach cases in the first of them, and the four context cases across their
  four agents. At least three scenarios are trackers with acquire, assess and extract steps. When the generator is run live, the tutor picks each next
  scenario to carry a case the learner hasn't passed.

  **Domains** vary by scenario, none repeating within the bank: an apartment hunt from a rentals
  site, a scholarship deadlines tracker from university pages, a concert ticket watch, a freelance
  translation gig finder, a book club's suggestion inbox, a research paper alert digest, a farmers
  market vendor list, a household's receipts for taxes. No domain from any other activity's list
  or illustration in this topic.

  **The key**, per question. For a reach question: the verdict; for `excess`, each thing the executor
  can reach that its step never uses, citing the sub-bullets that give it that reach (or, where no
  limit covers it, the reading's rule that it can do whatever its user can) and the step bullet
  saying what the step does; for `no-excess`, each limit, what it leaves, and the part of the step
  that uses that. For a context question: the verdict; each thing the agent reads and who wrote it, citing
  the sentence; for `shielded`, what the program hands over and that the program produced it
  itself; for `passed-through`, which part of the outside text arrives. The key notes that the
  question asks what the step does as described, not what could go wrong next or how to fix it.
  Credit: full for the key's choice; none for the other. A `tutor note` gives the follow-up's
  answer (what is unneeded, or where the text comes from).
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works the illustration aloud (filling out a variant into bullets in this activity's style,
  adding no fact): for a reach question, starts from the reading's rule (it can do whatever the user
  it runs as can, unless a limit narrows it), applies each stated limit, lists what that leaves it
  in the four kinds beside what its step uses, and says whether anything is left over; for a context question, lists
  everything the agent reads and who wrote each part, and says whether anyone but Lena could have
  written any of it. It may point to What a step can reach and When data becomes instructions in
  `tasks/read-permissions.md`.
- **doesn't show:** every scenario states how each executor runs, every limit it runs under, what
  sits in the places it could get to, and everything each agent reads, so a pass doesn't show the
  learner would find a limit, a saved login or a source nobody mentioned; in Problem Set 5 their
  agent's audit supplies those facts. A yes-or-no answer is right half the time by
  guessing, and no reason is asked. The learner isn't asked to name the unneeded reach or the
  source of the outside text, only to say whether there is one; the tutor's follow-up asks, ungraded.
  No question is asked about a person's step. The context question uses the word untrusted input
  unglossed, so a learner who has that word wrong may fail a question whose facts they read right.
- **offer as:** the work-out-the-reach check: a personal workflow, one bullet per step saying how its
  executor runs, then, step by step, whether each executor can reach anything it doesn't need and
  whether untrusted input ends up in each agent's context, each a yes or no. About 3 minutes for a
  scenario's first question and 1 for each after. Harder than `a-read-agent-audit`, since the
  learner works out each executor's reach from how it runs instead of being told it.
- **check note:** Skip only at the end of a scenario, as `tutor does` says, never question by
  question as the opening paragraph's "skips any question whose case is already passed" could be
  read: once `excess` is passed, skipping single reach questions would leave only No answers. Even
  at a scenario's end, a last question asked only because its case is unpassed gives its answer
  away to a learner who notices the pattern, so when only one question would remain, ask it anyway
  or move to a fresh scenario.

  When writing or recording a context question live, treat a list into which a program copied
  outside text word for word as `outside-text`, as the generator lists it, and keep
  `passed-through` for a program that hands over only part of the text, such as titles or
  descriptions.

  The `shielded` and `passed-through` variants change what the planning agent reads. When working
  one aloud as help, say that its sandbox allows access, read-only, to the file the fetcher writes in
  place of the shifts list; that is the only fact the variant implies. In the `shielded` variant the fetcher's step now
  also writes the count file in the posts folder, which its sandbox already holds.

### `a-read-agent-audit`

- **serves:** `c-spot-excess`, `c-spot-injection`
- **supports:** attempt
- **checks:** `c-spot-excess`, `c-spot-injection`
- **artifact:** no external source. A described personal workflow given as the answer an agent wrote when asked to describe each step, one bullet per step with labeled sub-bullets for what its executor can reach, with the same yes-or-no questions as `a-look-over-steps`, asked one at a time, from this activity's bank or written live per the generator below. About 2 or 3 minutes for a scenario's first question, with the reading, and about 1 for each after.
- **learner does:** reads the workflow's description and the agent's answer, then answers the
  questions one at a time, each by picking yes or no: whether an executor can reach anything its
  step does not need, and, for an agent, whether untrusted input ends up in its context.
- **tutor role:** examiner
- **tutor does:** as `a-look-over-steps`'s, including the ungraded follow-ups, except that it labels
  a live run `a-read-agent-audit/<scenario>/<executor>-reach` or
  `a-read-agent-audit/<scenario>/<agent>-context`.
- **done when:** the criterion of each goal met with no help, case by case: a right answer passes
  the case its question carries.
- **generator:** **A scenario** uses `a-look-over-steps`'s executors, reach rules, context cases, pointedness rule, questions, question order, key and credit, with one difference: the learner is told each executor's reach instead of working it out. One or two sentences say what the workflow is for and that the person asked her agent to describe each step: what it does, what runs it, how it runs, what it can read, change, run and reach, what its secrets let it do, and what each agent step reads. Then comes the agent's answer, laid out as `tasks/a-look-over-steps/scholarship-deadlines.md` is, addressing the person as "you": one top-level bullet per step, in order, then labeled sub-bullets under it.
  - **The step bullet** opens with the step's handle in bold, then in the same sentence says what runs it (a program, or an agent following your skill file) and what the step does (what it reads and writes, what it fetches and from where, what it does with an account): "**The fetcher**, a program, downloads ...". Then comes how it runs, as its own short sentence: "It runs in a sandbox." for a sandboxed executor, "It runs as a separate user you set up for it." for one running as a separate user, "Its harness's permission settings limit it." for an agent limited by its harness, and "You start it yourself." for an executor with no limit, never default settings or its harness's default settings, which the reading says vary between harnesses, and never a starting folder as if it were a boundary. The limits are not listed in the step bullet: the reach sub-bullets are where they show, so nothing is said twice.
  - **The sub-bullets**, in this order: "Files:", "Shell commands:", "Network:", "Secrets:", and for an agent only "Reads:". Each is one sentence starting lowercase after the label and ending with a full stop. Files says what it can read and what it can read and change, including any secrets saved there ("it can read its skill file, the races folder and your list, and it can read and change the shortlist file."; "it can read and change your files; your home folder holds the skill files, ... and the settings file where your email login is saved."). Shell commands says whether it can run them ("they are turned off."; "it can run them, with no limit set."). Network says what it can reach ("it is turned off."; "it can reach the race calendar's site, which is on the sandbox's network allowlist."; "it can reach the internet, with no limit set."). Secrets states as a fact what each secret lets its holder do ("it holds none."; "it holds your token for the race calendar site, which lets its holder read listings and delete the account."; "it holds none of its own, but it can read your email login in that settings file, which lets its holder send mail as you."), never phrased as what the executor would or might do with it. Reads, for an agent, says what it reads, saying who wrote each part wherever the source could be unclear (the skill file, anything others write, a list or profile the person typed, anything a program writes) and not for material plainly the person's own (her essay drafts in her own folder).
  - **Each reach sub-bullet agrees** with the reading's rule applied to how the executor runs: whatever its user can do, unless a stated limit narrows it, with a harness limit not covering shell commands the harness lets run without asking. The reach sub-bullets name places and what is in them, with no "only", "just" or "nothing else" for a limited executor and no "every", "whole", "all" or "any" for an unlimited one; the sub-bullets of `excess` and `no-excess` executors take the same forms. Write the opening, each bullet and each sub-bullet as one long line; never hard-wrap the scenario's prose.
  - **The answer states facts only.** It never says whether reach is more than the step needs and never says whether untrusted input reaches an agent: the person did not ask that, so the reading's third audit question ("Where does text from outside the workflow end up in an agent's context?") is never answered here. A step the person does by hand gets a bullet with no sub-bullets and no question.

  **Example**, the volunteering illustration in `a-look-over-steps` set this way; not a bank item.

  > Lena's workflow finds weekend volunteer shifts near her apartment. She asked her agent to describe each step: what it does, what runs it, how it runs, what it can read, change, run and reach, what its secrets let it do, and what each agent step reads. This is its answer.
  >
  > - **The fetcher**, a program, downloads the new posts every morning from a community volunteering board, where any organization can post, and saves them in a folder called posts. It runs in a sandbox.
  >   - Files: it can read and change the posts folder.
  >   - Shell commands: they are turned off.
  >   - Network: it can reach the volunteering board's site and a file-sharing site, which are both on the sandbox's network allowlist.
  >   - Secrets: it holds none.
  > - **The sorting agent**, following your skill file, reads each new post in the posts folder and your list of what you like doing and when you are free, and writes a one-line verdict on each post into a file called picks. You start it yourself.
  >   - Files: it can read and change your files; your home folder holds the skill files, the posts folder, your list, the picks file, your tax returns and the settings file where your email login is saved.
  >   - Shell commands: it can run them, with no limit set.
  >   - Network: it can reach the internet, with no limit set.
  >   - Secrets: it holds none of its own, but it can read your email login in that settings file, which lets its holder send mail as you.
  >   - Reads: the skill file and your list, which you wrote, and the posts, which organizations put on the volunteering board.
  > - **The planning agent**, following your skill file, reads the list of shifts you have signed up for and your list of other plans for the week on Sunday evenings, and writes a draft plan for the week into a file called plan. It runs in a sandbox.
  >   - Files: it can read its skill file and your two lists, and it can read and change the plan file.
  >   - Shell commands: they are turned off.
  >   - Network: it is turned off.
  >   - Secrets: it holds none.
  >   - Reads: the skill file and your two lists, which you type yourself.

  Same questions as the illustration in `a-look-over-steps`, and the same keys except the fetcher's: the file-sharing site is on its allowlist though its step only downloads from the volunteering board, so its key is Yes, and the keys read Yes, Yes, Yes, No, No.

  **How hard**, labeled exactly as in `a-look-over-steps`, by the facts: a scenario is Hard here
  when its facts would make it Hard there. The layout makes every question somewhat easier than the
  same facts in prose, which `offer as` and `doesn't show` say; it doesn't change the label. The
  question wording is unchanged.

  **Spread across the bank**, as in `a-look-over-steps`: six scenarios and 24 questions, with the same mix of executors, the same case counts, and the same pair of scenarios carrying all six cases.

  **Answer patterns.** A learner meets this bank after `a-look-over-steps`, so no scenario here has the same sequence of keys, by question position, as any scenario in `a-look-over-steps`'s bank (its `scholarship-deadlines` reads No, Yes, Yes, No, No). Across this bank, at least three of the six scenarios have an `excess` case on a limited executor (a sandbox wider than the step needs, a token broader than the step needs, a site on the allowlist the step never uses), and at least three have a limited agent whose context case is `outside-text` or `passed-through`, so "sandboxed means No" never works as a shortcut. Since the two banks may be drafted at the same time and either may grow later, bank-check compares every scenario's key sequence here with every scenario's in `a-look-over-steps` each time it runs, and reports any match.

  **Domains** are this activity's own, none repeating within the bank: a conference call-for-talks
  tracker, a summer camp openings watch, a neighborhood association's email digest, a community
  grants finder, a tutor's new-student inquiries, a podcast's guest requests, a thrift store
  furniture watch, a running race sign-up watch. No domain from any other activity's list or
  illustration in this topic.
- **worked example:** shown only as help when asked for, which records the attempt as helped. As `a-look-over-steps`'s, using the example above, reading each step's reach sub-bullets against its step bullet, what the step does.
- **doesn't show:** as `a-look-over-steps`'s, and the agent states each executor's reach, so a pass
  doesn't show the learner would work out reach from how an executor runs; `a-look-over-steps`
  asks for that. Problem Set 5's agent audit will look more like this
  than like a story, but a real agent's answer may leave out a kind of reach or call something safe,
  which no scenario here does.
- **offer as:** the read-the-audit check: the same questions, asked of a workflow described the way an agent's audit lays it out, one bullet per step with its reach under labeled sub-bullets. About 2 or 3 minutes for a scenario's first question and 1 for each after. Easier than `a-look-over-steps`, since the agent says what each executor can reach and you compare it with the step, and closer to what Problem Set 5 will hand you.
- **check note:** This entry runs as `a-look-over-steps` does, so the notes there on skipping and on
  recording copied text apply here too.

### `a-weigh-one-limit`

- **serves:** `c-judge-limits`
- **supports:** attempt
- **checks:** `c-judge-limits`
- **artifact:** no external source. A described workflow step, a short opening and then one bullet per step the harm needs with sub-bullets saying how its executor runs, then a named harm and one limit an agent proposes, with one compound question of two yes-or-no parts, from this activity's bank or written live per the generator below. Each question is a fresh scenario. About 3 or 4 minutes a question.
- **learner does:** reads the scenario, the harm and the proposed limit, then answers two yes-or-no
  parts: would this limit significantly reduce the risk of this harm, and could the step still do
  its work under it.
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; never names the
  cases, which fact matters, or which answers the key expects. Gives help whenever it is asked for,
  and records the attempt as helped. When the generator is run live, writes the key and the case
  into the record before showing the question. Labels the attempt with the question's path, or
  `a-weigh-one-limit/<domain>-<case>` when run live (the scenario's domain in a few hyphenated words,
  such as `a-weigh-one-limit/textbook-watch-no-effect`), and records the case with `--cases`. Rules each part
  from its choice alone; the question passes its case only when both parts are right. If the
  learner asks how the limit would be set up, or which limit would be best, says that is the agent's
  to work out and this question doesn't ask it. Never says what is wrong with an answer before both
  parts are answered.
- **done when:** the criterion met with no help, case by case: both parts right passes the case the
  question carries.
- **generator:** **A scenario** is one step of a made-up personal workflow on one person's laptop, with only as much of the workflow around it as the harm needs, in the third person about that person, who is named, laid out as `a-look-over-steps`'s scenarios are. One or two short opening sentences say who the person is and what the workflow is for. Then comes one top-level bullet per step the harm needs, in order, usually just one. Each follows `a-look-over-steps`'s step bullet, restriction sub-bullet and fact sub-bullet rules exactly: the step bullet says what the step does and what it uses, who runs it and, for an agent, everything it reads and who wrote each part, and its last sentence says how the executor runs in that entry's fixed forms; a limited executor's restrictions follow as restriction sub-bullets; fact sub-bullets say what sits in places the executor could get to and, for an executor with no limit, what secrets it holds of its own. The step the harm turns on is run, in at least four of a bank's six scenarios, by an agent following a skill file the person wrote, and otherwise by a program. Where a person already checks the step's output, or where nobody does and the output goes straight on, that is a fact sub-bullet under the step ("Nobody looks over the roster before Kofi texts it to the drivers on Friday morning."; "Priya reads every reply before it is sent."). The scenario states how each executor runs, its limits and what sits where, and never what that means for reach: `a-look-over-steps`'s "How pointed a fact may be" rule applies, so no "so it can read and change all his files, run shell commands and reach the internet"; the learner works out reach from the reading's rule that an executor can do whatever its user can, unless something narrows it. Write the opening and each bullet and sub-bullet as one long line; never hard-wrap the scenario's prose. Then two sentences in fixed frames, each its own paragraph below the bullets and likewise one long line:
  - "The harm <Name> is worried about: <harm>." One specific harm, one thing that could go wrong,
    following from one of the step's problems: its executor can reach something the step does not
    need, or untrusted input reaches an agent's context, or both, where text steers an agent into
    using reach its step doesn't need. Said concretely, as an event: "a hidden line in a listing
    makes the agent send her email login to a web address"; "the agent deletes the photos in her
    Pictures folder"; "a hidden line in a listing makes the agent rate a scam as a great deal, and it
    goes onto the list she calls from".
  - "Her agent proposes: '<limit>'" One limit, in the agent's words, one to three sentences, saying
    what it would restrict or check and how it would be imposed. It never says what the limit
    prevents, which harm it addresses, whether the step could still work, or what it costs. It comes
    from one of the reading's three groups:
    - narrowing what the executor can reach (which files, read-only access, which shell commands,
      which sites on the network, or what a secret lets it do), imposed in one of the reading's four
      ways: a separate user, a sandbox, the harness's permission settings (for an agent only), or a
      scoped token;
    - keeping untrusted text out of the agent's context: a program handles the untrusted input and
      the agent sees only what the program produced;
    - checking what the step produced before it takes effect: the agent proposes changes and a
      program applies them, or a person checks every output.
    Never an agent's approval prompts, which the reading calls a weak check, so their effect is
    not a clear call.

  **Clear calls only.** Each limit either clearly cuts off the harm's route or adds a check on every change before it takes effect, or clearly has little or nothing to do with the harm. Never a limit that cuts the route only partly, a person who checks only some outputs or might not look, or a limit whose effect turns on how carefully it was set up. Never a limit of the right kind built wrong: a sandbox that still holds the login, a scoped token that still has the harmful permission, an allowlist that still allows the harmful action. Every limit is set up as the agent describes it and works as described. Whether the step can still work is as clear: a limit that stops the work takes away something the step bullet says the step uses, and any other limit leaves everything the step uses. **How a limit is imposed settles what it covers**, as the reading says: a sandbox, a separate user or a scoped token covers everything the executor runs, and the harness's permission settings cover only what the agent asks the harness to do. So wherever a proposal uses the harness's permission settings, a sub-bullet under the step says what the harness lets the agent run without asking (no shell commands, or shell commands, because its step runs a named program): a restriction sub-bullet where the harness already sets restrictions ("shell commands are refused;"; "shell commands run without asking;"), otherwise a fact sub-bullet ("Omar has set its harness's permission settings to let it run shell commands without asking."), and nobody need wonder whether a command could get around it. The one limit that works as described and is still got around is this one, which the reading teaches: a file or network limit in the harness's permission settings, when a sub-bullet says the harness lets the agent run shell commands without asking and the harm's route can go through a command (network left off the harness allowlist, while the step runs an allowed download program and any command it runs still reaches the network). That limit is keyed `no-effect`.

  **A question** is a compound: the `###` stem is the scenario (the opening, the step bullets and the two framed sentences), then two mcq parts.
  - `#### a`: "Would this limit significantly reduce the risk of this harm?", then "1. Yes", "2. No".
  - `#### b`: "Could <step handle> still do its work under this limit?", then "1. Yes", "2. No".
  The rubric's `###` entry has `goal: c-judge-limits`, `type: compound` and one case; each part has
  `type: mcq` and its `answer`.

  **Cases**, each with its two answers:
  - `sound-limit` (a Yes, b Yes): the limit cuts off the harm's route (the agent can't send a login
    it can't read, or can't reach the internet to send it, for a step that never fetches; a token
    that can only read can't be used to move money; the agent never sees the outside words, so
    nothing in them can steer it, for a step that needs only a count; it can't change a folder it can
    only read) or checks every change before it takes effect (the person approves every reply before
    it is sent; a program applies only one kind of change, so a steered agent can't delete entries),
    and leaves the executor everything its step uses.
  - `stops-work` (a Yes, b No): the limit cuts off the harm's route in one of those ways, and also takes away something the step bullet says the step uses: read-only access to the folder the step writes into; no internet for a step that fetches pages; a program that hands over only a count, when the step's job is to write about what the text says; a sandbox that leaves out a file the step reads; a token that can only read, for a step that sends.
  - `no-effect` (a No, b Yes): the limit leaves everything the step uses and does nothing about the
    harm's route. It limits something the harm doesn't pass through (read-only access to a folder the
    harm never touches; no internet, when the harm happens entirely in files on the laptop; a narrower
    token for a different executor; a sandbox, when the harm is a skewed verdict written where the
    step is meant to write it), or adds a check that comes after the harm has happened (the person
    reviews the step's output, when the harm is the agent sending something out during its run), or
    a program that applies the agent's changes, when the harm is a wrong value of a kind the program
    does apply (as the reading says, propose-apply still lets bad values through), or a limit the
    step gets around because of how it is imposed (a file or network limit in the harness's
    permission settings, when the harness lets the agent run shell commands without asking and the
    harm's route goes through a command).

  **Illustrations**, not bank items; their domain is used by no bank in this topic. The scenario, up to the harm:

  > Omar is looking for a cat to adopt, and his workflow keeps a shortlist of promising ones.
  >
  > - Each evening the matching agent, following a skill file Omar wrote, fetches the new listings from three shelter websites, where any shelter can post, reads each one, and writes the promising ones, with a short note on each, into a file called shortlist. Omar starts it himself.
  >   - His home folder holds the skill file, the shortlist, his photos and a settings file with his bank login.
  >   - It holds no logins, keys or tokens of its own.
  >   - Nobody looks over the shortlist before Omar emails shelters from it the next morning.
  >
  > The harm Omar is worried about: a hidden line in a listing makes the agent send his bank login to a web address.

  Then one of these, each a separate scenario:
  - `sound-limit`, Medium: "His agent proposes: 'I can run the matching step in a sandbox folder holding only the skill file and the shortlist, still able to fetch pages from the internet.'" a Yes (nothing narrows the agent now, so by the reading's rule it can do whatever Omar can, including reading the settings file and reaching the internet; the login isn't in the sandbox, so the agent can't read it to send it); b Yes (it still reads its skill file, fetches the listings and writes the shortlist).
  - `stops-work`, Medium: "His agent proposes: 'I can run the matching agent in a sandbox with the network turned off.'" a Yes (it can't send anything anywhere); b No (it fetches the listings from the shelter websites).
  - `no-effect`, Hard: "His agent proposes: 'You could look over the shortlist each morning before contacting any shelter.'" a No (by the reading's rule the agent can read the login and reach the internet, so the login would be sent during the evening run, before Omar looks at anything, and the shortlist needn't show it); b Yes (the step runs as before).
  - `no-effect`, Hard, a variant of the scenario: the step bullet says the agent fetches the listings by running a download program Omar wrote, and a fact sub-bullet reads "Omar has set its harness's permission settings to let it run shell commands without asking." "His agent proposes: 'I can leave the network off the matching agent's allowlist in its harness's permission settings.'" a No (the harness checks only what the agent asks it to do; a command the agent runs can still do whatever Omar can, so it can read the login and reach the internet to send it); b Yes (it still runs the download program, which still fetches the listings).

  **How hard.** Medium when the limit plainly closes or plainly misses the harm's route (a sandbox
  without the login, against sending the login; read-only access to a folder the harm never
  touches) and plainly keeps or takes away what the step uses. Hard when it takes a step of
  reasoning: a check that comes after the harm; propose-apply against a wrong value; a person's
  check that leaves the agent's reach alone and still counts, since every output is checked before
  it takes effect; a limit on reach against a harm from untrusted input, where the steered action
  needs that reach; a shield from the outside text that would stop the harm, for a step whose job is
  to write about that text; a harness limit the step gets around because the harness lets the agent
  run shell commands without asking. The question wording is unchanged.

  **Spread across the bank.** A bank is six scenarios, six questions: each case twice, one of each
  pair Hard. Three harms follow from reach the step doesn't need and three from untrusted input
  (alone, or steering the agent into using reach). At least five different kinds of limit appear,
  none more than twice, counting as kinds each of the four ways of narrowing reach (a separate
  user, a sandbox, the harness's permission settings, a scoped token), a program that handles the
  untrusted input, propose-apply, and a person checking every output. Each of the reading's three
  groups appears at least once, at least one limit is a person checking every output, and one of
  the two `no-effect` questions is a harness limit the step gets around. When the generator is
  run live, the tutor picks each next case to be one the learner hasn't passed.

  **Domains** vary by scenario, none repeating within the bank: a wedding's RSVP inbox, a vintage
  camera auction watch, a used-textbook marketplace watch, an online course reviews summarizer, a
  club treasurer's reimbursement requests, a graduate program applications tracker, a hiking
  group's trip sign-ups. No domain from any other activity's list or illustration in this topic.

  **The key** gives both answers. For part a: the harm's route (what the executor would have to read, reach, use or do for the harm to happen, and when it would take effect), citing the sentences and, wherever the route depends on what an executor can reach with nothing narrowing it, the reading's rule that an executor can do whatever its user can, unless something narrows it; and whether the limit, as it is imposed, cuts that route, checks every change before it takes effect, or leaves the route as it was. For part b: what the step uses, citing the sentence, and whether the limit leaves it. Credit, per part: full for the key's choice, none for the other; the question passes its case only when both parts are right. A `tutor note` on the entry gives, for a `no-effect` question, what the limit does do, so the tutor can say afterward that it isn't useless, only not aimed at this harm; any tutor note that turns on what an executor can reach with nothing narrowing it cites the same rule.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The tutor works the illustration of the same case aloud: traces the harm's route from the scenario (what the agent would have to read and reach, starting from the reading's rule that it can do whatever its user can unless something narrows it, and when it would happen), asks whether the limit closes that route or checks every change before it takes effect, then lists what the step uses and asks whether the limit leaves it. It never adds a fact the illustration leaves out; for the harness variant, it fills the variant out into bullets in this activity's layout, adding no fact. It may point to What a step can reach, Limits you can put on a step and Judging a proposed limit in `tasks/read-permissions.md`.
- **doesn't show:** every limit is clearly on one side of "significantly", and every limit works as
  described, so a pass shows nothing about the borderline calls or about catching a limit built
  wrong, which the instructor left to the agent; the one way a limit is got around that a question
  may turn on is a harness limit beside shell commands allowed without asking, as the reading
  teaches. Approval prompts never appear, so a pass shows nothing about judging them. One limit at a time, so a pass shows nothing about
  combining limits, which the reading says often takes more than one. The agent's proposal is given,
  so a pass doesn't show the learner would think of a limit, which is the agent's work here. Each
  part is a yes or no, so guessing passes a question a quarter of the time. No question has both
  answers No (a limit that misses the harm and also takes away something the step uses), since the
  goal's three cases don't include one; so a learner who has settled that the step can't work may
  answer part a Yes without judging it, and in a `stops-work` question one judgment can stand in for
  two. The harm is named for the learner, so a pass doesn't show they would name it themselves.
- **offer as:** the one-at-a-time check: a fresh step, harm and proposed limit each time, and you
  say whether the limit would significantly reduce the risk and whether the step could still work.
  About 3 or 4 minutes a question. Harms vary from question to question, so each one is read from
  scratch.
- **check note:** A limit imposed by a sandbox, a separate user or a scoped token covers every command the executor runs. If a learner asks whether a shell command could get around one, say no: that is a fact of the scenario, not a hint. For a limit in the harness's permission settings, don't answer that question, since it is what part a judges; point to the sub-bullet on what the harness lets the agent run without asking.

### `a-weigh-proposals`

- **serves:** `c-judge-limits`
- **supports:** attempt
- **checks:** `c-judge-limits`
- **artifact:** no external source. One described workflow step and one named harm, then the agent's
  answer when asked what limits could reduce its risk: two or three proposals, each its own compound
  question of two yes-or-no parts, asked one at a time, from this activity's bank or written live
  per the generator below. About 4 minutes for a scenario's first question and about 2 for each
  after.
- **verified:** 2026-11-13
- **learner does:** reads the scenario and the harm once, then, for each proposal in turn, answers
  two yes-or-no parts: would this limit significantly reduce the risk of this harm, and could the
  step still do its work under it.
- **tutor role:** examiner
- **tutor does:** as `a-weigh-one-limit`'s, except that it sets the questions in file order, labels a
  live run `a-weigh-proposals/<scenario>/<proposal>`, and skips a scenario's remaining questions
  once they would carry only cases the learner has already passed.
- **done when:** the criterion met with no help, case by case: both parts right passes the case the
  question carries.
- **generator:** **A scenario** uses `a-weigh-one-limit`'s layout (the opening, the step bullets and their sub-bullets), harm sentence, clear-calls
  rule, cases, parts, key and credit, with one difference: the shared setup ends with "<Name> asks
  her agent what limits could reduce the risk of that harm. It proposes several; each question
  below gives one. Each proposal changes only what it names; everything else stays as described
  above." Each `###` question's body is "Proposal: '<limit>'", in the agent's words as
  `a-weigh-one-limit` describes, then the two parts. The opening, each bullet and sub-bullet, the harm sentence, the shared
  setup's closing sentences and each proposal are each written as one long line, never
  hard-wrapped. A scenario has two or three proposals. Each
  proposal stands on its own: none refers to another ("instead", "as well", "on top of the
  sandbox"), and none is judged as combined with another. No question's text gives away another's
  answer: a proposal names only what it changes, never what it leaves as it was ("still able to
  fetch pages" would tell the learner that fetching matters, which is another proposal's part b).

  **Cases within a scenario** follow no fixed pattern: a scenario may carry the same case twice, and
  at least two of a bank's scenarios do not carry one of each, so the learner can't count their way
  to an answer.

  **Example**, the cat adoption illustration in `a-weigh-one-limit` set as one scenario: the
  opening, the step bullet and the harm, then three proposals in this order: "I can run the matching agent in a
  sandbox with the network turned off" (`stops-work`); "You could look over the shortlist each
  morning before contacting any shelter" (`no-effect`); "I can run the matching agent as a separate
  user that has been given the skill file and the shortlist" (`sound-limit`, since the operating
  system then keeps it and every command it runs from the settings file with the login, and the
  internet stays open, since nothing narrows its network). A bank scenario would
  break that one-of-each pattern in at least two of its four scenarios.

  **How hard**, as in `a-weigh-one-limit`. The question wording is unchanged.

  **Spread across the bank.** A bank is four scenarios and ten or eleven questions, at least three
  carrying each case, about half Hard. Two harms follow from reach the step doesn't need and two
  from untrusted input. At least five different kinds of limit appear across the bank, counted as
  `a-weigh-one-limit` counts them, each of the reading's three groups appears, and a scenario never
  offers the same kind twice. At least one `no-effect` question is a harness limit the step gets
  around because the harness lets the agent run shell commands without asking.

  **Domains** are this activity's own, none repeating within the bank: a seed swap forum watch, a
  newsletter digest from the person's subscriptions, a band's gig inquiries, a language-exchange
  partner finder, a used kayak watch, a home repair quotes comparison. No domain from any other
  activity's list or illustration in this topic.
- **worked example:** shown only as help when asked for, which records the attempt as helped. As
  `a-weigh-one-limit`'s, working the proposal of the same case from the example above.
- **doesn't show:** as `a-weigh-one-limit`'s. Every proposal in a scenario is judged against one harm,
  and seeing several limits side by side may make the contrast easier than meeting one alone; in
  Problem Set 5 an agent will often propose several at once, which this is closer to. Each proposal
  is judged alone, so a pass still shows nothing about whether two limits together would do.
- **offer as:** the conversation-shaped check: one step and one harm, then the several limits an
  agent proposes, judged one at a time. About 4 minutes for the first and 2 for each after. Closer to
  how Problem Set 5 will go than `a-weigh-one-limit`, but every question shares one harm.
- **check note:** The notes on `a-weigh-one-limit` and on skipping in `a-look-over-steps` apply
  here. In particular, a scenario's last proposal asked only because its case is still unpassed
  gives away its two answers to a learner who notices the pattern; when only one proposal would
  remain, ask it anyway or move to a fresh scenario. The example's separate-user proposal covers
  every command the matching agent runs, as the reading says of a separate user, so it cannot read
  the bank login by any route.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
