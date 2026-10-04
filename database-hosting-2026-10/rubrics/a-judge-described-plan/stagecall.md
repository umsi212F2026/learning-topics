Quarrybank keeps only files under `/data`, on an attached volume; everything else on a server's
disk is gone after each redeploy or restart. Its managed Postgres is a separate service, so a
database there is not on the server's disk and survives a redeploy. Both questions are Medium
with no decoy, the kind served for a first counting attempt. In q1 the faulted plan is
`silent-location` (Plan A) and the sound one `sound-volume` with a seed script run once on the
host after the first deploy (Plan B): a survival fault. In q2 the faulted plan is `shared-dev`
(Plan B) and the sound one `sound-postgres` with a seed script run once from the laptop after the
first deploy (Plan A): an own-database fault. Remarks on connection strings, passwords, backups,
migrating data, cost or free tiers are neither credited nor counted as a false fault.

### q1

- **goal:** `c-plan-first-deploy`
- **answer:** Plan A: survives, no: no step says where the database lives (no volume, no path,
  no managed Postgres), so it is not shown to survive; "can't tell, the plan doesn't say" is the
  same answer. Its own, built by code, yes (step 3, the backend creates the tables, and nothing
  comes from the laptop). Plan B: survives, yes (steps 1 and 2 put the file at
  `/data/stagecall.sqlite`, on the volume); its own, built by code, yes (step 3 creates the
  tables, and step 4's seed script is kept in the repository and run once after the first
  deploy).
- **credit:** full for all four yes-or-no answers right, with Plan A's no on survival (or "can't
  tell") tied to the plan's never saying where the database lives, and no fault named in Plan B.
  A yes on Plan A's survival is wrong. Half for one plan judged fully right and the other not.
- **tutor note:** a learner who passes Plan A because the backend makes its tables on startup has
  seen that the app will run, not where its data goes: ask which step says where the database
  lives, and what Quarrybank does to a place it isn't told about. A learner who faults Plan B's
  step 4 as "test data in production" should be asked where the three sample slots are written
  down.

### q2

- **goal:** `c-plan-first-deploy`
- **answer:** Plan A: survives, yes (step 1, the data is in Quarrybank's managed Postgres, not on
  the server's disk); its own, built by code, yes (step 2 creates the tables; step 3's seed
  script is kept in the repository, so its rows come from the code though it is run from the
  laptop; step 4 keeps the laptop's development server on its own file). Plan B: survives, yes
  (step 1, managed Postgres); its own, no, step 3 points the laptop's development server at the
  production database, so development and production share one database.
- **credit:** full for all four yes-or-no answers right, with Plan B's no tied to step 3, the
  laptop's development server pointed at the production database, and no fault named in Plan A.
  Half for one plan judged fully right and the other not.
- **tutor note:** the likely false fault is Plan A's step 3: a seed script kept in the code and
  run once against production builds production from the code, wherever it is run from; it is
  not the laptop's data being copied, and not the laptop's development server working against
  production. If the learner faults it, ask where the two sample slots are written down, and what
  the laptop's development server uses afterwards (step 4).
