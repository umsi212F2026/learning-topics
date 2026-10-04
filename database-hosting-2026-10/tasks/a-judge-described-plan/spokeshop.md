Spokeshop is the repair queue for a campus bike co-op: riders add their bike to the queue with a
note on what is wrong, and volunteer mechanics mark each one fixed. It has a React frontend and
an Express backend. The backend keeps its data in a SQLite file at
`server/data/spokeshop.sqlite`, with two tables, `tickets` and `mechanics`.

Spokeshop will be deployed on Tidewell, a made-up host. Tidewell's servers have ephemeral disks:
anything written to them is gone after every redeploy or restart. A volume can be attached to a
service, mounted at `/data`, and only files under `/data` are kept. Tidewell also offers managed
Postgres as a separate service.

Two coding agents have each written a plan for deploying Spokeshop's database for the first time.
The steps of each plan are in the order they run. For each plan, answer two questions with a yes
or no, and for every no, name the plan step that decides it:

- Will the data survive a redeploy?
- Does production get a database of its own, built by the code rather than copied from the
  laptop?

### q1

**Plan A**

1. Create a Tidewell web service for the Spokeshop backend.
2. The backend keeps its SQLite file where it is now, at `server/data/spokeshop.sqlite` inside
   the app's folder.
3. Take `server/data/spokeshop.sqlite` out of `.gitignore` and commit it, so the database ships
   with the app and is ready the moment the backend starts.
4. Deploy the backend and the frontend.

Your data will be safe.

**Plan B**

1. Attach a volume to the Spokeshop backend service on Tidewell, mounted at `/data`.
2. Set `DB_PATH=/data/spokeshop.sqlite` in the service's environment, so the backend opens its
   database file there.
3. Deploy the backend and the frontend. On startup, the backend runs `CREATE TABLE IF NOT EXISTS`
   for `tickets` and `mechanics`. Production starts with an empty queue.
4. Note that Tidewell restarts the backend after every deploy, and may restart it again on its
   own now and then. That is expected, and needs nothing from you.

Your data will be safe.
