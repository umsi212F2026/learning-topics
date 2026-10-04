# Activities: database hosting

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

2026-10-04. The minimum route (orientation reading and dry run, then a-judge-described-plan with its worked example, then the seven words) comes to about 55 minutes and fits the topic's 60-minute budget only if the first counting attempt passes. A retry, or either study activity, takes it past 60. a-trace-own-database-setup and a-judge-own-deploy-plan belong naturally with Problem Set 3 (Oct 8 to 14), not before session 11.

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |
| `c-plan-first-deploy` | say what has to be in place for an app's database the first time it is deployed | Given an agent's plan for deploying an app's database for the first time, says whether the data will survive a redeploy, and whether production gets a database of its own, built by the code rather than copied from the laptop. It passes when they catch a plan that fails either one and don't fault a plan that meets both. |

## Coverage

<!--
  Derivation convention: an activity carrying `checks` sits only in the `checks` cell, never in
  `study`. Activities whose `serves` is `all` sit on the `o-orientation` row only.
-->

| goal | study | checks | notes |
| ---- | ----- | ------ | ----- |
| `o-orientation` | `a-read-database-survives` | `a-dry-run-database-plan` | |
| `c-plan-first-deploy` | `a-trace-own-database-setup`, `a-contrast-plan-pairs` | `a-judge-described-plan`, `a-judge-own-deploy-plan` | Both checks show the host's storage rule to the learner as true, and every banked plan says where the database lives. Neither check tests whether the learner would notice a plan that never says where the data goes, or doubt a plan's own claim that the host keeps its files, though that is the Problem Set 3 situation. The first counting question is also always an own-database fault (see a-judge-described-plan's note), so a met goal may rest on no unaided catch of a survival fault. When the learner reaches Problem Set 3, ask where their plan says the database lives and how they know the host keeps that place. |

---

## Activities

### `a-read-database-survives`

- **serves:** `all`
- **supports:** orient
- **artifact:** three short passages from three free pages, no account, read in this order as one
  sitting. All three opened 2026-10-04.
  1. MDN Web Docs, "Django Tutorial Part 11: Deploying Django to production" (last modified
     Sep 11, 2026), subsection "Database configuration",
     https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Server-side/Django/Deployment#database_configuration.
     Read only its first two paragraphs (about 130 words, no code): SQLite "cannot be used on some
     popular hosting services, such as Heroku, because they don't provide persistent data storage",
     and the other approach, "a database that runs in its own process somewhere on the Internet",
     here Postgres. The page is about Django, but these two paragraphs are not. Stop at the third
     paragraph (`DATABASE_URL`, which belongs to deploy-config) and skip the rest of the page.
  2. Render Docs, "Persistent Disks", https://render.com/docs/disks (no date on the page). Read the
     opening section, before "Setup" (about 170 words): "By default, Render services have an
     ephemeral filesystem", whose changes "are lost every time the service redeploys or restarts",
     and the persistent disk that preserves them. Then, under "Disk limitations and considerations"
     at the bottom, only the first bullet ("Only filesystem changes under your disk's mount path are
     preserved") and the bullet on zero-downtime deploys (about 100 words). Skip everything between.
  3. The Odin Project, "Using PostgreSQL" (Node path),
     https://www.theodinproject.com/lessons/nodejs-using-postgresql, section "Populate the db via a
     script". Read its two sentences of prose and skim the script for three things only: `CREATE
     TABLE IF NOT EXISTS`, the `INSERT` of three names, and the line that logs "seeding...". Skip
     the instruction about the PostgreSQL shell. Read "Local vs production dbs" in full (about 130
     words). Under "Populating production dbs", read only the code block's two comments ("populating
     local db", "populating production db ... run it from your machine once after deployment"); skip
     its prose, which is about passing connection information (deploy-config's business).
  About 550 words and a code skim: 7 minutes of reading, about 15 with the two stops. Words in
  place: SQLite and Postgres (MDN), ephemeral disk and persistent volume (Render's "ephemeral
  filesystem" and "persistent disk"), redeploy (Render), production (MDN's title, Odin), seed data
  (Odin's "seeding..."). Not repeated here: MDN "What is a web server?" and Odin's "Deployment"
  lesson, read in cloud-hosting; its "see database-hosting" boxes are what this fills.
- **verified:** 2026-10-04
- **learner does:** reads, and stops twice to answer in a sentence or two before reading on. Neither
  stop needs their code open; looking through their own app is `a-trace-own-database-setup`'s job.
  "I don't know yet" is an honest answer:
  1. After Render: says what their Problem Set 2 restart test would show if their app's SQLite file
     sat on an ephemeral disk and the host redeployed between adding something and checking for it.
  2. After Odin: says which lines of Odin's script build the production database, and what would be
     different in production if the laptop's database file were copied up instead.
- **tutor role:** explainer
- **tutor does:** stays quiet through the reading except at the stops and when asked. At each stop,
  takes the learner's answer first and replies with one near-miss question rather than a verdict.
  **The restart test**, which the learner did in Problem Set 2 (prior topic web-backends): add
  something through the app, restart the local server, and check through the app's own HTTP API
  that it is still there. It passes on the laptop because the SQLite file stays on the laptop's
  disk across a restart; on a host with an ephemeral disk, a redeploy starts the server on fresh
  storage, so the file is gone, the app may well start and make empty tables, and the item is
  missing. Near-miss at stop 1: "the app still starts and answers after the redeploy; would your
  restart test pass?" At stop 2, if the learner says copying the laptop's file is fine, asks what is
  in that file now (their Problem Set 2 test data), since test data in production and copying it up
  are what this topic watches for.
  Says that Odin's way (a script the developer runs once against the production database) and
  tables made by the app's own startup code are both "built by the code"; copying the laptop's file
  is not. **Vendor facts, as checked on the vendors' own pages 2026-10-04,** if the learner asks
  where volumes can be had: Render's persistent disks attach only to paid services; Railway's
  volumes (https://docs.railway.com/reference/volumes) are 0.5 GB on the Free and Trial plans, one
  per service, with a little downtime on each redeploy. Choosing a host is cloud-hosting's;
  connection strings and passwords are deploy-config's; backups and migrating real data are a
  later topic. Makes no change to the learner's app.
- **done when:** both stops have an answer: what the restart test would show after a redeploy on an
  ephemeral disk, and what in Odin's script builds production's database as against copying the
  laptop's file. No `checks`: the readiness indication is taken in `a-dry-run-database-plan`, which
  follows.
- **offer as:** this topic's orientation, one entry holding a sequence of three short passages: why
  SQLite needs storage that lasts (MDN), what ephemeral and persistent storage are on a real host
  (Render), and a production database filled by a script rather than by hand (Odin). About 15
  minutes with the two short stops; with `a-dry-run-database-plan`, about 20. Followed by
  `a-dry-run-database-plan`.
- **check note:** MDN's line that SQLite "cannot be used on some popular hosting services" can
  leave a learner thinking SQLite itself is unsafe in production. At the Render stop, make clear
  that SQLite on a persistent disk or volume is sound, and that the trouble is the ephemeral disk.
  A learner who keeps the wrong idea will fault the sound SQLite-on-a-volume plans in the checks
  and fail.

### `a-dry-run-database-plan`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** no external source. The learner's answers from `a-read-database-survives`, still in
  front of them. About 5 minutes. Nothing needs to be running.
- **learner does:** two quick rehearsals, neither judged, each answered in a sentence. First, the
  tutor gives one line saying where a made-up app's database will live on a made-up host, and the
  learner says whether its data would survive a redeploy. Second, the tutor gives one line saying how
  that app's production database gets its tables and rows, and the learner says whether it is built
  by the code or copied from the laptop. Then answers the question the tutor puts: with the readings
  and your answers beside you, could you now take an agent's plan for deploying an app's database
  for the first time and say whether the data will survive a redeploy, and whether production gets
  a database of its own, built by the code rather than copied from your laptop?
- **tutor role:** explainer
- **tutor does:** sets the two rehearsals from the generator below and grades neither. If an answer
  shows a misunderstanding (a file "on the server" taken as safe; a restart taken as the only thing
  that can lose data), explains it once and moves on. Then puts the readiness question as written
  and rules on the answer.
- **done when:** criterion met. The ruling is on the learner's own indication, not on the
  rehearsals. A plain yes to both parts is `criterion: met`. A hedge on either part, with no plain
  no, is `criterion: unclear`: explain the hedged part once more and ask again; a second hedge stays
  `unclear`, and the tutor offers `a-contrast-plan-pairs`. A plain no is `criterion: not met`:
  record it, ask what is missing, and offer to go back over the stop that bears on it; don't ask
  again in the same sitting. This goal isn't required, so a no blocks nothing.
- **generator:** vary the made-up app (small, React frontend, Express backend, SQLite: a club
  sign-up sheet, a recipe box, a study-group finder) and the host's one-line storage rule, written
  as `a-judge-described-plan`'s generator writes it. Rehearsal one is one plan line placing the
  SQLite file either in the app's folder with no volume (the `ephemeral` case, which that check
  never counts) or under the volume's mount path (sound). Rehearsal two is one plan line on how
  production gets its rows, either the backend creating empty tables at startup (sound) or the
  agent exporting the rows from the laptop's database and importing them into production (a
  fault that check never serves, so the learner doesn't meet a counting plan's deciding detail
  minutes before it). Never use the wording of a `laptop-copy`, `shared-dev`, `outside-mount` or
  `committed-file` step. Fixed: two rehearsals in that order, neither graded, then the readiness
  question word for word. Difficulty doesn't vary: this settles an indication, not a capability.
- **worked example:** if the learner freezes, the tutor answers a different made-up line aloud in two
  sentences, then hands the original back.
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. Each
  rehearsal is one line, helped and ungraded, so it shows nothing about finding the deciding detail
  in a whole plan, and nothing about the seven words, which `a-words` serves.
- **offer as:** the short step that closes orientation, after `a-read-database-survives`, not an
  alternative to it. About 5 minutes; about 20 with the reading.

### `a-trace-own-database-setup`

- **serves:** `c-plan-first-deploy`
- **supports:** deepen
- **artifact:** the learner's own Problem Set 2 repository and their coding agent. About 15
  minutes. Nothing is changed.
- **learner does:** finds four things in their own app, asking the agent to show the lines but
  not to judge them: (1) where the backend sets the path of its SQLite file; (2) what the code does
  when that file doesn't exist (does it create the tables?); (3) whether any code inserts rows
  itself, and which (seed data), as against rows they typed in while testing; (4) whether the
  database file is tracked by git (in `.gitignore` or not). Then says, for a host with an ephemeral
  disk and no volume, and for one with a volume mounted at `/data`, what would happen to their data
  on a redeploy, and what one line of a deploy plan would have to say for it to survive and for
  production to start from the code rather than from their laptop.
- **tutor role:** socratic questioner
- **tutor does:** waits while the learner looks. On each answer, asks one near-miss question ("the
  file is in `.gitignore`; then what does production start with?"; "your volume is at `/data` and
  your file is at `./db/app.sqlite`; which of those survives?"). If item 4 shows the file is
  committed, says plainly that shipping it would copy the laptop's test data up and, on every
  redeploy, put it back. Makes no change to the app.
- **done when:** the learner has all four facts about their own app, and says correctly for both
  hosts whether their data would survive a redeploy and what the plan would need. No `checks`: the
  learner is looking at their own code, not judging a plan.
- **offer as:** the hands-on one, on your own app, and the best preparation for Problem Set 3: what
  you find here is exactly what your agent's deploy plan has to get right, and it makes
  `a-judge-own-deploy-plan` quick. About 15 minutes. Pick `a-contrast-plan-pairs` to practice on
  made-up plans instead.
- **check note:** If the learner's app does not create its tables when the database file is
  missing, the right deploy-plan line is a code step (startup code or a setup script) that makes
  them, never uploading the laptop's file. Steer there if the learner proposes copying the file.

### `a-contrast-plan-pairs`

- **serves:** `c-plan-first-deploy`
- **supports:** deepen
- **artifact:** no external source. Pairs of plan excerpts written by the tutor per the generator
  below, three pairs a sitting. About 10 minutes. Nothing to run.
- **learner does:** for each pair, says which excerpt is sound and which is not, which of the two
  questions the faulty one fails (survives a redeploy; production has its own database built by the
  code), and the one detail that decides it. Some pairs are both sound, and then says so. After the
  last pair, states in a sentence the rule they used for each question.
- **tutor role:** socratic questioner
- **tutor does:** shows one pair at a time and takes the answer before commenting. Where it is
  wrong, asks what the host would do with the file, or where production's rows came from, rather
  than giving the verdict; after one such question, gives the verdict and the deciding detail.
- **done when:** the sitting's last two pairs are both called right on both questions, with the
  deciding detail named, without a near-miss question; and the two stated rules would sort every
  kind of pair in the generator correctly. No `checks`: each pair is identical but for one detail,
  so the learner is shown where to look, which a whole plan never does.
- **generator:** fixed: one made-up app like the learner's (React, Express, SQLite) and one made-up
  host whose storage rule is stated in a line, as `a-judge-described-plan`'s generator states it.
  Each excerpt is two or three lines of an agent's plan; the two excerpts in a pair are word for
  word the same but for one detail. The kinds of pair:
  - survival: the SQLite file's path under the volume's mount path, or beside it in the app's
    folder.
  - built by code: the backend creating the tables at startup, or "the tables are already there
    because we made them locally", with the laptop's file uploaded.
  - built by code: demo rows inserted by a seed script kept in the repository, or the laptop's
    database copied up "so production has data".
  - its own: the laptop's development server using its own local database, or pointed at the
    production one "to test against real data".
  - decoy, both sound, differing in a detail that doesn't bear: the database at the same vendor as
    the backend or a different one; a seed script or none.
  Serve three pairs a sitting: at least one survival pair and at least one built-by-code or its-own
  pair, the third any kind, and at most one decoy. Easy: the faulty excerpt says outright what it
  does. Medium: the deciding detail is a path or a single word; serve Easy first, Medium after.
  **How the key treats a one-time script:** a seed or setup script kept in the code and run once
  against production builds production from the code wherever it runs, on the host or from the
  laptop as in Odin's lesson; it is never the its-own fault. That fault is only the laptop's
  development server working against the production database. No connection strings, passwords,
  backups, migrations or prices appear.
- **offer as:** the quickest practice, on made-up plans: 10 minutes, nothing to run, with each pair
  pointing at the detail that matters. Pick `a-trace-own-database-setup` to work on your own app
  instead.
- **check note:** Three pairs a sitting can't satisfy "last two pairs right without a near-miss
  question" if pair 2 is missed. Serve further pairs until two in a row are right, and stop after
  about six so the sitting stays near 10 minutes. The decoy kind has no stated difficulty; treat
  it as Medium.

### `a-judge-described-plan`

- **serves:** `c-plan-first-deploy`
- **supports:** attempt
- **checks:** `c-plan-first-deploy`
- **artifact:** no external source. One made-up app and host, and two short deploy plans for its
  database from two different agents, one faulted and one sound, judged together as one question.
  Written per the generator below. About 10 to 12 minutes, plus 3 for the worked example before a
  learner's first attempt.
- **learner does:** reads the app's description, the host's storage line and both plans, then
  writes alone, for each plan, two answers, each a yes or no with the plan step that decides it:
  will the data survive a redeploy? Does production get a database of its own, built by the code
  rather than copied from the laptop? Hands it to the tutor.
- **tutor role:** none
- **tutor does:** before the learner's first attempt at this activity, works the worked example
  below aloud, on an Easy pair that is not from the bank. Then serves one question as written, with
  its scenario's setup. Waits, writing down any help word for word. Sends the adjudicator the
  setup, the two plans, the rubric, the learner's answer verbatim and every piece of help. A remark
  about connection strings or passwords (deploy-config), backups or migrating data (a later
  topic), or cost and free tiers (cloud-hosting) is neither credited nor counted as a false fault:
  the tutor tells the adjudicator to disregard it, and the learner where it belongs.
- **done when:** criterion met with no help on one question, which is one faulted plan and one sound
  plan: the fault caught on the faulted plan and nothing faulted on the sound one.
- **generator:** each question is a pair of plans for one scenario's app and host. Everything below
  is fixed unless listed under what varies.
  - **Scenario setup (shared by its questions).** A made-up app in three lines, shaped like Problem
    Set 2: what it does; a React frontend and an Express backend; a SQLite file at a named path
    inside the app's folder, such as `server/data/app.sqlite`, holding one or two named tables. Then
    a made-up host (never a real vendor's name) described in exactly these three facts, in one or
    two lines: its servers' disks are ephemeral, so anything written to them is gone after every
    redeploy or restart; a volume can be attached to a service, mounted at `/data`, and only files
    under `/data` are kept; it also offers managed Postgres as a separate service.
  - **Each plan.** Three to five numbered steps written as a coding agent writes, ending with an
    assurance such as "Your data will be safe." It says where the database lives and how
    production's tables, and any rows, come to exist. It never contains connection strings,
    passwords, backups, migrations of existing data, prices or free tiers. Label the two plans A
    and B; which one is faulted varies.
  - **What varies:** the app, the host's name, the wording, which plan is A, and the shapes. One
    plan is a faulted shape and the other a sound shape:
    - `outside-mount` (faulted, Hard): a volume is attached at `/data`, but the database path, in a
      step or an environment setting, is still inside the app's folder (`server/data/app.sqlite`,
      or `/app/server/data/app.sqlite`). The backend creates the tables at startup. Survives: no.
      Its own, built by code: yes.
    - `laptop-copy` (faulted, Medium): volume at `/data`, path `/data/app.sqlite`, but a step
      uploads the laptop's `app.sqlite` to `/data` "so production starts with the entries you
      already have". Survives: yes. Its own, built by code: no.
    - `shared-dev` (faulted, Medium): managed Postgres; the backend creates the tables at startup;
      a step also points the laptop's development server at that same production database "so you
      can test against real data". Survives: yes. Its own: no.
    - `committed-file` (faulted, Hard): no volume; the database file stays at its path in the app's
      folder, and a step takes it out of `.gitignore` and commits it "so the database ships with
      the app". Survives: no, since the disk is ephemeral and each redeploy starts again from the
      committed copy, losing what users added. Its own, built by code: no, since production starts
      as the laptop's copy.
    - `sound-volume` (sound, Medium): volume at `/data`, path `/data/app.sqlite`, the backend
      creates the tables at startup if they are missing; either no rows, or a seed script kept in
      the repository inserts two or three demo rows once. Survives: yes. Its own, built by code:
      yes.
    - `sound-postgres` (sound, Medium): managed Postgres; the backend creates the tables at
      startup; either no rows, or a seed script kept in the repository is run once against
      production. The laptop keeps using its own SQLite file. Survives: yes. Its own, built by
      code: yes.
    - `decoy` (sound, Hard): `sound-volume` or `sound-postgres` plus one detail that sounds
      alarming and doesn't bear: a few seconds of downtime on each redeploy because a volume is
      attached; the database at a different vendor from the backend; a note that the server
      restarts after each deploy. Survives: yes. Its own, built by code: yes.
    The `ephemeral` shape (no volume, file in the app's folder; survives: no) is for the worked
    example only and is never banked.
  - **How the key treats a one-time script:** a seed or setup script kept in the code and run once
    against production builds production from the code, wherever it runs, on the host or from the
    laptop as in Odin's lesson; it is never the its-own fault. That fault is only the laptop's
    development server working against the production database.
  - **Difficulty:** a question is as hard as its faulted plan, and Hard if the sound plan is a
    `decoy`. Serve Medium for a learner's first counting question; Hard on review visits.
  - **Coverage of a bank:** each faulted shape appears in at least one question and each sound shape
    in at least one, with at least two Medium questions with no decoy, for first attempts. On review
    visits serve a question whose faulted shape the learner hasn't had, reading the labels
    `served.mjs` returns.
  - **Which goal:** every question bears on `c-plan-first-deploy` alone. Rubric: `answer` gives, for
    each plan, yes or no on each question and the deciding step for every no; full credit is all
    four yes-or-no answers right, each no tied to the step that decides it, and no fault named that
    the key doesn't have; half credit is one plan judged fully right and the other not.
- **worked example:** before a learner's first attempt, take an `ephemeral` plan and a `sound-volume`
  plan for a made-up app, and work them aloud: in each, find the step that says where the file goes
  and read it against the host's storage line, then find the step that says where production's
  tables and rows come from. About 3 minutes. At the first level of help on a real attempt, ask only
  "where does the file live, and what does this host do to that place on a redeploy?"
- **doesn't show:** one question shows the learner catching one kind of fault (survival, or own
  database built by code), not both kinds; review visits serve the other. The host's storage is
  given in a line, while in Problem Set 3 the learner has only the agent's plan, which may assert
  how the host stores files, rightly or wrongly; so a pass doesn't show they would doubt the plan's
  own claim or find the rule on a real host's pages. The host is made up, so nothing about which
  real hosts offer volumes. The learner knows a check is on.
- **offer as:** the check that's available now, before Problem Set 3: two short made-up plans side by
  side, 10 to 12 minutes, nothing to run, with a 3-minute worked example the first time. Minimum
  route for this topic before session 11: `a-read-database-survives` and `a-dry-run-database-plan`
  (20 minutes), then this (15 with the worked example), about 35 minutes, and the seven words in
  `a-words` (about 20), about 55 in all. `a-judge-own-deploy-plan` is the same capability on your
  own agent's plan.
- **check note:** Every Medium faulted shape (`laptop-copy`, `shared-dev`) is an own-database
  fault, so a first counting question never tests a survival fault, and a pass there meets the
  goal. On review, choose a faulted shape of the other kind from the one already passed (survival
  is `outside-mount` or `committed-file`), not merely an unseen shape. Bank labels don't name the
  shape, so read it from the served question's rubric key.

### `a-judge-own-deploy-plan`

- **serves:** `c-plan-first-deploy`
- **supports:** attempt
- **checks:** `c-plan-first-deploy`
- **artifact:** no external source. The plan the learner's own agent writes in Problem Set 3 for
  deploying their Problem Set 2 app's database, taken before it is carried out; on a review visit, a
  tablemate's plan or a fresh run of the same request. Beside it, one made-up plan of the opposite
  case, so the sitting has one faulted plan and one sound one. About 15 minutes, plus the tutor's
  preparation, done before the sitting.
- **learner does:** before telling the agent to go ahead, writes alone, for the real plan and the
  made-up one, the same two answers as in `a-judge-described-plan`, each a yes or no with the plan
  step that decides it, and for any no on the real plan, what it would have to say instead. Hands
  it to the tutor.
- **tutor role:** none
- **tutor does:** before the sitting, reads the app the plan is for (the learner's own, or the
  tablemate's when it is a tablemate's plan): where the SQLite file's path is set, whether the code
  creates tables and inserts rows, whether the file is tracked by git. Reads the chosen host's own
  current pages on its storage and writes the host's storage rule in one line, as
  `a-judge-described-plan` gives it, with the page address and date, never from the agent's
  description. Writes the key from the plan, the code and that rule. A plan that never says where
  the database will live is keyed no on survival: an answer of no, or "can't tell, the plan doesn't
  say", counts as catching it, and yes does not. Then writes one made-up plan of the opposite case,
  for the same app and host, from `a-judge-described-plan`'s shapes: a sound shape if the real plan
  is faulted, a Medium faulted shape if it is sound. In the sitting, shows both plans and the
  storage line. Waits, writing down any help word for word. Sends the adjudicator both plans, the
  storage line with its source, the key, the learner's answer and every piece of help. Labels the
  attempt `a-judge-own-deploy-plan/<host>`. Disregards remarks on connection strings, passwords,
  backups, migrations and cost, as `a-judge-described-plan` does. Afterwards, if the real plan
  failed either question, the learner takes their corrected line back to their agent.
- **done when:** criterion met with no help, on the real plan and the made-up one together. If the
  tutor can't settle the key for the real plan (the host's pages don't say how it stores files),
  the sitting is practice, and the tutor says so and offers `a-judge-described-plan`.
- **generator:** the real plan is whatever the agent proposed, so nobody sets its shape or
  difficulty. Fixed: the storage line comes from the host's own pages on the day; the key comes from
  that line, the plan and the app's code; the made-up plan is always the opposite case. Across
  visits use a different real plan each time, a tablemate's or a fresh run, preferring one whose
  verdict differs from the last one the learner judged.
- **worked example:** none during the attempt. If the learner stalls, the first level of help is
  "where does the file live, and what does this host do to that place on a redeploy?", and the
  attempt is recorded `unaided: no`.
- **doesn't show:** whichever case the real plan is, the other comes from a made-up plan, so a pass
  shows the learner judging their own agent's plan on one side of the criterion only. The tutor
  writes the storage line, while in Problem Set 3 itself the learner has only the agent's plan,
  which may assert how the host stores files; so a pass doesn't show they would doubt that claim or
  read the rule off the host's pages. The key rests on the tutor's reading of the app and of the
  host's pages.
- **offer as:** the real thing: your own agent's plan for your own Problem Set 3 deploy, judged
  before you let it run. About 15 minutes, any time Oct 8 to 14. `a-judge-described-plan` is the one
  to take before session 11.
- **check note:** When the real plan is sound, the made-up opposite plan is an own-database fault,
  so prefer `outside-mount` or `committed-file` there if the learner has not yet caught a survival
  fault unaided. If you can't read the code the plan is for (a tablemate's repository you don't
  have), treat the sitting as practice, as when the host's pages are silent.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
