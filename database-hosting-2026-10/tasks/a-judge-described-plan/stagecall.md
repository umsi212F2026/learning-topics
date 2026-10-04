Stagecall is a rehearsal sign-up sheet for a student theater group: the director posts rehearsal
slots, and cast members sign up for the ones they can make. It has a React frontend and an
Express backend. The backend keeps its data in a SQLite file at `server/data/stagecall.sqlite`,
with two tables, `slots` and `signups`.

Stagecall will be deployed on Quarrybank, a made-up host. Quarrybank's servers have ephemeral
disks, so anything written to them is gone after every redeploy or restart. A volume can be
attached to a service, mounted at `/data`, and only files under `/data` are kept. Quarrybank also
offers managed Postgres as a separate service.

Two coding agents have each written a plan for deploying Stagecall's database for the first time.
The steps of each plan are in the order they run. For each plan, answer two questions with a yes
or no, and for every no, name the plan step that decides it:

- Will the data survive a redeploy?
- Does production get a database of its own, built by the code rather than copied from the
  laptop?

### q1

**Plan A**

1. Create a Quarrybank web service for the Stagecall backend, and a static site for the
   frontend.
2. Deploy the backend and the frontend.
3. On startup, the backend runs `CREATE TABLE IF NOT EXISTS` for `slots` and `signups`, so the
   tables are there the first time it runs. Production starts with no slots; the director posts
   them.

Your data will be safe.

**Plan B**

1. Attach a volume to the Stagecall backend service on Quarrybank, mounted at `/data`.
2. Set `DB_PATH=/data/stagecall.sqlite` in the service's environment, so the backend opens its
   database file there.
3. Deploy the backend and the frontend. On startup, the backend creates the `slots` and
   `signups` tables if they are missing.
4. Once the backend is running, open a shell on the Quarrybank service and run
   `node server/seed.js` once. That script, kept in the repository, inserts three sample
   rehearsal slots so the director can see how the page looks.

Your data will be safe.

### q2

**Plan A**

1. Create a managed Postgres database on Quarrybank and connect the Stagecall backend to it.
2. Deploy the backend and the frontend. On startup, the backend creates the `slots` and
   `signups` tables if they don't exist yet.
3. Once the backend is running, run `node server/seed.js` once from your laptop against the
   production database. That script, kept in the repository, inserts two sample rehearsal slots.
4. Your laptop's development server keeps using its own `server/data/stagecall.sqlite`.

Your data will be safe.

**Plan B**

1. Create a managed Postgres database on Quarrybank and connect the Stagecall backend to it.
2. Deploy the backend and the frontend. On startup, the backend creates the `slots` and
   `signups` tables if they don't exist yet.
3. Point your laptop's development server at that same Quarrybank database instead of
   `server/data/stagecall.sqlite`, so you can test against real data as you keep building.

Your data will be safe.
