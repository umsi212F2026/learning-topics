Backtrack is a lost-and-found board for one campus library: staff post items handed in at the
desk, and students claim the ones that are theirs. It has a React frontend and an Express
backend. The backend keeps its data in a SQLite file at `server/data/backtrack.sqlite`, with two
tables, `items` and `claims`.

Backtrack will be deployed on Pebblestack, a made-up host. Pebblestack's servers have ephemeral
disks: anything written to them is gone after every redeploy or restart. A volume can be attached
to a service, mounted at `/data`, and only files under `/data` are kept. Pebblestack also offers
managed Postgres as a separate service.

Two coding agents have each written a plan for deploying Backtrack's database for the first
time. The steps of each plan are in the order they run. For each plan, answer two questions with
a yes or no, and for every no, name the plan step that decides it:

- Will the data survive a redeploy?
- Does production get a database of its own, built by the code rather than copied from the
  laptop?

### q1

**Plan A**

1. Create a Pebblestack web service for the Backtrack backend.
2. SQLite needs no separate database server, so the backend keeps its file where it already is,
   at `server/data/backtrack.sqlite` inside the app's folder on the server.
3. Deploy the backend and the frontend. On startup, the backend runs `CREATE TABLE IF NOT EXISTS`
   for `items` and `claims`, so the tables are there the first time it runs.

Your data will be safe.

**Plan B**

1. Create a managed Postgres database on Pebblestack and connect the Backtrack backend to it.
2. Deploy the backend and the frontend. On startup, the backend creates the `items` and `claims`
   tables if they don't exist yet. Production starts with no items; staff add them as they come
   in.
3. Your laptop's development server keeps using its own `server/data/backtrack.sqlite`.

Your data will be safe.

### q2

**Plan A**

1. Attach a volume to the Backtrack backend service on Pebblestack, mounted at `/data`.
2. Set `DB_PATH=/data/backtrack.sqlite` in the service's environment, so the backend opens its
   database file there.
3. Deploy the backend and the frontend. On startup, the backend creates the `items` and `claims`
   tables if they are missing.
4. Because a volume is attached, Pebblestack stops the old server before starting the new one, so
   expect a few seconds of downtime on each redeploy.

Your data will be safe.

**Plan B**

1. Attach a volume to the Backtrack backend service on Pebblestack, mounted at `/data`.
2. Set `DB_PATH=/app/server/data/backtrack.sqlite` in the service's environment, so the backend
   opens the same file path it uses on your laptop.
3. Deploy the backend and the frontend. On startup, the backend creates the `items` and `claims`
   tables if they are missing.

Your data will be safe.
