Pantry Board lets a campus food pantry list what is on its shelves and lets students reserve items
to pick up. It has a React frontend and an Express backend. The backend keeps its data in a SQLite
file at `server/data/pantry.sqlite`, with two tables, `shelf_items` and `reservations`.

Pantry Board will be deployed to Larkspan, a made-up host. Larkspan's servers have ephemeral disks,
so anything written to them is gone after every redeploy or restart. A volume can be attached to a
service, mounted at `/data`, and only files under `/data` are kept. Larkspan also offers managed
Postgres as a separate service, which keeps its data across redeploys.

### q1

Pantry Board's coding agent proposes this plan:

> My plan for getting Pantry Board live on Larkspan:
>
> 1. Create a Larkspan web service for the Express backend, built from your repository.
> 2. Deploy the backend. When it starts, it creates the `shelf_items` and `reservations` tables if
>    they aren't there yet.
> 3. Deploy the React frontend as a second service and give it the backend's address.
> 4. Open the site and check that the shelf page loads.
>
> Your data will be safe.

Will this plan's data survive a redeploy? Say yes or no, and name the step in the plan that decides
it.

### q2

Pantry Board's coding agent proposes this plan:

> Here's how I'll set up Pantry Board's database on Larkspan:
>
> 1. Attach a Larkspan volume to the backend service, mounted at `/data`.
> 2. Change the backend's database location to `/data/pantry.sqlite` on that volume.
> 3. Upload `pantry.sqlite` from your laptop as production's database file, so production starts
>    with the entries you already have.
> 4. Deploy the backend, then the frontend.
>
> Nothing your users add will be lost.

Will this plan's data survive a redeploy? Say yes or no, and name the step in the plan that decides
it.

### q3

Pantry Board's coding agent proposes this plan:

> Deployment steps for Pantry Board's data:
>
> 1. Take `server/data/pantry.sqlite` out of `.gitignore` and commit the file, so the database ships
>    with the app.
> 2. Deploy the backend from the repository. It opens the database at `server/data/pantry.sqlite`
>    and creates the `shelf_items` and `reservations` tables if they are missing.
> 3. Deploy the frontend and connect it to the backend.
>
> Everything is in place, and your data comes along with the code.

Does production get a database of its own, built by the code rather than copied from the laptop or
shared with development? Say yes or no, and name the step in the plan that decides it.

### q4

Pantry Board's coding agent proposes this plan:

> Plan for Pantry Board's production database:
>
> 1. Set up a Larkspan managed Postgres database and have the production backend use it. On your
>    laptop, the backend keeps using `server/data/pantry.sqlite`.
> 2. Deploy the backend. On its first start it creates the `shelf_items` and `reservations` tables
>    in Postgres.
> 3. Deploy the frontend.
> 4. After that, from your laptop, run the seed script in the repository, `server/seed.js`, once
>    against the production Postgres database. It adds the three staples the pantry stocks every
>    week (rice, pasta and canned beans), so students can reserve them from opening day.
>
> Your data is in good hands.

Does production get a database of its own, built by the code rather than copied from the laptop or
shared with development? Say yes or no, and name the step in the plan that decides it.
