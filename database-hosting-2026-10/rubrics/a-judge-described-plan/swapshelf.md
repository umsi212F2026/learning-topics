Harborline keeps only files under `/data` on an attached volume, and its managed Postgres runs as
a separate service; everything else on a server's disk is gone after a redeploy. Shapes and
questions, all Medium, a first-attempt set with one question per case:

- q1: `no-volume`, survival question (case `catch-data-loss`).
- q2: `sound-postgres` with no rows, survival question (case `clear-survives`).
- q3: `shared-dev`, own-database question (case `catch-copied`).
- q4: `sound-volume` with a seed script run once on the server, own-database question
  (case `clear-own-database`).

No half credit on any question: a right verdict with no step, or tied to a step that doesn't
decide it, is not met. Naming a fault the key doesn't have on the asked question fails, as the
reason for a wrong verdict or alongside a right one. Remarks off the asked question (the other
question, connection strings, passwords, backups, cost) are neither credited nor counted.

### q1

- **goal:** `c-plan-first-deploy`
- **cases:** catch-data-loss
- **answer:** No. Step 2 keeps the SQLite file at `server/data/app.sqlite` in the app's folder on
  the server, which is on Harborline's ephemeral disk and outside `/data`, and no volume or managed
  Postgres is used, so the file is gone after every redeploy.
- **credit:** full for no, tied to step 2 (the file kept in the app's folder on the server, not
  under `/data`). Not met for yes, for no tied only to step 3 or step 4, or for no with no step.
- **tutor note:** a learner who answers yes because step 3 creates the tables has confused the
  tables existing with the rows lasting; the first level of help is "where does the data live, and
  what does this host do to that place on a redeploy?"

### q2

- **goal:** `c-plan-first-deploy`
- **cases:** clear-survives
- **answer:** Yes. Step 1 puts production's data in Harborline's managed Postgres, a separate
  service the host keeps, so redeploying the backend doesn't touch it.
- **credit:** full for yes, tied to step 1 (production's data in managed Postgres), or to step 2
  when the answer ties it to Postgres (step 2 sets up the tables in Postgres, which the host keeps).
  Not met for no, for "can't tell", for yes with no step, for yes tied to step 2 with nothing about
  Postgres, or tied only to step 3, or for yes alongside
  a survival fault (for example that the backend's disk is ephemeral so the data is lost, or that
  step 2 rebuilds the tables and wipes them on each redeploy).
- **tutor note:** the laptop still using `server/data/app.sqlite` is development, not production;
  a learner who faults the plan for it on survival has read the laptop's file as production's.

### q3

- **goal:** `c-plan-first-deploy`
- **cases:** catch-copied
- **answer:** No. Step 3 points the laptop's development server at production's Postgres instance,
  so development shares production's database instead of production having one of its own.
- **credit:** full for no, tied to step 3 (the development server working against production's
  database). Not met for yes, for no tied only to step 1 or step 2, or for no with no step.
- **tutor note:** a remark that step 2 builds the tables, so production's tables come from the code,
  is true and doesn't change the verdict; if the learner says yes on that ground, ask who else is
  reading and writing that database after step 3.

### q4

- **goal:** `c-plan-first-deploy`
- **cases:** clear-own-database
- **answer:** Yes. Step 3: the backend, on starting against the empty file on the volume, creates
  the `items` and `claims` tables itself. Step 4's seed script, kept in the repository and run once
  against production, also counts as built by the code, so either step decides it. Nothing comes
  from the laptop's file and nothing is shared with development.
- **credit:** full for yes, tied to step 3 (the backend creating its tables), step 4 (the seed
  script from the repository), or both. Not met for no, for yes with no step, for yes tied only to
  step 1 or step 2, or for yes alongside a fault on this question, such as calling the seed
  script's front-desk listings copied or test data.
- **tutor note:** a remark that the volume at `/data` keeps the data is about the other question;
  disregard it, and say it belongs to the survival question.
