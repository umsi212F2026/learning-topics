# Activities: database hosting

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

2026-10-04. The minimum route (orientation reading and dry run, then a-judge-described-plan with its worked example, then the seven words) comes to about 55 minutes. It fits the topic's 60-minute budget only if the first counting attempt passes; a retry, or a helped practice attempt after a hedged readiness answer, takes it past 60. a-judge-own-deploy-plan belongs with Problem Set 3 (Oct 8 to 14), not before session 11.

2026-10-04, from the curator, not the checker. The `study` cell for `c-plan-first-deploy` is empty
on purpose, against the generate skill's rule that every goal has an activity that isn't a check.
The course's rule is that outside orientation every activity is a question activity with a rubric:
practice is attempting a check's questions with help, which doesn't count, and checking is
attempting them unaided. The two study activities were dropped for that reason.

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
| `c-plan-first-deploy` | | `a-judge-described-plan`, `a-judge-own-deploy-plan` | Both checks give the learner the host's storage rule as true, and every banked plan says where the database lives. A plan that never says where the data goes is tested only in `a-judge-own-deploy-plan`, and only if the agent's real plan happens to leave it out. Doubting a plan's own claim about how the host stores files is tested by neither, though that is the Problem Set 3 situation. One unaided pass also catches one kind of fault, survival or own database; the other kind comes on review. When the learner reaches Problem Set 3, ask where their plan says the database lives and how they know the host keeps that place. |

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
  stop needs their code open; their own app's plan is judged in `a-judge-own-deploy-plan`, during
  Problem Set 3. "I don't know yet" is an honest answer:
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
  `unclear`, and the tutor offers a helped attempt at `a-judge-described-plan` as practice. A plain no is `criterion: not met`:
  record it, ask what is missing, and offer to go back over the stop that bears on it; don't ask
  again in the same sitting. This goal isn't required, so a no blocks nothing.
- **generator:** vary the made-up app (small, React frontend, Express backend, SQLite: a club
  sign-up sheet, a recipe box, a study-group finder) and the host's one-line storage rule. Neither rehearsal uses a fault that `a-judge-described-plan`
  serves, so the learner doesn't meet a counting plan's deciding detail minutes before it.
  Rehearsal one is a host whose disk is kept across a restart but starts empty on every redeploy,
  and one plan line that is either "we restarted the server and the entries were still there, so
  the data is safe" (a fault `a-judge-described-plan` never serves: a restart is not a redeploy)
  or the SQLite file placed on a volume that is kept across redeploys (sound). Rehearsal two is one
  plan line on how production gets its rows, either the backend creating empty tables at startup
  (sound) or the agent exporting the rows from the laptop's database and importing them into
  production (a fault `a-judge-described-plan` never serves). Never use the wording of a
  `no-volume`, `silent-location`, `laptop-copy`, `shared-dev`, `outside-mount` or
  `committed-file` step, and never give a line that leaves out where the database lives. Fixed: two rehearsals in that order, neither graded, then the readiness
  question word for word. Difficulty doesn't vary: this settles an indication, not a capability.
- **worked example:** if the learner freezes, the tutor answers a different made-up line aloud in two
  sentences, then hands the original back.
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. Each
  rehearsal is one line, helped and ungraded, so it shows nothing about finding the deciding detail
  in a whole plan, and nothing about the seven words, which `a-words` serves.
- **offer as:** the short step that closes orientation, after `a-read-database-survives`, not an
  alternative to it. About 5 minutes; about 20 with the reading.

### `a-trace-own-database-setup`

- **was:** a study activity: the learner found in their own Problem Set 2 repository where the
  SQLite file lives, whether the code makes the tables and seed rows, and whether the file is
  tracked by git.
- **status:** dropped (curator, 2026-10-04): outside orientation, every activity in a course topic
  is a question activity with a rubric, and this one had no checks. What it found is read by the
  tutor in `a-judge-own-deploy-plan`.

### `a-contrast-plan-pairs`

- **was:** a study activity: pairs of made-up plan excerpts differing in one detail, the learner
  saying which is sound and why.
- **status:** dropped (curator, 2026-10-04): outside orientation, every activity in a course topic
  is a question activity with a rubric, and this one had no checks. Practice on paired plans is
  `a-judge-described-plan` attempted with help, which its bank serves.

### `a-judge-described-plan`

- **serves:** `c-plan-first-deploy`
- **supports:** attempt
- **checks:** `c-plan-first-deploy`
- **artifact:** no external source. One made-up app and host, and two short deploy plans for its
  database from two different agents, one faulted and one sound, judged together as one question.
  Written per the generator below. About 10 to 12 minutes, plus 3 for the worked example before a
  learner's first attempt.
- **learner does:** reads the app's description, the host's storage line and both plans, then
  writes alone, for each plan, a yes or no to each of two questions, and for every no the plan
  step that decides it: will the data survive a redeploy? Does production get a database of its
  own, built by the code rather than copied from the laptop? Hands it to the tutor.
- **tutor role:** examiner
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
    assurance such as "Your data will be safe." The steps are in the order they run. It says where
    the database lives (except in `silent-location`) and how production's tables, and any rows,
    come to exist. Any seed step comes after the first deploy, once the backend has started and
    made its tables ("once after deployment", as in Odin's lesson), never before it. It never
    contains connection strings,
    passwords, backups, migrations of existing data, prices or free tiers. Label the two plans A
    and B; which one is faulted varies.
  - **What varies:** the app, the host's name, the wording, which plan is A, and the shapes. One
    plan is a faulted shape and the other a sound shape. Each faulted shape is a survival fault, an
    own-database fault, or both, as marked:
    - `no-volume` (faulted, survival, Medium): no volume is attached, and a step says plainly that
      the backend keeps its SQLite file at its default path in the app's folder
      (`server/data/app.sqlite`) on the server. The backend creates the tables at startup.
      Survives: no. Its own, built by code: yes.
    - `silent-location` (faulted, survival, Medium): no step says where the database file or the
      database goes: no volume, no path, no managed Postgres, only steps such as "deploy the
      backend" and "the backend creates its tables on startup". The backend creates the tables at
      startup and nothing comes from the laptop. Survives: no, keyed as not shown to survive; an
      answer of no, or "can't tell, the plan doesn't say", passes, and yes fails. A no may rest on
      either reason, and both earn full credit: the plan never says where the database lives; or,
      with no volume and no managed Postgres in the plan, the file stays at the setup's default
      path on the ephemeral disk. Its own, built by code: yes.
    - `outside-mount` (faulted, survival, Hard): a volume is attached at `/data`, but the database path, in a
      step or an environment setting, is still inside the app's folder (`server/data/app.sqlite`,
      or `/app/server/data/app.sqlite`). The backend creates the tables at startup. Survives: no.
      Its own, built by code: yes.
    - `laptop-copy` (faulted, own-database, Medium): volume at `/data`, path `/data/app.sqlite`,
      but a step uploads the laptop's `app.sqlite` to `/data` "so production starts with the
      entries you already have". No step creates tables: the uploaded laptop file is the only
      source of production's tables and rows. Survives: yes. Its own, built by code: no.
    - `shared-dev` (faulted, own-database, Medium): managed Postgres; the backend creates the tables at startup;
      a step also points the laptop's development server at that same production database "so you
      can test against real data". Survives: yes. Its own: no.
    - `committed-file` (faulted, both, Hard): no volume; the database file stays at its path in the app's
      folder, and a step takes it out of `.gitignore` and commits it "so the database ships with
      the app". Survives: no, since the disk is ephemeral and each redeploy starts again from the
      committed copy, losing what users added. Its own, built by code: no, since production starts
      as the laptop's copy.
    - `sound-volume` (sound, Medium): volume at `/data`, path `/data/app.sqlite`, the backend
      creates the tables at startup if they are missing; either no rows, or a seed script kept in
      the repository inserts two or three demo rows once, in a step after the first deploy.
      Survives: yes. Its own, built by code:
      yes.
    - `sound-postgres` (sound, Medium): managed Postgres; the backend creates the tables at
      startup; either no rows, or a seed script kept in the repository is run once against
      production, in a step after the first deploy. The laptop keeps using its own SQLite file. Survives: yes. Its own, built by
      code: yes.
    - `decoy` (sound, Hard): `sound-volume` or `sound-postgres` plus one detail that sounds
      alarming and doesn't bear: a few seconds of downtime on each redeploy because a volume is
      attached; the database at a different vendor from the backend; a note that the server
      restarts after each deploy. Survives: yes. Its own, built by code: yes.
    The `laptop-export` shape (the agent exports the rows from the laptop's database and imports
    them into production; its own, built by code: no) is for the worked example and the dry run
    only and is never banked.
  - **How the key treats a one-time script:** a seed or setup script kept in the code and run once
    against production builds production from the code, wherever it runs, on the host or from the
    laptop as in Odin's lesson; it is never the its-own fault. That fault is only the laptop's
    development server working against the production database.
  - **Difficulty:** a question is as hard as its faulted plan, and Hard if the sound plan is a
    `decoy`. A learner's first counting question is Medium with no decoy, and its fault may be of
    either kind. On review visits, prefer a question whose faulted plan is of the other kind from
    the one the learner has already passed (survival: `no-volume`, `silent-location`,
    `outside-mount`; own-database:
    `laptop-copy`, `shared-dev`; `committed-file` is both), then one whose faulted shape they
    haven't had, Hard once Medium is passed.
  - **Coverage of a bank:** each faulted shape appears in at least one question and each sound shape
    in at least one, with at least two Medium questions with no decoy for first attempts, at least
    one of them a survival fault and one an own-database fault. `silent-location` is required like
    every other faulted shape.
  - **The rubric key names the shapes.** Each scenario's rubric file says in its top part, for every
    question, which shape the faulted plan is and which the sound plan is, so the tutor reads the
    shape of a served question from its key (bank labels don't carry it).
  - **Which goal:** every question bears on `c-plan-first-deploy` alone. Rubric: `answer` gives, for
    each plan, yes or no on each question and the deciding step for every no (a yes may cite its
    step too, but the learner need not); full credit is all four yes-or-no answers right, each no
    tied to the step that decides it (for `silent-location`, to either the plan's never saying where the
    database lives or the file staying at its default path on the ephemeral disk because the plan
    names no volume and no managed Postgres; "can't tell" counts as no), and no fault named that the key doesn't have; a yes given
    without a step loses nothing; half credit is one plan judged fully right and the other not.
- **worked example:** before a learner's first attempt, take a `laptop-export` plan and a
  `sound-volume` plan for a made-up app (its fault is one the bank never serves), and work them
  aloud: in each, find the step that says where the file goes and read it against the host's
  storage line, then find the step that says where production's tables and rows come from. About
  3 minutes. At the first level of help on a real attempt, ask only
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
  made-up one, the same two answers as in `a-judge-described-plan`, a yes or no to each with the
  plan step that decides every no, and for any no on the real plan, what it would have to say
  instead. Hands
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
  is faulted; if it is sound, a Medium faulted shape (`no-volume` for survival, `laptop-copy` or
  `shared-dev` for own-database), of the kind the learner has not yet caught unaided, if there is
  one. In the sitting, shows both plans and the
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
- **check note:** If you can't read the code the plan is for (a tablemate's repository you don't
  have), you can't settle the key: treat the sitting as practice, as when the host's pages are
  silent, and offer `a-judge-described-plan`.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
