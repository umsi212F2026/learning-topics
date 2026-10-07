The first shape in each rotation: slot 1 `drop-on-start`, slot 2 `code-only` (a phone number on
each sign-up, a new `phone` column on `signups`, which production already has), slot 3 the
starting rows from a seed script run only on a fresh database. `clubs` holds the starting rows and
`signups` what users add. Production already has both tables, every club, and hundreds of
sign-ups, so anything that empties or recreates a table loses students' sign-ups, and anything
that inserts the clubs again doubles them.

Every plan has exactly one fault or none, and every step not named as the fault is sound. Plans 2
and 3 have the backend run `CREATE TABLE IF NOT EXISTS` when it starts, which is sound: on
production it does nothing, since both tables exist. No plan names a connection string's value.
How the frontend deploys is not in question. A remark beyond what a question asks is neither
credited nor counted, unless it asks for a change that would itself wipe or duplicate
production's rows, or leave production's tables behind the code (a reset or a drop moved into the
pre-deploy command, the seed script run on every deploy); such a change cancels the question's
credit.

### q1

- **goal:** `c-deploy-keeps-data`
- **cases:** seed-every-start
- **answer:** Not as it stands. Step 2 drops and recreates both tables every time the backend
  starts, which Ropewalk does on every deploy and every restart, so every push or saved setting
  deletes all the students' sign-ups and loads the clubs afresh. Change it so the backend creates
  the tables only if they are missing (`CREATE TABLE IF NOT EXISTS`) and the clubs go in once,
  from a seed run only on a fresh database or an insert that skips clubs already there; since
  production already has its clubs, taking the load out of startup is enough there.
- **credit:** full for naming step 2 and asking for a change that removes it: the tables created
  only if missing, and the clubs put in once (run once on a fresh database, or skipped when
  already there); "take the load out of startup, the clubs are already there" is full too. A
  reason is welcome, not required. Half for only stopping the drop, in any words ("don't delete
  the tables"), since the clubs would
  still go in on every start; for naming step 2 with no workable change, or a vague one ("be
  careful with the data"). None for any change that still deletes the sign-ups: moving the drop
  and reload into Ropewalk's pre-deploy command, which runs on every deploy, or dropping the
  tables after a backup. None for agreeing, or for
  objecting only to sound steps (keeping the definitions and the clubs in the repository, reading
  `CLUBHOP_DB` from Ropewalk's settings, the column test).
- **tutor note:** "so the tables always match the code" is the bait. If they agree, ask what is in
  `signups` just after Ropewalk's next deploy. If they only stop the drop, ask what
  `clubs` holds after the third restart.

### q2

- **goal:** `c-deploy-keeps-data`
- **cases:** schema-not-applied
- **answer:** Not as it stands. Nothing in the plan changes production's `signups` table: step 4
  adds `phone` only to the `CREATE TABLE IF NOT EXISTS` statement, which production skips because
  the table already exists, so the tests pass against their fresh database and the live app errors
  when it saves or lists a phone number. Ask for production's `signups` to have the column added,
  keeping its rows, when that version deploys, for example a migration (`ALTER TABLE signups ADD
  COLUMN phone text`) run by Ropewalk's pre-deploy command.
- **credit:** full for naming that nothing changes production's existing table (or naming step 4,
  the column added only to the `CREATE TABLE IF NOT EXISTS` statement) and asking for
  production's `signups` to get the column, keeping its rows, when that version deploys (a
  migration run by Ropewalk's pre-deploy command or as the backend starts); naming the means is
  welcome, not required, so "change the live table to add the column, keeping its rows, as part of
  the deploy" is full. Half for naming the gap with no workable change or a vague one; for adding
  the column by hand once in Cellarstone's query console, which keeps the rows but leaves the next
  change to memory. None for dropping and recreating `signups`, after a backup or not, which
  deletes the sign-ups; none for
  agreeing, or for objecting only to sound steps (the backend creating missing tables at startup,
  the form, the route, the tests, the push). A remark objecting to the backend creating missing
  tables when it starts, beside a right answer, is neither credited nor counted.
- **tutor note:** the passing tests are the bait. If they agree, ask what step 1 says that
  statement does when production already has `signups`, and which database the tests ran
  against.

### q3

- **goal:** `c-deploy-keeps-data`
- **cases:** sound-plan
- **answer:** Yes, go along with it: the backend creates the tables only if they are missing, the
  clubs went into production once and the seed script runs only on a fresh database, and table
  changes are migration files applied once each by the pre-deploy command, which keeps the rows.
- **credit:** full for agreeing, with or without harmless remarks; asking to swap the seed script
  for an insert that skips clubs already there counts as a harmless remark. A learner who raises a
  real gap in the plan as written is right, and that meets the case in full: for example, that the
  seed script needs someone to remember to run it on a fresh database, or that a club the student
  union recognizes later has no stated way into production's `clubs`. None for asking to change a sound step into a faulty one
  (seeding on every start or every deploy, dropping tables to apply a change), or for refusing the
  plan on a wrong ground: creating missing tables at startup wipes the data; the pre-deploy
  migration re-applies every change on every deploy, when step 4 says each is applied once and
  recorded; the seed script kept in the repository will run again, when step 2 says it is run by
  hand on a fresh database only.
- **tutor note:** if they refuse because the migration script "runs every deploy", ask what step 4
  says it does with a file it has already applied.

### q4

- **goal:** `c-deploy-keeps-data`
- **cases:** confirm-data
- **answer:** Sign up for a club in the live app (or add a sign-up through the backend's own HTTP
  API), then push a small change to `main` that redeploys the backend. Once Ropewalk's deploy list
  shows that push's deploy as Live, open the live app and see the sign-up still on the club's list.
- **credit:** full for adding something through the live app (in the browser, or through the
  backend's own HTTP API), pushing a change to `main`, and once Ropewalk shows that push's deploy
  Live, looking in the live app and seeing the thing still there. Half for adding the thing and
  then only restarting the backend (saving a setting) rather than pushing, which never runs the
  pre-deploy command; for checking in Cellarstone's query console rather than through the app; for
  checking before the push's deploy is Live; or for pushing and looking without having added
  anything of their own (seeing the clubs listed shows nothing about what users added). None for
  taking the agent's word or the Live status, or for reading the plan or the settings again.
- **tutor note:** if they only look at the club list after a push, ask which rows a student added
  and how they would know those survived.
