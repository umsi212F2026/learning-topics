Shapes `reset-on-deploy`, `skipped-table`, `restart-check`, then a `sound` account written around
the starting rows (an insert that skips rows already there, given in full in its step 2). Stave's
`scores` table holds the starting rows (the choir's 64 pieces) and `checkouts` holds what members
add. Production has had both for weeks, so anything that empties `checkouts` loses members' rows,
and any new column on `checkouts` has to be added to production's existing table. Every account's
startup `CREATE TABLE IF NOT EXISTS` is sound. Each account is judged on its own. q3's seed run
once and its migration step answer q1 and q2, and q4's check answers q3, hence this order.

### q1

- **goal:** `c-deploy-keeps-data`
- **cases:** seed-every-start
- **answer:** No. Step 3 goes wrong: the pre-deploy command runs on every deploy, so every deploy
  empties `checkouts`, wiping every member's checkouts, and reloads the pieces. Production already
  has its 64 pieces, so the reset should not run on deploy at all: the tables are created only if
  missing, and the pieces go in once (a seed run only on a fresh database, or an insert that skips
  pieces already there).
- **credit:** full for naming step 3 (or the reset script as the pre-deploy command) and asking for
  the reset to stop running on each deploy, with the pieces put in only once; "take the reset out
  of the pre-deploy command, the pieces are already there" is full. Half for step 3 with a missing
  or wrong fix: a vague one ("be careful with the data"), moving the reset into the start command or
  the startup code, which runs it on every start instead, or keeping the reset but backing up
  `checkouts` first. None for accepting, or for naming only step 1, 2 or 4. A remark objecting to
  the startup `CREATE TABLE IF NOT EXISTS`, beside a right answer, is neither credited nor counted.
- **tutor note:** if they accept, ask when a pre-deploy command runs, and what `checkouts` holds
  just after the next push.

### q2

- **goal:** `c-deploy-keeps-data`
- **cases:** schema-not-applied
- **answer:** No. Step 2 goes wrong: production's `checkouts` table already exists, so `CREATE
  TABLE IF NOT EXISTS` skips it and the new column never reaches it; the tests passed only because
  their database is created fresh. The live app will error when it saves or shows a due date.
  Production's existing `checkouts` table should have been changed to add `due_date`, keeping its
  rows, when this version deploys, for example by a migration run as Ropewalk's pre-deploy command.
- **credit:** full for naming step 2, or the push in step 4 or the "done" in step 5, and asking for
  production's existing `checkouts` table to be changed to add the column, keeping its rows, as
  part of the deploy; naming the means is welcome, not required. Half for the right step with a
  missing or wrong fix: a vague one, adding the column once by hand in Cellarstone's query console
  (keeps the rows but leaves the next change to memory), dropping and recreating `checkouts`, with
  or without a backup, or saying only that the agent never checked the live app (true, but it
  doesn't say what is missing). None for accepting, or for naming only step 1 or 3.
- **tutor note:** if they accept, ask what step 2's statement does when production already has a
  `checkouts` table, and what the tests' database had before they ran.

### q3

- **goal:** `c-deploy-keeps-data`
- **cases:** confirm-data
- **answer:** No. Steps 1 to 4 hold, but step 5's check shows nothing: a restart runs the startup
  code but not the pre-deploy command or a new version, and the 64 pieces say nothing about what
  members added. The agent should have checked out a copy through the live app, pushed a change to
  `main`, and once that push's deploy was Live on Ropewalk's list, seen the checkout still there in
  the live app.
- **credit:** full for naming step 5's check as the weak step and saying what would show it: a
  row added through the live app (in the browser, or through the backend's own HTTP API), a push
  to `main`, and the row seen in the live app once that push's deploy is Live. Half for naming step
  5 with a missing or wrong fix: only restarting again, checking in Cellarstone's query console
  rather than through the app, checking before the push's deploy is Live, or pushing and looking
  without adding anything of their own. None for accepting, for naming only steps 1 to 4, or for a
  check that takes the agent's word or the Live status, or rereads the setup or the settings.
- **tutor note:** if they accept, ask which of the backend's database steps a restart runs, and
  which rows on the library page a member put there.

### q4

- **goal:** `c-deploy-keeps-data`
- **cases:** sound-plan
- **answer:** Yes. Tables are created only if missing; the pieces go in through an insert that
  skips any `catalog_number` already there, so production's 64 are not doubled and `checkouts` is
  untouched; table changes are applied once each as a deploy step; and the check added a checkout
  through the live app, pushed, and saw it still there once that push's deploy was Live.
- **credit:** full for accepting, with or without harmless remarks; asking to swap the insert for
  a seed script run only on a fresh database is a harmless remark. A learner who raises a real gap
  in the account as written is right, and that meets `sound-plan` in full: for example, that a
  piece the choir removes from production would be inserted again on the next start, or that the
  test checkout under Test Alto should be returned or removed afterwards. None for naming any step
  as wrong on a ground the account rules out: that the insert in step 2 doubles the pieces on every
  start (it skips existing numbers), that the startup `CREATE TABLE IF NOT EXISTS` wipes the data,
  or that the pre-deploy migration re-applies every change on every deploy (it applies each once).
- **tutor note:** a learner who calls step 2 a reseed has missed `ON CONFLICT ... DO NOTHING`; ask
  what the insert adds on a database that already has all 64 numbers.
