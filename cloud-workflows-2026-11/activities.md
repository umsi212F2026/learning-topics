# Activities: cloud workflows

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

The initial study, the orientation and one passed question for each of the five words, comes to
about 29 minutes: about 14 for `a-read-cloud-workflows` (the reading is about 1,750 words, about 9
minutes on its own, plus its stop and close) and about 3 a word, so 15. That is well inside the
topic's 60-minute budget.
The capability carries `taught elsewhere` (the session 23 class), so its three activities are
offered during or after that class: the class works through as much of them as it can, and the learner finishes the rest on their own. Meeting `c-weigh-cloud-plan` takes one passed
question per case, twelve in all. Through `a-pick-better-plan` that is twelve scenarios at
about 2 or 3 minutes each, so about 30 minutes. Through `a-flip-one-fact` it is twelve scenarios,
since only a pair's first question carries a case, at about 3 minutes for the first question and 1
for the second, so about 48: more than one sitting, and meant as review spread over several.
Through `a-score-two-plans` it is eight scenarios, about 3 minutes for a scenario's first question
and about 1 for each after, with the tutor skipping questions whose cases are already passed, so
about 28. The rest of the hour is room for missed
questions.

Every question asks for one thing and works on its own as a bank question, never relying on a
tutor's follow-up to collect the rest of an answer. Every capability question is a choice among
three numbered options, always in this order: the first plan, the second plan, and "They do about
as well on <goal>". "About as well" is offered in every question and is the right answer in some
questions on every one of the four goals, not only on correctness. No question asks for a reason,
asks how to build or deploy anything, or asks which real product or company to use. Lucky guesses
are acceptable, and nothing is added to a question to prevent one. Learner-facing text states the
task, never the scoring.

In this topic's banks and live questions, every workflow is a made-up one described in words: a
small workflow someone first built on their own laptop, with at least one step done by an agent
following a skill file, that other people are now to use. Never the learner's own app, repo,
machine or project; never the reading's example workflow; never a homework or grading workflow.
Every scenario states every fact its answer needs, and states the fact that decides it among
several other ordinary facts about the workflow, in its own words, never in the words of a case
line in goals.md. No scenario contains code, a command, a query or SQL. No real model, product or
brand is named; a model company is "a model company" or "the model company she uses", and an
open-weight model is "an open-weight model". Prices and counts in scenarios are made up and are
stated in round numbers. The topic's words open-weight model, API key, BYOK, usage-based pricing and
data retention are used in question text where they fit, with no gloss. American spelling
throughout, and no em dash or en dash in any form.

## Check notes


## Goals

| id                   | Goal | Criterion: what gets examined, and what counts |
| -------------------- | ---- | ---------------------------------------------- |
| `o-orientation`      | get the shape of this area before working on any particular part of it | `orientation` |
| `c-weigh-cloud-plan` | say what a plan for where a workflow's agent steps run, and who pays for them, does to one goal | given a described workflow with at least one agent step, two plans for where that step runs and who pays for it, and one named goal (cost to the service's owner or to its users, privacy, access or correctness), says which plan does better on that goal, or that they do about as well on it. The facts about the workflow that decide it include who its users are and how many runs they will make, whose bill the agent compute lands on and how it is priced (per token, as part of a subscription, or as the rent of a server), whose data the agent step sees and which companies would then see it, who needs to start it or see its results, and whether the step needs a model as capable as the ones model companies sell. The plans are drawn from five: each user runs it on their own machine under their own subscription; it runs in the cloud on each user's own API key; it runs in the cloud and the service pays a model company from its own account; the service runs an open-weight model on servers it pays for; or an open-weight model runs in each user's browser. Cases: `cost-who-bears`, `cost-subscription`, `cost-light-user`, `privacy-own-device`, `privacy-no-vendor`, `privacy-same-parties`, `privacy-own-machine`, `privacy-public-input`, `access-no-subscription`, `access-all-equipped`, `correctness-capable`, `correctness-enough` |

## Coverage

| goal                 | checks | notes |
| -------------------- | ------ | ----- |
| `o-orientation`      | `a-read-cloud-workflows` |       |
| `c-weigh-cloud-plan` | `a-pick-better-plan`, `a-flip-one-fact`, `a-score-two-plans` |       |

---

## Activities

### `a-read-cloud-workflows`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** a reading the course wrote for this topic, `tasks/read-cloud-workflows.md` in this
  folder, "Where the agent runs, and who pays" (about 1,750 words, about 9 minutes). The
  instructor chose a course-written page over the outside candidates; some framing (where the
  model runs, fixed cost against cost per request, small in-browser models being less capable) is
  borrowed from web.dev Learn AI's "Choose your platform", paraphrased, with no Google product
  named and no browser built-in AI. Its made-up example is new to this topic: Nadia, who built an
  apartment-hunting workflow on her laptop (a program collects listings, an agent following her
  skill file pulls out rent, address and move-in date and judges each listing against her private
  notes), which about 200 students in her university's housing group now want to use. Sections: an
  untitled opening (Problem Set 5's workflow, wanting other people to use it or adding an agent to
  the Problem Set 3 app, and that deploying a web app is not re-taught); Nadia's workflow (the users, their runs, with a
  handful running it every hour, their devices and subscriptions, and their private notes); Five
  alternative plans (the five plans of the goal's criterion, numbered 1 to 5, with that a chat subscription
  covers OpenAI's and Anthropic's coding agents but not API calls); Cost (BYOK putting heavy users'
  runs on their own keys, and under plan 4 Nadia paying for servers instead of per token, which
  is cheaper or not depending on how carefully she sizes them; then cost to the users: per-token billing on an API key
  against a subscription's low cost for one more run, with the course's own experience of a subscription against API credits, so a heavy user who already subscribes pays
  far less under plan 1, and a light user with no subscription pays less under plan 2); Privacy (who besides the user sees the step's data
  under each plan, BYOK and the service paying doing about as well, API retention and the promise not to train, a chat subscription's
  training setting, so plan 1 beats plans 2 and 3 for a user who has turned training off, and public data
  making every plan tie); Access (who can start it: a laptop, a subscription and setting the
  workflow up for plan 1, with plan 1 tying the service plans if every user had all three; a
  model-company account and API key for BYOK; a browser for the service plans; a capable device
  and a large download for the browser plan); Correctness (open-weight models less capable, the small browser ones still less,
  and Nadia's trial: the extraction step about as well, the judging step better with a model
  company's model); Weighing a plan ("about as well" as an honest answer on every goal, and no plan
  wins on every goal). Words in place, each in bold where introduced:
  API key, BYOK and usage-based pricing (in plans 2 and 3), open-weight model (plan 4), data
  retention (Privacy). Also in bold, though none is a word of this topic: the five plan headings.
  It names OpenAI and Anthropic as model companies, ChatGPT and Claude as their chat apps, WebGPU as
  the browser feature, and, in the course's own experience, OpenAI's Sol and Astra models with the
  $20 a month and $50 a month it paid, and no other real product, model or price.
- **learner does:** reads the page once, top to bottom, and stops once, at the end of Five alternative plans,
  where the page says to stop, answering before reading on ("I don't know yet" is an honest
  answer): if Nadia's service runs the step for all 200 students, does plan 2 or plan 3 cost Nadia
  less? The Cost section opens with the page's own answer, which the learner then reads. Then the
  close, about 2 minutes, with the reading still beside them: answers the one question the tutor
  puts: with this page beside you, could you now take a short description of a workflow, two plans
  for where its agent step runs and who pays, and one goal (cost, privacy, access or correctness),
  and say which plan does better on that goal, or that they do about as well?
- **tutor role:** explainer
- **tutor does:** puts the reading in front of the learner by opening the file
  `tasks/read-cloud-workflows.md` from the topic folder on the local filesystem, so the learner's
  agent shows it formatted in a sidebar; does not paste it into the chat. Stays quiet through the
  reading except at the stop and when asked. At the stop, takes the learner's answer first and
  gives no verdict, then lets the learner read on to the page's own answer. The page's answer is plan 2, since under BYOK the hourly users' runs are billed
  to their own keys; what the tutor looks for is an answer that turns on who is billed for whose
  runs. An answer that picks plan 2 for that reason, or any reason resting on whose bill the runs
  land on, gets no question: the tutor says "read on and see" and the learner goes straight on to
  the Cost section. So does "I don't know yet", with no question asked. An answer that picks plan 3
  because "one key is simpler", or that names no fact about Nadia's users, gets one near-miss
  question ("who pays for the runs of the students who run it
  every hour, under each plan?"). Does not set or rehearse any word question from `a-words`: does
  not ask the learner to define any of the five words, to say what separates a word from its
  nearest confusable in goals.md (an open-weight model and a free tier, an API key and a
  subscription or a password, BYOK and sign-in, usage-based pricing and a subscription or an
  overage, data retention and training on user data or a backup), or to correct a misused sentence.
  Does not set or rehearse a question from this topic's capability activities for any workflow
  beyond Nadia's; if the learner asks how to do that, says the activities during or after the
  session 23 class are for that. Before the learner starts reading, not during it, says briefly three
  things: that deploying the app around the workflow was covered in the hosting, deploy config,
  deploy pipeline and database hosting topics and is not asked here; that no question asks which
  real company, model or product to use; and that the plans' prices and retention periods change
  often, so the page gives no current price list or retention period and no question turns on one. At the close, puts the readiness
  question as written above and rules on the answer.
- **done when:** criterion met. The bar for this goal is did it once and help is expected
  throughout, so the ruling is on the learner's answer to the readiness question. A plain yes is
  `criterion: met`. A hedge, with no plain no, is `criterion: unclear`: ask which goal or plan feels
  shaky, go over its section once more (Five alternative plans, or Cost, Privacy, Access or Correctness), and
  put the question again. A second hedge stays
  `unclear`: the tutor says the capability is taught in the session 23 class and offers the
  capability activities during or after it. Before session 23, an answer that waits on the class is a hedge,
  not a no. A plain no is `criterion: not met`: record it, ask what is missing, and offer to go back
  over the part that bears on it; don't put the question again in the same sitting. This goal isn't
  required, so a no never blocks anything else the learner wants to try.
- **worked example:** n/a
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. It
  shows nothing about the five words, which have their own supply in `a-words`, and nothing about
  the capability: the reading works one example, the stop is helped, ungraded and answered just
  before the page gives its own answer, and the readiness question asks only whether the learner
  thinks they could do the same. The reading is one course-written page built on one made-up
  workflow, so it shows nothing of a workflow in another domain, or of the case worked in the
  session 23 class.
- **offer as:** this topic's orientation: one short page the course wrote, following one made-up
  apartment-hunting workflow from a laptop to 200 users, through the five plans for where its
  agent step runs and who pays, and what each does to cost, privacy, access and correctness. One
  short stop and a one-question close. About 14 minutes.

### `a-pick-better-plan`

- **serves:** `c-weigh-cloud-plan`
- **supports:** attempt
- **checks:** `c-weigh-cloud-plan`
- **artifact:** no external source. A described workflow told in a short paragraph, then two plans
  and one goal, with one three-choice question, from this activity's bank or written live per the
  generator below. About 2 or 3 minutes a question.
- **learner does:** reads the scenario and the two plans, then picks which plan does better on the
  named goal, or that they do about as well.
- **tutor role:** examiner
- **tutor does:** the capability is taught in the session 23 class (`taught elsewhere`), and this
  activity is for during or after it: before session 23 the tutor says so and offers to wait, and goes ahead
  if the learner wants. Sets the question as served, without rewording it or hinting; never names
  the cases or which fact matters, and never says what is wrong with an option before the learner
  has chosen. Gives help whenever it is asked for, and records the attempt as helped. When the
  generator is run live, writes the key and the case into the record before showing the question.
  Labels the attempt with the question's path, or `a-pick-better-plan/<shape>` when run live, and
  records the case with `--cases` (none for `cost-reimbursed`, the one shape that carries no case). Rules from the
  rubric's `answer`. If the learner asks which real company or product to use, or how to deploy
  it, says this question doesn't ask that.
- **done when:** the criterion met with no help, case by case: a right choice passes the case its
  question carries. There is no half credit.
- **generator:** **A scenario** is one made-up workflow, told in one paragraph of running prose,
  seven to ten sentences, in the third person about the person who built it, who is named. It says
  what the workflow is for and what its steps are, in plain words; it was first built on that
  person's own laptop, at least one step is done by an agent following a skill file they wrote, and
  now other people (named as a group: "the club's forty members", "the shop's six staff") are to use
  it. Whatever goal the question names, the paragraph states facts from all four of these areas,
  mixed through it in no fixed order and never under labels:
  - **users and runs**: who the users are, how many, and how many runs they make, and how evenly
    (all about the same, or a few running it far more often than the rest);
  - **the data**: what the agent step reads, and whose it is (members' health notes, tenants'
    complaints, public bus timetables), and any wish or rule about who may see it;
  - **starting it and seeing results**: what devices the users have, whether they have a
    subscription to a model company's chat app or an API key, whether they have set the workflow
    up on their own laptops, and who needs to start a run or see its results, from where;
  - **what the step asks of a model**: what the agent step has to do, and a stated result of trying
    an open-weight model on it ("When she tried an open-weight model on last month's messages, it
    sorted them as well as the model she uses now", or "it got about one in four wrong, where the
    model she uses now got nearly all right"). When either plan is the browser plan, the trial is
    always of a model small enough to run in a browser, and says so ("a small open-weight model of
    the kind that runs in a web browser"); when the other plan is the service's open-weight model,
    the scenario states a trial of each.
  Where cost is the goal, the paragraph also states made-up round prices: what a run costs through
  a model company under usage-based pricing (at API prices, per token, said as a price a run), and for a plan with a subscription what it costs a month, whether the user already
  pays for it, and that the user's runs fit within its limits. A scenario may mention a model
  company's data retention as an ordinary fact; it never changes an answer, since a company that
  keeps prompts only briefly still sees them.

  **The deciding fact is one fact among the others.** It is never the first or last sentence, never
  the only fact in its area, and never phrased in the words of the case line in goals.md: no "far
  more", "no subscription", "should not leave", "most capable", "simple enough", "number of runs",
  "no model company", "already have" or "far less". A subscription the user pays for already is
  said as history or habit ("Theo has paid for a chat subscription since last spring, mostly for
  his coursework"). Facts are stated as facts, never as what they mean for a plan, and never using
  the words cost, privacy, access or correctness.

  **The plans.** Below the paragraph, two plans, labeled "Plan A" and "Plan B", each one sentence,
  drawn from these five and worded close to these forms:
  - own machine: "Each <user> runs the workflow on their own laptop, with the agent step working
    under their own subscription to a model company's chat app."
  - BYOK: "<Owner> runs the workflow as a web service, BYOK: each <user> gives it their own API key,
    and the agent step's model calls are billed to that key."
  - service pays: "<Owner> runs the workflow as a web service and pays a model company for the
    agent step's model calls from <owner>'s own account."
  - service open-weight: "<Owner> runs the workflow as a web service, with the agent step done by an
    open-weight model on a server <owner> rents."
  - browser: "<Owner> runs the workflow as a web page, with the agent step done by an open-weight
    model that runs in each <user>'s web browser, on their own device."
  Which of the pair is Plan A varies across the bank.

  **The goals, as the question names them.** Each is fixed in meaning:
  - cost: what one named party pays for the agent step's model compute, either the service's
    owner, the person or organization that runs it ("cost to the club"), or its users, one named
    user or kind of user ("cost to Theo, who runs it every hour"). Every cost question names whose
    cost. To the owner, the own-machine and BYOK plans cost nothing for the model, since users
    pay; to a user, the service-paying and service-run plans cost nothing. A subscription the user
    already pays for counts at what it adds, which is nothing while their runs fit within its
    limits; one they would buy only for this counts at its monthly price;
  - privacy: how many parties beyond the user see the data the agent step reads (the service, a
    model company); a plan does better when fewer do, and they do about as well when the same ones
    do, or when the step reads no one's private data;
  - access: how many of the intended users can start a run and see its results, given what they
    have and have done: for the own-machine plan, a laptop, a subscription and the workflow set up
    on it; for BYOK, a model-company account and an API key; for the browser plan, a device able to
    run the model; for the other service plans, only a web browser;
  - correctness: how often the agent step's output is right, by the scenario's stated trial.

  **A question** reads: "On <goal as named>, which plan does better?", then three numbered options:
  "Plan A", "Plan B", "They do about as well on <goal>". `type: mcq`. One question per scenario.

  **Shapes**, each with the case it carries, which its rubric `cases:` line lists. A shape marked
  "no case" carries none; its `cases:` line is left empty and a pass on it meets no case.
  - `cost-who-bears` (`cost-who-bears`): service pays against BYOK, cost to the owner. What decides
    it is whose bill the runs land on: under BYOK each user's runs are billed to their own key, so
    the owner pays for none of them, however the runs are spread. The paragraph says how many users
    there are and how often they run it, evenly or not, as ordinary facts; neither decides it.
    Answer BYOK.
  - `cost-reimbursed` (no case, tie): the same pair, cost to an organization that has said it will
    repay each member's API bill from its own budget. Answer about as well.
  - `cost-subscription` (`cost-subscription`): own machine against BYOK, cost to one named heavy
    user who already pays for a subscription to a model company's chat app for other things, whose
    runs (many a day) fit within its limits, and whose runs on an API key would cost a stated
    made-up price each. Answer own machine (the subscription adds nothing; the API key's bill grows
    with every run).
  - `cost-light-user` (`cost-light-user`): the same pair, cost to one named user who has no subscription and
    would buy one only for this, and who runs it a few times a month at a stated made-up price a
    run on an API key, far below the subscription's monthly price. Answer BYOK.
  - `privacy-own-device` (`privacy-own-device`): browser against service open-weight; the step reads
    each user's own private data (their health notes, their household budgets), said as what it is
    and nothing more. Answer browser.
  - `privacy-no-vendor` (`privacy-no-vendor`): service open-weight against service pays; the step
    reads private data the owner is allowed to see (a club's records of its own members) but that
    the members have not agreed to share with any outside company. Answer service open-weight.
  - `privacy-own-machine` (`privacy-own-machine`): own machine against BYOK; the step reads each
    user's private data, and the paragraph states, in its own words, that each user has turned off
    training in their subscription's settings. Answer own machine (the model company sees it either way; the BYOK service
    also does).
  - `privacy-public-input` (`privacy-public-input`): any of the four other privacy pairs, where the step reads
    only public material (published timetables, a shop's public price list) and no user's data.
    Answer about as well.
  - `privacy-same-parties` (`privacy-same-parties`): BYOK against service pays, the step reading
    private data. Answer about as well (the service and the model company see it under both).
  - `access-no-subscription` (`access-no-subscription`): service pays against own machine; among the
    users are many with no subscription, or only a phone, or both. Answer service pays.
  - `access-all-equipped` (`access-all-equipped`): the same pair, where every user is stated to have
    a laptop and a subscription, to have already set the workflow up on it, and to need only their
    own results there. Answer about as well.
  - `correctness-capable` (`correctness-capable`): an open-weight plan (service open-weight or
    browser) against a model-company plan (own machine, BYOK or service pays); the stated trial
    shows the open-weight model wrong much more often. Answer the model-company plan.
  - `correctness-enough` (`correctness-enough`): the same kinds of pair, where the trial shows the
    open-weight model about as good. Answer about as well.

  **Illustrations**, not bank items; their domains (a community garden, a choir) are used by no
  bank in this topic.
  - `cost-who-bears`, Medium: "Rosa built a workflow on her laptop that reads a community garden
    member's notes on their plot and has an agent, following her skill file, draft a watering and
    planting plan for the week. The garden has about sixty members. Most will ask for a plan once a
    week, but the eight members who run the seedling program want a fresh plan every morning.
    Members have phones and most have laptops, and a few have their own API key from a model
    company. The plot notes say little beyond what is planted where. When Rosa tried an open-weight
    model on the notes, its plans were often wrong about timing. Each plan through the model company
    she uses costs about 5 cents." Plan A: service pays; Plan B: BYOK. "On cost to Rosa, which plan
    does better?" Answer 2, Plan B: under BYOK each member's calls are billed to their own key, so
    the seedling members' daily runs cost Rosa nothing; under Plan A she pays for every run. Case
    `cost-who-bears`.
  - `correctness-enough`, Hard: a choir's workflow, where the agent step reads each singer's message
    and pulls out which rehearsals they will miss; the director tried a small open-weight model of
    the kind that runs in a web browser on a month of messages "and it pulled out the same dates as
    the model she uses now". Plan A: browser;
    Plan B: service pays. "On correctness of the absence list, which plan does better?" Answer 3,
    about as well. Case `correctness-enough`.

  **How hard.** Medium when the deciding fact is said in plain terms ("most members have no
  subscription to any model company's chat app"). Hard when it must be put together from two
  ordinary facts (a cost question where the learner multiplies runs by price; an access question
  where "most members only have a phone" must be joined to the own-machine plan needing a laptop),
  or when the tempting answer comes from a fact in another area (a privacy question in a scenario
  whose trial shows the open-weight model weaker). The question wording is unchanged.

  **Spread across the bank.** A bank is thirteen scenarios: each of the twelve case shapes once,
  plus `cost-reimbursed` once. At least two of the
  cost questions name a user's cost and at least two the owner's. About half are Hard. "About as well"
  is the answer in five of them, on every goal. Plan A and Plan B are each the answer at least three
  times. No domain is apartment hunting, the reading's example. When the generator is run
  live, the tutor picks each next shape to carry a case the learner hasn't passed, and puts a tie
  shape in about one question in three.

  **Domains** vary by scenario, none repeating within the bank: a running club's training plans, a
  food co-op's order sorting, a tenants' association's repair requests, a small bakery's catering
  quotes, a youth soccer league's game reports, a hiking group's trip packing lists, a dog rescue's
  adoption applications, a neighborhood newsletter's submissions, a book club's discussion
  questions, a family's shared recipe box, a theater group's audition notes, a cycling shop's repair
  tickets, a library volunteer's reading-level labels, a small farm's harvest logs, a community
  radio station's show logs, a commuter group's bike-route plans. No domain from
  the other two activities' lists, and no homework or grading workflow.

  The rubric gives the `answer` (the 1-based choice) and, in a `tutor note`, the sentence or
  sentences that settle it and, for each other option, why it is wrong (for a tie, why neither plan
  is ahead on this goal; for a plan answer, what the other plan does on the goal and why "about as
  well" fails). Credit: full for the right option; none for the others.
- **worked example:** shown only as help when asked for, which records the attempt as helped. The
  tutor works the illustration of the nearest shape aloud: says, for the named goal, what each plan
  does (who pays and for what; who sees the data; what a user needs to start it; which model does
  the step), then which facts in the paragraph bear on that and which don't, never adding a fact
  the illustration leaves out, and then which option follows. It may point to the section on the
  matching goal in `tasks/read-cloud-workflows.md`: Cost, Privacy, Access or Correctness.
- **doesn't show:** the learner picks among three options and gives no reason, so a pass can be a
  guess, a third of the time. Every scenario states every fact its answer needs, including a trial
  result for the model, so a pass doesn't show the learner would notice a missing fact (who the
  users are, whether anyone tried an open-weight model) and ask, as their own final project will
  make them. Each question names one goal and two plans, so a pass doesn't show the learner would
  weigh all four goals together or choose among all five plans. Many answers follow from the plan
  pair and the goal alone; the tie shapes and the deciding fact set among others make a lookup
  table fail some of the time, not all of it.
- **offer as:** the quick check, during or after session 23: a short description of a workflow, two plans for
  its agent step, one goal, and you pick which plan does better or that they do about as well.
  About 2 or 3 minutes a question. One question per scenario, so it is the most direct way to meet
  a particular case.

### `a-flip-one-fact`

- **serves:** `c-weigh-cloud-plan`
- **supports:** attempt
- **checks:** `c-weigh-cloud-plan`
- **artifact:** no external source. A described workflow, two plans and one goal, with a
  three-choice question; then the same workflow with one fact changed, and the same question again.
  From this activity's bank or written live per the generator below. About 3 minutes for a
  scenario's first question and 1 for its second.
- **learner does:** reads the scenario and the two plans and picks which plan does better on the
  named goal, or that they do about as well; then reads the one changed fact and picks again.
- **tutor role:** examiner
- **tutor does:** as `a-pick-better-plan`'s, including the offer to wait for session 23, except that
  it labels a live run `a-flip-one-fact/<pair>/first` or `a-flip-one-fact/<pair>/second`. Sets the
  second question only after the first is answered and never says whether the first was right
  before the second is answered. Sets the second question even though it carries no case, since the contrast is what this activity is for; skips it only if the learner
  asks to stop.
- **done when:** the criterion met with no help, case by case: a right choice passes the case its
  question carries. There is no half credit.
- **generator:** **A scenario** is a `a-pick-better-plan` scenario (same paragraph rules, plan
  forms, goal meanings, deciding-fact rule and options), with two `###` questions. The shared setup
  holds the paragraph and the two plans. The first question is "On <goal>, which plan does better?"
  with the three options. The second question begins "Now suppose one thing is different: <one
  sentence replacing one fact of the paragraph>. Everything else is as before." and then asks the
  same question with the same three options. The changed sentence states a fact, never what it
  means for either plan, and is never phrased in a case line's words.

  **Which question carries a case.** Only the first question of a pair carries one: the second is
  answered with the change sentence pointing at the fact that matters, so passing it shows less.
  Every second question's `cases:` line is left empty.

  **Pairs**, each naming the shapes of `a-pick-better-plan` its two questions take, in order, and
  the case the first carries:
  - `who-bears`: the service's owner is an organization (a club, a garden, a league), and both
    questions ask the cost to that organization by name. First `cost-who-bears` (BYOK); second
    `cost-reimbursed` (tie), the change being that the organization will repay every member's API
    bill from its own budget.
  - `heavy-light`: both questions ask the cost to one named user. First `cost-subscription` (own
    machine); second `cost-light-user` (BYOK), the change being one sentence replacing what the
    paragraph says about that user's runs and subscription (they run it a few times a month and
    would buy a subscription only for this).
  - `light-heavy`: the same, reversed: first `cost-light-user` (BYOK); second `cost-subscription`
    (own machine), the change saying the user runs it many times a day and has paid for a
    subscription for some time. These two are the only pairs whose change sentence carries two
    facts, since both make up how that user would pay.
  - `own-device`: first `privacy-own-device` (browser); second `privacy-public-input` (tie), the
    change being that the step now reads only public material.
  - `no-vendor`: first `privacy-no-vendor`; second `privacy-public-input` (tie), likewise.
  - `own-machine`: first `privacy-own-machine`; second `privacy-public-input` (tie), likewise.
  - `same-parties`: first `privacy-same-parties` (tie). No fact can separate these two plans on
    privacy, so the second question is always a `no-bearing` change (how many users run it often,
    or the trial result), and stays a tie.
  - `public-input`: first `privacy-public-input` (tie), on the `own-device`, `no-vendor` or
    `own-machine` pair; second, the change being that the step now also reads each user's own
    private data, so the answer is that pair's privacy answer (on the `own-machine` pair, the
    paragraph also states that each user has turned off training in their subscription's settings).
  - `subscription`: first `access-no-subscription` (service pays); second `access-all-equipped`
    (tie), the change being that every user now has a laptop and a subscription and has already
    set the workflow up on it.
  - `equipped`: first `access-all-equipped` (tie); second, the change being that most users now
    have only a phone, so the answer is service pays.
  - `trial-capable`: first `correctness-capable` (the model-company plan); second
    `correctness-enough` (tie), the change being the trial's result.
  - `trial-enough`: the same, reversed: first `correctness-enough`; second `correctness-capable`.
  - `no-bearing` variant, applying to any pair but `heavy-light` and `light-heavy`:
    the second question's change is a fact from a different area that doesn't bear on the named
    goal (the number of runs, in a privacy question; the trial result, in an access question), so
    the answer stays the same as the first. About one scenario in three is a `no-bearing` variant,
    so a learner cannot assume the answer flips.
  Between the first questions every case is carried.

  **Illustration**, not a bank item: the garden illustration in `a-pick-better-plan`, with the one
  difference that Rosa runs the service for the garden and its account is the garden's, so both
  questions ask "On cost to the garden, which plan does better?" First question: answer 2, Plan B,
  BYOK (`cost-who-bears`). Second: "Now suppose one thing is different: the garden's committee has
  agreed to repay every member's API bill from the garden's budget. Everything else is as before."
  Answer 3, about as well, since the garden pays for every run either way; no case.

  **How hard**, as in `a-pick-better-plan`, judged on the first question; the second is Medium when
  the change flips the answer and Hard in a `no-bearing` variant.

  **Spread across the bank.** A bank is twelve scenarios, each pair once, with four of them
  `no-bearing` variants, `same-parties` among them. Plan A and Plan B are each the answer at least
  five times across the twenty-four questions, and "About as well" at least eight times. When run
  live, the tutor picks pairs to carry cases the learner hasn't passed.

  **Domains** are this activity's own, none repeating within the bank: a swim team's meet entries,
  a church food drive's pickup routes, a makerspace's tool-training sign-offs, a small orchestra's
  part assignments, a scout troop's campout menus, a school parents' carpool, a birding club's
  sighting reports, a cat shelter's foster check-ins, a chess club's game reviews, a rowing club's
  boat bookings, a ski club's trip sign-ups, a language exchange's partner matches, a
  bowling league's score sheets. No domain from the other two activities' lists, and no homework
  or grading workflow.

  The rubric gives each question's `answer` and, in a `tutor note`, the settling sentence (for the
  second, the changed fact and why it does or doesn't bear on the goal) and why each other option
  is wrong. Credit: full for the right option; none for the others.
- **worked example:** shown only as help when asked for, which records the attempt as helped. As
  `a-pick-better-plan`'s for the first question; for the second, the tutor says which area the
  changed fact is in and whether that area bears on the named goal, then works the choice again.
- **doesn't show:** as `a-pick-better-plan`'s. The second question is set beside the first, so a
  pass on it shows the learner can tell whether one fact matters to one goal when told which fact
  changed, not that they would find it unprompted, which is why it carries no case; the `no-bearing` variants keep a flip from being
  assumed, though a learner who guesses "it flips" is still right two times in three.
- **offer as:** the contrast check, during or after session 23: the same workflow twice, one fact changed,
  and you say each time which plan does better on one goal. About 4 minutes a scenario. Best for a
  learner who keeps reaching for the same plan whatever the facts say.

### `a-score-two-plans`

- **serves:** `c-weigh-cloud-plan`
- **supports:** attempt
- **checks:** `c-weigh-cloud-plan`
- **artifact:** no external source. A described workflow and two plans, then a three-choice question
  for each of three or four goals in turn, from this activity's bank or written live per the
  generator below. About 3 minutes for a scenario's first question and about 1 for each after.
- **learner does:** reads the scenario and the two plans, then for each goal asked about picks
  which plan does better on it, or that they do about as well.
- **tutor role:** examiner
- **tutor does:** as `a-pick-better-plan`'s, including the offer to wait for session 23, except that
  it labels a live run `a-score-two-plans/<pair>/<goal>`. Once a scenario's remaining questions
  would carry only cases the learner has already passed, or no case, skips them, as study skips
  questions no longer needed.
- **done when:** the criterion met with no help, case by case: a right choice passes the case its
  question carries. There is no half credit.
- **generator:** **A scenario** is a `a-pick-better-plan` scenario (same paragraph rules, plan
  forms, goal meanings and deciding-fact rule), except that its paragraph runs ten to fourteen
  sentences, since it states the deciding facts for every goal asked about, each among the others. It has three or four `###` questions, one per goal, in
  this order where asked: cost, privacy, access, correctness. Each reads "On <goal as named>, which
  plan does better?" with the three options. No question's text gives away another's answer.

  **Pairs**, with the answer and case each goal's question takes. A question whose pair and goal
  match no case carries none.
  - `own-servers-or-pay` (service open-weight against service pays): privacy, service open-weight (`privacy-no-vendor`, the data being
    private and allowed to the owner but not to outside companies) or, where the step reads only
    public material, about as well (`privacy-public-input`); access, about as well (both are web
    services anyone can open; no case); correctness, by the trial of the open-weight model the
    server would run (`correctness-capable` or `correctness-enough`). No cost question.
  - `byok-or-pay` (BYOK against service pays): cost to the owner, BYOK (`cost-who-bears`: under BYOK
    the runs are billed to the users' own keys; how many users run it, and how often, are ordinary
    facts that don't decide it); privacy, about as well (the service
    and the model company see the data under both; `privacy-same-parties`); access, service pays (many users have
    no API key and would have to set up a paid account; no case); correctness, about as well (the
    same kind of model company's model; no case).
  - `laptop-or-byok` (own machine against BYOK): cost to one named user, own machine for a heavy
    user who has paid for a subscription for some time and whose runs fit within its limits
    (`cost-subscription`), or BYOK for a light user with no subscription who would buy one only for
    this (`cost-light-user`), those facts stated as ordinary ones; privacy, own machine
    (`privacy-own-machine`, the paragraph stating that each user has turned off training in their
    subscription's settings); access, keyed on what the paragraph states about the users' laptops,
    subscriptions, set-up and API keys, which it always states for both plans: BYOK when many have
    an API key or a model-company account but no laptop or subscription, own machine when many
    have a laptop and a subscription with the workflow set up but no API key, about as well when
    every user has both or the same share lacks each (no case); correctness, about as well (model
    companies' models under both; no case).
  - `laptop-or-pay` (own machine against service pays): cost to the owner, own machine (each user's
    subscription pays; no case); access, service pays where many users have no subscription or only
    a phone (`access-no-subscription`), or about as well where every user has a laptop and a
    subscription and has already set the workflow up (`access-all-equipped`); correctness, about as
    well (no case). No privacy question.
  - `browser-or-server` (browser against service open-weight): privacy, browser
    (`privacy-own-device`); access, by the facts (service open-weight when many users have only
    older phones or computers the scenario says can't run the model; about as well when all have
    recent laptops; no case); correctness, by the trial comparing the small model that fits in a
    browser against the larger one the server runs, about as well or service open-weight (no case).
    No cost question.
  Between the pairs every case is carried: a bank needs `own-servers-or-pay` twice (once with
  private data and a weaker trial, once with public material and a trial as good),
  `laptop-or-byok` twice (a heavy user once, a light user once), `laptop-or-pay` twice (once short
  of equipment, once all equipped), and `byok-or-pay` and `browser-or-server` once each.

  **Illustration**, not a bank item: the choir from `a-pick-better-plan`, with Plan A service
  open-weight and Plan B service pays; facts added for singers' messages
  sometimes giving health reasons, which the choir's rules say stay with the choir, and the trial
  restated as one of the open-weight model the server would run, with the same result. Privacy: Plan A (`privacy-no-vendor`).
  Access: about as well. Correctness: about as well (`correctness-enough`).

  **How hard**, as in `a-pick-better-plan`, scenario by scenario.

  **Spread across the bank.** A bank is eight scenarios, as listed above, about twenty-seven
  questions, half the scenarios Hard. "About as well" is the answer on each of the four goals at
  least once, and on at least eight questions in all. When run live, the tutor
  picks pairs to carry cases the learner hasn't passed.

  **Domains** are this activity's own, none repeating within the bank: a volunteer fire
  department's training records, a craft fair's vendor applications, a little league's snack
  schedule, a nonprofit's grant reports, a robotics club's parts orders, a senior center's ride
  requests, a quilting circle's pattern swaps, a debate team's practice rounds. No domain from the other two activities' lists, and
  no homework or grading workflow.

  The rubric gives each question's `answer` and, in a `tutor note`, the settling sentence and why
  each other option is wrong. Credit: full for the right option; none for the others.
- **worked example:** shown only as help when asked for, which records the attempt as helped. As
  `a-pick-better-plan`'s, worked for one goal of the illustration, then the tutor says aloud that the
  same two plans can come out differently on another goal and why.
- **doesn't show:** as `a-pick-better-plan`'s. The questions about one scenario share its facts, so
  a learner who misreads one fact can miss several; and the fixed goal order means the same plan
  pair is in view throughout, which helps the learner and makes a pass a weaker sign that they
  would weigh a new pair.
- **offer as:** the scorecard check, during or after session 23: one workflow and two plans, then which plan
  does better on each goal in turn. About 3 minutes for the first question and 1 for each after.
  Shows most clearly that a plan can win on one goal, lose on another and tie on a third.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
