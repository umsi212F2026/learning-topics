# Activities: database hosting

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

2026-10-04. The minimum route (orientation reading and dry run, then a-judge-described-plan with its worked example, then the seven words) comes to about 55 minutes. It fits the topic's 60-minute budget only if the first counting attempt passes; a retry, or a helped practice attempt after a hedged readiness answer, takes it past 60. a-judge-own-deploy-plan belongs with Problem Set 3 (Oct 8 to 14), not before session 11.

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |
| `c-plan-first-deploy` | say whether a first-deploy plan keeps the data and gives production a database of its own | Given an agent's plan for deploying an app's database for the first time, the host's rule for what it keeps, and one of two questions (will the data survive a redeploy, or does production get a database of its own, built by the code rather than copied from the laptop or shared with development), answers yes or no and names the step that decides it, whichever way the answer goes. It passes when the verdict is right and the step named is the one that decides it. For a plan that never says where the database lives, "no" or "can't tell" on survival, with that omission named, passes. A seed script kept in the code and run once against production counts as built by the code. Cases: `catch-data-loss`, `clear-survives`, `catch-copied`, `clear-own-database`. |

## Coverage

| goal | checks | notes |
| ---- | ------ | ----- |
| `o-orientation` | `a-read-database-survives`, `a-dry-run-database-plan` | |
| `c-plan-first-deploy` | `a-judge-described-plan`, `a-judge-own-deploy-plan` | |

---

## Activities

### `a-read-database-survives`

- **serves:** `all`
- **supports:** orient
- **checks:** o-orientation
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
  in that file now (their Problem Set 2 test data): copying the file up brings that test data along,
  and copying is what this topic watches for. Production starting with rows is not the concern: a
  few rows put in by a seed script kept in the code are seed data, the app's real starting content,
  and count as built by the code.
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
- **verified:** 2026-10-04
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
  `committed-file` step, and never give a line that leaves out where the database lives. The one
  exception is the restart line ("we restarted the server and the entries were still there, so
  the data is safe"): its point is that a restart is not a redeploy, not a plan that hides where
  the data lives. Don't add a location to it, since any location would preview a banked shape. Fixed: two rehearsals in that order, neither graded, then the readiness
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
- **artifact:** no external source. One made-up app and host, one short deploy plan for its
  database, and one of two questions about that plan. Written per the generator below. About 5
  minutes a question, plus about 4 for the worked example before a learner's first attempt at this
  activity.
- **verified:** 2026-10-04
- **learner does:** reads the app's description, the host's storage line and the plan, then
  answers alone the one question asked, which is either "Will this plan's data survive a
  redeploy?" or "Does production get a database of its own, built by the code rather than copied
  from the laptop or shared with development?" Writes yes or no and names the plan step that
  decides it, whichever way the answer goes. Hands it to the tutor.
- **tutor role:** examiner
- **tutor does:** before the learner's first attempt at this activity, whichever case it carries,
  works the worked example below aloud. Then serves one question as written, with its scenario's
  setup. Waits, writing down any help word for word. Sends the adjudicator the setup, the plan, the
  question, the rubric, the learner's answer verbatim and every piece of help. A remark off the
  asked question is neither credited nor counted as a false fault: the other of the two questions
  (on the survival question, a remark that the plan copies the laptop's file; on the own-database
  question, a remark about volumes), connection strings or passwords (deploy-config), backups or
  migrating data (a later topic), or cost and free tiers (cloud-hosting). The tutor tells the
  adjudicator to disregard it, and the learner where it belongs. A remark that gives a different
  verdict on the asked question is not off it.
- **done when:** `c-plan-first-deploy` is met when every one of its four cases has an unaided pass.
  A single question passes only the one case its rubric `cases:` line names, with the right yes or
  no on the asked question tied to the step that decides it; the tutor records that case
  (record-attempt `--cases <case>`).
- **generator:** each question is one plan for one scenario's app and host, and one of the two
  questions about it. Everything below is fixed unless listed under what varies.
  - **Scenario setup (shared by its questions).** A made-up app in three lines, shaped like Problem
    Set 2: what it does; a React frontend and an Express backend; a SQLite file at a named path
    inside the app's folder, such as `server/data/app.sqlite`, holding one or two named tables. Then
    a made-up host (never a real vendor's name) described in exactly these three facts, in one or
    two lines: its servers' disks are ephemeral, so anything written to them is gone after every
    redeploy or restart; a volume can be attached to a service, mounted at `/data`, and only files
    under `/data` are kept; it also offers managed Postgres as a separate service. A scenario may
    hold several questions on the same app and host, each in its own `###` section with its own
    plan and its one question. Scenarios are written in study order, and no question may give
    away the answer to a later one in its scenario: no plan is written as a correction or variant
    of an earlier one ("this time the file goes on the volume"), and nothing in one question's
    text says or hints how a later question's plan fares.
  - **Each question.** The plan, then exactly one of the two questions, word for word: "Will this
    plan's data survive a redeploy?" (the survival question) or "Does production get a database of
    its own, built by the code rather than copied from the laptop or shared with development?"
    (the own-database question). Then "Say yes or no, and name the step in the plan that decides
    it." Never both questions, and never two plans.
  - **Each plan.** Three to five numbered steps written as a coding agent writes, ending with an
    assurance such as "Your data will be safe." The steps are in the order they run. It says where
    the database lives (except in `silent-location`) and how production's tables, and any rows,
    come to exist. Any seed step comes after the first deploy, once the backend has started and
    made its tables ("once after deployment", as in Odin's lesson), never before it. It never
    contains connection strings,
    passwords, backups, migrations of existing data, prices or free tiers.
  - **What varies:** the app, the host's name, the wording, the plan's shape, and which question is
    asked. Every question is on `c-plan-first-deploy` and carries exactly one of its cases, and
    each shape below has a truth on each question that decides the case: on the survival
    question, a plan whose data won't survive carries `catch-data-loss` and one whose data will
    carries `clear-survives`; on the own-database question, a plan copied or shared carries
    `catch-copied` and one built by the code carries `clear-own-database`. A shape faulted on one
    question is sound on the other: `laptop-copy` and `shared-dev` survive, and `no-volume`,
    `silent-location` and `outside-mount` are built by the code. That is what makes the clear
    cases more than a yes to a tidy plan: the learner must
    say yes to a plan with a real fault elsewhere. `committed-file` fails both. For each shape,
    the deciding step on each question is given; it is the step the key names.
    - `no-volume`: no volume is attached, and a step says plainly that the backend keeps its
      SQLite file at its default path in the app's folder (`server/data/app.sqlite`) on the
      server. The backend creates the tables at startup. Survival: no, decided by the step keeping
      the file in the app's folder on the server (case `catch-data-loss`, Medium). Own database: yes,
      decided by the step where the backend creates its tables (case `clear-own-database`, Medium).
    - `silent-location`: no step says where the database file or the database goes: no volume, no
      path, no managed Postgres, only steps such as "deploy the backend" and "the backend creates
      its tables on startup". The backend creates the tables at startup and nothing comes from the
      laptop. Survival: no, keyed as not shown to survive; decided by the omission, which is named
      as the plan's never saying where the database lives (case `catch-data-loss`, Medium). Own
      database: yes, decided by the step where the backend creates its tables
      (case `clear-own-database`, Medium).
    - `outside-mount`: a volume is attached at `/data`, but the database path, in a step or an
      environment setting, is still inside the app's folder (`server/data/app.sqlite`, or
      `/app/server/data/app.sqlite`). The backend creates the tables at startup. Survival: no,
      decided by the step or setting that puts the path outside `/data` (case `catch-data-loss`,
      Hard). Own database: yes, decided by the step where the backend creates its tables
      (case `clear-own-database`, Medium).
    - `laptop-copy`: volume at `/data`, path `/data/app.sqlite`, but a step uploads the laptop's
      `app.sqlite` to `/data` "so production starts with the entries you already have". No step
      creates tables: the uploaded laptop file is the only source of production's tables and
      rows. Survival: yes, decided by the step putting the file at `/data/app.sqlite` on the
      volume (case `clear-survives`, Medium). Own database: no, decided by the upload step
      (case `catch-copied`, Medium).
    - `shared-dev`: managed Postgres; the backend creates the tables at startup; a step also points
      the laptop's development server at that same production database "so you can test against
      real data". Survival: yes, decided by the step putting the database in managed Postgres
      (case `clear-survives`, Medium). Own database: no, decided by the step pointing the
      development server at production's database (case `catch-copied`, Medium).
    - `committed-file`: no volume; the database file stays at its path in the app's folder, and a
      step takes it out of `.gitignore` and commits it "so the database ships with the app".
      Survival: no, since the disk is ephemeral and each redeploy starts again from the committed
      copy, losing what users added; decided by the step that keeps the file in the app's folder
      and ships it in the commit (case `catch-data-loss`, Hard). Own database: no, since production
      starts as the laptop's copy; decided by the commit step (case `catch-copied`, Hard).
    - `sound-volume`: volume at `/data`, path `/data/app.sqlite`, the backend creates the tables at
      startup if they are missing; either no rows, or a seed script kept in the repository inserts,
      once, in a step after the first deploy, two or three rows of real starting content the app is
      meant to open with (a pantry's staple items, the listings a front desk is already giving
      away), never described as "sample", "demo" or "so it doesn't look empty". Survival: yes, decided by the
      step putting the file at `/data/app.sqlite` (case `clear-survives`, Medium). Own database:
      yes, decided by the step where the backend creates its tables; when the plan has a seed step,
      naming only that step earns full credit too, and either step or both is fine
      (case `clear-own-database`, Medium).
    - `sound-postgres`: managed Postgres; the backend creates the tables at startup; either no
      rows, or a seed script kept in the repository is run once against production, in a step after
      the first deploy, inserting real starting content as in `sound-volume`, never "sample",
      "demo" or "so it doesn't look empty". The laptop keeps using its own SQLite file. Survival: yes, decided by the
      managed Postgres step (case `clear-survives`, Medium). Own database: yes, decided by the
      step where the backend creates its tables; when the plan has a seed step, naming only that
      step earns full credit too, and either step or both is fine (case `clear-own-database`,
      Medium).
    - `decoy`: `sound-volume` or `sound-postgres` plus one detail that sounds alarming and doesn't
      bear on the asked question. For the survival question: a few seconds of downtime on each
      redeploy because a volume is attached; the database at a different vendor from the backend;
      a note that the server restarts after each deploy. For the own-database question: the seed
      script kept in the repository is run once from the laptop against production, as in Odin's
      lesson, inserting real starting content as in `sound-volume`; the laptop keeps its own SQLite file with the same tables, made by the same code.
      Survival: yes (case `clear-survives`, Hard). Own database: yes (case `clear-own-database`,
      Hard). The deciding step is the sound shape's, so on the own-database question a seed step,
      including one run from the laptop, earns full credit on its own, as the table-creating step
      does.
    The `laptop-export` shape (a managed Postgres database, and a step where the agent exports the
    rows from the laptop's database and imports them into production; survival yes, own database
    no) is for the worked example and the dry run only and is never banked.
  - **How the key treats a one-time script:** a seed or setup script kept in the code and run once
    against production builds production from the code, wherever it runs, on the host or from the
    laptop as in Odin's lesson; it is never the copied-or-shared fault, and on the own-database
    question faulting it fails. The shared fault is only the laptop's development server working
    against the production database.
  - **Difficulty:** each shape's difficulty on each question is given above with its case. In
    short: Hard is `outside-mount` or `committed-file` on a question they fault, or a `decoy` on a
    clear case; everything else is Medium. A learner's first counting question on a case is
    Medium, and on a clear case is not a decoy. On later visits for a case, prefer a shape the
    learner hasn't had for that case, Hard once Medium is passed; for a clear case, prefer a plan
    faulted on the other question once a tidy sound plan is passed.
  - **Coverage of a bank:** about three questions per case, about twelve in all, with at least one
    Medium question per case for first attempts. `catch-data-loss` across more than one faulted
    shape, `silent-location` among them; `catch-copied` across more than one faulted shape. Each
    faulted shape appears in at least one question across the two catch cases.
    `clear-survives` includes at least one plan faulted on the own-database question
    (`laptop-copy` or `shared-dev`) and at least one `decoy`; `clear-own-database` includes at
    least one plan faulted on the survival question (`no-volume`, `silent-location` or
    `outside-mount`) and at least one `decoy`. The same shape may be used under both questions,
    in different questions.
  - **The rubric key names the shape.** Each scenario's rubric file says in its top part, for every
    question, which shape its plan is and which question it asks, so the tutor reads the shape of
    a served question from its key (bank labels don't carry it).
  - **Which goal and case:** every question bears on `c-plan-first-deploy` and carries exactly one
    case, the one its plan's truth on the asked question gives, as above; no question carries two.
    Rubric: `goal: c-plan-first-deploy` and `cases:` that one case. `answer` is the
    verdict, yes or no, and the step that decides it. `credit`: full credit is the right verdict
    tied to that step. On the own-database question, for a plan built by the code that has a seed
    step (a seed script kept in the repository and run once against production), the seed step
    and the step where the backend creates its tables each decide it: naming either one, or both,
    earns full credit on case `clear-own-database`, and `answer` lists both. For
    `silent-location` on the survival question (case `catch-data-loss`), as the criterion says,
    no or "can't tell", with the omission named (the plan never says
    where the database lives; an answer that the plan names no volume and no managed Postgres, so
    the file stays on the ephemeral disk, names it too), and yes fails. No half credit: a right
    verdict with no step, or tied to a step that doesn't decide it, is not met, since the
    criterion asks for both. Naming a fault the key doesn't have on the asked question fails,
    whether as the reason for a wrong verdict or alongside a right one; on a clear case this
    includes faulting a one-time seed script or a decoy detail. Remarks off the asked question
    (the other question, connection strings, passwords, backups, cost) are neither credited nor
    counted.
- **worked example:** before a learner's first attempt, take one `laptop-export` plan for a made-up
  app (a shape the bank never serves) and ask it both questions aloud, in turn. Survival: find the
  step that says where the database lives (managed Postgres), read it against the host's storage
  line, and say yes, naming that step. Own database: find the step that says where production's
  tables and rows come from (the export from the laptop and import into production), and say no,
  naming that step. Point out that one plan got a yes on one question and a no on the other, and
  that each answer named its step. About 4 minutes. At the first level of help on a real attempt,
  ask only, on the survival question, "where does the data live, and what does this host do to
  that place on a redeploy?", or, on the own-database question, "which step makes production's
  tables and rows, and where do they come from?"
- **doesn't show:** a pass passes one case: one side of one question. The goal needs all four
  cases, so a learner who answers no to every plan passes both catch cases and is held back by
  the clear cases. Each question names the question to ask, while in
  Problem Set 3 the learner must think to ask both of their own agent's plan unprompted. The
  host's storage is given in a line, while in Problem Set 3 the learner has only the agent's
  plan, which may assert how the host stores files, rightly or wrongly; so a pass doesn't show
  they would doubt the plan's own claim or find the rule on a real host's pages. The host is made
  up, so nothing about which real hosts offer volumes. The learner knows a check is on.
- **offer as:** `c-plan-first-deploy` is also taught at the session 11 table activity, so on first
  reaching it the tutor offers: do it here, with this; already done elsewhere (recorded as
  `elsewhere`, which counts as met, all cases included, and comes back for review); learn it
  there later (deferred, then recorded as done elsewhere after the table activity); or remove it.
  This is the one to take in the learn tool before session 11: one short made-up plan and one
  question at a time, about 5 minutes each, nothing to run, with a 4-minute worked example the
  first time, about 25 minutes for one passing question per case. With `a-read-database-survives` and `a-dry-run-database-plan` (20 minutes) and
  the seven words in `a-words` (about 20), the route is about 65 minutes for a student who takes
  all four plan questions here, a little past the topic's 60-minute budget, and well under an
  hour for one who defers them to the table activity. Questions from it also serve review.
  `a-judge-own-deploy-plan` is the same goal on your own agent's plan, for Problem Set 3.

### `a-judge-own-deploy-plan`

- **serves:** `c-plan-first-deploy`
- **supports:** attempt
- **checks:** `c-plan-first-deploy`
- **artifact:** no external source. The plan the learner's own agent writes in Problem Set 3 for
  deploying their Problem Set 2 app's database, taken before it is carried out; on a review visit, a
  tablemate's plan or a fresh run of the same request. It is asked the two questions of
  `a-judge-described-plan` as two separate questions. About 10 minutes for the two, plus the
  tutor's preparation, done before the sitting.
- **verified:** 2026-10-04
- **learner does:** before telling the agent to go ahead, answers alone the first question the
  tutor puts on the real plan, "Will this plan's data survive a redeploy?", with yes or no and the
  plan step that decides it, and for a no, what the plan would have to say instead; hands it in;
  then does the same for the second, "Does production get a database of its own, built by the code
  rather than copied from the laptop or shared with development?" What the plan would have to say
  instead is for the learner's agent, and is neither credited nor faulted unless it gives a
  different verdict on the asked question.
- **tutor role:** examiner
- **tutor does:** before the sitting, reads the app the plan is for (the learner's own, or the
  tablemate's when it is a tablemate's plan): where the SQLite file's path is set, whether the code
  creates tables and inserts rows, whether the file is tracked by git. Reads the chosen host's own
  current pages on its storage and writes the host's storage rule in one line, as
  `a-judge-described-plan` gives it, with the page address and date, never from the agent's
  description. Writes a key for each of the two questions from the plan, the code and that rule:
  the verdict, the step that decides it, and so the one case of `c-plan-first-deploy` that
  question carries, by `a-judge-described-plan`'s mapping (survival: no is `catch-data-loss`,
  yes is `clear-survives`; own database: copied or shared is `catch-copied`, built by the code is
  `clear-own-database`), with its one-time-script rule; on the own-database question
  a seed step run once against production and the step that creates the tables each decide it, so
  the key lists both and naming either earns full credit. A plan that never says where
  the database will live is keyed no on survival: an answer of no, or "can't tell, the plan doesn't
  say", with that omission named, counts as catching it, and yes does not. In the sitting, shows the
  real plan and the storage line, and puts the survival question; takes the answer in before
  putting the own-database question, and gives no verdict on either until both are in. Waits,
  writing down any help word for word. Sends the adjudicator each question as its own attempt: the
  plan, the storage line with its source, that question, its key, the goal and its case, the
  learner's answer to it and any help given during it. Records each on `c-plan-first-deploy`
  with the case its key gives (record-attempt `--cases <case>`), labelled
  `a-judge-own-deploy-plan/<host>/survival` and `a-judge-own-deploy-plan/<host>/own-database`.
  Disregards remarks off the asked question (the other question, connection strings, passwords,
  backups, migrations and cost), as `a-judge-described-plan` does, and tells the adjudicator that
  the learner's "what the plan would have to say instead" is neither credited nor faulted unless
  it gives a different verdict on the asked question. Afterwards, if the real plan
  got a no on either question, the learner takes their corrected line back to their agent.
- **done when:** `c-plan-first-deploy` is met when every one of its four cases has an unaided
  pass. Each of the two questions, passed with no help, passes only the case its key gives: one
  survival case and one own-database case. The two are recorded separately, so one can pass and
  the other not. If the tutor can't
  settle a key for the real plan (the host's pages don't say how it stores files), that question
  is practice, and the tutor says so and offers `a-judge-described-plan`.
- **generator:** the real plan is whatever the agent proposed, so nobody sets its shape, its
  difficulty or which cases its questions carry; its truth on each question decides that. The
  survival question carries `catch-data-loss` or `clear-survives`, and the own-database question
  carries `catch-copied` or `clear-own-database`, as the key gives. Fixed: the two
  questions, worded as in `a-judge-described-plan`, put one at a time, survival first; the storage
  line comes from the host's own pages on the day; each key comes from that line, the plan and the
  app's code. Across visits use a different real plan each time, a tablemate's or a fresh run,
  preferring one whose verdicts would carry cases the learner has not yet passed.
- **worked example:** none during the attempt. If the learner stalls, the first level of help is,
  on the survival question, "where does the data live, and what does this host do to that place on
  a redeploy?", or, on the own-database question, "which step makes production's tables and rows,
  and where do they come from?", and that question's attempt is recorded `unaided: no`.
- **doesn't show:** one real plan's two questions can pass at most two of the goal's four cases,
  one per question, and which two is up to the agent; the other two come from
  `a-judge-described-plan` or another plan, so this alone never meets the goal. The
  learner is handed the two questions, while in Problem Set 3 itself they must think to ask them.
  The tutor writes the storage line, while in Problem Set 3 itself the learner has only the
  agent's plan, which may assert how the host stores files; so a pass doesn't show they would
  doubt that claim or read the rule off the host's pages. The key rests on the tutor's reading of
  the app and of the host's pages.
- **offer as:** the real thing: your own agent's plan for your own Problem Set 3 deploy, judged on
  the two questions before you let it run. For Problem Set 3: about 10 minutes, any time Oct 8 to
  14. Before session 11, the goal is taken in the learn tool with `a-judge-described-plan`,
  or deferred to the session 11 table activity and recorded as done elsewhere after it.
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
