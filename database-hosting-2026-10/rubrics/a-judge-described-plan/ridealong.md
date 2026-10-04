Larchyard keeps only files under `/data`, on an attached volume; everything else on a server's
disk, the app's folder included, is gone after each redeploy or restart. Its managed Postgres is a
separate service, so a database there is not on the server's disk and survives a redeploy. In q1
the faulted plan is `committed-file` (Plan A) and the sound one `sound-postgres` with a seed
script run once from the laptop (Plan B): Hard, a fault of both kinds. In q2 the faulted plan is
`no-volume` (Plan B) and the sound one `sound-volume` with a seed script (Plan A): Medium with no
decoy, a survival fault, the kind served for a first counting attempt. Remarks on connection
strings, passwords, backups, migrating data, cost or free tiers are neither credited nor counted
as a false fault.

### q1

- **goal:** `c-plan-first-deploy`
- **answer:** Plan A: survives, no, steps 2 and 3 keep the file in the app's folder on the
  ephemeral disk with no volume, so each redeploy starts again from the committed copy and loses
  what parents added; its own, built by code, no, step 3 commits the laptop's database file, so
  production starts as the laptop's copy. Plan B: survives, yes (step 1, the data is in
  Larchyard's managed Postgres, not on the server's disk); its own, built by code, yes (step 2
  creates the tables; step 3's seed script is in the repository, so its rows come from the code
  though it is run from the laptop, and step 4 keeps the laptop on its own file).
- **credit:** full for all four yes-or-no answers right, with Plan A's no on survival tied to step
  2 or step 3 (the file in the app's folder, or the redeploy starting from the committed copy), its
  no on its own database tied to step 3, the laptop's file committed, and no fault named in Plan B.
  Half for one plan judged fully right and the other not.
- **tutor note:** a learner may pass Plan A on survival because "the file is in git, so it is
  never lost": ask what the committed file holds after a redeploy, given the rides parents added
  since. The likely false fault is Plan B's step 3: a seed script kept in the repository builds
  production from the code wherever it is run from, and is not the laptop's data being copied.
  If the learner faults it, ask where the two sample rides are written down.

### q2

- **goal:** `c-plan-first-deploy`
- **answer:** Plan A: survives, yes (steps 1 and 2 put the file at `/data/ridealong.sqlite`, on
  the volume); its own, built by code, yes (step 3 creates the tables, and step 4's seed script
  is in the repository). Plan B: survives, no, step 2 leaves the SQLite file in the app's folder
  on the server's ephemeral disk, with no volume, so it is gone after each redeploy; its own,
  built by code, yes (step 3 creates the tables).
- **credit:** full for all four yes-or-no answers right, with Plan B's no on survival tied to step
  2, the file left in the app's folder on the server, and no fault named in Plan A. Half for one
  plan judged fully right and the other not.
- **tutor note:** a learner who passes Plan B because the app will start and make its tables has
  seen that it runs, not that the data lasts: ask what Larchyard does to the app's folder on a
  redeploy.
