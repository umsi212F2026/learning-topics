# Activities: database hosting

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

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
| `c-plan-first-deploy` | `a-trace-own-database-setup`, `a-contrast-plan-pairs` | `a-judge-described-plan`, `a-judge-own-deploy-plan` | |

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
- **learner does:** reads with their Problem Set 2 repository open beside the pages, and stops twice
  to answer before reading on; asking their agent to point at a line of their code is fine, and "I
  don't know yet" is an honest answer:
  1. After Render: **finds where their backend opens its SQLite file and says where that file
     lives.** Then says what their Problem Set 2 restart test would show if they added something
     through the app, the host redeployed, and the file was on an ephemeral disk; and names the two
     ways out the passages gave (the file kept under a persistent volume's mount path, or a database
     that runs as a program of its own, such as Postgres).
  2. After Odin: says whether their own code makes the tables when it starts and finds no database,
     whether it puts in any rows itself (seed data), and which rows now in their laptop's database
     are test data that should not be in production.
- **tutor role:** explainer
- **tutor does:** stays quiet through the reading except at the stops and when asked. At each stop,
  takes the learner's answer first and replies with one near-miss question rather than a verdict
  ("the app still starts and makes empty tables after a redeploy; would your restart test pass?").
  At stop 2, if the learner says production should start with their laptop's file, asks what would
  then be in it, and that test data and copying it up are the two things this topic watches for.
  Says that Odin's way (a script the developer runs once against the production database) and
  tables made by the app's own startup code are both "built by the code"; copying the laptop's file
  is not. **Vendor facts, as checked on the vendors' own pages 2026-10-04,** if the learner asks
  where volumes can be had: Render's persistent disks attach only to paid services; Railway's
  volumes (https://docs.railway.com/reference/volumes) are 0.5 GB on the Free and Trial plans, one
  per service, with a little downtime on each redeploy. Choosing a host is cloud-hosting's;
  connection strings and passwords are deploy-config's; backups and migrating real data are a
  later topic. Makes no change to the learner's app.
- **done when:** both stops have an answer tied to the learner's own app: where its SQLite file
  lives and what an ephemeral disk would do to it, and whether its code builds the tables and any
  seed rows. No `checks`: the readiness indication is taken in `a-dry-run-database-plan`, which
  follows.
- **offer as:** this topic's orientation, one entry holding a sequence of three short passages: why
  SQLite needs storage that lasts (MDN), what ephemeral and persistent storage are on a real host
  (Render), and a production database filled by a script rather than by hand (Odin). About 15
  minutes with the stops; with `a-dry-run-database-plan`, about 20. Followed by
  `a-dry-run-database-plan`.

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
  sign-up sheet, a recipe box, a study-group finder) and the host's one-line storage rule. Rehearsal
  one is the "where the database lives" line of one shape from `a-judge-described-plan`'s
  generator at Easy (`ephemeral`, or a sound volume plan with the file under the mount path).
  Rehearsal two is the "how production gets its rows" line of `laptop-copy` or of a sound plan.
  Fixed: two rehearsals in that order, neither graded, then the readiness question word for word.
  Difficulty doesn't vary: this settles an indication, not a capability.
- **worked example:** if the learner freezes, the tutor answers a different made-up line aloud in two
  sentences, then hands the original back.
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. Each
  rehearsal is one line, helped and ungraded, so it shows nothing about finding the deciding detail
  in a whole plan, and nothing about the seven words, which have their own supply.
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

### `a-contrast-plan-pairs`

- **serves:** `c-plan-first-deploy`
- **supports:** deepen
- **artifact:** no external source. Pairs of plan excerpts written by the tutor per the generator
  below, two or three pairs a sitting. About 10 minutes. Nothing to run.
- **learner does:** for each pair, says which excerpt is sound and which is not, which of the two
  questions the faulty one fails (survives a redeploy; production has its own database built by the
  code), and the one detail that decides it. Some pairs are both sound, and then says so. After the
  last pair, states in a sentence the rule they used for each question.
- **tutor role:** socratic questioner
- **tutor does:** shows one pair at a time and takes the answer before commenting. Where it is
  wrong, asks what the host would do with the file, or where production's rows came from, rather
  than giving the verdict; after one such question, gives the verdict and the deciding detail.
- **done when:** the learner calls a pair right on each question without a near-miss question, and
  their two rules would sort the generator's pairs correctly. No `checks`: each pair is identical but
  for one detail, so the learner is shown where to look, which a whole plan never does.
- **generator:** fixed: one made-up app like the learner's (React, Express, SQLite) and one made-up
  host whose storage rule is stated in a line (for example "servers' disks are ephemeral; a volume
  can be mounted at `/data`"). Each excerpt is two or three lines of an agent's plan; the two
  excerpts in a pair are word for word the same but for one detail. What varies, one pair per kind:
  file path under the mount path, or beside it; tables created by the app at startup, or "already
  there because we made them locally" with the laptop file uploaded; demo rows inserted by a seed
  script, or the laptop's database copied up "so production has data"; production and the laptop
  each with their own database, or the laptop's dev server pointed at the production one; and a
  decoy pair, both sound, differing in a detail that doesn't bear (the database at the same vendor
  as the backend or a different one; a seed script or none). Easy: the faulty excerpt says outright
  what it does. Medium: the deciding detail is a path or a single word. Use one decoy pair a
  sitting at most. No connection strings, passwords, backups, migrations or prices appear.
- **offer as:** the quickest practice, on made-up plans: 10 minutes, nothing to run, with each pair
  pointing at the detail that matters. Pick `a-trace-own-database-setup` to work on your own app
  instead.

### `a-judge-described-plan`

- **serves:** `c-plan-first-deploy`
- **supports:** attempt
- **checks:** `c-plan-first-deploy`
- **artifact:** no external source. One made-up app and one agent's deploy plan for its database,
  written per the generator below. About 10 minutes.
- **learner does:** reads the app's description, the host's storage rule and the plan, then writes
  alone two answers, each a yes or no with the plan step that decides it: will the data survive a
  redeploy? Does production get a database of its own, built by the code rather than copied from
  the laptop? Hands it to the tutor.
- **tutor role:** none
- **tutor does:** writes the key into the record before showing anything: yes or no on each
  question and the deciding step. Shows the app, the rule and the plan. Waits, writing down any help
  word for word. Sends the adjudicator the material, the key, the learner's answer verbatim and
  every piece of help. Labels the attempt `a-judge-described-plan/<shape>`. A remark about
  connection strings or passwords (deploy-config), backups or migrating data (a later topic), or
  cost and free tiers (cloud-hosting) is neither credited nor counted as a false fault: the tutor
  tells the adjudicator to disregard it and the learner where it belongs.
- **done when:** criterion met with no help on a Medium or Hard instance.
- **generator:** fixed: the app is small and shaped like Problem Set 2 (React frontend, Express
  backend, a SQLite file with one or two named tables), described in three lines. The host is made
  up, and its storage is stated in one line: whether its servers' disks are ephemeral, whether it
  offers a volume and where it mounts, and whether it offers a managed Postgres. The plan is four
  to seven numbered steps, written as an agent writes, and ends with an assurance that the data is
  safe. Somewhere it says where the database lives and how production gets its tables and any rows.
  It never contains connection strings, passwords, backups, migrations of existing data, or prices.
  What varies: the app, the host, the wording, and the shape:
  - `ephemeral` (Easy): the SQLite file stays in the app's folder on an ephemeral disk, no volume.
    Fails survival.
  - `outside-mount` (Hard): a volume is mounted at `/data`, but the file path in the code or an
    environment setting stays elsewhere. Fails survival.
  - `laptop-copy` (Medium): the volume is right, but a step uploads the laptop's database file "so
    production starts with your data". Fails built-by-code.
  - `shared-dev` (Medium): a managed Postgres, with a step pointing the laptop's dev server at the
    same database "so you can test against real data". Fails its-own.
  - `committed-file` (Hard): the database file is taken out of `.gitignore` and committed "so it
    ships with the app". Fails both: production starts as the laptop's copy, and each redeploy puts
    that copy back.
  - `sound-volume` (Medium): the file under the volume's mount path, tables created by the app at
    startup, demo rows from a seed script or none. Meets both.
  - `sound-postgres` (Medium): a managed Postgres, tables made by a setup script run once after
    deploy, nothing from the laptop. Meets both.
  - `decoy` (Hard): a sound plan with a detail that sounds alarming and doesn't bear (a few seconds
    of downtime on each redeploy because of the volume, the database on a different vendor from the
    backend, a seed script inserting three demo rows). Meets both.
  Difficulty as marked. Every question bears on `c-plan-first-deploy`, through both of its parts at
  once. An answer that faults a step the key doesn't fault fails, on any shape. For the first
  counting attempt prefer a faulted Medium or Hard shape; on review visits serve a shape the learner
  hasn't had, alternating faulted and sound, reading the labels `served.mjs` returns. Easy is for
  the worked example and a retry with help after a miss.
- **worked example:** work one `ephemeral` instance aloud: find the step that says where the file
  goes, read it against the host's storage line, then find the step that says where production's
  rows come from. At the first level of help on a real attempt, ask only "where does the file live,
  and what does this host do to that place on a redeploy?"
- **doesn't show:** one sitting has one plan, so a pass on a faulted plan shows the learner catches
  that fault and invents none there, not that they would leave a whole sound plan alone; the sound
  and decoy shapes test that on later visits. The host's storage rule is given in a line, so a pass
  doesn't show the learner could find it on a real host's pages. The host is made up, so nothing
  about which real hosts offer volumes. The learner knows a check is on.
- **offer as:** the check that's available now, before Problem Set 3: one made-up plan, 10
  minutes, nothing to run. Minimum route for this topic before session 11: `a-read-database-survives`
  and `a-dry-run-database-plan` (20 minutes) and this (10), about 30 minutes besides the words.
  `a-judge-own-deploy-plan` is the same capability on your own agent's plan.

### `a-judge-own-deploy-plan`

- **serves:** `c-plan-first-deploy`
- **supports:** attempt
- **checks:** `c-plan-first-deploy`
- **artifact:** no external source. The plan the learner's own agent writes in Problem Set 3 for
  deploying their Problem Set 2 app's database, taken before it is carried out; on a review visit, a
  tablemate's plan or a fresh run of the same request. About 15 minutes, plus the tutor's
  preparation.
- **learner does:** before telling the agent to go ahead, writes alone the same two answers as in
  `a-judge-described-plan`, each a yes or no with the plan step that decides it, and for any no,
  what the plan would have to say instead. Hands it to the tutor.
- **tutor role:** none
- **tutor does:** before the attempt, reads the learner's app (where the SQLite file's path is set,
  whether the code creates tables and inserts rows, whether the file is tracked by git) and the
  chosen host's own current pages on its storage, then writes the host's storage rule in one line,
  as `a-judge-described-plan` gives it, with the page address and date, never from the agent's
  description. Writes the key from the plan, the code and that rule. A plan that never says where
  the database will live is keyed "not shown to survive", and a learner who says so has caught it.
  Shows the plan and the storage line. Waits, writing down any help word for word. Sends the
  adjudicator the plan, the storage line with its source, the key, the learner's answer and every
  piece of help. Labels the attempt `a-judge-own-deploy-plan/<host>`. Disregards remarks on
  connection strings, passwords, backups, migrations and cost, as `a-judge-described-plan` does.
  Afterwards, if the plan failed either question, the learner takes their corrected line back to
  their agent.
- **done when:** criterion met with no help.
- **generator:** the material is whatever the learner's agent proposed, so nobody sets the shape or
  the difficulty. Fixed: the storage line comes from the host's own pages on the day; the key comes
  from that line, the plan and the app's code. Across visits use a different plan each time, a
  tablemate's or a fresh run, preferring one whose verdict differs from the last one the learner
  judged.
- **worked example:** none during the attempt. If the learner stalls, the first level of help is
  "where does the file live, and what does this host do to that place on a redeploy?", and the
  attempt is recorded `unaided: no`.
- **doesn't show:** whether the plan is faulted, and how, depends on the agent, so a pass may come
  on a sound plan or one with a single plain fault. The tutor writes the storage line, so a pass
  doesn't show the learner could read it off the host's pages. The key rests on the tutor's reading
  of the app and of the host's pages.
- **offer as:** the real thing: your own agent's plan for your own Problem Set 3 deploy, judged
  before you let it run. About 15 minutes, any time Oct 8 to 14. `a-judge-described-plan` is the one
  to take before session 11.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
