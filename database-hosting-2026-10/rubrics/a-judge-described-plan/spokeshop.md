Tidewell keeps only files under `/data`, on an attached volume; everything else on a server's
disk, the app's folder included, is gone after each redeploy or restart. Its managed Postgres is
a separate service, so a database there is not on the server's disk and survives a redeploy. In
q1 the faulted plan is `committed-file` (Plan A), a fault of both kinds, and the sound one a
`decoy` (Plan B, `sound-volume` with no rows plus a note that the backend restarts after every
deploy and now and then): Hard. Remarks on connection strings, passwords, backups, migrating
data, cost or free tiers are neither credited nor counted as a false fault.

### q1

- **goal:** `c-plan-first-deploy`
- **answer:** Plan A: survives, no: steps 2 and 3 keep the file in the app's folder on the
  ephemeral disk with no volume, so each redeploy starts again from the committed copy and loses
  the tickets riders added since; its own, built by code, no: step 3 commits the laptop's
  database file, so production starts as the laptop's copy. Plan B: survives, yes (steps 1 and 2
  put the file at `/data/spokeshop.sqlite`, on the volume, which Tidewell keeps across restarts
  as well as redeploys); its own, built by code, yes (step 3 creates the tables).
- **credit:** full for all four yes-or-no answers right, with Plan A's no on survival tied to step
  2 or step 3 (the file in the app's folder, or each redeploy starting again from the committed
  copy), its no on its own database tied to step 3, the laptop's file committed, and no fault
  named in Plan B. Half for one plan judged fully right and the other not.
- **tutor note:** a learner may pass Plan A on survival because "the file is in git, so it is
  never lost": ask what the committed file holds after a redeploy, given the tickets riders added
  since it was committed. Plan B's step 4 is the decoy: a restart wipes only what is outside
  `/data`, and the file is under `/data`. A learner who faults it should be asked which files
  Tidewell keeps.
