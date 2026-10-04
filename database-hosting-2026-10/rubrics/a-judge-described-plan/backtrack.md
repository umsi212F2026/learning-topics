Pebblestack keeps only files under `/data`, on an attached volume; everything else on a server's
disk, including the app's folder (`/app` in q2's Plan B), is gone after each redeploy or restart. Its managed
Postgres is a separate service, so a database there is not on the server's disk and survives a
redeploy. In q1 the faulted plan is `no-volume` (Plan A) and the sound one `sound-postgres` with
no rows (Plan B): Medium with no decoy, a survival fault, the kind served for a first counting
attempt. In q2 the faulted plan is `outside-mount` (Plan B) and the sound one a `decoy` (Plan A,
`sound-volume` plus a few seconds of downtime on each redeploy): Hard, a survival fault. Remarks
on connection strings, passwords, backups, migrating data, cost or free tiers are neither
credited nor counted as a false fault.

### q1

- **goal:** `c-plan-first-deploy`
- **answer:** Plan A: survives, no, step 2 keeps the SQLite file inside the app's folder on the
  server's ephemeral disk, with no volume, so it is gone after each redeploy; its own, built by
  code, yes (step 3, the backend creates the tables). Plan B: survives, yes (step 1, the data is
  in Pebblestack's managed Postgres, not on the server's disk); its own, built by code, yes (step
  2 creates the tables, and step 3 keeps the laptop on its own file).
- **credit:** full for all four yes-or-no answers right, with Plan A's no on survival tied to step
  2, the file kept in the app's folder on the server, and no fault named in Plan B. Half for one
  plan judged fully right and the other not.
- **tutor note:** a learner who passes Plan A because "the tables are created every time it
  starts" has seen that the app will run, not that the data will last: ask what is in those
  tables after a redeploy. Plan B starting with no items is not a fault.

### q2

- **goal:** `c-plan-first-deploy`
- **answer:** Plan A: survives, yes (steps 1 and 2 put the file at `/data/backtrack.sqlite`, on
  the volume); its own, built by code, yes (step 3 creates the tables). Plan B: survives, no, step
  2 sets the database path to `/app/server/data/backtrack.sqlite`, inside the app's folder and not
  under `/data`, so the file sits on the ephemeral disk although a volume is attached; its own,
  built by code, yes (step 3 creates the tables).
- **credit:** full for all four yes-or-no answers right, with Plan B's no on survival tied to step
  2, the path outside `/data`, and no fault named in Plan A. Half for one plan judged fully right
  and the other not.
- **tutor note:** the downtime in Plan A's step 4 is the decoy: it is a pause while the server
  restarts, not lost data. A learner who faults it has answered a question the check doesn't ask.
  A learner who passes Plan B because step 1 attaches a volume has not read where step 2 puts the
  file: ask which files Pebblestack keeps.
