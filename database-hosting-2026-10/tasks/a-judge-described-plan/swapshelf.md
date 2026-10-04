Swapshelf lets students in one residence hall list things they are giving away (a desk lamp, a
textbook, a mini fridge) and lets other students claim them. It has a React frontend and an Express
backend. The backend keeps its data in a SQLite file at `server/data/app.sqlite`, with two tables,
`items` and `claims`.

Swapshelf will be deployed to Harborline, a made-up host. Harborline's servers have ephemeral
disks, so anything written to them is gone after every redeploy or restart. A volume can be attached
to a service, mounted at `/data`, and only files under `/data` are kept. Harborline also offers
managed Postgres as a separate service, which keeps its data across redeploys.

### q1

Swapshelf's coding agent proposes this plan:

> Here's how I'll get Swapshelf's database running on Harborline:
>
> 1. Deploy the Express backend to a Harborline web service, built from your repository.
> 2. Keep the SQLite file where the backend already expects it, at `server/data/app.sqlite` in the
>    app's folder on the server. No extra service is needed.
> 3. When the backend starts, it creates the `items` and `claims` tables if they don't exist yet.
> 4. Deploy the React frontend and point it at the backend.
>
> Your data will be safe.

Will this plan's data survive a redeploy? Say yes or no, and name the step in the plan that decides
it.

### q2

Swapshelf's coding agent proposes this plan:

> Plan for putting Swapshelf's data on Harborline:
>
> 1. Create a managed Postgres database on Harborline and have the production backend use it in
>    place of the SQLite file. On your laptop, the backend keeps using `server/data/app.sqlite`.
> 2. Deploy the backend. On its first start it sets up the `items` and `claims` tables in Postgres.
> 3. Deploy the frontend.
>
> Everything your users add will be kept.

Will this plan's data survive a redeploy? Say yes or no, and name the step in the plan that decides
it.

### q3

Swapshelf's coding agent proposes this plan:

> Here's the deployment plan for Swapshelf's database:
>
> 1. Spin up a Harborline managed Postgres instance for Swapshelf.
> 2. Ship the backend, configured to talk to that Postgres instance. The first time it boots, it
>    builds the `items` and `claims` tables.
> 3. Switch your laptop's development server over to that same Postgres instance as well, so you
>    can test against real data.
> 4. Ship the frontend.
>
> You're all set, and your data is in good hands.

Does production get a database of its own, built by the code rather than copied from the laptop or
shared with development? Say yes or no, and name the step in the plan that decides it.

### q4

Swapshelf's coding agent proposes this plan:

> Steps for deploying Swapshelf's database:
>
> 1. Attach a Harborline volume to the backend service, mounted at `/data`.
> 2. Set the backend's database path to `/data/app.sqlite`, so the SQLite file lives on the volume.
> 3. Deploy the backend. On startup it creates the `items` and `claims` tables if they are missing.
> 4. Once the backend is running, run the seed script in your repository, `server/seed.js`, once on
>    the server. It adds the three things the hall's front desk is giving away this week (a
>    microwave, a floor lamp and a box of hangers), so the shelf opens with real listings.
>
> Your data will be safe.

Does production get a database of its own, built by the code rather than copied from the laptop or
shared with development? Say yes or no, and name the step in the plan that decides it.
