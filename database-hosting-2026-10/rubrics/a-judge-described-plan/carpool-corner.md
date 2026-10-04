Mossgate keeps only files under `/data` on an attached volume, and its managed Postgres runs as a
separate service; everything else on a server's disk is gone after a redeploy. Shapes and
questions:

- q1: `outside-mount`, survival question (case `catch-data-loss`, Hard).
- q2: `decoy`, `sound-volume` with no rows and a few seconds of downtime on each redeploy, survival
  question (case `clear-survives`, Hard).
- q3: `laptop-copy`, own-database question (case `catch-copied`, Medium).
- q4: `silent-location`, own-database question (case `clear-own-database`, Medium). Faulted on the
  other question, sound on this one.

No half credit on any question: a right verdict with no step, or tied to a step that doesn't
decide it, is not met. Naming a fault the key doesn't have on the asked question fails, as the
reason for a wrong verdict or alongside a right one. Remarks off the asked question (the other
question, connection strings, passwords, backups, cost) are neither credited nor counted.

### q1

- **goal:** `c-plan-first-deploy`
- **cases:** catch-data-loss
- **answer:** No. Step 2 sets the database file to `/app/server/data/rides.sqlite`, inside the
  app's folder and outside `/data`, so the file sits on Mossgate's ephemeral disk and is gone after
  every redeploy, even though step 1 attached a volume.
- **credit:** full for no, tied to step 2 (the `DATABASE_FILE` setting, a path outside `/data`).
  Not met for yes, for no with no step, or for no tied only to step 1, step 3 or step 4.
- **tutor note:** the trap is step 1 and the closing line: a volume is attached, so the plan looks
  safe. If the learner says yes, ask where the database file actually is, and which folder Mossgate
  keeps.

### q2

- **goal:** `c-plan-first-deploy`
- **cases:** clear-survives
- **answer:** Yes. Step 2 puts the SQLite database at `/data/rides.sqlite`, on the volume step 1
  attached, and Mossgate keeps files under `/data` across redeploys.
- **credit:** full for yes, tied to step 2 (the database at `/data/rides.sqlite`), alone or
  together with step 1. Not met for no, for "can't tell", for yes with no step, for yes tied only to
  step 1 (attaching a volume does not by itself put the file on it), step 3 or step 4, or for yes
  alongside a survival fault, such as reading the few seconds of downtime as data being lost.
- **tutor note:** the decoy is step 1's downtime: the site is briefly unavailable, but nothing on
  the volume is lost. If the learner faults it, ask what is on the volume when the new server picks
  it up.

### q3

- **goal:** `c-plan-first-deploy`
- **cases:** catch-copied
- **answer:** No. Step 2 copies the laptop's `rides.sqlite` up as production's database, so
  production starts as a copy of the laptop's file, its tables and its rows, and no step has the code
  build it.
- **credit:** full for no, tied to step 2 (the copy of the laptop's file to `/data/rides.sqlite`).
  Not met for yes, for no with no step, or for no tied only to step 1, step 3 or step 4.
- **tutor note:** a remark that the volume keeps the data is true and about the other question;
  disregard it, and say it belongs to the survival question.

### q4

- **goal:** `c-plan-first-deploy`
- **cases:** clear-own-database
- **answer:** Yes. Step 2: on its first start the backend creates the `rides` and `seat_requests`
  tables, empty, so production's database is built by the code. Nothing comes from the laptop and
  nothing is shared with development.
- **credit:** full for yes, tied to step 2 (the backend creating its tables). Not met for no, for
  "can't tell", for yes with no step, for yes tied only to step 1 or step 3, or for yes alongside a
  fault on this question.
- **tutor note:** the plan never says where the database lives, which is a survival fault and off
  this question. A learner who answers no or "can't tell" on that ground has answered the other
  question and fails; a learner who answers yes and also remarks on the missing location has that
  remark disregarded, and is told it belongs to the survival question.
