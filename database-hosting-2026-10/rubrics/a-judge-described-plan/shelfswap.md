Driftwood keeps only files under `/data`, on an attached volume; everything else on a server's
disk is gone after each redeploy or restart. Its managed Postgres is a separate service, so a
database there is not on the server's disk and survives a redeploy. Both questions are Medium
with no decoy, the kind served for a first counting attempt. In q1 the faulted plan is
`laptop-copy` and the sound one `sound-volume`; in q2 the faulted plan is `shared-dev` and the
sound one `sound-postgres`. Both faults are own-database faults, so neither question tests a
survival fault. Remarks on connection strings, passwords, backups, migrating data, cost or free
tiers are neither credited nor counted as a false fault.

### q1

- **goal:** `c-plan-first-deploy`
- **answer:** Plan A: survives, yes (steps 1 and 2 put the file under `/data`, on the volume);
  its own, built by code, yes (step 3, the backend creates the tables on the empty volume).
  Plan B: survives, yes (steps 1 and 2, the file is under `/data`); its own, built by code, no,
  step 3 uploads the laptop's database file, so production starts as a copy of the laptop's
  books and requests.
- **credit:** full for all four yes-or-no answers right, with Plan B's no tied to step 3, the
  upload of the laptop's file, and no fault named in Plan A. Half for one plan judged fully right
  and the other not.
- **tutor note:** a learner who faults Plan A because the volume starts empty, or says Plan B is
  better because "production has data", has the own-database question backwards. A learner who
  says no to Plan B on survival because the file came from the laptop has mixed the two
  questions: where the file lives decides survival, and Plan B's file is under `/data`.

### q2

- **goal:** `c-plan-first-deploy`
- **answer:** Plan A: survives, yes (step 1, the data is in Driftwood's managed Postgres, not on
  the server's disk); its own, no, step 3 points the laptop's development server at the
  production database, so development and production share one database. Plan B: survives, yes
  (step 1, managed Postgres); its own, built by code, yes (step 2 creates the tables; step 3's
  seed script is in the repository, so its rows come from the code, and step 4 keeps the laptop
  on its own file).
- **credit:** full for all four yes-or-no answers right, with Plan A's no tied to step 3, the
  laptop's development server pointed at the production database, and no fault named in Plan B.
  Half for one plan judged fully right and the other not.
- **tutor note:** the likely false fault is Plan B's step 3: a seed script run once against
  production builds production from the code, wherever it is run from, and is not the laptop's
  data being copied. If the learner faults it, ask where the three sample books are written down.
