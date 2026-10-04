Shelfswap is a board where students on one dorm floor list books they are willing to lend and
ask to borrow each other's. It has a React frontend and an Express backend. The backend keeps
its data in a SQLite file at `server/data/shelfswap.sqlite`, with two tables, `books` and
`requests`.

Shelfswap will be deployed on Driftwood, a made-up host. Driftwood's servers have ephemeral
disks, so anything written to them is gone after every redeploy or restart. A volume can be
attached to a service, mounted at `/data`, and only files under `/data` are kept. Driftwood
also offers managed Postgres as a separate service.

Two coding agents have each written a plan for deploying Shelfswap's database for the first
time. For each plan, answer two questions, each with a yes or no and the plan step that decides
it:

- Will the data survive a redeploy?
- Does production get a database of its own, built by the code rather than copied from the
  laptop?

### q1

**Plan A**

1. Attach a volume to the Shelfswap backend service on Driftwood, mounted at `/data`.
2. Set `DB_PATH=/data/shelfswap.sqlite` in the service's environment, so the backend opens its
   database file there.
3. On startup, the backend runs `CREATE TABLE IF NOT EXISTS` for `books` and `requests`, so the
   tables are created the first time it runs against the empty volume.
4. Deploy the backend and the frontend.

Your data will be safe.

**Plan B**

1. Attach a volume to the Shelfswap backend service on Driftwood, mounted at `/data`.
2. Set `DB_PATH=/data/shelfswap.sqlite` in the service's environment.
3. Upload your local `server/data/shelfswap.sqlite` to `/data/shelfswap.sqlite`, so production
   starts with the books and requests you already have.
4. Deploy the backend and the frontend.

Your data will be safe.

### q2

**Plan A**

1. Create a managed Postgres database on Driftwood and connect the Shelfswap backend to it.
2. On startup, the backend creates the `books` and `requests` tables if they don't exist yet.
3. Point your laptop's development server at this same Driftwood database as well, so you can
   test against real data while you keep building.
4. Deploy the backend and the frontend.

Your data will be safe.

**Plan B**

1. Create a managed Postgres database on Driftwood and connect the Shelfswap backend to it.
2. On startup, the backend creates the `books` and `requests` tables if they don't exist yet.
3. Run `npm run seed` once against the Driftwood database. The seed script, kept in the
   repository at `server/seed.js`, adds three sample books so the board isn't empty on day one.
4. Your laptop's development server keeps using its own `server/data/shelfswap.sqlite`.
5. Deploy the backend and the frontend.

Your data will be safe.
