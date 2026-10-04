Ridealong is a carpool board for a youth soccer league: parents post the rides they are driving
to Saturday games, and other parents ask for a seat. It has a React frontend and an Express
backend. The backend keeps its data in a SQLite file at `server/data/ridealong.sqlite`, with two
tables, `rides` and `seats`.

Ridealong will be deployed on Larchyard, a made-up host. On Larchyard, a server's disk is
ephemeral, so whatever is written to it is gone after every redeploy or restart. A volume mounted
at `/data` can be attached to a service, and only files under `/data` are kept. Larchyard also
runs managed Postgres as a separate service.

Two coding agents have each written a plan for deploying Ridealong's database for the first
time. For each plan, answer two questions with a yes or no, and for every no, name the plan step
that decides it:

- Will the data survive a redeploy?
- Does production get a database of its own, built by the code rather than copied from the
  laptop?

### q1

**Plan A**

1. Create a Larchyard web service for the Ridealong backend.
2. The backend opens its database at `server/data/ridealong.sqlite`, inside the app's folder, as
   it does on your laptop.
3. Remove `server/data/ridealong.sqlite` from `.gitignore` and commit the file, so the database
   ships with the app.
4. Deploy the backend and the frontend.

Your data will be safe.

**Plan B**

1. Create a managed Postgres database on Larchyard and connect the Ridealong backend to it.
2. On startup, the backend creates the `rides` and `seats` tables if they don't exist yet.
3. From your laptop, run `npm run seed` once against the Larchyard database. The seed script,
   kept in the repository at `server/seed.js`, adds two sample rides so parents can see how the
   board works.
4. Your laptop's development server keeps using its own `server/data/ridealong.sqlite`.
5. Deploy the backend and the frontend.

Your data will be safe.

### q2

**Plan A**

1. Attach a volume to the Ridealong backend service on Larchyard, mounted at `/data`.
2. Set `DB_PATH=/data/ridealong.sqlite` in the service's environment, so the backend opens its
   database file on the volume.
3. On startup, the backend runs `CREATE TABLE IF NOT EXISTS` for `rides` and `seats`.
4. Run the seed script kept in the repository at `server/seed.js` once on the server, to add two
   sample rides.
5. Deploy the backend and the frontend.

Your data will be safe.

**Plan B**

1. Create a Larchyard web service for the Ridealong backend.
2. Leave the database where the backend already looks for it: `server/data/ridealong.sqlite` in
   the app's folder on the server. No extra service is needed for a SQLite file.
3. On startup, the backend creates the `rides` and `seats` tables if they are missing.
4. Deploy the backend and the frontend.

Your data will be safe.
