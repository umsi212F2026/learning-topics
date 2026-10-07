The second shape in each rotation: slot 1 `reset-in-start`, slot 2 `local-only` (seats free on
each ride, a new `seats` column on `rides`, which production already has), slot 3 the starting
rows from an insert that skips rows already there. `games` holds the starting rows and `rides`
what users add. Production already has both tables, every game, and dozens of rides, so anything
that empties or recreates a table loses parents' rides, and anything that inserts the games again
doubles them.

Every plan has exactly one fault or none, and every step not named as the fault is sound. Plans 1
to 3 create the tables only if they are missing (in plan 1, as the first thing `reset.js` does),
which is sound: on production it does nothing, since both tables exist. No plan names a connection
string's value. How the frontend deploys is not in question. A remark beyond what a question asks
is neither credited nor counted, unless it asks for a change that would itself wipe or duplicate
production's rows, or leave production's tables behind the code (a reset or a drop moved into the
pre-deploy command, the games inserted on every start with nothing skipping those already there);
such a change cancels the question's credit.

### q1

- **goal:** `c-deploy-keeps-data`
- **cases:** seed-every-start
- **answer:** Not as it stands. Steps 2 and 3 together run `reset.js` before the server every time
  it starts, which Ropewalk does on every deploy and every restart, and the script empties both
  tables and loads the games again, so every push or saved setting deletes all the parents' rides.
  Change it so the tables are created only if they are missing and the games go in once, from a
  seed run only on a fresh database or an insert that skips games already there; since production
  already has its games, taking the reset out of the start command is enough there.
- **credit:** full for naming the reset (the emptying and loading in step 2, or step 3 running it
  on every start) and asking for a change that removes it: the tables created only if missing, and
  the games put in once (run once on a fresh database, or skipped when already there); "take the
  reset out of the start command, the games are already there" is full too. A reason is welcome,
  not required. Half for only stopping the emptying, in any words ("don't delete the rows"), since
  the games would still go in on every start; for naming the reset with no workable change, or a
  vague one ("be careful with the data"). None for any change that still deletes the rides: only
  stopping the load while the tables are still emptied, moving the reset into Ropewalk's
  pre-deploy command, which runs on every deploy, or resetting after a backup. None for agreeing, or for objecting only to sound steps (keeping the
  schedule in the repository, creating missing tables, reading `AWAYDAY_DB` from Ropewalk's
  settings, the ride test).
- **tutor note:** "the same known state" is the bait. If they agree, ask what is in `rides` just
  after Ropewalk's next deploy. If they read the start command as running once, point them to
  Ropewalk's bullet on starting the server afresh.

### q2

- **goal:** `c-deploy-keeps-data`
- **cases:** schema-not-applied
- **answer:** Not as it stands. No step changes production's `rides` table: step 4 adds `seats`
  only to the `CREATE TABLE IF NOT EXISTS` statement, which production skips because the table
  already exists, and step 5 changes only the local database. The tests pass against their fresh
  database, the app works locally, and the live app errors when it saves or lists seats. Ask for
  production's `rides` to have the column added, keeping its rows, when that version deploys, for
  example a migration (`ALTER TABLE rides ADD COLUMN seats integer`) run by Ropewalk's pre-deploy
  command.
- **credit:** full for naming that nothing changes production's existing table (or naming step 4,
  the column added only to the `CREATE TABLE IF NOT EXISTS` statement, or step 5, the column added
  only to the local database) and asking for production's `rides` to get the column, keeping its
  rows, when that version deploys (a migration run by Ropewalk's pre-deploy command or as the
  backend starts); naming the means is welcome, not required, so "change the live table to add the
  column, keeping its rows, as part of the deploy" is full. Half for naming the gap with no
  workable change or a vague one; for adding the column by hand once in Cellarstone's query
  console, the way step 5 did locally, which keeps the rows but leaves the next change to memory;
  none for dropping and recreating `rides`, after a backup or not, which deletes the rides. None for agreeing, or for
  objecting only to sound steps (the backend creating missing tables at startup, the form, the
  route, the tests, the push). A remark objecting to the backend creating missing tables when it
  starts, beside a right answer, is neither credited nor counted.
- **tutor note:** step 5 is the bait: it works on the learner's machine. If they agree, ask which
  databases now have a `seats` column, and which one the live app uses.

### q3

- **goal:** `c-deploy-keeps-data`
- **cases:** sound-plan
- **answer:** Yes, go along with it: the backend creates the tables only if they are missing, each
  game goes in once because the insert skips games already there, and table changes are migration
  files applied once each by the pre-deploy command, which keeps the rows.
- **credit:** full for agreeing, with or without harmless remarks; asking to swap the insert that
  skips existing games for a seed script run only on a fresh database counts as a harmless remark.
  A learner who raises a real gap in the plan as written is right, and that meets the case in full:
  for example, that a game whose details change in `games.json` keeps its old details in
  production, since its id is already there. None for asking to change a sound step into a faulty
  one (inserting the games on every start with nothing skipping, emptying the tables, dropping
  tables to apply a change), or for refusing the plan on a wrong ground: creating missing tables at
  startup wipes the data; inserting the games on every start doubles them, when step 2 says games
  already there are skipped; the pre-deploy migration re-applies every change on every deploy,
  when step 4 says each is applied once and recorded.
- **tutor note:** if they refuse because the games "go in on every start", ask what step 2 says
  happens to a game whose id is already in `games`.

### q4

- **goal:** `c-deploy-keeps-data`
- **cases:** confirm-data
- **answer:** Offer a ride to a game in the live app (or add one through the backend's own HTTP
  API), then push a small change to `main` that redeploys the backend. Once Ropewalk's deploy list
  shows that push's deploy as Live, open the live app and see the ride still listed for that game.
- **credit:** full for adding something through the live app (in the browser, or through the
  backend's own HTTP API), pushing a change to `main`, and once Ropewalk shows that push's deploy
  Live, looking in the live app and seeing the thing still there. Half for adding the thing and
  then only restarting the backend (saving a setting) rather than pushing, which never runs the
  pre-deploy command; for checking in Cellarstone's query console rather than through the app; for
  checking before the push's deploy is Live; or for pushing and looking without having added
  anything of their own (seeing the games listed shows nothing about what users added). None for
  taking the agent's word or the Live status, or for reading the plan or the settings again.
- **tutor note:** if they only look at the schedule after a push, ask which rows a parent added
  and how they would know those survived.
