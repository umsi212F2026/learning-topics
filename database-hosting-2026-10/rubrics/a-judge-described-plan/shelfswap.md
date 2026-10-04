Driftwood keeps only files under `/data`, on an attached volume; everything else on a server's
disk is gone after each redeploy or restart. Its managed Postgres is a separate service, so a
database there is not on the server's disk and survives a redeploy. q1 is Medium with no decoy,
the kind served for a first counting attempt. Its faulted plan is `laptop-copy` and its sound one
`sound-volume`. The fault is an own-database fault, so q1 does not test a survival fault. Remarks on connection strings, passwords, backups, migrating data, cost or free
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
