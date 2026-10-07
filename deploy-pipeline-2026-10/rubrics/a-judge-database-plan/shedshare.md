The third shape in each rotation: slot 1 `reseed-on-start`, slot 2 `drop-to-fix` (a due date on
each loan, a new `due_date` column on `loans`, which production already has; the change is live
and erroring), slot 3 the starting rows from a seed script run only on a fresh database. `tools`
holds the starting rows and `loans` what users add. Production already has both tables, every
tool, and over a hundred loans, so anything that empties or recreates a table loses members'
loans, and anything that inserts the tools again doubles them.

Every plan has exactly one fault or none, and every step not named as the fault is sound. Every
plan has the backend run `CREATE TABLE IF NOT EXISTS` when it starts, which is sound: on
production it does nothing, since both tables exist. No plan names a connection string's value.
How the frontend deploys is not in question. A remark beyond what a question asks is neither
credited nor counted, unless it asks for a change that would itself wipe or duplicate
production's rows, or leave production's tables behind the code (a reset or a drop moved into the
pre-deploy command, the seed script run on every deploy); such a change cancels the question's
credit.

### q1

- **goal:** `c-deploy-keeps-data`
- **cases:** seed-every-start
- **answer:** Not as it stands. Step 3 adds every tool in `tools.json` as a new row each time the
  backend starts, which Ropewalk does on every deploy and every restart, with nothing checking
  whether the tool is already there, so every push or saved setting adds the whole shed to `tools`
  again and the list fills with copies. Members' loans survive. Change it so the tools go in once,
  from a seed run only on a fresh database or an insert that skips tools already there; since
  production already has its tools, taking the insert out of startup is enough there.
- **credit:** full for naming step 3 and asking for a change that puts the tools in once (run once
  on a fresh database, or skipped when already there); "take the insert out of startup, the tools
  are already there" is full too. A reason is welcome, not required. Half for naming step 3 with
  no workable change, or a vague one ("be careful with the data"); or for moving the insert into
  Ropewalk's pre-deploy command, which runs on every deploy and still doubles the tools. None for
  agreeing, or for objecting only to sound steps (keeping the list in the repository, step 2's
  `CREATE TABLE IF NOT EXISTS`, reading `SHEDSHARE_DB` from Ropewalk's settings, the listing
  test); objecting only to step 2 is none.
- **tutor note:** "never missing a tool" and the passing test are the bait: the test starts from an
  empty database, so it never sees a second start. If they agree, ask how many rows for the
  shed's ladder `tools` holds after the third deploy.

### q2

- **goal:** `c-deploy-keeps-data`
- **cases:** schema-not-applied
- **answer:** Not as it stands. Step 2's script drops `loans`, deleting every loan members have
  recorded, and step 3 makes it the pre-deploy command, so it does that on every deploy from now
  on. The version is already live, so change production's `loans` now to add the `due_date`
  column, keeping its rows: a one-time `ALTER TABLE loans ADD COLUMN due_date date`, by a script or
  in Cellarstone's query console, or a migration run on the next deploy.
- **credit:** full for naming the drop (step 2, or step 3 running it) and asking for any change to
  production's `loans` that adds the column and keeps its rows, run now (a one-time change by
  script or in Cellarstone's query console, or a migration on the next deploy); naming the means
  is welcome, not required, so "add the column to the live table without deleting the loans" is
  full. Asking that later changes run as a deploy step is welcome, not required. Half for naming
  the drop with no workable change, or a vague one. None for any change that still deletes the
  loans: keeping the drop but running it only once (taking it out of the pre-deploy command
  afterwards), or dropping the table after a backup. None for agreeing, or for objecting only to
  sound steps (the backend creating missing tables at startup, the script reading
  `SHEDSHARE_DB`).
- **tutor note:** "so the table matches the code" is the bait, and the error makes any fix look
  welcome. If they agree, ask what `loans` holds once the next deploy is live.

### q3

- **goal:** `c-deploy-keeps-data`
- **cases:** sound-plan
- **answer:** Yes, go along with it: the backend creates the tables only if they are missing, the
  tools went into production once and the seed script runs only on a fresh database, and table
  changes are migration files applied once each by the pre-deploy command, which keeps the rows.
- **credit:** full for agreeing, with or without harmless remarks; asking to swap the seed script
  for an insert that skips tools already there counts as a harmless remark. A learner who raises a
  real gap in the plan as written is right, and that meets the case in full: for example, that the
  seed script needs someone to remember to run it on a fresh database, or that a tool added to the
  shed later needs some way into production's `tools`. None for asking to change a sound step into
  a faulty one (seeding on every start or every deploy, dropping tables to apply a change), or for
  refusing the plan on a wrong ground: creating missing tables at startup wipes the data; the
  pre-deploy migration re-applies every change on every deploy, when step 4 says each is applied
  once and recorded; the seed script kept in the repository will run again, when step 2 says it is
  run by hand on a fresh database only.
- **tutor note:** if they refuse because the seed script is in the repository, ask what step 2
  says about when it runs.

### q4

- **goal:** `c-deploy-keeps-data`
- **cases:** confirm-data
- **answer:** Record a loan in the live app (or add one through the backend's own HTTP API), then
  push a small change to `main` that redeploys the backend. Once Ropewalk's deploy list shows that
  push's deploy as Live, open the live app and see the loan still listed as out.
- **credit:** full for adding something through the live app (in the browser, or through the
  backend's own HTTP API), pushing a change to `main`, and once Ropewalk shows that push's deploy
  Live, looking in the live app and seeing the thing still there. Half for adding the thing and
  then only restarting the backend (saving a setting) rather than pushing, which never runs the
  pre-deploy command; for checking in Cellarstone's query console rather than through the app; for
  checking before the push's deploy is Live; or for pushing and looking without having added
  anything of their own (seeing the tools listed shows nothing about what users added). None for
  taking the agent's word or the Live status, or for reading the plan or the settings again.
- **tutor note:** if they only look at the tool list after a push, ask which rows a member added
  and how they would know those survived.
