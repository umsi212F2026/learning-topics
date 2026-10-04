Larkspan keeps only files under `/data` on an attached volume, and its managed Postgres runs as a
separate service; everything else on a server's disk is gone after a redeploy. Shapes and
questions:

- q1: `silent-location`, survival question (`c-catch-data-loss`, Medium).
- q2: `laptop-copy`, survival question (`c-clear-data-survives`, Medium). Faulted on the other
  question, sound on this one.
- q3: `committed-file`, own-database question (`c-catch-copied-database`, Hard).
- q4: `decoy`, `sound-postgres` with a seed script run once from the laptop against production,
  own-database question (`c-clear-own-database`, Hard).

No half credit on any question: a right verdict with no step, or tied to a step that doesn't
decide it, is not met. Naming a fault the key doesn't have on the asked question fails, as the
reason for a wrong verdict or alongside a right one. Remarks off the asked question (the other
question, connection strings, passwords, backups, cost) are neither credited nor counted.

### q1

- **goal:** `c-catch-data-loss`
- **answer:** No, or can't tell. The plan never says where the database lives: no volume, no path,
  no managed Postgres. Nothing shows the data anywhere Larkspan keeps it, and left as it is, the
  backend's SQLite file stays at `server/data/pantry.sqlite` on the ephemeral disk and is gone after
  a redeploy. What decides it is that omission.
- **credit:** full for no or "can't tell", with the omission named: the plan never says where the
  database lives, or, equally, no step attaches a volume or uses managed Postgres, so the file stays
  on the ephemeral disk. Not met for yes, for no or "can't tell" with no reason, or for no tied only
  to step 2's table creation or to step 1, 3 or 4 without the omission.
- **tutor note:** a learner who answers yes because step 2 creates the tables has confused the
  tables existing with the rows lasting. The first level of help is "where does the data live, and
  what does this host do to that place on a redeploy?"

### q2

- **goal:** `c-clear-data-survives`
- **answer:** Yes. Step 2 puts production's database at `/data/pantry.sqlite`, on the volume step 1
  attached, and Larkspan keeps files under `/data` across redeploys.
- **credit:** full for yes, tied to step 2 (the database at `/data/pantry.sqlite`), alone or
  together with step 1; or tied to step 3 when the answer says the uploaded file lands at
  `/data/pantry.sqlite` on the volume. Not met for no, for "can't tell", for yes with no step, for
  yes tied only to step 1 (attaching a volume does not by itself put the file on it), to step 3
  with nothing about where the file lands, or to step 4, or for yes alongside a survival fault.
- **tutor note:** step 3's upload of the laptop's file is the other question's fault. A remark about
  it is disregarded and belongs to the own-database question; a learner who answers no on survival
  because of it has mixed the two questions, and fails.

### q3

- **goal:** `c-catch-copied-database`
- **answer:** No. Step 1 commits the laptop's `pantry.sqlite` and ships it with the app, so
  production starts as a copy of the laptop's database, rows and all, rather than one the code
  builds.
- **credit:** full for no, tied to step 1 (the laptop's database file taken out of `.gitignore` and
  committed). Not met for yes, for no with no step, or for no tied only to step 2 or step 3.
- **tutor note:** the trap is step 2's "creates the tables if they are missing": they are not
  missing, because the committed file already holds them and the laptop's rows. If the learner says
  yes on that ground, ask what is in the file the backend opens on its first start. A remark that
  the file is on the ephemeral disk is about the other question; disregard it.

### q4

- **goal:** `c-clear-own-database`
- **answer:** Yes. Step 2: the backend creates the `shelf_items` and `reservations` tables itself in
  the new Postgres database. Step 4's seed script, kept in the repository and run once against
  production, also counts as built by the code, even though it is run from the laptop, so either
  step decides it. Nothing is copied from the laptop's file, and nothing is shared with
  development.
- **credit:** full for yes, tied to step 2 (the backend creating its tables), step 4 (the seed
  script from the repository), or both. Not met for no, for yes with no step, for yes tied only to
  step 1 or step 3, or for yes alongside a fault on this question, such as calling step 4 a copy
  from the laptop because it runs there, or calling the staple items test data.
- **tutor note:** the decoy is the seed script run from the laptop. A learner who faults it has
  taken "run from the laptop" for "copied from the laptop"; ask where the rows step 4 adds come
  from.
