Shapes `duplicated-rows`, `dropped-to-fix`, `console-check`, then a `sound` account written around
a table change (a new `meal` column on `ratings`, given in full in steps 3 to 5). Forkcast's
`dishes` table holds the starting rows (the hall's 40 dishes) and `ratings` holds what students
add. Production has had both for weeks, so anything that empties `ratings` loses students' rows,
and any new column on `ratings` has to be added to production's existing table, keeping its rows.
`dishes` has no unique column, so inserting the 40 dishes again adds 40 more rows rather than
failing. Every account's startup `CREATE TABLE IF NOT EXISTS` is sound. Each account is judged on
its own. q3's insert that skips existing dishes answers q1, q4's migration answers q2, and q4's
check answers q3, hence this order.

### q1

- **goal:** `c-deploy-keeps-data`
- **cases:** seed-every-start
- **answer:** No. Step 3 goes wrong: the startup code inserts the 40 dishes every time the server
  starts, and production already has them, so this deploy doubled them and every later deploy or
  restart adds 40 more. Tidying by hand in step 5 only clears this round. The dishes should go in
  once: take the insert out of startup, since production already has them, and load them only on
  a fresh database (a seed run once, or an insert that skips dishes already there).
- **credit:** full for naming step 3 (the startup insert) and asking that the dishes go in only
  once; "take the insert out of startup, the dishes are already there" is full. Naming step 5 is
  naming the wrong step when the fix given goes back to the startup insert (stop inserting on
  every start), and is full then. Half for step 5 with a fix that stays with the tidying (delete
  the duplicates, by hand or by a script), or for step 3 with a missing or wrong fix: a vague one
  ("be careful with the data"), or moving the insert into the pre-deploy command, which runs it on
  every deploy instead. None for accepting, or for naming only step 1, 2 or 4. A remark objecting
  to the startup `CREATE TABLE IF NOT EXISTS`, beside a right answer, is neither credited nor
  counted.
- **tutor note:** if they name only the tidying, ask what the menu page will show after the next
  push, once the duplicates are gone.

### q2

- **goal:** `c-deploy-keeps-data`
- **cases:** schema-not-applied
- **answer:** No. Steps 2 and 3 go wrong: dropping `ratings` deleted every rating students had
  added, to fix an error that needed only a new column. The version that reads `helpful_count` is
  already live, so production's existing `ratings` table should have been changed now to add the
  column, keeping its rows, for example by a one-time `ALTER TABLE` run by a script or in
  Cellarstone's query console, or by a migration applied on the next deploy.
- **credit:** full for naming step 2 or step 3 (the drop and recreate, or running it on
  production) and asking for production's existing `ratings` table to be changed to add the
  column, keeping its rows, run now; any means is fine, including once by hand in the query
  console, and naming none is fine. Asking that later table changes run as a deploy step is
  welcome, not required. Naming step 4 is naming the wrong step when the fix given goes back to the
  drop (add the column, keeping the rows), and is full then. Half for the right step with a
  missing or wrong fix: a vague one ("be careful with the data"). None for any fix that still
  deletes the ratings: moving the drop and recreate into the pre-deploy command, which runs it on
  every deploy, or dropping the table after a backup. None for accepting, or for naming only step
  1.
- **tutor note:** a learner who adds that the lost ratings now need restoring from a backup is
  neither credited nor counted for it; backups are not part of this goal. If they accept, ask what
  `ratings` held just before step 3 and just after.

### q3

- **goal:** `c-deploy-keeps-data`
- **cases:** confirm-data
- **answer:** No. Steps 1 to 4 hold, but step 5's check shows nothing: the second count was taken
  while the deploy was still Building, before the deploy was live, so the pre-deploy command and
  the new version may not yet have run, and nothing the agent added was looked for. The agent should have added a rating through the
  live app, pushed a change to `main`, and once that push's deploy was Live on Ropewalk's list,
  seen the rating still there in the live app.
- **credit:** full for naming step 5's check as the weak step and saying what would show it: a
  row added through the live app (in the browser, or through the backend's own HTTP API), a push
  to `main`, and the row seen in the live app once that push's deploy is Live. Half for naming step
  5 with a missing or wrong fix: only counting again once the deploy is Live, checking in
  Cellarstone's query console rather than through the app, restarting the backend rather than
  pushing, or pushing and looking without adding anything of their own. None for accepting, for
  naming only steps 1 to 4, or for a check that takes the agent's word or the Live status, or
  rereads the setup or the settings.
- **tutor note:** if they accept, ask what had run on production when the deploy still showed
  Building, and which of the 1,212 rows the agent put there.

### q4

- **goal:** `c-deploy-keeps-data`
- **cases:** sound-plan
- **answer:** Yes. Tables are created only if missing; the dishes went in once from a seed run
  only on a fresh database; the new column is added to production's existing `ratings` table,
  keeping its rows, by a migration applied once as the pre-deploy command when this version
  deploys; and the check added a rating through the live app, pushed, and saw it still there once
  that push's deploy was Live.
- **credit:** full for accepting, with or without harmless remarks; asking to swap the seed for an
  insert that skips dishes already there is a harmless remark. A learner who raises a real gap in
  the account as written is right, and that meets `sound-plan` in full: for example, that the seed
  script needs someone to remember to run it on a fresh database, or that Test Diner's rating
  should be removed afterwards. Asking, while accepting, for `meal` also to be listed in the
  startup statement is a harmless remark. None for naming any step as wrong on a ground the
  account rules out: that the startup `CREATE TABLE IF NOT EXISTS` wipes the data, that the seed
  script kept in the repository will run again (nothing runs it), that the pre-deploy migration
  re-applies every change on every deploy (it applies each once), or that adding the column
  deletes the ratings (it keeps them).
- **tutor note:** a learner who objects that `meal` should have gone into the `CREATE TABLE IF NOT
  EXISTS` statement instead of a migration is asking for a faulty change, which is none; ask what
  that statement does when production already has `ratings`.
